### Custom Page Templates

The files defining each page template are found in your Themes directory. To create a new custom page template for a page you must create a file in ``templates`` directory. Let's call our first page template for our page snarfer.twig. At the top of the snarfer.twig file, put the following:

```twig
{% extends 'layouts.frontend' %}

{% block content %}
    {# Your template content #}
{% endblock %}
```

* ``layouts.frontend`` is the default layout with added styles. You can replace it with an existing template in your theme.

* block ``content`` is block default shows content in layout.

