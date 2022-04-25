### Create plugin
Creating a plugin is simple and straightforward. Run the following command to create a plugin.
```
php artisan plugin:make author/plugin-name
```
E.x:
```
php artisan plugin:make theanh/ecommerce
```
- Plugin folder truck
```
plugins/
|-- author/plugin-name/
    |-- src/
        |-- database/
          |-- factories/
          |-- migrations/
          |-- seeders/
        |-- Http/
          |-- Controllers/
          |-- Middleware/
          |-- Requests/
          |-- Datatables/
        |-- Models/
        |-- Providers/
          |-- PluginNameServiceProvider.php
        |-- resources/
          |-- assets/
              |-- js/
                |-- app.js
              |-- sass/
                |-- app.scss
          |-- lang/
          |-- views/
        |-- routes/
          |-- api.php
          |-- admin.php
    |-- tests/
    |-- composer.json
    |-- package.json
    |-- webpack.mix.js
```
Open the composer.json file, you will see a file of the form
```json
{
    "name": "author/name",
    "description": "Description plugin.",
    "extra": {
        "laravel": {
            "providers": [
                "Author\\Name\\Providers\\PluginNameServiceProvider"
            ]
        },
        "juzaweb": {
            "name": "Name plugin",
            "domain": "domain",
            "version": "1.0"
        }
    },
    "autoload": {
        "psr-4": {
            "Author\\Name\\": "src/"
        },
        "classmap": [
            "database/seeders"
        ]
    }
}
```

## Custom namespaces
When you create a new module it also registers new custom namespace for `Lang, View and Config`. For example, if you create a new module named blog, it will also register new namespace/hint blog for that module. Then, you can use that namespace for calling `Lang, View or Config`. Following are some examples of its usage:
Calling Lang:
```
Lang::get('domain::group.name');

@trans('domain::group.name');
```
Calling View:
```
view('domain::index')

view('domain::partials.sidebar')
```