---
title: Réalisation de ces projets dans la cadre de la formation Data Scientist-Machine Learning
---

---

<div align="center">
  <a href="/" class="btn">🏠 Accueil</a>
  <a href="/systeme_recommandation" class="btn">⚙️ Projet technique</a>
  <a href="/carte_mentale" class="btn">🧠 Carte conceptuelle</a>
  <a href="/formation_projet" class="btn">📁 Projets réalisés</a>
  <a href="/cv" class="btn">📄 CV</a>
  <a href="/contact" class="btn">📞 Contact</a>
</div>

---

## Système de recommandation agricole 

- [![GitHub - Système recommandation agricole](https://img.shields.io/badge/-GitHub-181717?style=for-the-badge&logo=github)](https://github.com/SCFlorian/Systeme_recommandation_agricole)

[![GitHub - Système recommandation agricole](https://img.shields.io/badge/GitHub-Code-24292e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SCFlorian/Systeme_recommandation_agricole)

[![GitHub - Système recommandation agricole](https://img.shields.io/badge/GitHub-Code_source-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Systeme_recommandation_agricole)

Ce projet a pour but de réaliser une application web simple et intuitive pour aider les agriculteurs à prendre de meilleurs décisions. L'application aura deux fonctions au sein de la même interface :

- Fonction de prédiction : Permettre à un utilisateur de sélectionner une culture spécifique, de renseigner les conditions de sa parcelle (température, usage de pesticides, etc.) et d'obtenir une estimation chiffrée du rendement attendu.
- Fonction de recommandation : L'utilisateur renseigne uniquement les conditions de sa parcelle, et l'application lui recommande la culture la plus rentable en simulant le rendement pour toutes les cultures possibles et en affichant un classement.

  <a href="/rapport_metier.pdf" class="btn" target="_blank">📄 Rapport métier</a>

---

## Évaluez les performances d'un LLM

- [Evaluation LLM](https://github.com/SCFlorian/Evaluation_LLM)

Ce projet implémente un assistant virtuel basé sur un modèle Llama, utilisant la technique de Retrieval-Augmented Generation (RAG) pour fournir des réponses précises et contextuelles à partir d'une base de connaissances personnalisée. L'objectif est de reprendre un prototype réalisé qui était fonctionnel et de procéder à des améliorations afin d'obtenir de meilleurs résultats. Les améliorations seront visibles avec une comparaison des métriques Ragas sur le prototype vs la nouvelle structure du projet.

---

## Déploiement d'un système RAG

- [Déploiement d'un système RAG](https://github.com/SCFlorian/Deploiement_systeme_RAG)

Ce projet est une Preuve de Concept (POC). Il s'agit d'un chatbot intelligent capable de recommander des événements culturels à Paris (concerts, théâtres, expositions) en se basant sur des données fraîches via l'API OpenAgenda.

Le système utilise une architecture RAG (Retrieval-Augmented Generation) pour garantir que les réponses sont factuelles et basées sur les documents fournis, évitant ainsi les hallucinations des modèles de langage classiques.

---

## Déploiement d'un modèle de scoring

- [Déploiement modèle scoring](https://github.com/SCFlorian/Deploiement_modele_scoring)

Précédemment nous avons réalisé un modèle de scoring en partant du projet Home Credit Default Risk de Kaggle. Nous allons reprendre le meilleur modèle de ce projet afin de le déployer.

Les objectifs sont les suivants :

- un historique des versions
- une API fonctionnelle -> FastAPI avec une interface réalisée avec Gradio
- des tests unintaires automatisés
- un dockerfile
- une analyse du Data Drift -> Réalisée avec EvidentlyAI
- un dashboard avec Streamlit
- une solution de stockage des données en production
- un pipeline CI/CD
- une documentation README

---

## Classification d'images médicale

- [Apprentissage semi-supervisé](https://github.com/SCFlorian/Apprentissage_semi_supervise)

L'objectif ici est d'explorer la possibilité d'automatiser la détection de tumeurs au cerveau. Un ensemble conséquent de radios a été collecté : la majorité de ces images ne dispose d’aucun étiquetage, tandis qu’un sous-ensemble limité a été annoté par des radiologues experts.

La mission est :

- d'explorer les images et extraire des caractéristiques visuelles via un modèle pré-entraîné
- d'appliquer des méthodes de clustering pour identifier des structures ou regroupements dans les données
- de mettre en œuvre une méthode d’apprentissage semi-supervisé à partir des quelques étiquettes disponibles
- de synthétiser vos résultats, formuler des recommandations

---

## Modèle de scoring avec suivi MLFlow

- [Modèle scoring MLFlow](https://github.com/SCFlorian/Modele_scoring_MLFlow)

L'objectif de ce projet est de réaliser un modèle de scoring et un suivi sur MlFlow à partir du projet Home Credit Default Risk sur Kaggle.

La problématique :

- Construire et optimiser un modèle de scoring qui donnera une prédiction sur la probabilité de faillite d'un client de façon automatique.
- Analyser les features qui contribuent le plus au modèle, d’une manière générale (feature importance globale) et au niveau d’un client (feature importance locale), afin, dans un soucis de transparence, de permettre à un chargé d’études de mieux comprendre le score attribué par le modèle.
- Mettre en œuvre une approche globale MLOps de bout en bout, du tracking des expérimentations à la pré-production du modèle.

---

## Déploiement d'un modèle de machine learning

- [Déploiement modèle machine learning](https://github.com/SCFlorian/Deploiement_modele_machine_learning)

Ce projet reprend le modèle développé dans « Classifiez automatiquement des informations » et le déploie sous la forme d’une API FastAPI accessible en ligne via Hugging Face Spaces.

L’objectif :

- rendre le modèle prédictif accessible via une interface utilisateur (Gradio)
- automatiser les tests et le déploiement grâce à GitHub Actions (CI/CD)
- journaliser les prédictions dans une base de données (PostgreSQL ou SQLite selon l’environnement)

---

## Classifiez automatiquement des informations

- [Classifiez automatiquement des informations](https://github.com/SCFlorian/Classifiez_automatiquement_des_informations)

L’objectif de ce projet est de prédire la probabilité de démission des employés de l’ESN TechNova Partners. Pour cela, nous explorons les données RH, appliquons plusieurs modèles de machine learning et comparons leurs performances afin d’identifier les facteurs clés influençant les départs.

---

## Anticipez les besoins en consommation des bâtiments

- [Anticipez besoins consommations bâtiments](https://github.com/SCFlorian/Anticipez_besoins_consommations_batiments)

L’objectif de ce projet est de développer un modèle de prédiction de la consommation énergétique des bâtiments à partir de données publiques de la ville de Seattle (2016).

Le travail consiste à explorer les données, tester plusieurs modèles de machine learning et comparer leurs performances afin d’identifier les facteurs ayant le plus d’impact sur la consommation.



