# Classification des Données d’Imagerie Cérébrale de la Maladie d’Alzheimer à l’Aide de l’Apprentissage Profond

Ce dépôt contient l'implémentation de la préparation des données, du filtrage, et de la classification des images IRM provenant de la base de données ADNI. Le processus inclut l'organisation des données en format voxel, le filtrage à l'aide du clustering K-means, et l'entraînement d'un modèle VGG16 pour la classification de la maladie d'Alzheimer. Le dépôt est structuré en deux ensembles de données : **données traitées** et **données non traitées**.

## Structure du Dépôt

- **organisation.ipynb** : Ce notebook contient le code pour l'analyse et l'organisation des dossiers. Il inclut également la transformation des données de la base ADNI en format voxel, essentielle pour les étapes suivantes, y compris le clustering K-means.
  
- **filtrage_k_means.ipynb** : Ce notebook implémente le filtrage des données en utilisant l'algorithme K-means, produisant un jeu de données prêt pour le traitement d'images et l'entraînement du modèle.
  
- **traitement.ipynb** : Ce notebook couvre les étapes de traitement d'image, y compris le filtre gaussien, l'extraction du crâne, et la segmentation. À la fin de cette étape, nous obtenons deux jeux de données :
  1. Un **jeu de données traité** avec des images entièrement traitées.
  2. Un **jeu de données non traité** obtenu directement à partir du filtrage K-means, sans traitement d'image supplémentaire.

## Jeux de Données

Vous pouvez accéder aux jeux de données utilisés dans ce projet sur Kaggle :

- **Jeu de données traité** : [Images IRM (AD, CN, MCI) traité](https://www.kaggle.com/datasets/medjbertoufik/irm-images-adni-adcnmci)
- **Jeu de données non traité** : [Images IRM (AD, CN, MCI) non traité](https://www.kaggle.com/datasets/medjbertoufik/kmeans-nonsegm)

## Entraînement et Classification avec le Modèle VGG16

Le dépôt contient deux répertoires pour l'entraînement et le test du modèle VGG16 :

1. **VGG16 dataset traité** : Ce répertoire contient tout le code pour l'entraînement, la classification, et le test du modèle VGG16 en utilisant le jeu de données traité. Il inclut :
   - La classification en 3 classes : Maladie d'Alzheimer (AD), Normal Cognitivement (CN), et Déficit Cognitif Léger (MCI).
   - Les tâches de classification binaire : CN vs. MCI, CN vs. AD, et MCI vs. AD.

2. **VGG16 dataset non traité** : Ce répertoire contient un code similaire, mais utilise le jeu de données non traité pour l'entraînement et la classification du modèle.

## Résultats
Le modèle VGG16 a été entraîné et évalué sur :

Classification en 3 classes : AD, CN, MCI.
Classifications binaires : CN vs. MCI, CN vs. AD, MCI vs. AD.

## Instructions d'Utilisation

1. Clonez ce dépôt sur votre machine locale :
   ```bash
   git clone https://github.com/touXik/PFE_Master.git
  
2. Exécutez les notebooks dans l'ordre suivant :
   organisation.ipynb
   filtrage_k_means.ipynb
   traitement.ipynb
3. Choisissez le jeu de données souhaité (traité ou non traité) pour entraîner le modèle VGG16.
4. Utilisez le code dans les répertoires VGG16 dataset correspondants pour l'entraînement, la classification, et l'évaluation.
