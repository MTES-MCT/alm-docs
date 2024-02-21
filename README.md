Acceslibre Mobilités - docs
===========================

Main documentation site. Written in markdown, built with 
[MkDocs](https://www.mkdocs.org/)


Run locally
-----------

In a python venv:

```
pip install -r requirements.txt
mkdocs serve
```

And visit <http://localhost:8000> in your favourite browser.


Write new docs
--------------

Add markdown files in the `docs/` folder.

To add this file in the main table of contents, add it in
the `nav` section of the `mkdocs.yml` file.

[Writing your docs](https://www.mkdocs.org/user-guide/writing-your-docs/)


Deploy
------

```
mkdocs build
```

And serve the `site/` folder with your favourite web server.

