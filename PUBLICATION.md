# Publication — Réflexions et Propositions

> Note de design — à décider avant de configurer.
> Le contenu Markdown existe déjà, seul l'outillage reste à choisir.

---

## Objectifs

- **Lecture locale** : voir le résultat rendu au fil de la rédaction (hot reload)
- **Partage** : publier facilement pour que d'autres lisent (lien URL)
- **PDF** : option future, un "livre" exportable
- **CLI** : tout doit fonctionner en ligne de commande, sans interface graphique
- **CI/CD** : publication automatique à chaque modification

---

## Analyse du Contenu

Le projet est une **encyclopédie naviguable** (couches L0→L4, liens transversaux),
pas un livre séquentiel (chapitres 1, 2, 3...).

Ce point oriente le choix : les outils de type "livre" (mdBook) sont moins adaptés
que les outils de type "documentation" (MkDocs, Hugo).

---

## Options Analysées

### Option A — MkDocs + Material Theme ⭐ Recommandée

**Installation**
```bash
pip install mkdocs-material
pip install mkdocs-with-pdf  # pour export PDF
```

**Usage quotidien**
```bash
mkdocs serve        # http://localhost:8000 — hot reload automatique
mkdocs build        # génère le site statique dans site/
mkdocs gh-deploy    # publie sur GitHub Pages en une commande
```

**Pour le PDF**
```bash
# avec le plugin mkdocs-with-pdf configuré :
mkdocs build        # génère aussi un PDF
```

**CI/CD (GitHub Actions — 5 lignes)**
```yaml
# .github/workflows/publish.yml
name: Publish
on: push
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: pip install mkdocs-material
      - run: mkdocs gh-deploy --force
```

**Avantages**
- Navigation latérale permanente, breadcrumbs, search instantanée
- Liens Markdown relatifs existants fonctionnent sans modification
- Mobile-friendly, thème sombre/clair
- Les répertoires 01-periodes/, 02-civilisations/, etc. deviennent des sections automatiquement
- Excellent pour contenu non-linéaire avec références croisées

**Inconvénient**
- Requiert Python (mais disponible partout)
- Nécessite un `mkdocs.yml` à la racine

---

### Option B — mdBook

**Installation**
```bash
cargo install mdbook          # si Rust installé
# OU télécharger le binaire unique depuis GitHub releases
```

**Usage quotidien**
```bash
mdbook serve        # http://localhost:3000 — hot reload
mdbook build        # génère le site dans book/
```

**Pour le PDF**
```bash
cargo install mdbook-pdf      # via Chrome headless
```

**Avantages**
- Un seul binaire, aucune dépendance
- PDF natif de bonne qualité
- Navigation style "livre" (table des matières à gauche)
- Idéal si l'objectif final est vraiment un livre imprimable

**Inconvénient**
- Requiert un fichier `SUMMARY.md` qui liste TOUS les fichiers dans l'ordre
- Navigation moins adaptée à une encyclopédie non-linéaire
- Plus rigide : mal adapté aux liens transversaux entre couches

---

### Option C — Hugo + Geekdoc ou Docsy

**Installation**
```bash
brew install hugo   # ou binaire unique sur GitHub
```

**Usage quotidien**
```bash
hugo server -D      # http://localhost:1313 — hot reload
hugo                # génère le site dans public/
```

**Avantages**
- Le plus rapide (Go), idéal pour gros projets
- Meilleur écosystème de thèmes
- Le plus flexible pour la navigation complexe
- Excellent CI/CD avec Netlify (déploiement preview par branche)

**Inconvénient**
- Nécessite du front matter YAML dans chaque fichier Markdown (ou un archetype)
- Configuration plus complexe
- Overkill pour ce projet au stade actuel

---

## Recommandation

**Court terme : MkDocs + Material**
- Prêt en 15 minutes
- `mkdocs serve` pour lire en local
- `mkdocs gh-deploy` pour partager

**Si besoin PDF : ajouter `mkdocs-with-pdf`** plutôt que changer d'outil

**Si le projet grossit beaucoup** (centaines de fichiers) : envisager Hugo à ce moment-là

---

## Structure Minimale pour MkDocs

Créer `mkdocs.yml` à la racine :

```yaml
site_name: Histoire de l'Humanité
site_description: Une histoire philosophique et transculturelle de l'humanité
docs_dir: .
site_dir: _site

theme:
  name: material
  language: fr
  palette:
    - scheme: default
      toggle:
        icon: material/brightness-7
        name: Mode sombre
    - scheme: slate
      toggle:
        icon: material/brightness-4
        name: Mode clair
  features:
    - navigation.tabs
    - navigation.sections
    - navigation.expand
    - search.suggest
    - toc.integrate

nav:
  - Accueil: INDEX.md
  - Vue Globale: 00-vue-globale.md
  - Grandes Périodes:
    - 01-periodes/prehistoire.md
    - 01-periodes/periode-axiale.md
    # ... à compléter
  - Civilisations: 02-civilisations/
  - Thèmes: 03-themes/
  - Figures: 04-figures/
  - Références:
    - Index: references/INDEX.md
    - Glossaire: references/glossaire.md
    # sources/ à lister

exclude_docs: |
  _site/
  PROGRESS.md
  PUBLICATION.md
  templates/

plugins:
  - search:
      lang: fr
```

---

## Hébergement

| Option | Commande | Coût | Domaine custom |
|--------|----------|------|----------------|
| GitHub Pages | `mkdocs gh-deploy` | Gratuit | Oui (CNAME) |
| Netlify | push git → auto | Gratuit (tier) | Oui |
| Cloudflare Pages | push git → auto | Gratuit | Oui |

---

## Prochaine Étape

1. Initialiser un dépôt git dans ce répertoire
2. Installer MkDocs Material
3. Créer `mkdocs.yml`
4. Tester `mkdocs serve`
5. Pousser sur GitHub et activer GitHub Pages

*À faire dans une prochaine session — le contenu prime sur la publication.*
