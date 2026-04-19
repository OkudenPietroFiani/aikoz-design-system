# Aikoz — Design System

> Version 1.0 — Produit par [Okuden](https://www.okuden.fr)

---

## Table des matières

1. [Brand Identity](#1-brand-identity)
2. [Brand Values](#2-brand-values)
3. [Brand Personality](#3-brand-personality)
4. [Color System](#4-color-system)
5. [Typography](#5-typography)
6. [Logo](#6-logo)
7. [Iconography & Visual Elements](#7-iconography--visual-elements)
8. [Voice & Tone](#8-voice--tone)
9. [Assets](#9-assets)

---

## 1. Brand Identity

**Aikoz** est une plateforme d'analyse d'avis clients propulsée par l'IA,
développée par [Okuden](https://www.okuden.fr).

Elle agrège et analyse les signaux clients issus de sources multiples
(Google, Trustpilot, réseaux sociaux, NPS, réclamations...) pour révéler
les irritants invisibles et les opportunités de croissance cachées dans la voix client.

### Mission

Transformer les avis clients en levier business —
pour les réseaux de marques comme pour leurs agents de terrain.

### Positionnement

Aikoz s'adresse aux **grandes marques en réseau** (assurance, automobile, retail...)
qui ont besoin d'une lecture unifiée de leur expérience client à deux niveaux :

- **Le central** (directions marketing, CX, stratégie) — pour piloter et benchmarker
- **Le terrain** (agents, responsables d'agence) — pour agir localement

### Nom

Aikoz est la contraction de **AI** et **écho** — la voix client amplifiée par l'intelligence artificielle.

### Produit par

Okuden — Cabinet de conseil en stratégie client
Version 1.0

---

## 2. Brand Values

### Accuracy — Précision

Chaque donnée compte. Aikoz garantit que ce que les marques voient
et entendent de leurs clients est fiable et exploitable.

> Traduction visuelle : contrastes forts, typographie calibrée, pas d'ornement superflu.

### Technological — Technologie

La technologie n'est pas un outil, c'est l'ADN de la marque.
Aikoz anticipe les besoins futurs autant qu'elle répond aux enjeux actuels.

> Traduction visuelle : Midnight Blue profond, interfaces épurées, géométrie précise.

### Innovative — Innovation

Créativité, curiosité, expérimentation. Aikoz se positionne
comme pionnier dans la lecture de la perception de marque.

> Traduction visuelle : Aquamarine comme accent disruptif, formes dynamiques du logo.

---

## 3. Brand Personality

**Archétype principal (70%) : Creator**
Aikoz résout les problèmes avec ingéniosité, en développant
des solutions sur-mesure adaptées à chaque réseau de marque.

**Archétype secondaire (30%) : Explorer**
Aikoz explore en permanence de nouveaux insights,
repoussant les limites de la compréhension de l'expérience client.

---

## 4. Color System

### Palette de marque

| Rôle      | Nom              | Token                     | HEX       |
|-----------|------------------|---------------------------|-----------|
| Primary   | Midnight Blue    | `color.midnight-blue.900` | `#0A1128` |
| Secondary | Ultramarine Blue | `color.ultramarine.500`   | `#3B5DCE` |
| Accent    | Aquamarine Green | `color.aquamarine.300`    | `#70FFD4` |
| Base      | Frozen White     | `#FFFFFF`                 | `#FFFFFF` |

Chaque couleur de marque est déclinée en 12 nuances (50 → 1000)
dans `primitives.json`. Les tokens sémantiques sont dans `semantics.json`.
Ne jamais utiliser une couleur primitive directement en production —
toujours passer par un token sémantique.

---

### Midnight Blue vs Neutrals

**Midnight Blue** est une couleur de marque, pas un gris fonctionnel.
**Neutrals** sont les gris d'interface au quotidien (légèrement teintés
de la même hue, mais sans charge identitaire).

| Situation                        | Couleur                             |
|----------------------------------|-------------------------------------|
| Fond hero / navbar               | Midnight Blue 900                   |
| Texte principal sur fond clair   | Midnight Blue 900 (`text.primary`)  |
| Texte secondaire / métadonnée    | Neutral 600 (`text.secondary`)      |
| Fond de page app                 | Neutral 50 (`surface.page`)         |
| Bordures de composants           | Neutral 200 (`border.default`)      |
| Card sur fond clair              | White (`surface.raised`)            |
| Section éditoriale forte         | Midnight Blue 900 (`surface.brand`) |

---

### Fonds sombres vs fonds clairs

Ratio cible en interface applicative : **~20% sombre / ~80% clair.**
Au-delà, l'interface devient fatiguante et l'effet de contraste s'érode.

**Fond sombre** = prise de parole de la marque. Expressif, à utiliser
avec parcimonie pour conserver son impact.

**Fond clair** = espace de travail de l'utilisateur. Lisibilité et
confort priment.

| Situation                        | Fond                   |
|----------------------------------|------------------------|
| Hero / landing page              | Sombre — Midnight 900  |
| Navigation principale            | Sombre — Midnight 900  |
| Écrans d'onboarding              | Sombre — Midnight 900  |
| Tooltips, popovers               | Sombre — Midnight 900  |
| Sections éditoriales intercalées | Sombre — Midnight 900  |
| App / dashboard                  | Clair — Neutral 50     |
| Cards, tableaux, listes          | Clair — White          |
| Modals, drawers                  | Clair — White          |

---

### Accents

- L'Aquamarine est réservé aux CTA principaux, highlights et badges
- Ne jamais l'utiliser sur fond blanc — contraste insuffisant
- Privilégier `color.brand.accent` sur `color.surface.brand`
- Le texte sur fond Aquamarine utilise toujours `color.text.on-accent` (Midnight Blue 900)

---

### Contraste & accessibilité

- Texte courant : minimum **4.5:1**
- Texte large / logo : minimum **3:1**
- Focus ring : toujours `color.border.focus` (Ultramarine 500)
- Ne jamais substituer une couleur de marque à une couleur de statut
  (success / warning / error / info sont dans `semantics.json`)

---

## 5. Typography

### Polices

| Rôle    | Police           | Graisses disponibles                   | Fallback                      |
|---------|------------------|----------------------------------------|-------------------------------|
| Heading | PP Radio Grotesk | Regular, Semi Bold, Extra Bold         | —                             |
| Body    | Satoshi          | Regular, Medium, Semi Bold, Extra Bold | Bahnschrift (Microsoft)       |

> **Note PP Radio Grotesk** : pas de graisse Medium.
> Ne pas simuler un faux medium avec `font-weight: 500` — passer
> directement à Semi Bold (600).

> **Bahnschrift** est la police de remplacement pour les environnements
> Microsoft (PowerPoint, Word, emails). Elle s'active automatiquement
> quand Satoshi n'est pas disponible.

---

### Hiérarchie typographique

| Token                        | Police           | Taille | Graisse      | Line height | Usage                     |
|------------------------------|------------------|--------|--------------|-------------|---------------------------|
| `typography.heading.display` | PP Radio Grotesk | 72px   | Black (900)  | 1.0         | Hero / splash             |
| `typography.heading.h1`      | PP Radio Grotesk | 48px   | Bold (700)   | 1.15        | Titre de page principal   |
| `typography.heading.h2`      | PP Radio Grotesk | 36px   | Bold (700)   | 1.15        | Titre de section          |
| `typography.heading.h3`      | PP Radio Grotesk | 30px   | Bold (700)   | 1.25        | Titre de sous-section     |
| `typography.heading.h4`      | PP Radio Grotesk | 24px   | Bold (700)   | 1.25        | Titre de card / panel     |
| `typography.body.lg`         | Satoshi          | 18px   | Regular (400)| 1.5         | Paragraphe d'introduction |
| `typography.body.md`         | Satoshi          | 16px   | Regular (400)| 1.5         | Corps de texte par défaut |
| `typography.body.sm`         | Satoshi          | 14px   | Regular (400)| 1.625       | Texte secondaire          |
| `typography.body.xs`         | Satoshi          | 12px   | Regular (400)| 1.625       | Notes, helper text        |
| `typography.label.lg`        | Satoshi          | 14px   | Medium (500) | 1.25        | Labels de formulaire, nav |
| `typography.label.md`        | Satoshi          | 12px   | Medium (500) | 1.25        | Badges, tabs              |
| `typography.label.sm`        | Satoshi          | 10px   | Medium (500) | 2.0         | Chips, micro labels       |
| `typography.caption`         | Satoshi          | 12px   | Regular (400)| 2.0         | Légendes, timestamps      |

---

### Règles d'usage

**PP Radio Grotesk — Headings uniquement**
- Réservée aux titres (display → h4)
- Ne jamais l'utiliser pour du corps de texte ou des labels
- Toujours en Extra Bold pour les moments forts (hero, splash)
- Letter-spacing négatif sur les grandes tailles (tighter / tight)

**Satoshi — Body, labels, UI**
- Police de travail par défaut pour tout ce qui n'est pas un titre
- Medium (500) exclusivement pour les labels et éléments interactifs
- Ne pas dépasser Semi Bold en corps de texte

**Alignement**
- Texte aligné à gauche par défaut
- Centré uniquement pour les héros, splashs et éléments isolés
- Jamais de texte justifié

**Longueur de ligne**
- Corps de texte : 60–80 caractères par ligne (optimal)
- Ne pas laisser un paragraphe s'étirer sur toute la largeur d'écran

**Casse**
- Respecter la casse naturelle de la langue en toutes circonstances
- Pas de tout-majuscule décoratif dans l'interface ou les communications
- Les acronymes et noms propres suivent les règles typographiques standard

---

### Couleurs de texte

| Contexte                 | Token                  |
|--------------------------|------------------------|
| Texte principal          | `color.text.primary`   |
| Texte secondaire         | `color.text.secondary` |
| Placeholder / métadonnée | `color.text.tertiary`  |
| Désactivé                | `color.text.disabled`  |
| Sur fond sombre          | `color.text.inverse`   |
| Lien / interactif        | `color.text.brand`     |
| Sur fond Aquamarine      | `color.text.on-accent` |

---

## 6. Logo

### Variantes disponibles

| Variante   | Coloris         | Fichier                                              |
|------------|-----------------|------------------------------------------------------|
| Horizontal | Blue (dark)     | `Logo/Horizontal/logo_horizontal_blue.svg`           |
| Horizontal | White           | `Logo/Horizontal/logo_horizontal_white.svg`          |
| Horizontal | By Okuden Blue  | `Logo/Horizontal/logo_horizontal-by-okuden_blue.svg` |
| Horizontal | By Okuden White | `Logo/Horizontal/logo_horizontal-by-okuden_white.svg`|
| Symbole    | Blue (dark)     | `Logo/Symbol/logo_symbol_blue.svg`                   |
| Symbole    | White           | `Logo/Symbol/logo_symbol_white.svg`                  |
| Vertical   | Blue (dark)     | `Logo/Vertical/logo_vertical_blue.svg`               |
| Vertical   | White           | `Logo/Vertical/logo_vertical_white.svg`              |
| Vertical   | By Okuden Blue  | `Logo/Vertical/logo_vertical-by-okuden_blue.svg`     |
| Vertical   | By Okuden White | `Logo/Vertical/logo_vertical-by-okuden_white.svg`    |

---

### Quelle variante utiliser ?

**Logotype horizontal** — variante par défaut.
À utiliser en priorité, notamment quand la marque doit
s'expliquer auprès d'un public qui ne connaît pas encore Aikoz.

**Symbole seul** — quand l'espace est contraint ou que
la marque est déjà établie dans le contexte (favicon,
avatar, icône d'app).

**Vertical** — avec parcimonie, quand la compacité
est nécessaire et que la lecture horizontale est impossible.

**By Okuden** — sur les supports où la filiation avec
Okuden est pertinente (présentations commerciales, onboarding,
documents partenaires).

---

### Coloris

| Contexte          | Variante à utiliser  |
|-------------------|----------------------|
| Fond clair        | Blue (`#0A1128`)     |
| Fond sombre       | White (`#FFFFFF`)    |
| Contraste minimum | 3:1 dans tous les cas|

---

### Espace de protection

L'espace de protection correspond à la taille du symbole
de chaque côté du logo. Aucun élément ne doit empiéter
sur cette zone.

---

### Taille minimale

| Variante   | Taille minimale |
|------------|-----------------|
| Horizontal | 120px de large  |
| Symbole    | 24px de large   |
| Vertical   | 80px de large   |

---

### Interdits

- Ne jamais déformer ou étirer le logo
- Ne jamais modifier les couleurs hors des variantes définies
- Ne jamais utiliser le logotype sans son symbole
- Ne jamais placer le logo dans un conteneur (rectangle, cercle...)
- Ne jamais ajouter d'ombre portée
- Ne jamais recréer le logo en typographie seule

---

## 7. Iconography & Visual Elements

### Icônes

Bibliothèque : **Material Symbols** (Google)
Style : **Rounded** exclusivement
→ [fonts.google.com/icons](https://fonts.google.com/icons)

| Attribut     | Valeur                         |
|--------------|--------------------------------|
| Style        | Rounded                        |
| Fill         | 1 (filled)                     |
| Weight       | 400                            |
| Grade        | 0                              |
| Optical size | Adapté à la taille d'affichage |

**Tailles**

| Token     | Taille | Usage                         |
|-----------|--------|-------------------------------|
| `icon-xs` | 16px   | Icônes inline, dense UI       |
| `icon-sm` | 20px   | Boutons, champs de formulaire |
| `icon-md` | 24px   | Taille par défaut             |
| `icon-lg` | 32px   | Mise en avant, cards          |
| `icon-xl` | 48px   | Illustrations fonctionnelles  |

> Taille minimale absolue : **14px**. En dessous, la lisibilité
> du style Rounded n'est plus garantie.

**Couleurs**

| Contexte              | Token couleur           |
|-----------------------|-------------------------|
| Icône par défaut      | `color.text.primary`    |
| Icône secondaire      | `color.text.secondary`  |
| Icône interactive     | `color.text.brand`      |
| Icône sur fond sombre | `color.text.inverse`    |
| Icône de statut       | Token sémantique statut |

**Icônes brandées**

Formule : **icône + conteneur symbole Aikoz = icône brandée**
Usage réservé aux supports marketing et onboarding.
Ne pas utiliser dans l'interface applicative courante.

**Interdits**
- Ne jamais utiliser Sharp ou Outlined
- Ne jamais descendre sous 14px
- Ne jamais appliquer l'Aquamarine sur fond clair
- Ne jamais mélanger des styles d'icônes au sein d'un même écran

---

### Halo

Gradient radial expressif, réservé aux assets visuels de marque.

| Attribut | Valeur                      |
|----------|-----------------------------|
| Type     | Radial gradient             |
| Couleur  | `#3B5DCE` (Ultramarine 500) |
| Stop 0%  | `#3B5DCE` à 30% d'opacité  |
| Stop 80% | `#3B5DCE` à 0% d'opacité   |

**Autorisé** : posts LinkedIn, assets visuels, créations marketing
**Interdit** : interfaces applicatives, présentations, documents

Le Halo se place en arrière-plan, centré ou légèrement décalé
pour créer un effet de profondeur. Il ne doit jamais interférer
avec la lisibilité du contenu.

---

### Patterns

Grille de carrés en outline utilisée comme élément décoratif.
Positionnement libre, généralement en coin de composition.

| Contexte    | Couleur du pattern      |
|-------------|-------------------------|
| Fond sombre | Aquamarine — `#70FFD4`  |
| Fond clair  | Ultramarine — `#3B5DCE` |

**Interdits**
- Ne jamais remplir les carrés — outline uniquement
- Ne jamais placer le pattern sur le sujet principal
- Ne jamais utiliser une couleur hors palette

---

### Photographie

Aikoz utilise des images qui transmettent espace,
profondeur et perspective. L'authenticité prime.

**À privilégier**
- Vues aériennes, drone, grand angle
- Architecture épurée, lignes géométriques fortes
- Paysages naturels avec lumière naturelle
- Images porteuses d'une sensation d'échelle et de mouvement

**À éviter**
- Photos de personnes en situation de travail posée
- Stock photos génériques ou artificielles
- Images surchargées, sans espace de respiration
- Couleurs saturées ou traitements HDR excessifs

---

## 8. Voice & Tone

### Personnalité

Aikoz parle comme un expert qui n'a pas besoin de le prouver.
La marque est directe, engageante, légèrement provocatrice —
elle challenge les idées reçues sur la valeur des avis clients
sans jamais tomber dans l'arrogance ou le jargon.

---

### Archétypes

**Creator (70%)** — Aikoz propose, construit, résout.
Le discours est orienté solution et valeur concrète.

**Explorer (30%)** — Aikoz questionne, découvre, révèle.
Le discours ouvre des perspectives nouvelles sur la voix client.

---

### Curseurs de voix

| Dimension    | Position                      |
|--------------|-------------------------------|
| Humour       | Plutôt sérieux (7/10)         |
| Formalité    | Plutôt formel (7/10)          |
| Respect      | Légèrement impertinent (3/10) |
| Enthousiasme | Enthousiaste (3/10)           |

---

### Principes rédactionnels

**Direct et factuel**
On va à l'essentiel. Chaque mot doit gagner sa place.
Pas de phrases creuses, pas de remplissage.

**Confiant sans arrogance**
On affirme, on ne sur-vend pas. Les chiffres et
les faits parlent mieux que les superlatifs.

**Légèrement provocateur**
On challenge les idées reçues. Les avis clients
ne sont pas une contrainte — c'est un levier business.

**Adapté à l'audience**
Même clarté et même exigence pour une direction marketing
et pour un agent de terrain. On ne condescend pas,
on ne simplifie pas à outrance.

---

### Casse et ponctuation

- Respecter la casse naturelle de la langue en toutes circonstances
- Pas de tout-majuscule décoratif
- Préférer les phrases courtes aux constructions complexes
- Éviter les points d'exclamation — l'enthousiasme passe
  par les mots, pas la ponctuation

---

### À éviter

- Le ton trop corporate et lisse
- Les superlatifs vides ("révolutionnaire", "disruptif", "puissant")
- Le jargon IA opaque ("LLM", "embeddings", "vector search"...)
- Les anglicismes inutiles quand le français suffit
- Les formules passives qui diluent le message

---

### Exemples UI

| ❌ À éviter                                           | ✅ Aikoz                                       |
|-------------------------------------------------------|------------------------------------------------|
| "Analysez vos données grâce à notre IA de pointe"    | "Vos clients parlent. Aikoz traduit."          |
| "Tableau de bord analytique"                          | "Ce que vos clients disent vraiment"           |
| "Erreur de chargement des données"                    | "On n'a pas pu charger vos avis. On réessaie." |
| "Notre solution révolutionnaire transforme votre CX" | "+ 60% d'anticipation sur les irritants"       |
| "Veuillez patienter pendant le traitement"           | "On analyse vos avis..."                       |

---

### Selon le support

| Support            | Ton                                        |
|--------------------|--------------------------------------------|
| Interface app      | Concis, fonctionnel, rassurant             |
| Landing page       | Affirmatif, orienté bénéfice, percutant    |
| LinkedIn / réseaux | Direct, légèrement provocateur, engageant  |
| Onboarding         | Chaleureux, guidant, sans sur-expliquer    |
| Emails             | Professionnel, personnalisé, orienté action|
| Erreurs / vides    | Humain, clair, toujours avec une sortie    |

---

## 9. Assets

### Structure du repository

```
aikoz-design/
├── DESIGN.md
├── Logo/
│   ├── Horizontal/
│   │   ├── logo_horizontal_blue.svg
│   │   ├── logo_horizontal_white.svg
│   │   ├── logo_horizontal-by-okuden_blue.svg
│   │   └── logo_horizontal-by-okuden_white.svg
│   ├── Symbol/
│   │   ├── logo_symbol_blue.svg
│   │   └── logo_symbol_white.svg
│   └── Vertical/
│       ├── logo_vertical_blue.svg
│       ├── logo_vertical_white.svg
│       ├── logo_vertical-by-okuden_blue.svg
│       └── logo_vertical-by-okuden_white.svg
└── Design tokens/
    ├── primitives.json
    └── semantics.json
```

---

### Tokens

| Fichier           | Contenu                                                               |
|-------------------|-----------------------------------------------------------------------|
| `primitives.json` | Couleurs brutes, typographie, spacing, radius, shadows, border-width  |
| `semantics.json`  | Tokens sémantiques — couleurs par rôle UI, typographie par usage,     |
|                   | radius et shadows nommés                                              |

> Toujours référencer les tokens sémantiques en production.
> Les primitives sont la source de vérité, pas des valeurs
> à consommer directement.

---

### Formats de logo

Tous les logos sont fournis en **SVG uniquement**.
Pour les exports PNG ou autres formats dérivés,
générer depuis les SVG sources — ne jamais retravailler
un export comme source.

---

### Versionning

Ce fichier suit le versionning du repository.
Toute modification de guidelines doit être accompagnée
d'une mise à jour de `DESIGN.md` dans le même commit.

| Version | Description      |
|---------|------------------|
| 1.0     | Version initiale |

---

### Ressources externes

| Ressource        | Lien                                                      |
|------------------|-----------------------------------------------------------|
| Material Symbols | [fonts.google.com/icons](https://fonts.google.com/icons)  |
| PP Radio Grotesk | Licence commerciale — fichiers non versionnés             |
| Satoshi          | [fontshare.com](https://www.fontshare.com/fonts/satoshi)  |
| Bahnschrift      | Native Microsoft — pas d'installation requise             |
