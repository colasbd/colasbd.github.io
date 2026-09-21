# Page personnelle de Colas Bardavid

Ceci est le repo de ma page web construite avec [Jekyll](https://jekyllrb.com).

J'utilise le thème [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/).

## Deux designs

Le site a deux designs, choisis par la ligne `design:` de `_config.yml` :

- `design: classique` — le thème Minimal Mistakes (bandeaux images, colonne auteur) ;
- `design: moderne` — le design maison, sans dépendance au thème
  (`_includes/design/moderne.html` + `assets/css/moderne.css`).

Le design moderne affiche en haut de chaque page l'image indiquée par `bandeau:` dans
`_config.yml` ; mettre cette ligne en commentaire pour ne pas avoir de bandeau.

Le fichier `_layouts/myBasicLayout.html` sert d'aiguilleur. On peut aussi forcer le design
d'une seule page en mettant `design: classique` ou `design: moderne` dans son front matter.

## Revenir à l'ancien design

1. Ouvrir `_config.yml` et trouver la ligne `design: moderne`.
2. La remplacer par `design: classique`.
3. Commiter et pousser : GitHub reconstruit le site en une minute environ.

Pour revenir au nouveau design, remettre `design: moderne`. Rien d'autre à changer :
les deux designs restent dans le dépôt, seule cette ligne choisit celui qui est affiché.

## Prévisualiser en local

```bash
LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8 bundle exec jekyll serve --livereload
```

(la variable `LANG` évite une erreur d'encodage du vieux compilateur Sass utilisé par GitHub Pages).
