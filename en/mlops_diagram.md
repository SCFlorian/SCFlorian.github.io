---
title: MLOps skills
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

# MLOps diagram

![MLOps diagram](/assets/schema_mlops.png)

# Related projects

## Agricultural recommendation system

[![GitHub](https://img.shields.io/badge/GitHub-Agricultural_recommendation_system-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Systeme_recommandation_agricole)

[![Model on HF](https://huggingface.co/datasets/huggingface/badges/resolve/main/model-on-hf-md-dark.svg)](https://huggingface.co/FlorianSC/yield-prediction-model)

[![Open in Spaces](https://huggingface.co/datasets/huggingface/badges/resolve/main/open-in-hf-spaces-md-dark.svg)](https://huggingface.co/spaces/FlorianSC/agritech-interface?logs=container)


This project aims to build a simple and intuitive web application to help farmers make better decisions. The application provides two functions within a single interface:

- Prediction function: Allows a user to select a specific crop, fill in the conditions of their plot (temperature, pesticide use, etc.), and obtain a numeric estimate of the expected yield.
- Recommendation function: The user only fills in the conditions of their plot, and the application recommends the most profitable crop by simulating yields across all possible crops and displaying a ranking.

  <a href="/assets/pdf/rapport_metier.pdf" class="btn" target="_blank">📄 Business report</a>

---

## Deployment of a scoring model

[![GitHub](https://img.shields.io/badge/GitHub-Scoring_Model_Deployment-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Deploiement_modele_scoring)

[![Model on HF](https://huggingface.co/datasets/huggingface/badges/resolve/main/model-on-hf-md-dark.svg)](https://huggingface.co/FlorianSC/homecredit-scoring-artifacts)

[![Open in Spaces](https://huggingface.co/datasets/huggingface/badges/resolve/main/open-in-hf-spaces-md-dark.svg)](https://huggingface.co/spaces/FlorianSC/Deploiement_modele_scoring)

In a previous project, we built a scoring model based on the Home Credit Default Risk Kaggle competition. Here we take the best model from that project and deploy it.

The objectives are:

- a version history
- a functional API → FastAPI with a Gradio interface
- automated unit tests
- a Dockerfile
- Data Drift analysis → done with EvidentlyAI
- a dashboard with Streamlit
- a production data storage solution
- a CI/CD pipeline
- README documentation

---

## Scoring model with MLFlow tracking

[![GitHub](https://img.shields.io/badge/GitHub-Scoring_Model_MLFlow-181717?style=flat-square&logo=github)](https://github.com/SCFlorian/Modele_scoring_MLFlow)

The goal of this project is to build a scoring model and track it with MLflow, based on the Home Credit Default Risk Kaggle project.

The challenges:

- Build and optimize a scoring model that automatically predicts the probability of a client defaulting.
- Analyze the features that contribute most to the model, both globally (global feature importance) and at the client level (local feature importance), in order to allow an analyst to better understand the score assigned by the model — for transparency.
- Implement a comprehensive end-to-end MLOps approach, from experiment tracking to pre-production deployment.

---
