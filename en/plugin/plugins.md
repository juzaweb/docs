

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

## Assets
### Libs added
- Jquery
- Bootstrap
- select2
- bootstrap-datepicker
- font-awesome
- sweetalert2
- toastr

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

