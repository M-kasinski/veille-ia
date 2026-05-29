# Veille IA

Média tech francophone sur les **gros modèles, les architectures et l'actualité de l'IA générale** : fondation models, scaling laws, multimodal, agents, alignement, enjeux industriels.

🌐 **En ligne :** [https://veille-ia-zeta.vercel.app](https://veille-ia-zeta.vercel.app/)

## Stack

- [Astro 6](https://astro.build/) — site statique, content collections (Markdown)
- Déploiement **Vercel** (auto-deploy à chaque push sur `main`)
- Images Open Graph générées au build (`scripts/generate-og-images.mjs`, via `sharp`)

## Développement

```shell
npm install
npm run dev      # http://localhost:4321
npm run build    # génère les images OG puis build dans dist/
npm run preview
```

## Structure

```
src/
  content/blog/      # articles (Markdown + frontmatter)
  components/        # Header, Footer, BaseHead, ...
  layouts/           # BlogPost
  pages/             # index, blog, about, rss
  styles/global.css  # design system
scripts/
  generate-og-images.mjs   # images OG par article (build-time)
public/og/
```

## Ajouter un article

Créer un fichier `.md` dans `src/content/blog/` avec le frontmatter suivant :

```yaml
---
title: "Titre de l'article"
description: "Description courte et claire."
pubDate: 2026-05-29
tags: ["tag1", "tag2"]
author: "Veille IA"
draft: false
sources:
  - label: "Source"
    url: "https://..."
---
```

Puis `git push origin main` — Vercel rebuild automatiquement.
