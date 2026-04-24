---
title: Formation
---

---

<div align="center">
  <a href="/" class="btn">🏠 Accueil</a>
  <a href="/carte_mentale" class="btn">🔙 Précédent</a>
  <a href="/details_carte/competences" class="btn">🎯 Compétences</a>
  <a href="/details_carte/experiences" class="btn">👔 Expériences passées</a>
  <a href="/details_carte/formation" class="btn">🎒 Formation</a>
  <a href="/details_carte/reflexion" class="btn">🤔 Réflexion</a>
    <a href="/details_carte/soft_skills" class="btn">🤝 Mes soft skills</a>
</div>

---

# Formation Data Scientist - Machine Learning

La formation Data Scientist - Machine Learning dispensée par **OpenClassrooms** couvre l'ensemble du cycle de vie d'un projet de data science, depuis la collecte et l'analyse des données jusqu'au déploiement des modèles en production. Cette page détaille les compétences techniques acquises, illustrées par les projets concrets menés tout au long du parcours.

## 🔍 Analyse des données

Toute démarche de modélisation commence par une compréhension fine des données. J'ai appris à explorer, nettoyer et préparer les jeux de données de façon rigoureuse avant toute tentative de modélisation.

- **Gestion des valeurs manquantes**
  - Détection des patterns de valeurs manquantes
  - Stratégies d'imputation : moyenne, médiane, mode, modèles d'imputation
  - Choix raisonné entre imputation et suppression selon le contexte métier

- **Gestion des NaN et des anomalies**
  - Identification des outliers via boxplots, IQR, z-score
  - Décision de traitement selon leur signification métier
  - Validation croisée des hypothèses avec les parties prenantes

- **Analyse de la distribution des variables**
  - Statistiques descriptives (moyenne, médiane, écart-type, asymétrie, kurtosis)
  - Visualisation via histogrammes, densités
  - Transformations (log, Box-Cox) pour normaliser les distributions

- **Analyse des corrélations**
  - Matrices de corrélation (Pearson, Spearman)
  - Analyse de l'importance des variables vis-à-vis de la cible

## 🧠 Modélisation

La modélisation consiste à transformer des données en modèles prédictifs capables d'éclairer la décision ou d'automatiser un processus.

### Création de pipelines ML

Construction de pipelines reproductibles avec `scikit-learn` (preprocessing + modèle) pour garantir la cohérence entre l'entraînement et la production.

### Apprentissage supervisé

- **Modèles de classification** — prédiction de catégories (défaut de crédit, maladie, satisfaction client)
- **Modèles de régression** — prédiction de valeurs continues (rendement, prix, délai)
- **Algorithmes maîtrisés** : régression linéaire/logistique, Random Forest, XGBoost, LightGBM
- **Bonnes pratiques** : validation croisée, tuning d'hyperparamètres (GridSearch), métriques adaptées au déséquilibre de classes

### Apprentissage semi-supervisé

- Utilisation pertinente quand les données labellisées sont rares et coûteuses à produire
- **Projet réalisé** : classification d'images médicales avec approche semi-supervisée
- Techniques de pseudo-labelling

### Deep Learning

- Conception de réseaux de neurones basiques
- Réseaux convolutifs (CNN) pour la vision par ordinateur
- **Application concrète** : classification d'images médicales — détection automatisée à partir de bases d'images annotées

### Systèmes RAG (Retrieval-Augmented Generation)

Les RAG combinent recherche vectorielle et génération par LLM pour produire des réponses contextualisées et fiables.

- **Mise en place d'un système RAG complet** avec LangChain, embeddings et base vectorielle
- **Évaluation des performances** avec la librairie RAGAS (fidélité, pertinence, rappel)
- **Création d'un agent SQL** capable d'interpréter une question en langage naturel et de générer la requête SQL correspondante

## 🚀 Déploiement

Un modèle qui n'est pas déployé ne produit aucune valeur. Cette phase m'a permis de passer de l'expérimentation en notebook à la mise en production réelle.

### Mise en place d'API

- **FastAPI** — framework Python moderne pour exposer des modèles en tant qu'API REST
- **Documentation automatique via Swagger** — interface interactive de test des endpoints
- **Tests avec Postman** — validation des requêtes et des réponses, gestion des cas d'erreur

### Déploiement sur Hugging Face

- **HF Spaces** — plusieurs projets déployés avec interface utilisateur (Gradio, Streamlit)
- **HF Models** — modèles ML publiés et versionnés, accessibles publiquement
- Intégration continue via GitHub et HF pour automatiser les mises à jour

### Conteneurisation Docker

- Création de **Dockerfiles** pour encapsuler les dépendances et garantir la reproductibilité
- Construction d'images Docker pour le déploiement sur différents environnements
- Bonnes pratiques : images légères, sécurité, versioning

## 📋 Gestion de projet

La réussite d'un projet de data science ne repose pas uniquement sur la technique, mais sur la capacité à piloter l'ensemble de la démarche.

- **Cadrage du besoin métier** — compréhension des enjeux, définition des objectifs mesurables
- **Prototypage** — POC rapide pour valider la faisabilité avant d'investir
- **Industrialisation** — passage du prototype à une solution robuste, maintenable et déployée
- **Présentation et communication** — restitution des résultats à des interlocuteurs techniques et non techniques
