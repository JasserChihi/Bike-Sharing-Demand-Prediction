# Bike Sharing Demand Prediction

Ce dépôt contient un projet d'analyse et de modélisation pour la prédiction de la demande de vélos (Bike Sharing Demand), principalement sous la forme d'un notebook Jupyter : `bikes_regression.ipynb`. Le notebook montre le nettoyage des données, l'exploration, des régressions linéaires et des modèles de réseaux de neurones pour prédire le nombre de vélos loués à midi à partir de variables météorologiques et contextuelles.

## Table des matières

- [Présentation](#présentation)
- [Contenu du dépôt](#contenu-du-dépôt)
- [Fonctionnalités](#fonctionnalités)
- [Technologies utilisées](#technologies-utilisées)
- [Installation](#installation)
- [Préparation des données](#préparation-des-données)
- [Utilisation](#utilisation)
- [Résultats et visualisations](#résultats-et-visualisations)

## Présentation

L'objectif du projet est d'explorer et de prédire la demande quotidienne/horaires de vélos (nombre de locations) en utilisant le dataset "Seoul Bike Sharing" (extrait UCI / data.seoul.go.kr). Le notebook présente des étapes classiques de Data Science : nettoyage, visualisation, séparation train/validation/test, modèles linéaires et modèles neuronaux, évaluation et visualisation des résultats.

## Contenu du dépôt

- bikes_regression.ipynb — Notebook principal avec l'ensemble du flux de travail (prétraitement, EDA, régression linéaire, réseaux de neurones).
- README.md — (Ce fichier) présentation et instructions.
- SeoulBikeData.csv — (non inclus dans le dépôt) jeu de données d'origine à télécharger et placer dans le même dossier que le notebook.
- (facultatif) requirements.txt — liste des dépendances Python (si fournie).

## Fonctionnalités

- Chargement et prétraitement du jeu de données (sélection de colonnes, conversion des types, filtrage d'heures).
- Visualisations exploratoires (scatter plots).
- Séparation aléatoire en ensembles train / validation / test.
- Régression linéaire simple (température vs nombre de vélos).
- Régression linéaire multiple (plusieurs variables explicatives).
- Régressions avec réseaux de neurones (normalisation, architectures simples, suivi loss/val_loss).
- Traces graphiques des predictions vs données.

## Technologies utilisées

- Python 3.x
- pandas, numpy (manipulation de données)
- matplotlib, seaborn (visualisation)
- scikit-learn (LinearRegression, métriques)
- TensorFlow / Keras (réseaux de neurones)
- imbalanced-learn (si utilisé pour sur-échantillonnage)
- Jupyter Notebook / Google Colab

## Installation

1. Cloner le dépôt :
   ```bash
   git clone https://github.com/JasserChihi/Bike-Sharing-Demand-Prediction.git
   cd Bike-Sharing-Demand-Prediction
   ```

2. (Optionnel) Créer et activer un environnement virtuel :
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux / macOS
   venv\Scripts\activate     # Windows
   ```

3. Installer les dépendances :
   - Si un fichier requirements.txt est présent :
     ```bash
     pip install -r requirements.txt
     ```
   - Sinon, installer manuellement les paquets principaux :
     ```bash
     pip install pandas numpy matplotlib seaborn scikit-learn tensorflow imbalanced-learn jupyter
     ```

## Préparation des données

1. Télécharger le jeu de données "SeoulBikeData.csv" (source : http://data.seoul.go.kr/ ou archive UCI mentionnée dans le notebook).
2. Placer `SeoulBikeData.csv` à la racine du projet (au même niveau que `bikes_regression.ipynb`), ou modifier le chemin dans le notebook.

Remarque : le notebook effectue des opérations spécifiques (ex. suppression de colonnes Date/Holiday/Seasons, filtrage pour l'heure 12h). Vérifiez les noms de colonnes si vous utilisez une version légèrement différente du CSV.

## Utilisation

- Ouvrir et exécuter le notebook localement :
  ```bash
  jupyter notebook bikes_regression.ipynb
  ```
  puis exécuter les cellules (Shift+Enter) de haut en bas.

- Exécuter dans Google Colab :
  1. Aller sur https://colab.research.google.com/
  2. Ouvrir le notebook depuis GitHub : File → Open notebook → GitHub → collez l'URL du dépôt ou du fichier `bikes_regression.ipynb`.
  3. Télécharger et monter le fichier CSV dans l'environnement Colab (ou stocker sur Google Drive).

## Résultats et visualisations

Le notebook génère :
- Plots exploratoires (scatter plots entre variables d'entrée et cible).
- Courbes d'entraînement (loss et val_loss) pour les modèles TensorFlow.
- Comparaisons entre prédictions de la régression linéaire et des modèles neuronaux.

Exemples de métriques renseignées dans le notebook :
- R² (score) pour la régression simple et multiple.
- MSE affiché par la loss des réseaux.
- Export du modèle (SavedModel / ONNX) et déploiement en API.
- Ajout d'un notebook ou script d'évaluation automatisée et d'un requirements.txt si nécessaire.

---

Auteur : Jasser Chihi  
Pour toute question, suggestion ou bug, ouvrez une issue sur le dépôt ou contactez-moi directement.
