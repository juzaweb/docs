## Custom Page Templates

### Register page templates
Add or edit your `register.json` file
```json
{
    // Your code
    "templates": {
        "home": {
            "label": "Home",
            "view": "theme::templates.home", // View template
            "blocks": { // Define blocks for template
                "content": {
                    "label": "Content"
                }
            }
        },
        "support": {
            "label": "Support",
            "view": "theme::templates.support" // View template
        }
    },
    // Your code
}
```

The files defining each page template are found in your Themes directory. To create a new custom page template for a page you must create a file in `templates` directory. Let's call our first page template for our page home.twig. At the top of the `home.twig` file, put the following:

```twig
{% extends 'cms::layouts.frontend' %}

{% block content %}
    {# Your template content #}
{% endblock %}
```

* ``cms::layouts.frontend`` is the default layout with added styles. You can replace it with an existing template in your theme.

* block ``content`` is block default shows content in layout.

