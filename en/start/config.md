### Publish
- Publish config
```
php artisan vendor:publish --tag=cms_config
```

- Publish views
```
php artisan vendor:publish --tag=cms_views
```

- Publish translation
```
php artisan vendor:publish --tag=cms_lang
```

- Publish assets
```
php artisan vendor:publish --tag=cms_assets
```

### Config

- Publish config file
```
php artisan vendor:publish --tag=cms_config
```

```php
<?php

return [
    /**
     * Admin url prefix
     *
     * Default: admin-cp
     */
    'admin_prefix' => env('ADMIN_PREFIX', 'admin-cp'),

    'email' => [
        /**
         * Method send email
         *
         * Support: sync, queue, cron
         * Default: sync
         */
        'method' => env('EMAIL_METHOD', 'sync'),

        'default' => [
            'driver' => env('MAIL_MAILER'),
            'host' => env('MAIL_HOST'),
            'port' => env('MAIL_HOST'),
            'from_address' => env('MAIL_FROM_ADDRESS'),
            'from_name' => env('MAIL_FROM_NAME'),
            'encryption' => env('MAIL_ENCRYPTION'),
            'username' => env('MAIL_USERNAME'),
            'password' => env('MAIL_PASSWORD'),
        ],
    ],

    'theme' => [
        /**
         * Enable upload themes
         *
         * Default: true
         */
        'enable_upload' => true,

        /**
         * Themes path
         *
         * This path used for save the generated theme. This path also will added
        automatically to list of scanned folders.
         */
        'path' => base_path('themes'),
    ],

    'plugin' => [
        /**
         * Enable upload plugins
         *
         * Default: true
         */
        'enable_upload' => true,

        /**
         * Path plugins folder
         *
         * Default: plugins
         */
        'path' => base_path('plugins'),

        /**
         * Plugins assets path
         *
         * Path for assets when it was published
         * Default: plugins
         */
        'assets' => public_path('plugins'),
    ],

    'performance' => [
        /**
         * Minify views when compile
         *
         * Default: true
         */
        'minify_views' => true,

        /**
         * Deny iframe to website
         *
         * Default: true
         */
        'deny_iframe' => true,

    ],
    
    /**
     * File management setting
     */
    'filemanager' => [
        'disk' => 'public',
        'image-optimizer' => (bool) env('IMAGE_OPTIMIZER', false),
        'types' => [
            'file'  => [
                'max_size' => 50, // size in MB
                'valid_mime' => [
                    'image/jpeg',
                    'image/pjpeg',
                    'image/png',
                    'image/gif',
                    'image/svg+xml',
                    'application/pdf',
                    'text/plain',
                    'text/xml',
                ],
            ],
            'image' => [
                'max_size' => 5, // size in MB
                'valid_mime' => [
                    'image/jpeg',
                    'image/pjpeg',
                    'image/png',
                    'image/gif',
                    'image/svg+xml',
                ],
            ],
        ],
    ],

    /**
     * Default database config
     */
    'config' => [
        'title',
        'description',
        'banner',
        'logo',
        'icon',
        'banner',
        'sitename',
        'user_registration',
        'user_verification',
        'comment_able',
        'comment_type',
        'comments_per_page',
        'comments_approval',
        'author_name',
        'facebook',
        'twitter',
        'pinterest',
        'youtube',
        'google_analytics',
        'language',
        'timezone',
        'date_format',
        'time_format',
        'fb_app_id',
    ]
];
```
