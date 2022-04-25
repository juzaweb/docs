### Twig is a modern template engine
- Fast: Twig compiles templates down to plain optimized PHP code. The overhead compared to regular PHP code was reduced to the very minimum.
- Secure: Twig has a sandbox mode to evaluate untrusted template code. This allows Twig to be used as a template language for applications where users may modify the template design.
- Flexible: Twig is powered by a flexible lexer and parser. This allows the developer to define its own custom tags and filters, and create its own DSL.

### Using

#### Twig for Template Designers
##### Synopsis
- A template is a regular text file. It can generate any text-based format (HTML, XML, CSV, LaTeX, etc.). It doesn't have a specific extension, .html or .xml are just fine.

- A template contains variables or expressions, which get replaced with values when the template is evaluated, and tags, which control the template's logic.

- Below is a minimal template that illustrates a few basics. We will cover further details later on:

```twig
<ul id="navigation">
    {% for item in navigation %}
        <li><a href="{{ item.href }}">{{ item.caption }}</a></li>
    {% endfor %}
</ul>

<h1>My Webpage</h1>
{{ a_variable }}
```

There are two kinds of delimiters: {% ... %} and {{ ... }}. The first one is used to execute statements such as for-loops, the latter outputs the result of an expression.

##### Variables
The application passes variables to the templates for manipulation in the template. Variables may have attributes or elements you can access, too. The visual representation of a variable depends heavily on the application providing it.

Use a dot (.) to access attributes of a variable

``{{ foo.bar }}``

**Note:** It's important to know that the curly braces are not part of the variable but the print statement. When accessing variables inside tags, don't put the braces around them.

##### Setting Variables
You can assign values to variables inside code blocks. Assignments use the ``set`` tag:
```twig
{% set foo = 'foo' %}
{% set foo = [1, 2] %}
{% set foo = {'foo': 'bar'} %}
```

##### Filters
Variables can be modified by filters. Filters are separated from the variable by a pipe symbol (|). Multiple filters can be chained. The output of one filter is applied to the next.

The following example removes all HTML tags from the name and ``title-cases`` it:

``{{ name|striptags|title }}``

Filters that accept arguments have parentheses around the arguments. This example joins the elements of a list by commas:

``{{ list|join(', ') }}``

To apply a filter on a section of code, wrap it with the apply tag:

```twig
{% apply upper %}
    This text becomes uppercase
{% endapply %}
```
Go to the filter's page to learn more about built-in filters.

##### Functions
Functions can be called to generate content. Functions are called by their name followed by parentheses (()) and may have arguments.

For instance, the range function returns a list containing an arithmetic progression of integers:
```twig
{% for i in range(0, 3) %}
    {{ i }},
{% endfor %}
```
Go to the function's page to learn more about the built-in functions.

See all documention [https://twig.symfony.com/doc/3.x/](https://twig.symfony.com/doc/3.x/)
