---
title: systeme_recommandation
---

[🏠 Accueil](/) | [🎯 systeme_recommandation](/systeme_recommandation)

# Rapport de conduite de projet Data & ML

## Contexte et analyse des besoins

1. [Présentation](#présentation)
2. [Collecte et analyse du besoin métier](#collecte-et-analyse-du-besoin-métier)
3. [Audit de la solution data existante](#audit-de-la-solution-data-existante)
4. [Identification de la solution technique cible](#identification-de-la-solution-technique-cible)

### Présentation

**SportSee** est une entreprise évoluant dans le secteur de la data sportive, spécialisée dans la production et la valorisation de contenus et de statistiques autour du Basketball. L'entreprise s'adresse à la fois aux amateurs de basketball (contenus éditoriaux, forums) et aux clients professionnels (médias, applications de fantasy sports, parieurs, analystes).

- Secteur d'activité : data sportive — édition de contenu et fourniture de statistiques de Basketball.
- Taille estimée : PME en phase de croissance, avec une équipe produit/data restreinte.
- Enjeux stratégiques liés à la donnée : la donnée est le cœur de métier de SportSee. La valeur produite dépend directement de la capacité à croiser des données structurées (statistiques officielles NBA) avec des données non structurées (articles, forums Reddit, communiqués) pour offrir une expérience utilisateur enrichie et différenciante.


- Maturité data & ML :

    - Forces : une base de données statistiques NBA bien structurée, une veille active sur les forums et archives textuelles, et un premier prototype de chatbot déjà réalisé.
    - Faiblesses : le prototype existant n'a jamais été évalué objectivement, pas d'observabilité en production, pas de monitoring des coûts d'inférence, absence de validation stricte des entrées/sorties, et pas de processus industrialisé d'intégration des évolutions du modèle.

### Collecte et analyse du besoin métier

#### **Identification des parties prenantes**

| Pertie prenante | Rôle | Attentes principales |
| --- | --- | --- |
| Direction SportSee | Commanditaire | ROI mesurable, différenciation produit, maîtrise des coûts |
| Équipe éditoriale | Utilisateurs internes | Assistant pour accélérer la recherche documentaire |
| Data Scientist  | Réalisateur | Projet reproductible, évaluable, monitoré |

#### **Recueil justifié des besoins métiers**

La démarche de recueil s'est appuyée sur trois sources complémentaires :

- **Brief initial de SportSee** : l'entreprise a remonté explicitement une insatisfaction sur les réponses du chatbot existant, particulièrement sur les questions statistiques. Les réponses sur les archives textuelles étaient jugées « encourageantes » mais celles portant sur les chiffres étaient jugées insuffisantes.
- **Audit du prototype existant** : prise en main du projet, lancement de l'interface Streamlit, interaction avec le chatbot sur différents types de questions (simples, compliquées, bruitées).
- **Évaluation chiffrée via RAGAS** : mise en place d'un jeu d'évaluation de 20 questions couvrant trois niveaux de complexité et quatre métriques standard du domaine (faithfulness, answer relevancy, context precision, context recall).

#### **Hiérarchisation des besoins (matrice de priorisation Valeur × Effort)**

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

### Audit de la solution data existante

Le prototype reçu en entrée de mission présente les caractéristiques suivantes :

#### **Outils et technologies**

- Langage : Python
- Interface utilisateur : Streamlit
- LLM : Mistral mistral-small-latest
- Embeddings : Mistral mistral-embed
- Orchestration : LangChain
- Base vectorielle : FAISS
- Gestion des dépendances : requirements.txt

#### **Pipeline d'exploitation des données**

1. Chargement des documents PDF (captures d'écran de fils Reddit) et d'un fichier Excel (statistiques NBA par joueur).
2. Découpage en chunks textuels (le fichier Excel est traité comme du texte brut).
3. Création d'embeddings Mistral.
4. Indexation dans FAISS.
5. À la requête utilisateur : recherche sémantique → passage du contexte au LLM → génération de la réponse.

#### **Organisation du projet**

Structure monolithique, code regroupé dans quelques fichiers (`MistralChat.py`, `indexer.py`, `utils/vector_store.py`, `utils/data_loader.py`) sans séparation claire des responsabilités, pas de tests, pas de logs, pas d'API.

### Évaluation RAGAS du prototype existant

Quatre critères ont été retenus : performance qualitative (via RAGAS), robustesse, coût et scalabilité, pertinence métier.

#### **Résultats de l'évaluation RAGAS sur le prototype**

Évaluation sur 20 questions réparties en trois catégories (faciles, compliquées, bruitées) :

- **Au global** :
![alt text](assets/moyenne_ragas_first_evaluation.png)

Answer relevancy (0,92) : Le LLM comprend bien la question
Faithfulness (0,17) : Hallucinations massives, les réponses ne s'appuient pas sur le contexte
Context precision (0,20) : Retrieval bruité, beaucoup de documents non pertinents ramenés
Context recall (0,33) : Informations clés souvent absentes du contexte

- **Par catégorie de question** : 
![alt text](assets/moyenne_ragas_par_categorie_first_evaluation.png.png)

**Constat principal** : le prototype produit des réponses sémantiquement cohérentes avec la question mais factuellement non fiables. Le modèle compense le manque d'information pertinente en extrapolant à partir de ses connaissances internes, ce qui est inacceptable sur un cas d'usage de restitution statistique.

#### **Identification des écarts et des limites**

| Écart | Cause racine |
| --- | --- |
| Faithfulness très basse | Les chunks récupérés ne contiennent pas les bonnes informations, le LLM invente |
| Retrieval inefficace sur les stats | Le fichier Excel est traité comme du texte, les données chiffrées sont « perdues » lors du chunking |
| Aucune visibilité en production | Pas de logs, pas de monitoring |
| Pas de garde-fou sur les entrées/sorties | Une entrée vide fait planter l'application |
| Pas d'API | Impossible d'intégrer le chatbot à un système tiers|
| Dépendance monolithique à Mistral | Limite de tokens gratuits atteinte rapidement |

#### **Visualisation du système RAG existant**

![alt text](assets/old_rag_system.png)

#### **Conclusion de l'audit :**

Le prototype est fonctionnel comme démonstrateur mais non-adapté à un usage en production. Il nécessite une refonte architecturale pour traiter correctement les données hétérogènes (texte + chiffres) et intégrer des mécanismes d'évaluation, de monitoring et de robustesse.

### Identification de la solution technique cible

#### **Comparatif d'approches techniques**

Trois approches ont été envisagées pour répondre au besoin :

| Approche | Principe | Avantages | Inconvénients |
| --- | --- | --- | --- |
| A. RAG pur amélioré | Garder une seule base vectorielle mais améliorer le chunking, les embeddings et le prompt | Simple à mettre en œuvre, conserve l'architecture prototype | Ne résout pas le problème fondamental : les chiffres restent noyés dans le texte |
| B. Text-to-SQL pur | Remplacer le RAG par un agent qui génère du SQL à partir de la question | Excellente précision sur les stats | Perd toute la valeur des archives textuelles (Reddit) |
| C. RAG hybride avec routeur| Deux bases (vectorielle + SQL), un routeur LLM qui oriente la requête vers la bonne source | Traite chaque type de donnée avec l'outil adapté | Complexité architecturale supérieure, coût d'orchestration |

**Choix retenu** : approche C (RAG hybride avec routeur), seule à répondre à l'ensemble des besoins métier (questions statistiques ET questions textuelles ET questions mixtes).

#### **Architecture cible**

![alt text](assets/new_rag_system.png)

#### **Facteurs clés de succès et points de vigilance**

- Un routeur LLM bien prompté qui fait les bons choix d'orientation.
- Une base SQL propre avec des métadonnées (glossaire des acronymes de stats NBA) pour aider le LLM à générer du SQL correct.
- Un jeu d'évaluation RAGAS solide pour valider les améliorations.
- Une observabilité de bout en bout pour détecter les régressions.

#### **Points de vigilance**

- Biais LLM-as-a-judge : RAGAS s'appuie sur un LLM pour noter, ce qui introduit un biais de verbosité et une sensibilité au formatage.
- Barrière linguistique : les modèles d'embedding utilisés sont optimisés pour l'anglais, la nuance du français peut être sous-évaluée.
- Dépendance au ground truth : la qualité de l'évaluation est plafonnée par la qualité du jeu de référence.
- Dérive des performances dans le temps : nécessité d'un monitoring continu.