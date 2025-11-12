# Visualisation de l'incertitude des sources

Présentation pour le **Séminaire de recherche de la faculté d'Histoire d'UniDistance Suisse** (14 novembre 2025)

## 🎯 Sujet

Flux de travail numériques avec modèles de langage (locaux) et Graph RAG - Phase 4 selon Gasser et Sibille

## 📊 Contenu

**15 slides** couvrant :
- Architecture Graph-RAG et Neo4j
- Traçabilité des sources (quote-first : 95,5%)
- Triple incertitude (temporelle, factuelle, provenance)
- Visualisation interactive timeline
- Corpus : 192 documents, 234 événements reconstitués

## 🌐 Voir la présentation

**En ligne :** https://gbottazzoli.github.io/colloque_141125/presentation.html

**Localement :**
```bash
python3 -m http.server 8001
# Ouvrir http://localhost:8001/presentation.html
```

## 🎨 Design

- Framework : Reveal.js 5.0.4
- Design system unifié (variables CSS)
- Responsive optimisé (mobile, tablette, desktop)
- Images optimisées avec transform: scale()

## 📚 Documentation

- `INSTRUCTIONS_TRAVAIL.md` : Méthode de travail et historique
- `DESIGN_SYSTEM.md` : Spécifications design

## 🤖 Développement

Présentation générée par **protoprompting** via [Claude Code](https://claude.com/claude-code)

---

© 2025 Gérard Bottazzoli - UniDistance Suisse
