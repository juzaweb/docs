

- [Create plugin](#create-plugin)
- [Custom namespaces](#custom-namespaces)
- [Hook actions](#hook-actions)
- [Resource](#resource)
    - [Resource model](#resource-model)
    - [Resource controller](#resource-controller)
    - [Resource route](#resource-route)
- [Post type](#post-type)
- [Breadcrumb](#breadcrumb)
- [Menu](#menu)
    - [Add admin menu](#add-admin-menu)
- [Assets](#assets)
    - [Libs added](#libs-added)
- [Commands](#commands)

## Breadcrumb
Add Breadcrumb admin panel, you can extend `Mymo\Backend\Http\Controllers\BackendController` for your controller in admin and add by code:
```php
<?php
$this->addBreadcrumb([
    'title' => 'Title',
    'url' => 'Url',
]);
```
E.x:
```php
<?php

// Your code

use Juzaweb\CMS\Http\Controllers\BackendController;

class YourController extends BackendController
{
    // Your code

    public function index()
    {
        // Your code
        $this->addBreadcrumb([
            'title' => 'Title',
            'url' => 'your-url',
        ]);
        // Your code
    }

    // Your code
}
```

### Register HookAction

#### Register Admin Page

```php
HookAction::registerAdminPage(string $key, array $args);
```

- `@param string $key`: Key as page
- `@param array $args`
  - title (string): Title/Label menu
  - menu (array):
    - icon: default(fa fa-list)
    - position: default(30)

```php
HookAction::registerPermalink($key, $args);
```

- `@param string $key`: Post Type key (Ex: pages, posts)
- `@param array $args`

