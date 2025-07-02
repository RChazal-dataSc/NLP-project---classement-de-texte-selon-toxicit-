# NLP Project – Classification de commentaires selon leur toxicité

Ce projet a été réalisé dans le cadre de mon apprentissage du traitement automatique du langage naturel (NLP). L’objectif était de m’initier à l’analyse de texte brut, à la vectorisation et à la classification supervisée, à partir de données publiques issues d’un concours Kaggle.

## 🎯 Objectif

Classer automatiquement les commentaires en ligne selon plusieurs types de toxicité :

- `toxic`
- `severe_toxic`
- `obscene`
- `threat`
- `insult`
- `identity_hate`

## 🗃 Données

Les données sont issues du jeu de données [Toxic Comment Classification Challenge – Kaggle](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge):

- `train.csv` : 160 000 commentaires avec labels (multi-label)
- `test.csv` : 150 000 commentaires sans labels

## 🔧 Pipeline de traitement

### 1. **Prétraitement des données**
- Nettoyage des textes (regex, suppression de liens, chiffres, caractères spéciaux, etc.)
- Tokenisation (`RegexpTokenizer`)
- Analyse de la longueur des phrases et vocabulaire

### 2. **Vectorisation**
- Utilisation de la méthode **TF-IDF** (`TfidfVectorizer`)
- Application sur l’ensemble des textes

### 3. **Modélisation**
- Entraînement d’un modèle de **régression logistique** pour chaque label (multi-sortie)
- Évaluation empirique des résultats via inspection des prédictions
- Génération d’un fichier de soumission (`submission.csv`) avec les probabilités de toxicité

## ⚙️ Outils et bibliothèques

- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `nltk`, `scikit-learn`
- `re` pour les expressions régulières

## 📊 Résultats

Le modèle a généré des probabilités de classification pour chaque commentaire sur les six dimensions. À cette étape, aucune métrique n’a été calculée, l’objectif étant d’établir un prototype simple et fonctionnel.

Exemple de sortie (`submission.csv`) :

| id              | toxic | severe_toxic | obscene | threat | insult | identity_hate |
|-----------------|-------|--------------|---------|--------|--------|----------------|
| 00001cee341fdb12 | 0.997 | 0.160        | 0.992   | 0.039  | 0.948  | 0.246          |
| ...             | ...   | ...          | ...     | ...    | ...    | ...            |

## 🧠 Perspectives

Ce projet constitue une première approche des problématiques NLP. Il servira de base pour :

- Un projet plus avancé d’analyse de sentiments
- Une implémentation avec du deep learning (RNN, BERT, etc.)
- L’ajout d’une interface Flask pour tester les prédictions

## 👨‍💻 Auteur

Richard Chazal – Data Scientist en reconversion, spécialisé en sciences de la vie et traitement de données scientifiques.

