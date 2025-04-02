# Material for MkDocs

Générateur de site statique pour la documentation technique.

Installer MkDocs :

```console
$ python3 -m venv ~/.venv/mkdocs
$ source ~/.venv/mkdocs/bin/activate
(mkdocs) $ pip install --upgrade pip
(mkdocs) $ pip install mkdocs
```

Tester MkDocs :

```console
(mkdocs) $ mkdocs new test
INFO    -  Creating project directory: test
INFO    -  Writing config file: test/mkdocs.yml
INFO    -  Writing initial docs: test/docs/index.md
(mkdocs) $ cd test/
(mkdocs) $ tree
.
├── docs
│   └── index.md
└── mkdocs.yml

1 directory, 2 files
```

Lancer le serveur de développement :

```console
(mkdocs) $ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.06 seconds
INFO    -  [20:11:32] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [20:11:32] Serving on http://127.0.0.1:8000/
```

Ouvrir la page http://127.0.0.1:8000 dans un navigateur web.

> Le serveur de développement gère le rafraîchissement automatique. Dès qu'il y
> a le moindre changement dans le fichier de configuration `mkdocs.yml` ou dans
> le répertoire `docs/` la documentation est mise à jour à chaud.


## Ressources

- https://www.mkdocs.org/

- https://squidfunk.github.io/mkdocs-material/


