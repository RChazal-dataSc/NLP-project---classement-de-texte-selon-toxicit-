📝 NLP Project – Classification de commentaires selon leur toxicité

Ce projet a été réalisé dans le cadre de mon apprentissage du traitement automatique du langage naturel (NLP) et de la classification supervisée.
L’objectif était de construire un pipeline complet allant du nettoyage des textes à la modélisation, puis de comparer différentes approches classiques du machine learning.

🎯 Objectif

Classer automatiquement des commentaires en ligne selon plusieurs types de toxicité (multi-label) :
toxic
severe_toxic
obscene
threat
insult
identity_hate

🗃 Données

Jeu de données : Toxic Comment Classification Challenge – Kaggle
train.csv : ~160 000 commentaires avec labels (multi-label)
test.csv : ~150 000 commentaires sans labels

🔧 Pipeline de traitement
1. Prétraitement des données

Nettoyage des textes (regex, suppression des liens, chiffres, caractères spéciaux)
Tokenisation (RegexpTokenizer)
Analyse exploratoire : longueur des phrases, distribution des classes (déséquilibre fort)

2. Vectorisation

TF-IDF (TfidfVectorizer) appliqué sur l’ensemble des textes

3. Modélisation & Expérimentations
   
Baseline
Régression logistique (un classifieur par label)
Gestion du déséquilibre
Application de SMOTE : nette amélioration du recall et du F1-score pour les classes minoritaires
Modèles testés
Régression logistique (avec et sans SMOTE)
Random Forest
XGBoost
Réduction de dimensions (TruncatedSVD) : testée mais peu concluante (perte de recall)
Validation
Découpage train/validation avec stratification
Évaluation via : accuracy, precision, recall, F1-score, et matrices de confusion

📊 Résultats

Régression logistique (baseline) : bons résultats globaux, mais recall limité sur les classes rares.
Régression logistique + SMOTE : amélioration claire du F1 sur les classes minoritaires.
Random Forest : précision correcte, mais recall insuffisant.
XGBoost : performances comparables à la régression logistique, mais plus coûteux en ressources.
TruncatedSVD : réduction de dimensions testée, mais perte d’information sur ce type de données.

👉 Conclusion : pour ce problème, un modèle simple (régression logistique + SMOTE) surpasse ou égale les modèles plus complexes.

⚙️ Outils et bibliothèques

Data science : pandas, numpy, matplotlib, seaborn
NLP & ML : nltk, scikit-learn, imblearn, xgboost
Divers : re (expressions régulières)

🧠 Perspectives

Ce projet m’a permis d’explorer plusieurs points clés :
Importance de la gestion du déséquilibre des classes
Comparaison modèles simples vs. complexes
Limites de la réduction de dimensions pour du texte vectorisé

Prochaines pistes :
Tester des modèles NLP avancés (Word2Vec, BERT, DistilBERT)
Explorer des approches deep learning (RNN, LSTM, transformers)

Développer une petite interface web (Flask/Streamlit) pour tester les prédictions en direct

