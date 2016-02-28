Enfield is a command line tool.

## Building your docs
```bash
$ enfield build

# To watch for changes or serve your site:
# enfield build --watch --serve
```

#### `--config, -c`
The location of your config relative to where you are running the command from. If you don't explicitly define a config location Enfield will look for `config.yml` in the root of your project.

#### `--watch, -w`
Whether you would like for enfield to watch for changes and rebuild or not. Enfield watches:
- Your config file
- Your entire theme directory
- Any markdown files you specify in your config.
- Any files you manually specified you'd like to include in your config.

#### `--outputDir, -o`
Where your like to 'output' your docs. This is basically the folder you want your static site built into. Enfield deletes this folder before every build.

#### `--serve, -s`
Whether you would like for enfield to 'serve' your site locally.

#### `--port, -p`
The port on which to serve your site. By default the port is 3000. This only has effect if you are using `--serve`

#### `--debug, -d`
Turns on debug logging, probably not useful at all.


## Publishing to Github
```bash
$ enfield publish
```
This will build your site, then copy over those files into the gh-pages branch and push those changes.

_ProTip_: If you are not using a custom domain you will need to specify a `base_url` your config.

#### `--outputDir, -o`
Same as in the build command. It is from this folder that your GitHub pages are created.
