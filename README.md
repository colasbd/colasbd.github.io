# Page personnelle de Colas Bardavid

Ceci est le repo de ma page web construite avec [Jekyll](https://jekyllrb.com).

J'utilise le thème [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/).

## Deux designs

Le site a deux designs, choisis par la ligne `design:` de `_config.yml` :

- `design: classique` — le thème Minimal Mistakes (bandeaux images, colonne auteur) ;
- `design: moderne` — le design maison, sans dépendance au thème
  (`_includes/design/moderne.html` + `assets/css/moderne.css`).

Le fichier `_layouts/myBasicLayout.html` sert d'aiguilleur. On peut aussi forcer le design
d'une seule page en mettant `design: classique` ou `design: moderne` dans son front matter.

## Prévisualiser en local

```bash
LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8 bundle exec jekyll serve --livereload
```

(la variable `LANG` évite une erreur d'encodage du vieux compilateur Sass utilisé par GitHub Pages).
