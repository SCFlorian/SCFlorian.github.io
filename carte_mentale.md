---
title: Carte conceptuelle
---

<script src="https://cdn.jsdelivr.net/npm/d3@7"></script>
<script src="https://cdn.jsdelivr.net/npm/markmap-view@0.18.10"></script>
<script src="https://cdn.jsdelivr.net/npm/markmap-toolbar@0.18.10"></script>
<script src="https://cdn.jsdelivr.net/npm/markmap-autoloader@0.18.10"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/markmap-toolbar@0.18.10/dist/style.css">

<style>
.markmap-wrapper {
  position: relative;
  width: 100%;
  height: 800px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background: #fafafa;
  margin: 20px 0;
}

.markmap-wrapper .markmap,
.markmap-wrapper .markmap > svg {
  width: 100%;
  height: 100%;
}

.mm-toolbar {
  position: absolute;
  bottom: 20px;
  right: 20px;
  z-index: 100;
}
</style>

---

<div align="center">
  <a href="/" class="btn">🏠 Accueil</a>
  <a href="/systeme_recommandation" class="btn">⚙️ Projet technique</a>
  <a href="/carte_mentale" class="btn">🧠 Carte conceptuelle</a>
  <a href="/formation_projet" class="btn">📁 Projets réalisés</a>
  <a href="/contact" class="btn">📞 Contact</a>
</div>

---

# Carte conceptuelle interactive

Cette carte synthétise mes compétences techniques et mon parcours. **Utilisez les boutons en bas à droite** pour zoomer ou recentrer la carte. Cliquez sur les nœuds pour plier/déplier les branches, et sur les liens en bleu pour accéder aux projets.

<div class="markmap-wrapper">
<div class="markmap">
<script type="text/template">
---
markmap:
  colorFreezeLevel: 2
  initialExpandLevel: 3
  maxWidth: 300
---

# Florian SCHORER

## 🤝 Soft skills
- Esprit d'analyse
- Curiosité
- Travail en équipe
- Adaptabilité
- Gestion de projet
- Créativité
- Rigueur, détail

## 🔍 Analyse exploratoire
- **Stack**
  - Pandas, NumPy
  - Matplotlib, Seaborn
- **Compétences**
  - Nettoyage des données
  - Détection d'outliers
  - Analyse statistique
- **Projet**
  - [AgriTech - EDA](/systeme_recommandation)

## 🧠 Modélisation supervisée
- **Stack**
  - scikit-learn
  - XGBoost, LightGBM
- **Compétences**
  - Pipelines ML
  - Classification & régression
  - Validation croisée
- **Projet**
  - [Système de recommandation](/systeme_recommandation)

## 🖼️ Deep Learning
- **Stack**
  - TensorFlow, Keras
- **Compétences**
  - CNN
  - Transfer Learning
  - Apprentissage semi-supervisé
- **Projet**
  - [Classification médicale](https://github.com/SCFlorian/Apprentissage_semi_supervise)

## 🤖 IA générative & RAG
- **Stack**
  - LangChain, FAISS
  - RAGAS
- **Compétences**
  - Embeddings
  - Évaluation RAG
  - Agents SQL
- **Projet**
  - [Système RAG hybride](/systeme_recommandation)

## 🚀 MLOps & déploiement
- **Stack**
  - MLflow, Docker
  - FastAPI, GitHub Actions
  - Hugging Face Spaces
- **Compétences**
  - Tracking d'expériences
  - Conteneurisation
  - APIs REST
  - CI/CD
- **Projet**
  - [Déploiement HF](https://huggingface.co/FLORIANSC)

## 🗄️ Bases de données
- **Stack**
  - PostgreSQL, SQL
- **Compétences**
  - Requêtes complexes
  - Modélisation relationnelle
- **Projet**
  - [Agent SQL](/systeme_recommandation)
</script>
  </div>
</div>

<style>
/* FORCE LE HEADER : Nom en haut, Description dessous */
.page-header {
    display: flex !important;
    flex-direction: column !important;
    justify-content: center !important;
    align-items: center !important;
    padding: 2rem !important;
}
.project-name { font-size: 2.5rem !important; margin-bottom: 0.5rem !important; display: block !important; }
.project-tagline { font-size: 1.2rem !important; opacity: 0.9 !important; display: block !important; }

/* QUALITÉ IMAGE PROFIL */
.page-header img, img[alt*="Florian"] {
    image-rendering: -webkit-optimize-contrast !important;
    image-rendering: crisp-edges !important;
}

/* TOOLBAR INTERACTIVE */
.mm-toolbar {
    position: absolute !important;
    bottom: 20px !important;
    right: 20px !important;
    z-index: 999 !important;
    background: white !important;
    border: 1px solid #d1d5db !important;
    border-radius: 6px !important;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15) !important;
}
</style>

<script>
(function() {
    function tryInitToolbar() {
        const { markmap } = window;
        const svg = document.querySelector('.markmap svg');
        
        // On vérifie si Markmap est prêt et si le SVG a été généré
        if (markmap && svg && svg.__markmap__) {
            if (!document.querySelector('.mm-toolbar')) {
                const mm = svg.__markmap__;
                const toolbar = new markmap.Toolbar();
                toolbar.attach(mm);
                const el = toolbar.render();
                el.classList.add('mm-toolbar');
                document.querySelector('.markmap-wrapper').appendChild(el);
                console.log("Toolbar Markmap installée avec succès");
            }
        } else {
            // Si pas encore prêt, on réessaie toutes les 250ms
            setTimeout(tryInitToolbar, 250);
        }
    }
    // Lancement du script
    if (document.readyState === 'complete') { tryInitToolbar(); }
    else { window.addEventListener('load', tryInitToolbar); }
})();
</script>