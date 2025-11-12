# Design System - Présentation Colloque 2025

## 📐 Audit Design (2025-11-09)

### Problèmes Identifiés

#### ❌ Incohérence typographique
- **Avant** : 10 tailles différentes fragmentées (.5em, .6em, .65em, .7em, .75em, .8em, .85em, .9em, 1em, 1.1em)
- **Après** : 8 tailles standardisées avec variables CSS

#### ❌ Espacement chaotique
- **Avant** : 4 valeurs de max-width (75%, 80%, 85%, 90%)
- **Après** : 3 valeurs standardisées (narrow, standard, wide)

#### ❌ Line-height incohérent
- **Avant** : 6 valeurs (1.2, 1.3, 1.4, 1.5, 1.6, 1.8)
- **Après** : 3 valeurs (headings, body, code)

#### ❌ H3 avec 2 tailles différentes
- **Avant** : 1.3em pour sections normales, 1.5em pour part-dividers
- **Après** : H3 = 1.3em, Part dividers utilisent H2 (1.4em)

### ✅ Ce Qui Fonctionnait Déjà

- Palette de couleurs cohérente (4 couleurs)
- Bordure gauche bleue 4px
- Background gris clair
- Famille de polices Helvetica

---

## Variables CSS Standardisées

### Échelle Typographique

| Variable | Taille | Usage |
|----------|--------|-------|
| `--font-size-h1` | 1.8em | Titres principaux |
| `--font-size-h2` | 1.4em | Sous-titres + Sections principales (Partie 1, 2) |
| `--font-size-h3` | 1.3em | Sections standard |
| `--font-size-h4` | 1em | Sous-sections italiques |
| `--font-size-h5` | 1.1em | Méthodologie / CLI |
| `--font-size-body` | 1em | Texte normal |
| `--font-size-small` | 0.8em | Texte secondaire |
| `--font-size-micro` | 0.6em | Notes/captions/footnotes |

### Espacement Modulaire

| Variable | Taille | Usage |
|----------|--------|-------|
| `--spacing-xs` | 0.5em | Espacement minimal |
| `--spacing-sm` | 1em | Espacement petit |
| `--spacing-md` | 2em | Espacement moyen |
| `--spacing-lg` | 3em | Espacement large |

### Max-Width

| Variable | Taille | Usage |
|----------|--------|-------|
| `--width-narrow` | 75% | Images d'archives |
| `--width-standard` | 85% | Citations, listes, contenus |
| `--width-wide` | 90% | Méthodologie, grilles |

### Line-Height

| Variable | Taille | Usage |
|----------|--------|-------|
| `--line-height-headings` | 1.2 | Tous les titres (H1-H5) |
| `--line-height-body` | 1.6 | Texte normal, citations |
| `--line-height-code` | 1.8 | Code monospace, CLI art |

---

## Classes Réutilisables

### Listes

#### `.structure-list` / `.key-points`
Listes avec bordure bleue et fond gris.

```css
font-size: var(--font-size-small);
line-height: var(--line-height-body);
padding: var(--spacing-sm) var(--spacing-md);
margin-bottom: var(--spacing-sm);
border-left: 4px solid var(--accent-color);
background: var(--light-gray);
```

**Usage** :
- Structure de l'exposé (Slide 3)
- Points clés Partie 1 (Slide 8)

### Citations

#### `.citation-block`
Bloc de citation avec bordure gauche.

```css
font-size: var(--font-size-small);
font-style: italic;
line-height: var(--line-height-body);
padding: var(--spacing-sm) var(--spacing-md);
border-left: 4px solid var(--accent-color);
background: var(--light-gray);
max-width: var(--width-standard);
```

**Usage** :
- Citation allemande (Slide 6)

#### `.source-ref`
Référence de source (micro, gris foncé).

```css
font-size: var(--font-size-micro);
color: var(--dark-gray);
margin-top: var(--spacing-sm);
font-style: normal;
```

**Usage** :
- Source citation Selbstverschuldung (Slide 6)

### Notes

#### `.footnote`
Notes de bas de page (micro, bordure supérieure).

```css
margin-top: var(--spacing-lg);
font-size: var(--font-size-micro);
color: var(--dark-gray);
border-top: 1px solid var(--light-gray);
padding-top: var(--spacing-sm);
max-width: var(--width-wide);
```

**Usage** :
- Toutes les slides avec références bibliographiques

#### `.image-caption`
Légende d'image (micro, alignée gauche).

```css
font-size: var(--font-size-micro);
color: var(--dark-gray);
margin-top: var(--spacing-sm);
line-height: var(--line-height-body);
text-align: left;
```

**Usage** :
- Carte parcours carcéral (Slide 4)

### Méthodologie

#### `.cli-flow`
Code monospace (Courier New, line-height 1.8).

```css
font-family: 'Courier New', monospace;
line-height: var(--line-height-code);
color: var(--main-color);
```

**Usage** :
- Problématiques méthodologiques (Slide 7)

#### `.methodology-grid`
Grille 2 colonnes pour méthodologie.

```css
display: grid;
grid-template-columns: 1fr 1fr;
gap: var(--spacing-lg);
margin: var(--spacing-md) auto;
max-width: var(--width-wide);
position: relative;
```

**Usage** :
- Circularité vs Sources contemporaines (Slide 7)

### Sections

#### `.part-divider`
Section principale (Partie 1, 2) centrée.

```css
text-align: center;
margin-top: var(--spacing-lg);
```

**Usage** :
- Partie 1 : Traçabilité (Slide 8)
- Partie 2 : Triple incertitude (à venir)

---

## Règles pour Futures Slides

### 1. Tailles de Police

❌ **NE JAMAIS** :
```css
font-size: 0.7em;  /* Valeur arbitraire */
```

✅ **TOUJOURS** :
```css
font-size: var(--font-size-small);  /* Ou autre variable */
```

### 2. Espacement

❌ **NE JAMAIS** :
```css
margin-top: 1.5em;  /* Valeur arbitraire */
```

✅ **TOUJOURS** :
```css
margin-top: var(--spacing-md);  /* Ou xs/sm/md/lg */
```

### 3. Max-Width

❌ **NE JAMAIS** :
```css
max-width: 80%;  /* Valeur arbitraire */
```

✅ **TOUJOURS** :
```css
max-width: var(--width-standard);  /* Ou narrow/standard/wide */
```

### 4. Bordures et Backgrounds

✅ **TOUJOURS** utiliser cette combinaison pour les conteneurs :
```css
border-left: 4px solid var(--accent-color);
background: var(--light-gray);
padding: var(--spacing-sm) var(--spacing-md);
```

### 5. Line-Height

✅ **TOUJOURS** utiliser :
- `var(--line-height-headings)` pour titres
- `var(--line-height-body)` pour texte normal
- `var(--line-height-code)` pour code/CLI

---

## Exemple : Créer une Nouvelle Slide

```html
<section>
    <h3>Titre de la Section</h3>

    <ul class="key-points">
        <li>Premier point important</li>
        <li>Deuxième point important</li>
        <li>Troisième point important</li>
    </ul>

    <div class="footnote">
        <sup>4</sup> Référence bibliographique complète ici.
    </div>
</section>
```

**Résultat** :
- H3 automatiquement à 1.3em, centré
- Liste avec bordure bleue, fond gris, padding cohérent
- Footnote à 0.6em, bordure supérieure, espacement cohérent

---

## Checklist Avant Ajout de Nouvelle Slide

- [ ] Utiliser variables CSS pour toutes les tailles (police, espacement, width)
- [ ] Bordure gauche = toujours 4px solid accent
- [ ] Background = toujours light-gray
- [ ] Padding = toujours `var(--spacing-sm) var(--spacing-md)`
- [ ] Line-height = utiliser headings/body/code
- [ ] Vérifier cohérence avec slides existantes

---

*Dernière mise à jour : 2025-11-09 - Audit design complet*
