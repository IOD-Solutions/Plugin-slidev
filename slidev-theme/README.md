# @iod-solutions/slidev-theme

Thème Slidev officiel **IoD solutions** : identité cyan / blanc / noir, layouts dérivés du template d'entreprise.

## Installation

```bash
npm install @iod-solutions/slidev-theme
```

C'est tout. Le package est publié sur le registry npm public ([npmjs.com/package/@iod-solutions/slidev-theme](https://www.npmjs.com/package/@iod-solutions/slidev-theme)) — pas de token, pas de config Git, pas de SSH.

### Pendant le développement du thème (lien local)

Pour itérer sur le thème depuis ce repo sans publier à chaque modification :

```bash
# Depuis votre projet de présentation :
npm install file:/chemin/vers/Plugin-slidev/slidev-theme
```

Le repo source vit dans [`IOD-Solutions/Plugin-slidev`](https://github.com/IOD-Solutions/Plugin-slidev) sous le dossier `slidev-theme/`.

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
