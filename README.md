# Material for MkDocs

Générateur de site statique pour la documentation technique.

Installer MkDocs :

```console
$ python3 -m venv ~/.venv/mkdocs
$ source ~/.venv/mkdocs/bin/activate
$ pip install --upgrade pip
$ pip install mkdocs
```

Tester MkDocs :

```console
$ mkdocs new test
INFO    -  Creating project directory: test
INFO    -  Writing config file: test/mkdocs.yml
INFO    -  Writing initial docs: test/docs/index.md
$ cd test/
$ tree
.
├── docs
│   └── index.md
└── mkdocs.yml

1 directory, 2 files
```

Lancer le serveur de développement :

```console
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.06 seconds
INFO    -  [20:11:32] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [20:11:32] Serving on http://127.0.0.1:8000/
```

Ouvrir la page http://127.0.0.1:8000 dans un navigateur web.

Le serveur de développement gère le rafraîchissement automatique. Dès qu'il y a
le moindre changement dans le fichier de configuration `mkdocs.yml` ou dans le
répertoire `docs/` la documentation est mise à jour à chaud.

## Le site par défaut

Voici le site par défaut tel qu'il est généré par la commande `mkdocs new
site-01` :

```console
$ cd sites/site-01
$ mkdocs serve
```

Alternativement on peut également créer le répertoire d'abord :

```console
$ mkdir site-01
$ cd site-01/
$ mkdocs new .
INFO    -  Writing config file: ./mkdocs.yml
INFO    -  Writing initial docs: ./docs/index.md
```

## Le titre du site

```console
$ cd sites/site-02
$ mkdocs serve
```

Éditer `mkdocs.yml` pour changer le titre du site :

```yaml
site_name: My Site
```


## Ajouter des pages

Ajouter une page à la documentation :

```console
$ curl 'https://jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md
$ tree
.
├── docs
│   ├── about.md
│   └── index.md
└── mkdocs.yml

1 directory, 3 files
```

Éditer `mkdocs.yml` et renseigner les infos d'en-tête pour la navigation :

```yaml
site_name: My Site
nav:
  - Home: index.md
  - About: about.md
```

Exemple : `sites/site-03`


## Utiliser un thème

Éditer `mkdocs.yml` et choisir un thème :

```yaml
site_name: My Site
nav:
  - Home: index.md
  - About: about.md
theme: readthedocs
```

Exemple : `sites/site-04`


## Construire le site

Invoquer cette commande à la racine du projet :

```console 
$ mkdocs build
INFO    -  Cleaning site directory
INFO    -  Building documentation to directory: .../site-05/site
INFO    -  Documentation built in 0.08 seconds
```

On se retrouve avec un nouveau répertoire `site/` :

```console
$ ls site/
404.html  css  index.html  search       sitemap.xml
about     img  js          search.html  sitemap.xml.gz
```

Si l'on stocke le projet dans un dépôt Git, il va falloir ajouter un fichier
`.gitignore` correspondant :

```console
$ echo 'site/' >> .gitignore
```

Exemple : `sites/site-05`


## Ressources

- https://www.mkdocs.org/

- https://squidfunk.github.io/mkdocs-material/


