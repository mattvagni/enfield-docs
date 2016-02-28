This page describes how you

## Page Data
This is an example bit of template of how you include your page's data in your template:
```jinja
<h1>{{ page.title }}</h1>
{% if page.headings %}
    <p>Table of Contents:</p>
    <ul>
        {% for heading in page.headings %}
            <li class="level-{{ anchor.level }}">
                <a href="{{ heading.anchor|url }}">
                    {{ heading.heading }}
                </a>
            </li>
        {% endfor %}
    </ul>
{% endif %}

{# Notice the use of the safe filter below. It ensures
our page content (which is html) is not escaped #}
{{ page.content|safe }}
```
The raw data the current page is:
```js
{ "page": {
    "title": "Template Variables",
    "section": "Themes",
    "url": "/the-page-url/",
    "content": "<p>Your page's html</p>",

    // The headings/titles within the page (h1 & h2s only)
    "headings": [
        {
            "level": 2,
            "anchor": "/themes/template-variables/#menusections-object",
            "heading": "menuSections Object"
        }
    ]
}}
```

## Pagination Data
This is an example of template of how you could implement pagination for each page to the next & previous
```jinja
<div>
    {% if pagination.previousPage %}
        <div class="pagination prev">
            <a href={{ pagination.previousPage.url|url }}>
                Prev: {{pagination.previousPage.title}}
            </a>
        </div>
    {% endif %}
    {% if pagination.nextPage %}
        <div class="pagination next">
            <a href={{ pagination.nextPage.url|url }}>
                Next: {{pagination.nextPage.title}}
            </a>
        </div>
    {% endif %}
</div>
```
The raw data for the pagination data is:
```js
{ "pagination": {
    // Both the previous and next page can be empty if there is no
    // previous or next page.
    "previousPage": {
        // The previous page's title
        "title": "Command Line Options",
        // The previous page's url
        "url": "/setup-usage/command-line-options/"
    },
    "nextPage": {
        // The next page's title
        "title": "Template Variables",
        // The next page's url
        "url": "/themes/template-variables/"
    }
}}
```

## Menu Data
This is an example bit of templating of how you could implement a template. All css classes are obviously omited for readability.
```jinja
{% for menuSection in menuSections %}

    {% if menuSection.title %}
        <li>
            {{ menuSection.title }}
        </li>
    {% endif %}

    {% for page in menuSection.pages %}
        <li>
            <a  href="{{ page.url|url }}"
                class="{% if menuItem.isActive %}active{% endif %}">
                {{ page.title }}
            </a>

            {% if page.headings %}
                <ul>
                    {% for heading in page.headings %}
                        <li>
                            <a href="{{ heading.anchor|url }}">
                                {{ heading.heading }}
                            </a>
                        </li>
                    {% endfor %}
                </ul>
            {% endif %}
        </li>
    {% endfor %}

{% endfor %}
```

The raw data given to templates for the menu is:
```js
{ "menuSection": [{
    // This is the title of this section,
    // this can be an empty string if a page is not in a section.
    "title": "Section Title",

        // The list of pages in this menu section
        "pages": [{
            // Whether this is the page the user is on:
            "isActive": true,
            // The section this page is in:
            "section": "Section Title",
            // The page title:
            "title": "The Page Title",
            // The url of this page:
            "url": "/",
            // The headings/titles within the page:
            // (This can be empty if the page has no titles)
            "headings": [
                {

                    "level": 1,
                    "anchor": "/#an-in-page-title",
                    "heading": "An In Page Title"
                },
                {
                    "level": 2,
                    "anchor": "/#another-title",
                    "heading": "Another Title"
                },
                // ... any other headings on this page.
            ]
        },
        // Another page in this section:
        {
            "isActive": false,
            "section": "Section Title",
            "title": "Some Other Page",
            "url": "/some-other-page/",
            "headings": []
        },
        // ... any other pages in this section.
    ]
},
// ... any other sections in the menu
```

## Custom Variables
Any custom data included in the config file will also be exposed to the theme template.

For example, if in the config the use defined `twitter_link` then it can be used in the template like so:
```jinja
<a href="{{ site.twitter_link }}">Follow Me Twitter</a>
```
