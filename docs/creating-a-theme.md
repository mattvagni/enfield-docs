You can customize how your docs looks by creating a theme.

A theme is essentially just a folder with a template that defines the structure of your docs and any css or javascript you'd like.

You specify where the theme you'd like to use in your config.

## Defining a template
Your theme must define a file called `template.html` this is the template that is used to render your site. Every page is rendered using the same template.

Templates are rendered using Mozilla's [Nunjucks](https://mozilla.github.io/nunjucks/templating.html) as a template language. This is nearly identical to what Jekyll uses with some slight differences in terms of what filters are available etc.

If you want to see an example template check out the [sample theme](https://github.com/mattvagni/enfield-docs/tree/master/theme)

To see what data you have available in your template check out the available [template variables](/themes/template-variables/).

## Static files
Any files besides the template in your theme are copied over in the same folder structure to the root of your built site.

So if your theme folder looks like so:
```bash
theme/
    - template.html
    - css/
        - styles.css
    - js/
        - scripts.js
```
When you build your site it will copy over the `css` and `js` directory.

## Urls in your theme
In your theme if you want to refer to a static file or a page url you have to use the `url` filter.

For example, given the above theme structure, in your theme you will have to do this if you want to include a the javascript file:
```jinja
<script type="text/javascript" src="{{ '/js/scripts.js'|url }}"></script>
```
This will ensure that if you specified a `base_url` in your config it is respected.

Don't do this on external urls as it will break them, only to internal links within your site.
