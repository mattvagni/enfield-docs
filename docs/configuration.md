For enfield to work you need to have `.yml` config file. It can be anywhere but by default enfield will look for a file called `config.yml` in your root.

These are the basic config options.

```YAML
# The title of your site, most commonly used in the <title> tag.
title: 'Your Sites Title'

# This is the folder to your theme.
theme: 'theme/'

# This defines the structure of your site & which markdown file each page maps to.
pages:
    - Page Title: 'docs/markdown-a.md'
    - Another Page Title: 'docs/markdown-b.md'
```
Page headings in your markdown files will be automatically extracted and exposed to your theme so that you can use them in the navigation.

## Subpages/sections
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

_Important:_ Enfield will automatically parse each of your page's content and expose any h1 & h2s to your theme so you can have in-page anchors to your headings. You don't have to do anything for this to happen.

## Images & static assets
If you would like to include some files additionally to the one your theme specifies you can define a list of files to copy over to the root of your built site.

For example:
```yaml
include:
    - 'images/' # You can specify folders
    - 'favicon.ico' # or files.
```
That means that in your root of your build directory the `images/` folder and the `favicon.ico` will be copied.

## Changing the base url
If you would like the publish your site to a sub-path such as `http://mysite.com/docs/` you will need to specify
a base url in your config.

For example:
```YAML
base_url: 'http://mysite.com/docs/'

# Alternatively you can also just specify a base path.
base_url: '/docs/'
```
This is prepended to all url's when your run `enfield publish`. Enfield will also change any links or images in your markdown to respect this. Basically, you shouldn't have to change any of your content.

## Custom template variables
If you would like to have any custom variables exposed to your theme's template just add it to your config. Any keys besides the ones used by Enfield directly will be provided to your theme for use.

If you do this in your config:
```YAML
twitter_url: 'Your Sites Name'
```
You can use these in your theme by doing:
```jinja
<a href="{{ site.twitter_url }}">Follow Me On Twitter</a>
```
