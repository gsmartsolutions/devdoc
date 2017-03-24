GSS - Dev Documentation
======================
Used [mkdocs](http://www.mkdocs.org/) to generate.
Still under development, but you could check [dev version](http://devdocs.gssdev.xyz/) here

## Contribute

## Build

Make sure you have `Python` and `pip`

```
python --version
# Python 2.7.13
pip --version
# pip 9.0.1
```

Install `mkdocs`

```
pip install mkdocs && mkdocs --version
# Material requires MkDocs >= 0.16.
```

Highly recommended to install Pygments and PyMdown extensions

```
pip install pygments
pip install pymdown-extensions
```

Then install theme Material

```
pip install mkdocs-material
```

Serve your build, theme supports live-reload on changes and auto-build

```
mkdocs serve
```

To build and release

```
mkdoc build
scp -r ./site gssdev:doc.gssdev.xyz/
```


