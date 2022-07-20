## Post type
There are many different types of content in Juza CMS. These content types are normally described as Post Types, which may be a little confusing since it refers to all different types of content in Juza CMS. For example, a post is a specific Post Type, and so is a page.

### Default Post Types
- Post (Post Type: ``posts``)
- Page (Post Type: ``pages``)

### Register post type
Add to your file action
```php
<?php

namespace Author\PluginName;

use Juzaweb\Backend\Facades\HookAction;
use Juzaweb\CMS\Abstracts\Action;

class YourAction extends Action
{
    public function handle()
    {
        $this->addAction(Action::INIT_ACTION, [$this, 'registerPostType']);
    }

    public function registerPostType()
    {
        HookAction::registerPostType(
            'movies',
             [
                'label' => trans('movie::app.movies'),
                'menu_icon' => 'fa fa-film',
                'menu_position' => 10,
                'supports' => ['tag'], // Support options: tag, category
            ]
        );
        
        // Register Taxonomy for Post Type
        HookAction::registerTaxonomy(
            'genres',
            'movies',
            [
                'label' => trans('movie::app.genres'),
                'menu_icon' => 'fa fa-edit',
                'menu_position' => 6,
                'supports' => [
                    'thumbnail'
                ],
            ]
        );
        
        // Or register Taxonomy with multi post type
        HookAction::registerTaxonomy(
            'genres',
             ['movies', 'tv-series'],
             [
                'label' => trans('movie::app.genres'),
                'menu_icon' => 'fa fa-edit',
                'menu_position' => 6,
                'supports' => [
                    'thumbnail'
                ],
            ]
        );
    }
}
```
