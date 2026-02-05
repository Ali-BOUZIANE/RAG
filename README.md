# 🤖 Projet RAG : Question–Réponse sur PDF avec LangChain, Ollama et Chroma

Ce projet implémente une architecture **RAG (Retrieval-Augmented Generation)** permettant d’interroger le contenu d’un **document PDF** à l’aide d’un **modèle de langage local**.

Le pipeline repose sur :
- le **chargement et le découpage du PDF**,
- la **génération d’embeddings**,
- l’**indexation dans une base vectorielle (ChromaDB)**,
- la **recherche sémantique**,
- et la **génération de réponses** via le modèle **Mistral** exécuté localement avec **Ollama**.

L’orchestration est assurée par **LangChain**, permettant de fournir des **réponses contextualisées**, basées exclusivement sur les informations contenues dans le document source.  
Le projet démontre la faisabilité d’un **système de question-réponse local, efficace et sans dépendance cloud**, applicable à la documentation technique et aux systèmes d’aide à la décision.


👨‍💻 Auteur 
Ali Bouziane Ingénieur en Génie Informatique | IA, Big Data & Cybersécurité 
