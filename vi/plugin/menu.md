## Menu

### Add admin menu
Add to your file actions
```php
<?php
HookAction::addAdminMenu(
    trans('movie::app.sliders'), // Label menu
    'sliders', // Menu key
    [
        'icon' => 'fa fa-paint-brush', // Icon
        'position' => 10, // Position item
        'parent' => 'appearance', // parent (default: null)
    ]);
```


