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

## 🔍 EDA
- **Stack**
  - Pandas, NumPy
  - Matplotlib, Seaborn
- **Compétences**
  - Nettoyage des données
  - Détection d'outliers
  - Analyse statistique
  - Visualisation
- **Projet**
  - [AgriTech - EDA](/systeme_recommandation)

## 🗄️ Bases de données
- **Stack**
  - PostgreSQL, SQL
  - SQLite
- **Compétences**
  - Requêtes complexes
  - Modélisation relationnelle
  - Optimisation
- **Projet**
  - [Agent SQL](/systeme_recommandation)

## 🚀 MLOps
- **Stack**
  - MLflow, Docker
  - FastAPI, GitHub Actions
  - Hugging Face Spaces
- **Compétences**
  - Tracking d'expériences
  - Conteneurisation
  - APIs REST avec Swagger
  - CI/CD
- **Projet**
  - [Déploiement HF](https://huggingface.co/FLORIANSC)

## 🤖 GenAI / RAG
- **Stack**
  - LangChain, FAISS
  - RAGAS
- **Compétences**
  - Embeddings
  - Évaluation RAG
  - Agents SQL
- **Projet**
  - [Système RAG hybride](/systeme_recommandation)
</script>
</div>
</div>

<script>
(function() {
  function tryAttachToolbar() {
    var wrapper = document.querySelector('.markmap-wrapper');
    var svg = wrapper ? wrapper.querySelector('svg') : null;
    
    if (!wrapper || !svg || !window.markmap || !window.markmap.Toolbar) {
      setTimeout(tryAttachToolbar, 500);
      return;
    }
    
    if (wrapper.querySelector('.mm-toolbar')) {
      return;
    }
    
    try {
      var mm = svg.__markmap__ || (svg.__data__ && svg.__data__.markmap);
      if (!mm) {
        setTimeout(tryAttachToolbar, 500);
        return;
      }
      
      var toolbar = new window.markmap.Toolbar();
      toolbar.attach(mm);
      var el = toolbar.render();
      el.classList.add('mm-toolbar');
      wrapper.appendChild(el);
    } catch (e) {
      console.error('Toolbar error:', e);
    }
  }
  
  if (document.readyState === 'complete') {
    setTimeout(tryAttachToolbar, 1000);
  } else {
    window.addEventListener('load', function() {
      setTimeout(tryAttachToolbar, 1000);
    });
  }
})();
</script>

---

## 📥 Version statique (PNG)

<a href="/assets/carte_mentale.png" target="_blank">
  <img src="/assets/carte_mentale.png" 
       alt="Carte mentale des compétences" 
       style="width: 100%; height: auto; cursor: zoom-in; border: 1px solid #ddd; border-radius: 8px;">
</a>