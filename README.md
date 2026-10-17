# The random walk

Blog en français sur les mathématiques et l’intelligence artificielle, construit avec [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) et Jekyll. Aucun billet d’exemple n’est fourni.

## Publier sur GitHub Pages

Le dépôt est préparé pour un nom `the-random-walk` : `_config.yml` utilise `baseurl: "/the-random-walk"`. Si le dépôt porte un autre nom ou si tu utilises un domaine personnalisé, adapte `baseurl` et `url` dans `_config.yml`.

Le workflow `.github/workflows/pages-deploy.yml` construit et déploie le site sur GitHub Pages. Après avoir ajouté les fichiers à ton dépôt et poussé la branche `main`, sélectionne **Settings → Pages → Build and deployment → GitHub Actions** si ce n’est pas déjà choisi.

## Ajouter tes articles

Ajoute un fichier Markdown daté dans `_posts/`, par exemple `YYYY-MM-DD-mon-sujet.md`, avec un front matter Jekyll comprenant `title`, `date`, `categories` et `tags`. Le thème Chirpy prend en charge les formules mathématiques, les blocs de code, les archives, les catégories, les tags et la recherche.

## Prévisualisation locale

Après installation de Ruby et Bundler :

```sh
bundle install
bundle exec jekyll serve --host 0.0.0.0 --port 3000
```
