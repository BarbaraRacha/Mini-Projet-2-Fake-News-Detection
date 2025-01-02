# Détection des Fausses Nouvelles à l'Aide des Transformateurs

## Description
Ce projet vise à détecter les fausses nouvelles en combinant les atouts des modèles de transformateurs BERT et GPT. L'objectif est de créer un système hybride capable de classifier les articles en "fake" ou "réel" avec une grande précision. Ce projet est une contribution importante dans la lutte contre la désinformation en ligne.

## Membres du Projet
- **Barbara Racha**
- **Zerheri Fatima Zahrae**
- 
---

## Objectifs
- Utiliser BERT pour exceller dans la classification textuelle.
- Exploiter GPT pour une étape supplémentaire d'analyse de similarité et de cohérence.
- Améliorer la précision globale grâce à une approche hybride.

---

## Dataset
- Source : [fake-and-real-news-dataset](https://www.kaggle.com)
- Composition :
  - 63,678 textes d'actualités (21,197 pour chaque classe : "fake" et "real").
- Prétraitement :
  - Nettoyage des textes : suppression des URL, balises HTML, ponctuation, etc.
  - Division en ensembles d'entraînement (80%) et de test (20%).
  - Encodage des étiquettes en indices numériques.
  - Exportation en fichiers CSV : `train.csv` et `test.csv`.

---

## Architecture du Modèle

### BERT
1. **Tokenisation** : Conversion des textes en séquences de tokens à l'aide du tokenizer BERT.
2. **Classification** : Utilisation de `AutoModelForSequenceClassification` de Hugging Face pour une classification binaire.
3. **Entraînement** :
   - Classe Trainer avec des paramètres optimisés (nombre d'époques, taille des lots, etc.).
   - Utilisation de la précision flottante 16 bits pour améliorer la vitesse.

### GPT
1. **Prétraitement** : Tokenisation des textes avec GPT-2.
2. **Analyse Sémantique** : Utilisation de `AutoModelForCausalLM` pour prédire des séquences adaptées.
3. **Entraînement** :
   - Paramètres similaires à ceux utilisés pour BERT.
   - Approche fine-tunée pour une performance optimale.

### Fonction Hybride
- Détection initiale avec BERT.
- Analyse de similarité avec GPT pour valider ou réfuter les résultats.

---

## Résultats
- Haute précision obtenue grâce à l'approche hybride.
- Amélioration notable dans l'identification des fausses nouvelles par rapport aux méthodes classiques.
- Génération d'une matrice de confusion pour évaluer les performances sur les données de test.

---

## Conclusion
Ce projet démontre l'efficacité de la combinaison des forces de BERT et GPT pour améliorer la détection des fausses nouvelles. Il constitue une base solide pour des recherches futures et des applications concrètes, telles que la modération de contenu en ligne et la vérification automatique des faits.

---

## Prérequis
- Python 3.8+
- Bibliothèques :
  - Hugging Face Transformers
  - NumPy, Pandas
  - scikit-learn
- Données disponibles dans les fichiers `train.csv` et `test.csv`.

---

## Installation
1. Clonez ce dépôt :
   ```bash
   git clone https://github.com/BarbaraRacha/Mini-Projet-2-Fake-News-Detection.git
