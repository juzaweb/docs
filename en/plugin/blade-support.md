### Component Support
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

- Card component
```php
@component('cms::components.card', [
    'label' => trans('cms::app.status')
])
    // Your code
@endcomponent
```

### Field Support
- Input text field
```php
Field::text($label, $name, $options = [])
```

  - `@param string $label` Input label
  - `@param string $name` Input name
  - `@param array $options`
    - id : Input id
    - value: Input value
    - class: Add custom class
    - default: Default value for input
    - disabled: Disabled input
    - required: Require input
    - readonly: Readonly input
    - data: Array data input `data-`, format ['key' => 'value'] (`data-key="value"`)

- Input textarea field
```php
Field::textarea($label, $name, $options = [])
```

- `@param string $label` Input label
- `@param string $name` Input name
- `@param array $options`
  - id : Input id
  - value: Input value
  - class: Add custom class
  - default: Default value for input
  - disabled: Disabled input
  - required: Require input
  - readonly: Readonly input
  - data: Array data input `data-`, format ['key' => 'value'] (`data-key="value"`)

- Input select field
```php
Field::select($label, $name, $options = [])
```

- Input checkbox field
```php
Field::checkbox($label, $name, $options = [])
```

- Input editor field
```php
Field::editor($label, $name, $options = [])
```

- Input image field
```php
Field::image($label, $name, $options = [])
```

- Input images field
```php
Field::images($label, $name, $options = [])
```

### Form ajax
- Add class `form-ajax` to your form to use ajax send form
```html
<form action="" method="post" class="form-ajax">
// Your code
</form>
```
