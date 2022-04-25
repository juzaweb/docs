Plugin is a Laravel package which was created to manage your large Laravel app using modules. A plugin is like a Laravel package, it has some views, controllers or models. This package is supported and tested in Laravel 9.

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
Add Breadcrumb admin panel, you can extends `Mymo\Backend\Http\Controllers\BackendController` for your controller in admin and add by code:
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

## Assets
### Libs added
- Jquery
- Bootstrap
- select2
- bootstrap-datepicker
- font-awesome
- sweetalert2
- toastr
### Support
#### Form ajax
- Add class `form-ajax` to your form to use ajax send form
```html
<form action="" method="post" class="form-ajax">
// Your code
</form>
```
- Resource form component
```php
@component('cms::components.form', [
    'method' => 'method: post, put, get, ...',
    'action' => 'action url'
])
```

- Use component for form resource
```php
@component('cms::components.form_resource', [
    'method' => $model->id ? 'put' : 'post',
    'action' =>  $model->id ?
        route('admin.posts.update', [$model->id]) :
        route('admin.posts.store')
])
```
#### Select image from file manager
- by component
```php
@component('cms::components.form_image', [
    'label' => trans('cms::app.thumbnail'), // Label
    'name' => 'thumbnail', // Name for input
    'value' => $model->thumbnail, // Value to show image
])@endcomponent
```

- by element: Add class `file-manager` to element select file:
    - data-input: id input get path file
    - data-preview: id div show preview image

E.x:
```html
<div class="form-group">
    <label class="col-form-label" for="logo">Logo <span class="float-right"><a href="javascript:void(0)" data-input="logo" data-preview="preview-logo" class="file-manager"><i class="fa fa-edit"></i> Change image</a></span></label>
    <div id="preview-logo">
        <img src="{{ asset('jw-styles/images/thumb-default.png') }}" alt="" class="w-25">
    </div>
    <input id="logo" class="form-control" type="hidden" name="logo" value="">
</div>
```

