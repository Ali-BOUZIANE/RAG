# 🤖 Projet RAG : Question–Réponse sur PDF avec LangChain, Ollama et Chroma

## 📌 Description du Projet

Ce projet met en œuvre une architecture **RAG (Retrieval-Augmented Generation)** permettant d’interroger le contenu d’un **document PDF** à l’aide d’un **modèle de langage local**.

L’approche combine :
- La **recherche sémantique** (embeddings + base vectorielle).
- La **génération de texte** par un LLM (Large Language Model).

L'objectif est de produire des **réponses précises et contextualisées**, basées uniquement sur les informations contenues dans le document source, garantissant ainsi la confidentialité et la fiabilité des données.

Le projet utilise **LangChain** pour l’orchestration, **Ollama** pour l’exécution locale du modèle **Mistral**, et **ChromaDB** comme base de données vectorielle.

---

## 🎯 Objectifs

* **Charger et analyser** un document PDF complexe.
* **Segmenter le texte** en unités exploitables (chunks).
* **Générer des embeddings** (vecteurs numériques) pour chaque segment.
* **Indexer les données** dans une base de données vectorielle performante.
* **Effectuer une recherche sémantique** pour retrouver le contexte pertinent.
* **Générer des réponses** via un LLM local sans dépendance au cloud.
* **Déployer un pipeline RAG** fonctionnel de bout en bout.

---

## 🧠 Architecture du Système

Le flux d'informations suit le schéma suivant :

**Document PDF** ⮕ **Découpage (Splitter)** ⮕ **Embeddings** ⮕ **ChromaDB** ⮕ **Similarity Search** ⮕ **LLM (Mistral)** ⮕ **Réponse finale**

---

## 🛠️ Technologies Utilisées

* **Langage :** Python
* **Orchestrateur :** LangChain
* **Moteur LLM :** Ollama (Modèle : Mistral)
* **Vector Store :** ChromaDB
* **Parser PDF :** PyPDF
* **Embeddings :** OllamaEmbeddings (modèle local)

---

## 📦 Installation & Configuration

### 1. Installation des dépendances
```bash
pip install -U langchain langchain-community chromadb pypdf ollama
2. Configuration d'Ollama
Assurez-vous qu'Ollama est installé sur votre machine, puis téléchargez le modèle requis :

Bash
# Vérifier l'installation
ollama list

# Télécharger le modèle Mistral
ollama pull mistral
⚙️ Détails du Pipeline Technique
📄 Traitement du Document
Le texte est extrait avec PyPDFLoader puis découpé avec RecursiveCharacterTextSplitter pour conserver la cohérence sémantique.

Taille des segments (chunk_size) : 500 caractères.

Chevauchement (overlap) : 50 caractères pour éviter la perte de contexte entre les segments.


🧬 Indexation & Persistance
Les embeddings sont générés localement. La base de données ChromaDB est configurée pour être persistante dans le dossier ./rag_db, évitant ainsi de ré-indexer le document à chaque exécution.


🔎 Recherche & Génération
Le système utilise la recherche par similarité pour extraire les passages les plus pertinents du PDF. Ces passages sont ensuite injectés dans un prompt structuré envoyé à Mistral pour produire la réponse.


✅ Résultats et Validation
Le pipeline a été validé avec succès sur un document technique relatif à l'écosystème Oracle. Le modèle a été capable d'expliquer avec précision :

L'architecture de l'entreprise et de la base de données Oracle.

Le fonctionnement de Oracle Forms & Reports.

L'utilisation de SQL*Plus et du langage PL/SQL.


📂 Structure du Projet
Plaintext
.
├── rag_db/                 # Base de données vectorielle persistante
├── main.py                 # Script Python principal (Logique RAG)
├── ORACLE.pdf              # Document source analysé
└── README.md               # Documentation complète


👨‍💻 Auteur
Ali Bouziane Ingénieur en Génie Informatique | IA, Big Data & Cybersécurité 📧 bouziane_ali@upf.ac.ma 🔗 LinkedIn
