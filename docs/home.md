Enfield is a static-site generator based on pages, it's designed for docs.

You can write your docs in markdown and use your own the theme to customize virtually every aspect of your docs. You can specify the order of the pages and structure them into sections so they are more readable.

Like with any other static site generator, you can deploy it to basically anything since the output is just a bunch of static files.

These docs are generated using enfield.

## Installation
Assuming you already have node and npm installed:
```bash
npm install -g enfield
```
You don't have to install it globally but this is probably the easiest option if you just want to try it out.

## Jekyll
Given how nicely github integrates with github it's super tempting to try and use Jekyll for small page based sites such as API docs.

However, since it was built for creating blogs it's super awkward if you just want a list of pages you define in markdown. It's definitely possible but just feels a bit over-the-top for a simple docs site.
