Enfield is a static-site generator based on pages, it's designed for docs.

You can write your docs in markdown and use your own the theme to customize and design your docs to your liking. You can specify the order of the pages and structure them into sections so they are more readable.

Like with any other static site generator, you can deploy it to basically anything since the output is just a bunch of static files.

It has built-in support for publishing to github-pages to make it super easy.

These docs are generated using enfield, [check them out](https://github.com/mattvagni/enfield-docs).

## Installation
Assuming you already have node and npm installed:
```bash
npm install -g enfield
```
You don't have to install it globally but this is probably the easiest option if you just want to try it out.

## Why not Jekyll?
Given how nicely Jekyll integrates with Github it's super tempting to try and use Jekyll for small page based sites such as API docs.

However, since it was built for creating blogs it's super awkward if you just want a list of pages you define in markdown. It's definitely possible but just feels a bit over-the-top/hacky for a simple docs site.
