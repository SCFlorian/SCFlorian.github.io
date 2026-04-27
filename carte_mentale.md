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

<script>
(function() {
    const addToolbar = () => {
        // On cherche l'instance Markmap créée par l'autoloader
        const svg = document.querySelector('.markmap-wrapper svg');
        const { markmap } = window;

        if (svg && svg.__markmap__ && markmap && markmap.Toolbar) {
            // Si la toolbar existe déjà, on ne fait rien
            if (document.querySelector('.mm-toolbar')) return;

            try {
                const mmInstance = svg.__markmap__;
                const toolbar = new markmap.Toolbar();
                toolbar.attach(mmInstance);
                const el = toolbar.render();
                el.classList.add('mm-toolbar');
                document.querySelector('.markmap-wrapper').appendChild(el);
                console.log("Toolbar activée !");
            } catch (e) {
                console.error("Erreur toolbar:", e);
            }
        } else {
            // Si pas encore prêt, on réessaie toutes les 200ms
            setTimeout(addToolbar, 200);
        }
    };

    // On lance la détection
    addToolbar();
})();
</script>

---

## 📥 Version statique (PNG)

<a href="/assets/carte_mentale.png" target="_blank">
  <img src="/assets/carte_mentale.png" 
       alt="Carte mentale des compétences" 
       style="width: 100%; height: auto; cursor: zoom-in; border: 1px solid #ddd; border-radius: 8px;">
</a>