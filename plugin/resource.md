## Resource
- Resource in Juza CMS is created to easily create create, update, or delete actions
- It includes components
    - Controller: Include actions
        - index + datatable
        - create
        - edit
        - store
        - update
        - bulk action
    - Model
    - Route
    
### Resource model
- Make migration
```
php artisan plugin:make-migration create_examples_table author/plugin-name
```
- Make your model by command
```
php artisan plugin:make-model Slider author/plugin-name
```
- Use trait `ResourceModel` for your model
```php
<?php

namespace Plugins\Example\Models\Movie;

use Illuminate\Database\Eloquent\Model;
use Juzaweb\Traits\ResourceModel;

class Slider extends Model
{
    use ResourceModel;

    protected $fieldName = 'name';// Define column to show in breadcrumb
    protected $fillable = [
        'name',
    ];

    // Define column for seach by keyword
    protected $searchAttributes = [
        'name',
    ];
    // Your code
}
```

### Resource controller
- Make controller
```
php artisan plugin:make-controller SliderController author/plugin-name
```
- Use trait `ResourceController` for your model
```php
<?php

namespace Plugins\Example\Http\Controllers;

use Juzaweb\Http\Controllers\BackendController;
use Plugins\Example\Models\Slider;

class SliderController extends BackendController
{
    use ResourceController;

    protected $viewPrefix = 'example::slider'; // View prefix for resource

    // Make validator for store and update
    protected function validator(array $attributes, ...$params)
    {
        $validator = Validator::make($attributes, [
            'name' => 'required|string|max:250',
        ]);

        return $validator;
    }

    protected function getModel()
    {
        return Slider::class;
    }

    protected function getTitle()
    {
        return trans('example::app.sliders');
    }
}
```
### Resource route
- Add route for resource
```php
<?php

Route::jwResource('sliders', 'SliderController');
```