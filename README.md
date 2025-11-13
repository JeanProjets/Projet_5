# Mission : Segmentez des clients d'un site e-commerce

## Introduction

Cette mission suit un scénario de projet professionnel.  
Vous pouvez suivre les étapes pour vous aider à réaliser vos livrables.

### Avant de démarrer

- Lire toute la mission et ses documents liés.
- Prendre des notes sur ce que vous avez compris.
- Consulter les étapes pour vous guider.
- Préparer une liste de questions pour votre première session de mentorat.

---

## Contexte

**28 mai 2024** : le fichier contenant les requêtes SQL est modifié (la question 4 a été changée).  
Si vous démarrez le projet, suivez directement les consignes ci-dessous.  

Vous êtes consultant pour **Olist**, une entreprise brésilienne proposant une solution de vente sur les marketplaces en ligne.

### Objectif

Accompagner Olist dans la création de leur équipe Data et leur premier cas d’usage Data Science : la **segmentation client**.  

Vous êtes en renfort pour aider Fernanda, Lead Data Analyst chez Olist.

---

## Messages clés de Fernanda

**De :** Fernanda  
**À :** Moi  
**Objet :** Dashboard Customer Experience  

Bonjour,  

Bienvenue chez Olist ! Nous construisons et maintenons un **Dashboard Customer Experience** pour exposer les KPIs essentiels.  
Nous avons besoin de votre aide sur l’implémentation de requêtes SQL urgentes pour alimenter ce dashboard.  

**Pièce jointe :** Liste de requêtes SQL

---

## Mission principale

Après avoir traité les urgences SQL, la mission principale est :

**Objectif :** Fournir une segmentation exploitable des clients pour l’équipe Marketing.

### Données disponibles

- Historique des commandes depuis janvier 2017
- Produits achetés
- Commentaires de satisfaction
- Localisation des clients

### Attentes

- Utilisation de **méthodes non supervisées** pour regrouper des clients similaires.
- Fournir une **description actionable** de la segmentation.
- Proposer un **contrat de maintenance** basé sur la stabilité des segments dans le temps.

---

## Précisions de João (équipe Marketing)

**De :** João  
**À :** Moi  
**Objet :** Re: segmentation des clients  

- Les données disponibles suffisent pour un premier clustering.  
- La segmentation doit différencier les **bons et moins bons clients** en termes de commandes et satisfaction.  
- Recommandation sur la **fréquence de mise à jour** de la segmentation.  
- Code fourni doit respecter **PEP8**.  
- Exemple joint : **Segmentation RFM** (récence, fréquence, montant).

**Pièces jointes :** Schéma RFM

---

## Documents à produire

1. Notebook avec essais de différentes approches de modélisation
2. Notebook de simulation pour déterminer la fréquence de mise à jour
3. Présentation pour validation interne

---

# Étapes de la mission

## Étape 1 : Répondre aux requêtes SQL

**Avant de démarrer :**

- Appropriation des ressources SQL
- Installation d’un logiciel de gestion de bases de données (Workbench, DBeaver, SQLTools VSCode)

**Livrable attendu :**

- Script final avec les 4 requêtes SQL demandées

**Recommandations :**

- Faire quelques opérations basiques pour comprendre le contenu des tables
- Structurer les requêtes avec `WITH AS`
- Justifier les choix de jointures (LEFT, INNER, OUTER)

**Ressources :**

- Cours “Requêtez une base de données avec SQL”
- Présentation du jeu de données sur Kaggle
- SQLZoo

---

## Étape 2 : Transformer les données

**Avant :**

- Aisance en SQL pour agrégations

**Livrable :**

- Notebook avec feature engineering par client

**Recommandations :**

- Requêtes exploratoires pour comprendre le jeu de données
- Réflexion sur la répartition SQL vs Python pour le calcul des features
- Focus sur features clés : RFM
- Transformation de variables (normalisation, encodage)
  
**Points de vigilance :**

- Ne pas supprimer les clients ayant plusieurs commandes

**Ressources :**

- Documentation méthode RFM

---

## Étape 3 : Élaborer un modèle de clustering

**Avant :**

- Sélection de features pertinentes
- Bases théoriques du clustering

**Livrable :**

- Notebook avec différentes simulations de clustering

**Recommandations :**

- Commencer par k-means avec 3 à 6 clusters
- Déterminer le nombre optimal de clusters (data-driven et métier)
- Justifier la qualité du clustering avec métriques
- Caractériser les clusters et leur lien avec les features
- Prioriser la tangibilité métier sur la performance pure

**Points de vigilance :**

- Choisir un nombre de clusters pertinent et gérable
- Assurer la cohérence métier des clusters

**Ressources :**

- Analyse exploratoire des données
- Librairie Yellowbrick (silhouette, distorsion)

---

## Étape 4 : Simuler un contrat de maintenance

**Avant :**

- Clustering final optimisé et interprétable

**Livrable :**

- Notebook de simulation de stabilité du clustering

**Recommandations :**

- Utiliser **ARI** pour mesurer la divergence des clusters
- Suivre l’évolution des distributions des features numériques
- Méthodes graphiques ou test de Kolmogorov-Smirnov

**Points de vigilance :**

- Cohérence des données entre entraînement et prédiction

**Ressources :**

- Documentation Adjusted Rand Index (ARI)

---

## Étape 5 : Préparer la soutenance

**Avant :**

- Modélisation finalisée

**Livrable :**

- Capacité à justifier :
  - Choix des features
  - Nombre de clusters
  - Évaluation du clustering
  - Sens métier des clusters
  - Approche pour mesurer la stabilité dans le temps

**Recommandations :**

- Présentation claire avec focus sur insights métier
- Discussion des choix techniques et méthodologiques
- Compresser les analyses pour le storytelling essentiel
