# NLP-project---classement-de-texte-selon-toxicit-
NLP project - classement de texte selon toxicité

#le but de ce premier projet NLP est de se familiariser avec les bases du Traitement automatique
#du langage naturel et de l'analyse de sentiment
#je vais réutiliser les techniques de l'exercise kaggle et des tweets de Trump
#la prédiction se fera en entrainant un classifieur, plusieurs si le premier ne donne pas satisfaction

#cela nous servira de base pour le prochain projet, qui sera plus complexe


- Quel était le problème ?
Mon objectif est de me former au NLP, je n'avais fairt qu'un exercice lors de ma formation. Je souhaite donc faire 2 ou 3 projets autour de cette thématique.
Celui ci est le plus simple, l'objectif est d'acquérir les bases nécéssaires au NLP.

- Quelle méthode avez-vous suivi pour le résoudre ?

analyse et nettoyage des données, regex pour épurer les données textuelles, tokenize, exploration des mots ainsi constituées ainsi que la longueur des phrases, vectorisation via TFIDF, classification avec une régression logistique. 

- Quels outils avez-vous choisi ?

regex, RegexpTokenizer, TfidfVectorizer, train_test_split, logisticregression, et les habituelles


- Éventuellement, quelques remarques sur le code programmé.

J'ai du détailler le code autour de Tfid pour le comprendre. C'est éltape qui manquait dans l'exercise Tweets de Trump pour faire le lien entre les données textuelles et la classification

- Des exemples de résultats obtenus.

Voyez le fichier Submission, et la capture d'écran de celui ci avant son export sous format .csv
