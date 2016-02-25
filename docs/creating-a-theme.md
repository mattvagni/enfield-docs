You can customize how your docs looks by creating a theme.

A theme is essentially just a folder with a template that defines the structure of your docs and any css or javascript you'd like.

You specify where the theme you'd like to use in your config.

## Defining a template
Your theme must define a file called `template.html` this is the template that is used to render your site.

Templates are rendered using [Swig] as a template language. This is nearly identical to what Jekyll uses.

Every page is rendered using the same tempalte.

Checking the [sample]
