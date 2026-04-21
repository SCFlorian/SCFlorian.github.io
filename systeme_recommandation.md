---
title: systeme_recommandation
---

[🏠 Accueil](/) | [🎯 systeme_recommandation](/systeme_recommandation)

# Rapport de conduite de projet Data & ML

## Contexte et analyse des besoins

1. [Présentation](#présentation)
2. [Collecte et analyse du besoin métier](#collecte-et-analyse-du-besoin-métier)

### Présentation

**SportSee** est une entreprise évoluant dans le secteur de la data sportive, spécialisée dans la production et la valorisation de contenus et de statistiques autour du Basketball. L'entreprise s'adresse à la fois aux amateurs de basketball (contenus éditoriaux, forums) et aux clients professionnels (médias, applications de fantasy sports, parieurs, analystes).

- Secteur d'activité : data sportive — édition de contenu et fourniture de statistiques de Basketball.
- Taille estimée : PME en phase de croissance, avec une équipe produit/data restreinte.
- Enjeux stratégiques liés à la donnée : la donnée est le cœur de métier de SportSee. La valeur produite dépend directement de la capacité à croiser des données structurées (statistiques officielles NBA) avec des données non structurées (articles, forums Reddit, communiqués) pour offrir une expérience utilisateur enrichie et différenciante.


- Maturité data & ML :

    - Forces : une base de données statistiques NBA bien structurée, une veille active sur les forums et archives textuelles, et un premier prototype de chatbot déjà réalisé.
    - Faiblesses : le prototype existant n'a jamais été évalué objectivement, pas d'observabilité en production, pas de monitoring des coûts d'inférence, absence de validation stricte des entrées/sorties, et pas de processus industrialisé d'intégration des évolutions du modèle.

### Collecte et analyse du besoin métier

**Identification des parties prenantes**

| Pertie prenante | Rôle | Attentes principales |
| --- | --- | --- |
| Direction SportSee | Commanditaire | ROI mesurable, différenciation produit, maîtrise des coûts |
| Équipe éditoriale | Utilisateurs internes | Assistant pour accélérer la recherche documentaire |
| Data Scientist  | Réalisateur | Projet reproductible, évaluable, monitoré |

**Recueil justifié des besoins métiers**

La démarche de recueil s'est appuyée sur trois sources complémentaires :

- **Brief initial de SportSee** : l'entreprise a remonté explicitement une insatisfaction sur les réponses du chatbot existant, particulièrement sur les questions statistiques. Les réponses sur les archives textuelles étaient jugées « encourageantes » mais celles portant sur les chiffres étaient jugées insuffisantes.
- **Audit du prototype existant** : prise en main du projet, lancement de l'interface Streamlit, interaction avec le chatbot sur différents types de questions (simples, compliquées, bruitées).
- **Évaluation chiffrée via RAGAS** : mise en place d'un jeu d'évaluation de 20 questions couvrant trois niveaux de complexité et quatre métriques standard du domaine (faithfulness, answer relevancy, context precision, context recall).

**Hiérarchisation des besoins (matrice de priorisation Valeur × Effort)**

Dix besoins métier ont été identifiés, puis positionnés dans une matrice Valeur métier × Effort de mise en oeuvre :

| Besoin métier | Quadrant | Justification |
| --- | --- | --- |
| Fiabiliser les réponses (réduire les hallucinations) | Projet stratégique | Problème n°1 remonté, nécessite une refonte RAG complète |
| Améliorer les réponses sur questions statistiques | Projet stratégique | Nécessite base SQL + routeur |
| Création d'un environnement structuré | Projet stratégique | Séparation rag de la logique API et interface |
| Maintenir la qualité des réponses textuelles  | À éviter | Déjà fonctionnel, à voir dans les perspectives |
| Gérer les questions mixtes (texte + chiffres)  | Projet stratégique | Routeur, dépend de l'architecture dual-source |
| Évaluer objectivement les performances  | Quick win | Valeur forte pour effort modéré via RAGAS |
| Monitorer le système en production  | Projet stratégique | Mise en place Logfire |
| Garantir la robustesse (pas de crash)  | Projet stratégique | Mise en place Logfire |
| Offrir plusieurs modes d'interaction  | Tâche mineure | Postman + Interface |
| Documenter l'API (Swagger)  | Tâche mineure | Automatique avec FastAPI |
| Maîtriser les coûts d'inférence  | Quick win | Blocage réel rencontré (limite tokens Mistral) |

**Plan d'action déduit** : prioriser les quick wins pour débloquer rapidement la situation, puis engager les projets stratégiques qui nécessitent la refonte architecturale.