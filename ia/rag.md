# RAG

  Un RAG (Retrieval-Augmented Generation) est un moyen d’optimiser les résultats d’un LLM (Large Language Model) en rajoutant des données de différentes sources. Les LLM étant entraînés sur un certain corpus de données à une date donnée, l’idée est de pouvoir compléter ce corpus initial avec des données soit plus récentes soit spécifiques à un contexte donné. Par exemple, des documents internes si on construit un chatbot d’entreprise.

## Indexation

  Pour cela, il va donc falloir ingérer des données. Une fois que l’on a converti les données en format texte, on va pouvoir les découper en petits bouts (chunks). L’opération est appelée chunking. En général, il y a un chevauchement entre les chunks pour être sûr de ne pas manquer d'informations. Maintenant que nous avons des extraits de phrases, il va falloir les convertir dans un format que comprend une machine : c’est l’embedding. Chaque chunk (suite de mots) va être converti en un vecteur à N dimensions. Donc pour chaque suite de mots, nous allons pouvoir y associer une coordonnée. La distance entre deux vecteurs sera la distance sémantique entre deux chunks. Ces vecteurs sont stockés dans une base de données dite “vectorielle”. À partir d’une entrée utilisateur, on va pouvoir extraire les chunks qui sont proches en sens.

## Requête

  La question de l’utilisateur va être transformée pour garder uniquement les mots ayant un sens fort (élimination des articles par exemple). Ensuite la requête va être transformée en vecteurs comme les données d’entrée. Ces vecteurs seront les paramètres d’entrées d’une recherche vectorielle dans la base de données vectorielle. Cela va sortir les N meilleurs résultats. Ces résultats seront ensuite chargés dans le contexte du LLM qui va produire une réponse à partir du contexte généré et d’un prompt prédéfini.

## Pipeline global

- Indexation (convertir des documents dans une base vectorielle)
- Récupération (requêter la base de données pour trouver les chunks pertinents)
- Augmentation (injecter les chunks retrouvés dans le prompt du LLM)
- Génération (interroger le LLM pour produire une réponse)
