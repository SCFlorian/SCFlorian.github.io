---
title: Projects completed during my Data Scientist - Machine Learning training
---

---

<div align="center">
  <a href="/en/" class="btn">🏠 Home</a>
  <a href="/en/mind_map" class="btn">🧠 Mind Map</a>
  <a href="/en/projects" class="btn">📁 Projects</a>
  <a href="/en/contact" class="btn">📞 Contact</a>
  <a href="/" class="btn" style="background-color: #f0f0f0 !important; color: #606060 !important; font-weight: bold;">🇫🇷 Version Française</a>
</div>

---

# Projects completed during my "Data Scientist - Machine Learning" training

## **Agricultural recommendation system**

[![GitHub](https://img.shields.io/badge/GitHub-Agricultural_recommendation_system-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Systeme_recommandation_agricole)

[![Model on HF](https://huggingface.co/datasets/huggingface/badges/resolve/main/model-on-hf-md-dark.svg)](https://huggingface.co/FlorianSC/yield-prediction-model)

[![Open in Spaces](https://huggingface.co/datasets/huggingface/badges/resolve/main/open-in-hf-spaces-md-dark.svg)](https://huggingface.co/spaces/FlorianSC/agritech-interface?logs=container)


The aim of this project was to build a simple and intuitive web application to help farmers make better decisions. The application has two functions within a single interface:

- Prediction function: Allows a user to select a specific crop, fill in the conditions of their plot (temperature, pesticide use, etc.), and obtain a numeric estimate of the expected yield.
- Recommendation function: The user only fills in the conditions of their plot, and the application recommends the most profitable crop by simulating yields across all possible crops and displaying a ranking.

  <a href="/assets/pdf/rapport_metier.pdf" class="btn" target="_blank">📄 Business report</a>

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/recommandation.png" target="_blank">
    <img src="/assets/image_projet/recommandation.png" style="width: 100%; cursor: zoom-in;">
  </a>
  <a href="/assets/image_projet/prediction.png" target="_blank">
    <img src="/assets/image_projet/prediction.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Evaluating the performance of an LLM**

[![GitHub](https://img.shields.io/badge/GitHub-LLM_Evaluation-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Evaluation_LLM)

This project implemented a virtual assistant based on a Llama model, using the Retrieval-Augmented Generation (RAG) technique to provide accurate and contextual answers from a custom knowledge base. The objective was to take an existing functional prototype and improve it to obtain better results. The improvements are visible through a comparison of Ragas metrics between the prototype and the new project structure.

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/interfacechat_reponse.png" target="_blank">
    <img src="/assets/image_projet/interfacechat_reponse.png" style="width: 100%; cursor: zoom-in;">
  </a>
  <a href="/assets/image_projet/postman_ask.png" target="_blank">
    <img src="/assets/image_projet/postman_ask.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Deployment of a RAG system**

[![GitHub](https://img.shields.io/badge/GitHub-RAG_System_Deployment-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Deploiement_systeme_RAG)

This project is a Proof of Concept (POC). It is an intelligent chatbot capable of recommending cultural events in Paris (concerts, theater, exhibitions) based on fresh data from the OpenAgenda API.

The system uses a RAG (Retrieval-Augmented Generation) architecture to ensure that responses are factual and based on the provided documents, thus avoiding the hallucinations of standard language models.

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/postman_rag_project.png" target="_blank">
    <img src="/assets/image_projet/postman_rag_project.png" style="width: 100%; cursor: zoom-in;">
  </a>
  <a href="/assets/image_projet/old_rag_system.png" target="_blank">
    <img src="/assets/image_projet/old_rag_system.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Deployment of a scoring model**

[![GitHub](https://img.shields.io/badge/GitHub-Scoring_Model_Deployment-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Deploiement_modele_scoring)

[![Model on HF](https://huggingface.co/datasets/huggingface/badges/resolve/main/model-on-hf-md-dark.svg)](https://huggingface.co/FlorianSC/homecredit-scoring-artifacts)

[![Open in Spaces](https://huggingface.co/datasets/huggingface/badges/resolve/main/open-in-hf-spaces-md-dark.svg)](https://huggingface.co/spaces/FlorianSC/Deploiement_modele_scoring)

In a previous project, we built a scoring model based on the Home Credit Default Risk Kaggle competition. We then took the best model from that project in order to deploy it.

The objectives were the following:

- a version history
- a functional API → FastAPI with a Gradio interface
- automated unit tests
- a Dockerfile
- Data Drift analysis → done with EvidentlyAI
- a dashboard with Streamlit
- a production data storage solution
- a CI/CD pipeline
- README documentation

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/dataset_drift.png" target="_blank">
    <img src="/assets/image_projet/dataset_drift.png" style="width: 100%; cursor: zoom-in;">
  </a>
  <a href="/assets/image_projet/evidentlyai.png" target="_blank">
    <img src="/assets/image_projet/evidentlyai.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Medical image classification**

[![GitHub](https://img.shields.io/badge/GitHub-Semi_supervised_learning-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Apprentissage_semi_supervise)

The goal here was to explore the possibility of automating the detection of brain tumors. A substantial set of X-rays was collected: most of these images were unlabeled, while a limited subset had been annotated by expert radiologists.

The mission was:

- to explore the images and extract visual features using a pre-trained model
- to apply clustering methods to identify structures or groupings in the data
- to implement a semi-supervised learning method using the few available labels
- to summarize the results and provide recommendations

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/cluster_classification.png" target="_blank">
    <img src="/assets/image_projet/cluster_classification.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Scoring model with MLFlow tracking**

[![GitHub](https://img.shields.io/badge/GitHub-Scoring_Model_MLFlow-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Modele_scoring_MLFlow)

The goal of this project was to build a scoring model and track it with MLflow, based on the Home Credit Default Risk Kaggle project.

The challenges:

- Build and optimize a scoring model to provide an automatic prediction of a client's probability of default.
- Analyze the features that contributed the most to the model, both globally (global feature importance) and at the client level (local feature importance), in order to allow an analyst to better understand the score assigned by the model — for transparency.
- Implement a comprehensive end-to-end MLOps approach, from experiment tracking to pre-production deployment.

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/run_mlflow.png" target="_blank">
    <img src="/assets/image_projet/run_mlflow.png" style="width: 100%; cursor: zoom-in;">
  </a>
  <a href="/assets/image_projet/shap_importance.png" target="_blank">
    <img src="/assets/image_projet/shap_importance.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Deployment of a machine learning model**

[![GitHub](https://img.shields.io/badge/GitHub-ML_Model_Deployment-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Deploiement_modele_machine_learning)

[![Open in Spaces](https://huggingface.co/datasets/huggingface/badges/resolve/main/open-in-hf-spaces-md-dark.svg)](https://huggingface.co/spaces/FlorianSC/Deploiement_modele_machine_learning)

This project takes the model developed in "Automatically classify information" and deploys it as a FastAPI API accessible online via Hugging Face Spaces.

The objective was:

- to make the predictive model accessible through a user interface (Gradio)
- to automate testing and deployment with GitHub Actions (CI/CD)
- to log predictions in a database (PostgreSQL or SQLite depending on the environment)

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/bdd.png" target="_blank">
    <img src="/assets/image_projet/bdd.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Automatically classify information**

[![GitHub](https://img.shields.io/badge/GitHub-Automatic_Classification-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Classifiez_automatiquement_des_informations)

The goal of this project was to predict the probability of resignation for employees of the IT services company TechNova Partners. To do so, we explored the HR data, applied several machine learning models and compared their performance to identify the key factors influencing departures.

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/feature_importance.png" target="_blank">
    <img src="/assets/image_projet/feature_importance.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>

---

## **Forecasting building energy consumption**

[![GitHub](https://img.shields.io/badge/GitHub-Building_energy_forecasting-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Anticipez_besoins_consommations_batiments)

The goal of this project was to develop a model that predicts the energy consumption of buildings, based on public data from the city of Seattle (2016).

The work consisted of exploring the data, testing several machine learning models and comparing their performance to identify the factors with the greatest impact on consumption.

<div style="display: flex; gap: 10px;">
  <a href="/assets/image_projet/test_different_model.png" target="_blank">
    <img src="/assets/image_projet/test_different_model.png" style="width: 100%; cursor: zoom-in;">
  </a>
</div>
