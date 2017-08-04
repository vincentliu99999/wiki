# wiki

https://vincentliu99999.github.io/wiki/ 

## site generator: [MkDocs](http://www.mkdocs.org/)

* installation
```sh
brew install mkdocs
```

* Create a new project
```sh
mkdocs new [dir-name]
```

* Add smaple page
```sh
curl 'https://jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md
```

* Modify mkdocs.yml
```yml
site_name: wiki
pages:
    - Home: index.md
    - About: about.md
```

* Start the live-reloading docs server. local priview url: http://127.0.0.1:8000/
```sh
mkdocs serve
```

* Build the documentation site. Generating new directory `site`
```sh
mkdocs build
echo "site/" >> .gitignore
mkdocs build --clean # Removing documentation
```

* depolying
```sh
mkdocs gh-deploy
```
