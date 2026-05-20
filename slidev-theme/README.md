# @iod-solutions/slidev-theme

Thème Slidev officiel **IoD solutions** : identité cyan / blanc / noir, layouts dérivés du template d'entreprise.

## Installation

### Depuis le repo Plugin-slidev (recommandé)

Le thème vit dans le monorepo [`IOD-Solutions/Plugin-slidev`](https://github.com/IOD-Solutions/Plugin-slidev) sous le dossier `slidev-theme/`. Installez-le directement par URL Git :

```bash
# HTTPS
npm install "git+https://github.com/IOD-Solutions/Plugin-slidev.git#subdirectory=slidev-theme"

# SSH
npm install "git+ssh://git@github.com:IOD-Solutions/Plugin-slidev.git#subdirectory=slidev-theme"
```

Cela ajoute dans votre `package.json` :

```json
"dependencies": {
  "@iod-solutions/slidev-theme": "git+https://github.com/IOD-Solutions/Plugin-slidev.git#subdirectory=slidev-theme"
}
```

### Épingler une version (tag git)

```bash
npm install "git+https://github.com/IOD-Solutions/Plugin-slidev.git#semver:v0.1.0&subdirectory=slidev-theme"
```

### Pendant le développement du thème (lien local)

```bash
npm install file:/chemin/vers/Plugin-slidev/slidev-theme
```

## Activation dans une présentation Slidev

Dans le frontmatter de `slides.md` :

```yaml
---
theme: '@iod-solutions/slidev-theme'
layout: cover
title: Titre de la présentation
---
```

> ⚠️ Les guillemets sont nécessaires autour de `@iod-solutions/...` (YAML interprète `@` comme un caractère spécial).

## Layouts disponibles

| Layout       | Usage                                                       |
|--------------|-------------------------------------------------------------|
| `cover`      | Slide de titre (fond cyan, logo centré bas)                 |
| `default`    | Slide de contenu (fond blanc, logo + footer en bas)         |
| `section`    | Transition de section (fond cyan, numéro + titre)           |
| `two-cols`   | Deux colonnes (utiliser `::right::` pour séparer)           |
| `statement`  | Contenu centré (idéal pour 3 takeaways, rule of three)      |
| `quote`      | Citation centrée avec marque guillemet en cyan              |
| `end`        | Slide de clôture (fond noir, « Merci ! », contacts)         |

## Frontmatter par slide

```yaml
---
layout: default
meta: 'Atelier — Recherche sémantique'   # texte du footer (optionnel)
sectionTag: 'Cas d''usage 1 / 3'         # pastille top-left (optionnel)
---
```

Pour le layout `section` :

```yaml
---
layout: section
num: 1                                    # numéro affiché (01, 02, ...)
---

# Titre de la section
## Sous-titre optionnel
```

Pour `end` :

```yaml
---
layout: end
email: contact@iod-solutions.fr
phone: '07 61 43 99 23'
website: www.iod-solutions.fr
linkedin: LinkedIn/iod-solutions
---
```

## Tokens de design

Variables CSS exposées via `:root`, modifiables avec un bloc `<style>` dans `slides.md` :

| Variable             | Valeur     | Usage                       |
|----------------------|------------|-----------------------------|
| `--iod-cyan`         | `#009FBC`  | Couleur primaire IoD        |
| `--iod-cyan-dark`    | `#007D94`  | Hover, accents foncés       |
| `--iod-cyan-light`   | `#E5F4F7`  | Backgrounds accentués       |
| `--iod-cream`        | `#EFE9DC`  | Boxes d'information         |
| `--iod-warning`      | `#E8A23C`  | Boxes d'avertissement       |
| `--iod-text`         | `#1F2937`  | Texte courant               |
| `--iod-muted`        | `#6B7280`  | Sous-titres, footers        |

## Classes utilitaires

- `.accent` — texte en cyan IoD
- `.muted` — texte en gris secondaire
- `.iod-box` — box crème (info)
- `.iod-box-accent` — box cyan light avec bordure cyan
- `.iod-box-warning` — box orange avec bordure orange
- `.iod-cols-2` / `.iod-cols-3` — grilles 2 / 3 colonnes
- `.iod-numbered` — carte numérotée 01 / 02 / 03 (style template IoD)

## Roadmap

- [ ] Logo en SVG vectoriel (actuellement PNG 500 × 246)
- [ ] Variante dark du logo pour le layout `end`
- [ ] Layout `image-content` (image + texte, bande cyan latérale)
- [ ] Tests visuels (snapshots Playwright)
- [ ] Workflow GitHub Actions pour publication automatique en GitHub Packages

## License

UNLICENSED — usage interne IoD solutions uniquement.
