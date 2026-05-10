# Histoire de l'Humanité — Instructions Claude CLI

## Vision du Projet

Construction progressive d'une histoire philosophique et transculturelle de l'humanité.

**Angle directeur** : l'universalité comme grille de lecture — non pas pour démontrer que les
civilisations convergent, mais pour identifier, dans chaque époque et chaque culture, ce qui
se retrouve partout (universel) et ce qui reste propre à son contexte (particulier).
L'histoire occidentale n'est qu'un fil parmi d'autres.

**Question centrale du projet**
> Les idées ont-elles façonné l'histoire, ou l'histoire a-t-elle façonné les idées ?
Les deux directions sont explorées : contraintes géographiques, économiques, techniques,
biologiques — et systèmes de pensée, philosophies morales, religions. La granularité d'analyse
augmente en se rapprochant du présent : de l'esquisse conceptuelle pour la préhistoire à
l'analyse fine (philosophique, scientifique, économique, politique) pour les périodes récentes.

**La Période Axiale — exemple emblématique de convergence** (Karl Jaspers, 1949)
Entre ~800 et 200 av. J.-C., simultanément et indépendamment :
- Grèce : Héraclite, Socrate, Platon, Aristote, Stoïciens
- Inde : Upanishads, Bouddha (~563-483 av. J.-C.), Jaïnisme
- Chine : Confucius (~551-479 av. J.-C.), Laozi, Zhuangzi
- Proche-Orient : Prophètes hébreux, Zoroastre
→ Un cas emblématique de convergence indépendante — point de référence du projet, pas son axe
organisateur. D'autres moments de convergence ont la même valeur : émergence des grandes
religions mondiales (IVe-VIIe s.), révolutions scientifiques et industrielles simultanées, etc.

**Fil comparatiste à maintenir dans chaque fichier** :
- Poser la double question : qu'est-ce qui converge ? qu'est-ce qui diverge ? pourquoi ?
- Chercher les parallèles inter-culturels (stoïcisme ↔ détachement bouddhiste, etc.)
- Signaler les convergences indépendantes (sans influence mutuelle prouvée)
- Signaler aussi les divergences — ce qui n'est pas universel est aussi informatif
- Éviter l'eurocentrisme — Europe = un angle parmi d'autres ; inclure activement les traditions
  africaines, indiennes, chinoises, islamiques

---

## Structure du Dépôt

```
histoireH/
├── docs/                       ← contenu publié (MkDocs)
│   ├── INDEX.md                   L0 : vue globale
│   ├── 01-periodes/               L1 : grandes périodes
│   ├── 02-civilisations/          L2 : civilisations par période
│   ├── 03-themes/                 L3 : thèmes transversaux
│   ├── 04-figures/                L4 : figures et textes
│   └── references/                sources, glossaire, lectures
│       ├── sources/               fiches projet (300-700 mots)
│       ├── lectures/              présentations didactiques (1500-2000 mots)
│       └── par-ou-commencer.md    guide d'entrée pour néophyte
├── templates/                  ← gabarits (non publiés)
├── mkdocs.yml                  ← configuration MkDocs
├── pyproject.toml              ← dépendances Python (uv)
├── CLAUDE.md                   ← instructions Claude CLI
└── PROGRESS.md                 ← suivi de session
```

### Couches de contenu (toutes dans `docs/`)

```
L0 : Vue globale          → docs/INDEX.md
L1 : Grandes périodes     → docs/01-periodes/
L2 : Civilisations        → docs/02-civilisations/{periode}/
L3 : Thèmes transversaux  → docs/03-themes/
L4 : Figures et textes    → docs/04-figures/
```

### Convention de navigation dans chaque fichier

```markdown
[← Vue globale](../00-vue-globale.md) | [Index](../INDEX.md)
**Enfants :** [A](./A.md) · [B](./B.md)
**Connexions :** [Thème X](../../03-themes/X.md) · [Figure Y](../../04-figures/Y.md)
```

---

## Workflow de Session

Au début de chaque session Claude CLI :
1. Lire `PROGRESS.md` → savoir où on en est et ce qui est prioritaire
2. Lire `docs/INDEX.md` → carte de navigation du projet
3. L'utilisateur indique l'axe à développer
4. Lire les fichiers existants pertinents avant d'écrire
5. Créer ou enrichir les fichiers dans `docs/` selon les templates dans `templates/`
6. Mettre à jour `PROGRESS.md` (section "Dernière session" + "Fait")
7. Mettre à jour `docs/INDEX.md` et `mkdocs.yml` (section `nav`) si de nouveaux fichiers sont créés

---

## Principes d'Écriture

- **Ton** : synthétique, comparatif, factuel — ni cours magistral, ni essai
- **Structure** : toujours commencer par le contexte global, puis descendre dans le détail
- **Comparaisons** : expliciter les parallèles philosophiques entre cultures
- **Nuance** : noter quand une connexion est établie vs. hypothétique
- **Longueur** : préférer des fichiers denses et courts à des fichiers exhaustifs et longs
- **Langue** : français, sauf les termes techniques sans équivalent (Axial Age, etc.)

---

## Système de Références à Deux Niveaux

Les références utilisent deux formats selon l'importance de l'auteur pour le projet.

### Fiches projet (`references/sources/`)
Format court : 300-700 mots. Orienté projet : thèse, concepts clés, pertinence, connexions. Ne suppose pas que le lecteur a lu le livre.

### Lectures didactiques (`references/lectures/`)
Format long : 1500-2000 mots. Factuel et didactique — non orienté projet. Présente l'auteur, le livre, l'argument en détail, la réception, les limites. Accessible sans formation philosophique préalable. Réservé aux **auteurs-cœur** (~6 auteurs centraux pour le projet).

**Un auteur mérite une lecture longue si :** son œuvre est directement centrale pour le projet, ou si comprendre sa thèse en profondeur conditionne la compréhension d'autres auteurs du corpus. La liste évolue avec le corpus — voir `references/INDEX.md` pour l'état actuel.

**Principe :** les deux formats sont complémentaires — la fiche `sources/` pour naviguer dans le projet, la lecture `lectures/` pour comprendre un auteur en profondeur.

---

## Templates

Les gabarits sont dans `templates/`. Le contenu créé va dans `docs/` (même arborescence).

| Couche | Template | Usage |
|--------|----------|-------|
| L1 | `templates/periode.md` | Une grande période historique |
| L2 | `templates/civilisation.md` | Une civilisation dans une période |
| L3 | `templates/theme.md` | Un thème transversal (philo, religion...) |
| L4 | `templates/figure.md` | Un penseur, texte, ou événement clé |

---

## Grandes Périodes (L1 — feuille de route)

| Code | Période | Dates approx. | Statut |
|------|---------|---------------|--------|
| P1 | Préhistoire & Émergence humaine | -300 000 → -3 500 | ☐ |
| P2 | Premières Civilisations | -3 500 → -800 | ☐ |
| P3 | **Période Axiale** | -800 → -200 | ☐ |
| P4 | Empires & Expansion | -200 → 500 | ☐ |
| P5 | Moyen Âge Mondial | 500 → 1 500 | ☐ |
| P6 | Révolutions Modernes | 1 500 → 1 800 | ☐ |
| P7 | Ère Contemporaine | 1 800 → présent | ☐ |

Chaque période est traitée à égalité — aucune n'est le "cœur" du projet.
La Période Axiale (P3) reste un excellent point d'entrée par la richesse documentaire.
