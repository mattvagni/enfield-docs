For enfield to work you need to have `.yml` config file. It can be anywhere but by default enfield will look for a file called `config.yml` in your root.

These are the basic config options.

```YAML
# This is the title of your site.
# This is most commonly used as the <title> of your site and for logging.
title: 'Enfield Docs'

# This is the folder to your theme.
theme: 'theme/'

# This defines the structure of your site & which markdown file each page maps to.
pages:
    - Page Title: 'docs/markdown-a.md'
    - Another Page Title: 'docs/markdown-b.md'
```
Page headings in your markdown files will be automatically extracted and exposed to your theme so that you can use them in the navigation.

## Using subpages
If you want, you can break your pages into sections.
You can do this by nesting pages like so:
```YAML
pages:
    - Page Title: 'docs/markdown-a.md'
    - Another Page Title: 'docs/markdown-b.md'
    - Section Title:
        - Subpage: 'docs/markdown-c.md'
        - Another Subpage: 'docs/markdown-c.md'
```
Pages can only go one level deep like above.


## Changing the base url
If you would like the publish your site to a sub-path such as `http://mysite.com/docs/` you will need to specify
a base url in your config. This is prepended to all url's when your run `enfield publish`.

Some valid examples:
```YAML
base_url: '/docs/'

# If you would like absolute urls you can also do this:
base_url: 'http://foo.com/bar/baz/'
```
