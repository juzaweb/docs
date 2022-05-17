### Config
- Config method send email. Supported sync, queue, cron
- Open file config ``juzaweb.php``
```php
<?php

return [
    // Your config
    
    'email' => [
        /**
         * Method send email
         *
         * Support: sync, queue, cron
         * Default: sync
         */
        'method' => 'sync'
    ]
];
```

### Setup mail in cron
- If you use crontab to send email, you need to set up ``The Scheduler`` on your server, hosting
- Setup ``The Scheduler``: Add command to your server
```
* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1
```
View more: [Starting The Scheduler](https://laravel.com/docs/6.x/scheduling#introduction)

### Make Email Template and Send email
- Before sending an email, you need to create an email template. You can manage email templates at ``/admin-cp/email-template``
```php
<?php
use Juzaweb\Backend\Models\EmailTemplate;

EmailTemplate::create([
    'code' => 'test_mail',
    'subject' => 'Send email test for {name}',
    'body' => '<p>Hello {name},</p>
               <p>This is the test email</p>',
    'params' => [
        'name' => 'Your Name',
    ],
]);
```

- Send email with template
```php
<?php

use Juzaweb\Support\Email;

Email::make()
    ->withTemplate('test_mail')
    ->setEmails('test@example.com')
    ->setParams([
        'name' => 'Juzaweb',
    ])
    ->send();
```

### Email Hook
- Email Hooks like Laravel's events provide a simple observer pattern implementation that allows you to subscribe and users can set up listening for various events that occur in your application. It will listen and send all email templates with the action hook selected

- Register Email Hook: Add to your file Action
```php
<?php

namespace Vendor\Name\Actions;

use Juzaweb\Abstracts\Action;
use Juzaweb\Backend\Facades\HookAction;

class YourAction extends Action
{
    public function handle()
    {
        // Your code
        $this->addAction(Action::INIT_ACTION, [$this, 'registerEmailHooks']);
    }

    public function registerEmailHooks()
    {
        HookAction::registerEmailHook(
            'register_success',
             [
                'label' => trans('domain::content.email_hook_label'),
                'params' => [
                    'param' => trans('domain::content.param_label'),       
                ],
            ]
        );
    }
}    
```

- In controller add event
```php
<?php

use Juzaweb\Events\EmailHook;
use Illuminate\Http\Request;

class YouController
{
    public function register(Request $request)
    {
        // Your code
        
        $name = $request->input('name');
        $email = $request->input('email');
        
        event(new EmailHook('register_success', [
            'to' => [$email],
            'params' => [
                'param' => [
                    'name' => $name,
                    'email' => $email
                ],
            ],
        ]));
    }
}
```

- In email template manage, you can choose ``Email Hook`` for email templates. When the ``register_success`` event occurs, this email template will be sent.
![Chosse hook in email template](https://i.imgur.com/4J38pgW.png)
