# Personal website

This is my personal website, you can check it [live](http://juanriaza.com). It's powered by [Pelican](http://getpelican.com), a static site generator. Design based on [Hyde](http://hyde.getpoole.com/) and [this](https://github.com/jvanz/pelican-hyde) layout.

For checking live the output generated while writing just run `$ pelican -r content` and serve it via the handy `$ python -m http.server`


In order to generate the static content and deploy the output to `github-pages`

```
$ pelican content -o output -s publishconf.py
$ ghp-import output
$ git push origin gh-pages
```
