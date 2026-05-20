# slidev-theme-iod

Thème Slidev officiel **IoD solutions** : identité cyan/blanc/noir, layouts dérivés du template d'entreprise.

## Installation

### Dans un projet Slidev existant

```bash
npm install slidev-theme-iod
```

Puis dans le frontmatter de `slides.md` :

```yaml
---
theme: iod
---
```

### Installation locale (pendant le développement du thème)

Depuis le dossier de la présentation, lier le package local :

```bash
npm install ../slidev-theme-iod
# ou en relatif depuis le repo Plugin-slidev :
npm install file:../Plugin-slidev/slidev-theme-iod
```

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

Variables CSS exposées (modifiables via `<style>` dans `slides.md`) :

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
- `.muted` — texte en gris muted
- `.iod-box` — box crème (info)
- `.iod-box-accent` — box cyan light avec bordure cyan
- `.iod-box-warning` — box orange avec bordure orange
- `.iod-cols-2` / `.iod-cols-3` — grilles 2/3 colonnes
- `.iod-numbered` — carte numérotée (01/02/03 style)

## Logo

Le logo IoD est servi via `/iod-logo.png` (rendu par Slidev depuis `public/`).
Pour le remplacer par un SVG vectoriel : remplacer `public/iod-logo.png`.

## Roadmap

- [ ] Logo en SVG vectoriel (actuellement PNG 500×246)
- [ ] Variante dark mode du logo (pour layout `end`)
- [ ] Layout `image-content` (image + texte deux colonnes, style "À propos")
- [ ] Composant `<SectionTag />` réutilisable
- [ ] Tests visuels (snapshots)
