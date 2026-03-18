
***
# Information Retrieval : RAG (Retrieval Augmented Generation)

Ce projet est un Travail Pratique (TP) réalisé dans le cadre du cycle d'ingénierie à l'**EMSI**. Il explore la mise en œuvre d'un système de **Génération Augmentée par Récupération (RAG)** pour améliorer les capacités de réponse d'un Grand Modèle de Langage (LLM) en utilisant des sources de données externes.

## 📝 Présentation du projet

Le but de ce projet est de dépasser les limites intrinsèques des LLM (comme la date limite de connaissance ou les hallucinations) en injectant un contexte dynamique dans le prompt. Le système permet d'interroger des documents spécifiques (ici, le **Rapport Financier Annuel 2023 de l'OCP**) pour obtenir des réponses précises et sourcées.

### Points clés :
* **Récupération d'informations** : Extraction de segments pertinents depuis des documents PDF.
* **Génération enrichie** : Utilisation de l'API OpenAI pour générer des réponses basées uniquement sur le contexte fourni.
* **Évaluation RAG** : Mise en place d'une méthodologie "LLM-as-a-judge" pour évaluer la pertinence de la récupération et de la génération.

## 🚀 Aperçu et Résultats

*Cette section illustre le fonctionnement du système RAG étape par étape.*

### 1. Chargement et Vectorisation
Le système découpe le document PDF en segments (chunks) et les transforme en vecteurs numériques stockés dans une base de données.
> **[IMAGE : Capture d'écran du code de chargement du PDF ou de la création de la base de données]**

### 2. Requête et Récupération (Retrieval)
Lorsqu'une question est posée, le système retrouve les passages les plus pertinents dans le document.
> **[IMAGE : Capture montrant les "chunks" de texte récupérés pour une question donnée]**

### 3. Réponse Générée et Jugement (Evaluation)
Le modèle génère une réponse finale et une étape d'auto-évaluation vérifie si la réponse est bien présente dans le contexte fourni.
> **[IMAGE : Capture du résultat final montrant la question, la réponse et l'avis du "Judge"]**

## 🛠️ Technologies utilisées

* **Langage** : Python 3.x
* **Framework** : LangChain
* **LLM & Embeddings** : OpenAI (GPT-3.5/4)
* **Vector Store** : ChromaDB
* **Notebook** : Jupyter / Google Colab

## ⚙️ Installation et Configuration

### 1. Clonage du dépôt
```bash
git clone https://github.com/votre-pseudo/votre-repo-rag.git
cd votre-repo-rag
```

### 2. Installation des dépendances
```bash
pip install langchain openai chromadb pypdf tiktoken
```

### 3. Variables d'environnement
Créez un fichier `.env` à la racine du projet et ajoutez votre clé API OpenAI :
```text
OPENAI_API_KEY=votre_cle_api_ici
```
*Note : Le fichier `.env` est ignoré par Git pour des raisons de sécurité.*

## 📖 Utilisation

1.  Ouvrez le notebook `RAGV2.ipynb`.
2.  Assurez-vous que le document PDF est présent dans le répertoire.
3.  Exécutez les cellules pour initialiser le `VectorStore` et lancer les requêtes via la fonction `RAG(query)`.

---

**Auteur :** [Ton Nom]
**École :** École Marocaine des Sciences de l'Ingénieur (EMSI)
**Spécialisation :** IA & Data Science

***

### Comment insérer tes images concrètement :
Pour remplacer les lignes en gras par tes vraies images, utilise cette syntaxe :
`![Description de l'image](le_nom_de_ton_image.png)`

Si tu as créé un dossier `screenshots`, utilise :
`![Résultat final](screenshots/resultat.png)`
