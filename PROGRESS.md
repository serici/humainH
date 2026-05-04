# Progression du Projet

## Dernière Session
- **Date** : 2026-04-30
- **Travail** : Initialisation complète — structure, CLAUDE.md, templates, références

## Fait ✓

### Infrastructure
- [x] Structure de répertoires
- [x] `CLAUDE.md` — instructions Claude CLI
- [x] `INDEX.md` — carte de navigation du projet
- [x] `PROGRESS.md` — ce fichier

### Templates
- [x] `templates/periode.md`
- [x] `templates/civilisation.md`
- [x] `templates/theme.md`
- [x] `templates/figure.md`

### Références (corpus séparé)
- [x] `references/INDEX.md` — index hiérarchique par cluster
- [x] `references/glossaire.md` — concepts clés
- [x] `references/sources/jaspers.md`
- [x] `references/sources/armstrong.md`
- [x] `references/sources/huxley.md`
- [x] `references/sources/guenon.md`
- [x] `references/sources/leibniz.md`
- [x] `references/sources/campbell.md`
- [x] `references/sources/levi-strauss.md`
- [x] `references/sources/eliade.md`
- [x] `references/sources/spengler.md`
- [x] `references/sources/toynbee.md`
- [x] `references/sources/ibn-khaldun.md`
- [x] `references/sources/braudel.md`
- [x] `references/sources/diamond.md`
- [x] `references/sources/smil.md`
- [x] `references/sources/christian.md`
- [x] `references/sources/teilhard.md`
- [x] `references/sources/wilber.md`
- [x] `references/sources/harari.md`

## Prochaine Session — Suggestions

Le corpus principal (L0, L1, L2, L3, L4) n'a pas encore démarré.
Plusieurs points d'entrée possibles selon l'envie :

1. **Écrire L0** — vue globale : toute l'histoire en une page, le fil philosophique
2. **Commencer par la Période Axiale (L1-P3)** — cœur philosophique, ce qui a motivé le projet
3. **Commencer par la Préhistoire (L1-P1)** — dans l'ordre chronologique
4. **Ouvrir un premier thème (L3)** — le détachement, la figure du héros, les mythes fondateurs...
5. **Compléter les références** — ajouter des sources manquantes (Foucault, Jung, Mumford...)

## Publication

Voir [PUBLICATION.md](./PUBLICATION.md) pour l'analyse complète.

**Recommandation retenue (à valider)** : MkDocs + Material theme
- Local : `mkdocs serve` → http://localhost:8000 avec hot reload
- Partage : `mkdocs gh-deploy` → GitHub Pages
- PDF : plugin `mkdocs-with-pdf`
- CI/CD : GitHub Actions (5 lignes)

**Prérequis avant de configurer** : initialiser un dépôt git + installer MkDocs

---

## Backlog Références

Sources identifiées non encore traitées :
- [ ] Carl Jung — archétypes, inconscient collectif
- [ ] Michel Foucault — épistémès, archéologie du savoir
- [ ] Lewis Mumford — *Technics and Civilization* (1934)
- [ ] Pierre Hadot — *La Philosophie comme manière de vivre*
- [ ] Peter Turchin — Cliodynamics (cycles historiques quantifiés)
- [ ] Johan Huizinga — *Homo Ludens* (le jeu comme fondement de la culture)
- [ ] Victor Turner — liminité et rites de passage
- [ ] Mircea Eliade — *Shamanism* (à compléter dans la fiche existante)
