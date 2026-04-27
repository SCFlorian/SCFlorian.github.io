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
  const initToolbar = () => {
    const { markmap, mm } = window;
    const wrapper = document.querySelector('.markmap-wrapper');
    const svg = wrapper ? wrapper.querySelector('svg') : null;

    // 1. Vérifier si les librairies sont chargées
    if (!markmap || !markmap.Toolbar || !markmap.Markmap) return;

    // 2. Récupérer ou créer l'instance Markmap
    let mmInstance;
    if (svg && svg.__markmap__) {
      mmInstance = svg.__markmap__;
    } else if (svg) {
      // Si l'autoloader n'a pas encore lié l'instance, on peut essayer de la récupérer via les données D3
      mmInstance = mm.Markmap.get(svg);
    }

    // 3. Si l'instance existe et qu'il n'y a pas déjà de toolbar
    if (mmInstance && !wrapper.querySelector('.mm-toolbar')) {
      const toolbar = new markmap.Toolbar();
      toolbar.attach(mmInstance);
      const el = toolbar.render();
      el.classList.add('mm-toolbar');
      wrapper.appendChild(el);
      console.log("Toolbar attachée avec succès !");
    } else {
      // Réessayer si pas encore prêt
      setTimeout(initToolbar, 500);
    }
  };

  // Lancer après un court délai pour laisser l'autoloader travailler
  setTimeout(initToolbar, 800);
})();
</script>

---

## 📥 Version statique (PNG)

<a href="/assets/carte_mentale.png" target="_blank">
  <img src="/assets/carte_mentale.png" 
       alt="Carte mentale des compétences" 
       style="width: 100%; height: auto; cursor: zoom-in; border: 1px solid #ddd; border-radius: 8px;">
</a>