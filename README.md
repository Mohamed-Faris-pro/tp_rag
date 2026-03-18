Voici une proposition complète pour ton fichier **README.md**, structurée de manière professionnelle et basée sur le contenu de ton notebook **RAGV2.ipynb**. Tu peux copier et coller ce texte directement sur ton dépôt GitHub.

***

# Information Retrieval : RAG (Retrieval Augmented Generation)

Ce projet est un Travail Pratique (TP) réalisé dans le cadre du cycle d'ingénierie à l'**EMSI**. Il explore la mise en œuvre d'un système de **Génération Augmentée par Récupération (RAG)** pour améliorer les capacités de réponse d'un Grand Modèle de Langage (LLM) en utilisant des sources de données externes.

## 📝 Présentation du projet

Le but de ce projet est de dépasser les limites intrinsèques des LLM (comme la date limite de connaissance ou les hallucinations) en injectant un contexte dynamique dans le prompt. Le système permet d'interroger des documents spécifiques (ici, le **Rapport Financier Annuel 2023 de l'OCP**) pour obtenir des réponses précises et sourcées.

### Points clés :
* **Récupération d'informations** : Extraction de segments pertinents depuis des documents PDF.
* **Génération enrichie** : Utilisation de l'API OpenAI pour générer des réponses basées uniquement sur le contexte fourni.
* **Évaluation RAG** : Mise en place d'une méthodologie "LLM-as-a-judge" pour évaluer la pertinence de la récupération et de la génération.

## 🚀 Fonctionnalités

-   **Pipeline RAG complet** : Chargement, découpage (chunking), vectorisation et stockage des documents.
-   **Base de données vectorielle** : Utilisation de ChromaDB pour le stockage des embeddings.
-   **Interface de requête** : Système capable de répondre à des questions complexes sur les performances financières de l'OCP en 2023.
-   **Métriques d'évaluation** : Vérification automatique de la fidélité de la réponse par rapport au contexte.

## 🛠️ Technologies utilisées

* **Langage** : Python 3.x
* **Framework** : LangChain
* **LLM & Embeddings** : OpenAI (GPT-3.5/4)
* **Vector Store** : ChromaDB / VectorStore
* **Notebook** : Jupyter / Google Colab

## ⚙️ Installation et Configuration

### 1. Clonage du dépôt
```bash
git clone https://github.com/votre-pseudo/votre-repo-rag.git
cd votre-repo-rag
```

### 2. Installation des dépendances
Il est recommandé d'utiliser un environnement virtuel :
```bash
pip install langchain openai chromadb pypdf tiktoken
```

### 3. Variables d'environnement
Créez un fichier `.env` à la racine du projet (ajoutez-le à votre `.gitignore`) et ajoutez votre clé API OpenAI :
```text
OPENAI_API_KEY=votre_cle_api_ici
```
*Note : Un fichier `.env.example` est fourni comme modèle.*

## 📖 Utilisation

1.  Ouvrez le notebook `RAGV2.ipynb`.
2.  Assurez-vous que le document PDF (ex: `Rapport Financier Annuel OCP 2023.pdf`) est présent dans le répertoire indiqué.
3.  Exécutez les cellules pour initialiser le `VectorStore` et lancer les requêtes.
4.  La fonction `RAG(query)` centralise la logique de récupération et de réponse.

## 📊 Évaluation

Le projet inclut une section dédiée à l'évaluation du système où le modèle s'auto-évalue selon deux axes :
1.  **Retrieval** : Le contexte récupéré contient-il la réponse ?
2.  **Generation** : La réponse est-elle strictement basée sur le contexte fourni ?

---

**Auteur :** [Ton Nom]
**École :** École Marocaine des Sciences de l'Ingénieur (EMSI)
**Spécialisation :** IA & Data Science
