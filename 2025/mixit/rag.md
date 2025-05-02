# RAG

14h40

Framework LangChain4j identique à LangChain de Python

# Introduction

Limites :
- Date du dernier apprentissage
- Ne connaisse pas non données
- Hallucination
- Taille de la fenêtre des tokens dans un contexte => Pas possible de mettre toutes les données dans le prompt pour avoir une réponse

Retrieval : A partir d'une source externe

Augmented

Generation

# Bénéfice

- améliore la précision
- reduit les allucinations
- données à jour
- explication de la réponse

Données stockés dans une BDD vecteur. Si les données sont proches alors les vecteurs sont proches. Le vecteur d'une question est proche du vecteur de la réponse.

Découpage des documents en chunck pour être mis dans la BDD vecteur.

Les chuncks similaires dans la BDD vecteur sont mis dans le context du prompt.

# Chunck technique

Optimisation du découpage en chunck du document

- Faire une overlap pour pourvoir intégrer dans les chuncks les données complètes
- Découpage par phrase (perte de liens entre les phrases)
- Contexte parent & enfant => chunck Phrase + Paragraphe ou fenêtre glissante
    Modele Embedding

    Utilisation du contexte parent de la BDD Vecteur trouvé à partir du chunck dans le prompte du LLM

    Le recherche dans la BDD vecteur se fait sur la similarité des vecteurs

- Hypothetical questions
    Comparaison des questions gérées à partir d'un LLM en ayant comme source un paragraphe du document.
    Stockage des questions dans la BDD vecteur
    Possiblement plusieurs questions générées par paragraphe

- Contextual Retrieval (by anthropic)
    Inconvenient => Coût mais marche bien
    Résumé d'un paragraphe mise dans la BDD vecteur

Attention "Embedding Model" doivent être multilingue dans certain cas pour que cela fonctionne. Exemple : Questions Anglais -> Données en francais

# Retreival technical

Query compression => Création d'une question qui regroupe toutes les questions précédentes

# Query routing

Recherche sur le web

# Metadata Filtering

# Reranking

Model de reranking qui redonne un score à partir d'un chunck similaire

# function calling agentic RAG

Appel d'une fonction d'un agent pour avoir des données externes 

# AI Agents

Appel d'IA spécialisés

Décomposition de la question en plusieurs questions destinées à différent agent
Les diffents rapport (réponse des IA) sont regroupés par le LLM parent