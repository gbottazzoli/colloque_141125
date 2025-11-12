# Instructions de travail - Présentation colloque recherche

## Méthode de travail établie

### Principes fondamentaux
1. **Approche itérative** : Construction pas à pas, slide par slide
2. **Rôle de l'assistant** : Assister, PAS faire à la place de l'utilisateur
3. **Challenges requis** : L'assistant DOIT challenger le contenu pour garantir la rigueur académique
4. **Validation utilisateur** : Chaque modification nécessite validation avant de continuer

### Workflow établi
1. Utilisateur fournit le contenu (texte oral + structure souhaitée)
2. Assistant challenge sur :
   - Références bibliographiques (exactitude, complétude)
   - Terminologie (définitions, citations)
   - Cohérence académique
   - Positionnement méthodologique
3. Discussion/ajustements
4. Implémentation de la slide
5. Test visuel (serveur http://localhost:8001/presentation.html)
6. Corrections itératives
7. Validation → slide suivante

### Standards de qualité académique
- **Références bibliographiques complètes** en notes de bas de page
- **Citations exactes** avec sources précises
- **Terminologie rigoureuse** ("selon X" plutôt que parenthèses vagues)
- **Hiérarchie visuelle claire** (titres, sous-titres, notes)
- **Style sobre et professionnel** (typographie sans-serif, couleurs neutres)

## Spécifications techniques

### Style visuel
- **Typographie** : Helvetica Neue, sans-serif
- **Couleurs** :
  - Principal : #2c3e50 (bleu-gris foncé)
  - Accent : #3498db (bleu)
  - Gris clair : #ecf0f1
  - Gris foncé : #7f8c8d
- **Approche** : Minimaliste, épuré, "less is more"
- **Cohérence** : Style aligné avec la timeline interactive existante

### 📐 DESIGN SYSTEM UNIFIÉ (établi le 2025-11-09)

#### Variables CSS Standardisées

**Échelle Typographique**
```css
--font-size-h1: 1.8em    /* Titres principaux */
--font-size-h2: 1.4em    /* Sous-titres + Sections principales (Partie 1, 2) */
--font-size-h3: 1.3em    /* Sections standard */
--font-size-h4: 1em      /* Sous-sections italiques */
--font-size-h5: 1.1em    /* Méthodologie / CLI */
--font-size-body: 1em    /* Texte normal */
--font-size-small: 0.8em /* Texte secondaire */
--font-size-micro: 0.6em /* Notes/captions/footnotes */
```

**Espacement Modulaire**
```css
--spacing-xs: 0.5em
--spacing-sm: 1em
--spacing-md: 2em
--spacing-lg: 3em
```

**Max-Width**
```css
--width-narrow: 75%    /* Images d'archives */
--width-standard: 85%  /* Citations, listes, contenus */
--width-wide: 90%      /* Méthodologie, grilles */
```

**Line-Height**
```css
--line-height-headings: 1.2
--line-height-body: 1.6
--line-height-code: 1.8
```

#### Règles pour Futures Slides

1. **Texte secondaire** : Toujours `var(--font-size-small)` (0.8em)
2. **Notes/captions/footnotes** : Toujours `var(--font-size-micro)` (0.6em)
3. **Espacement** : Utiliser xs/sm/md/lg (0.5em/1em/2em/3em)
4. **Max-width** : narrow/standard/wide (75%/85%/90%)
5. **Line-height** : headings (1.2) / body (1.6) / code (1.8)
6. **Bordure gauche** : Toujours `4px solid var(--accent-color)`
7. **Background** : Toujours `var(--light-gray)`
8. **Padding** : Toujours `var(--spacing-sm) var(--spacing-md)` = 1em 2em

#### Classes Réutilisables

- `.structure-list` / `.key-points` : Listes avec bordure bleue et fond gris
- `.citation-block` : Bloc de citation avec bordure gauche
- `.source-ref` : Référence de source (micro, gris foncé)
- `.footnote` : Notes de bas de page (micro, bordure supérieure)
- `.image-caption` : Légende d'image (micro, alignée gauche)
- `.cli-flow` : Code monospace (Courier New, line-height 1.8)
- `.methodology-grid` : Grille 2 colonnes pour méthodologie
- `.part-divider` : Section principale (Partie 1, 2) centrée

### Architecture technique
- **Fichier unique** : `presentation.html` (autonome, tout via CDN)
- **Framework** : Reveal.js 5.0.4
- **Prêt pour GitHub Pages** : Pas de build step nécessaire
- **Serveur local** : `python3 -m http.server 8001` dans le dossier

### Fonctionnalités implémentées
- Navigation clavier (flèches)
- Notes de bas de page avec références
- Style des exposants (sup) en bleu
- Centrage pour slide de titre
- Alignement gauche pour slides de contenu
- Design system cohérent avec variables CSS

## État actuel du projet

### Slides complétées
1. ✅ **Slide 1 - Titre**
   - Titre : "Visualisation de l'incertitude des sources"
   - Sous-titre : Phase 4 selon Gasser et Sybille
   - Note de bas de page : Référence Kluttig (2025)
   - Affiliations : Gérard Bottazzoli, UniDistance Suisse

2. ✅ **Slide 2 - Citation Pollin**
   - Citation sur l'incertitude historique (5 manifestations)
   - Auto-advancing fragments (1 sec)
   - Référence bibliographique complète

3. ✅ **Slide 3 - Structure de l'exposé**
   - Partie 1 : Traçabilité des sources et stratégie "quote-first"
   - Partie 2 : Visualisation de la triple incertitude

4. ✅ **Slide 4 - Carte parcours carcéral**
   - Contextualisation historique (1)
   - Image : Carte Grand Reich 1944 avec prisons
   - Caption détaillée avec sources

5. ✅ **Slide 5 - Commission KNV**
   - Contextualisation historique (2)
   - Image dossier archives Müller
   - Référence AFS complète

6. ✅ **Slide 6 - Citation Selbstverschuldung**
   - Contextualisation historique (3)
   - Citation allemande avec traduction conceptuelle
   - Référence Altermatt & Späti (2006)

7. ✅ **Slide 7 - Problématiques méthodologiques**
   - Grille 2 colonnes : Circularité / Sources contemporaines
   - Style CLI art (monospace)
   - Flèche SVG pointillée
   - Légende explicative

8. ✅ **Slide 8 - Partie 1 : Traçabilité et quote-first**
   - Section divider
   - 3 points clés : Architecture Neo4j / Quote-First 95,5% / Traçabilité complète

### Slides à créer
9. ⏳ Détails architecture Neo4j "Assertion-First"
10. ⏳ Visualisation chaîne Document → Assertion → Événement
11. ⏳ Partie 2 : Triple incertitude (divider)
12. ⏳ Timeline interactive (iframe)
13. ⏳ Résultats et découvertes
14. ⏳ Conclusion et perspectives

## Références bibliographiques à intégrer

### Déjà validées
- **Kluttig, Thekla** (2025). "KI im Archiv". Eindrücke vom 29. Archivwissenschaftlichen Kolloquium in Marburg. *SAXARCHIV-Blog*, 9 juin 2025. https://doi.org/10.58079/142qt
  - Contexte : Gasser & Sybille - 4 phases (transformation → enrichissement → interprétation → génération)

### À valider/compléter
- **Christopher Pollin** - Citation sur "incertitude comme propriété inhérente de l'information historique"
  - ⚠️ Référence exacte à confirmer
  - Triple incertitude : temporelle, spatiale, factuelle (adaptation ou modèle original ?)

- **Altermatt, Späti** (2006, pp. 542-558) - "Selbstverschuldung"
  - ⚠️ Titre complet à ajouter

### Terminologie à définir
- **Protoprompting** : Prompts itératifs pour générer code de visualisation (néologisme ?)
- **Graph RAG** : Retrieval-Augmented Generation basé sur graphe de connaissances

## Éléments techniques à prévoir

### Timeline interactive
- **URL** : https://gbottazzoli.github.io/timeline_visualization_public/
- **Intégration** : iframe dans les slides (slide 7)
- **⚠️ Plan B nécessaire** : Version offline si problème connexion au colloque

### Données du projet
- **Corpus** : 192 documents (cote principale + 20 autres cotes + 2 sources externes)
- **Architecture Neo4j** : 3,117 nœuds, 12,296 relations
- **Couverture Quote-First** : 95.5%
- **Événements timeline** : T1 (10), T2 (70), T3 (152)

## Commandes utiles

### Démarrer le serveur de présentation
```bash
cd /home/steeven/PycharmProjects/test_recherche/presentation_colloque_recherche
python3 -m http.server 8001
```
Puis ouvrir : http://localhost:8001/presentation.html

### Reprendre le travail dans un nouveau chat
```
Je reprends le travail sur ma présentation reveal.js pour le colloque de recherche.

Contexte :
- Dossier : /home/steeven/PycharmProjects/test_recherche/presentation_colloque_recherche
- Fichier : presentation.html
- Instructions de travail : Lis le fichier INSTRUCTIONS_TRAVAIL.md pour comprendre notre méthode

Lis d'abord les instructions, puis dis-moi où nous en sommes et propose-moi de continuer.
```

### Tuer le serveur si nécessaire
```bash
# Trouver le PID
lsof -ti:8001
# Tuer le processus
kill $(lsof -ti:8001)
```

## Notes de session

### Session 1 - 2025-11-09 (Matin)
- ✅ Création dossier `presentation_colloque_recherche/`
- ✅ Premier fichier HTML reveal.js
- ✅ Slide 1 (titre) créée et validée
- ✅ Correction note de bas de page (positionnement)
- ✅ Validation référence Kluttig (2025)

### Session 2 - 2025-11-09 (Continuation)
- ✅ Slides 2-8 créées et validées
- ✅ Citation Pollin avec auto-advancing
- ✅ Carte parcours carcéral
- ✅ Contextualisation historique Commission KNV
- ✅ Problématiques méthodologiques (CLI art + SVG arrow)
- ✅ Requêtes Neo4j pour parcours filtré
- ✅ **AUDIT DESIGN COMPLET** : Unification CSS
  - Variables CSS standardisées
  - Échelle typographique cohérente
  - Espacement modulaire
  - Classes réutilisables documentées
- 🎯 Prochaine étape : Slide 9 (Détails architecture Neo4j)

## Public cible et focus

### Public
- **Type** : Mixte (historiens + digital humanities + informaticiens)
- **Niveau** : Académique (colloque recherche)

### Focus principal
1. **Démonstration live** : Timeline interactive intégrée
2. **Outils et reproductibilité** : Framework réutilisable
3. **Découvertes historiques** : Résultats sur Elisabeth Müller
4. **Triple incertitude** : Modèle selon Pollin

### Objectif
Montrer comment la méthode Graph-RAG conduit à des ébauches de nouveaux résultats de recherche
⚠️ Préciser que "la visualisation n'est que partielle encore"

---

*Dernière mise à jour : 2025-11-09*
