
***
# Information Retrieval : RAG (Retrieval Augmented Generation)

Ce TP explore la mise en œuvre d'un système de **Génération Augmentée par Récupération (RAG)** pour améliorer les capacités de réponse d'un Grand Modèle de Langage (LLM) en utilisant des sources de données externes.

## 📝 Présentation du TP

Le but de ce TP est de dépasser les limites intrinsèques des LLM (comme la date limite de connaissance ou les hallucinations) en injectant un contexte dynamique dans le prompt. Le système permet d'interroger des documents spécifiques (ici, le **Rapport Financier Annuel 2023 de l'OCP**) pour obtenir des réponses précises et sourcées.

### Points clés :
* **Récupération d'informations** : Extraction de segments pertinents depuis des documents PDF.
* **Génération enrichie** : Utilisation de l'API OpenAI pour générer des réponses basées uniquement sur le contexte fourni.
* **Évaluation RAG** : Mise en place d'une méthodologie "LLM-as-a-judge" pour évaluer la pertinence de la récupération et de la génération.

## 🚀 Aperçu et Résultats

*Cette section illustre le fonctionnement du système RAG étape par étape.*

### 1. Chargement et Vectorisation
Le système découpe le document PDF en segments (chunks) et les transforme en vecteurs numériques stockés dans une base de données.
> <img width="737" height="81" alt="image" src="https://github.com/user-attachments/assets/624ae46f-25e0-4ec3-97f4-6d9b1bfa396e" />


### 2. Requête et Récupération (Retrieval)
Lorsqu'une question est posée, le système retrouve les passages les plus pertinents dans le document.
> <img width="734" height="86" alt="image" src="https://github.com/user-attachments/assets/0df05742-27a5-426d-9efc-26f3e8deb9be" />


### 3. Réponse Générée et Jugement (Evaluation)
Le modèle génère une réponse finale et une étape d'auto-évaluation vérifie si la réponse est bien présente dans le contexte fourni.
> <img width="733" height="113" alt="image" src="https://github.com/user-attachments/assets/a32955ae-166c-4505-a169-f7990b76b864" />
> <img width="735" height="272" alt="image" src="https://github.com/user-attachments/assets/84f5d1e4-9c1b-49af-b187-76876cf77c6c" />
> <img width="771" height="287" alt="image" src="https://github.com/user-attachments/assets/d17196ce-9909-433e-9a47-40f717d88541" />



## 🛠️ Technologies utilisées

* **Langage** : Python 3.x
* **Framework** : LangChain
* **LLM & Embeddings** : OpenAI (GPT-X)
* **Vector Store** : ChromaDB

## ⚙️ Installation et Configuration

### 1. Clonage du dépôt
```bash
git clone https://github.com/votre-pseudo/votre-repo-rag.git
cd votre-repo-rag
```

### 2. Installation des dépendances

### 3. Variables d'environnement
Créez un fichier `.env` à la racine du projet et ajoutez votre clé API OpenAI :
```text
OPENAI_API_KEY=votre_cle_api_ici
```
*Note : Le fichier `.env` est ignoré par Git pour des raisons de sécurité.*

## 📖 Utilisation

1.  Ouvrez le notebook `rag.ipynb`.
2.  Assurez-vous que le document PDF est présent dans le répertoire.
3.  Exécutez les cellules pour initialiser le `VectorStore` et lancer les requêtes via la fonction `RAG(query)`.

---
