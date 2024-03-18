# Apprentissage Contrastif Supervisé pour la tache 5 du défi de DCASE2023

## Introduction
Dans le cadre de la tâche 5 du défi DCASE, l’étude vise à résoudre le problème de l’apprentissage à partir de peu d’exemples (few-shot learning) dans le contexte de la détection d’événements bioacoustiques. L’objectif est de développer un modèle capable de détecter des événements sonores en utilisant un nombre limité d’exemples annotés pour l'entraînement.

## Configuration de l'Environnement Conda

Pour utiliser ce projet, il faut d'abord configurer un environnement Conda avec les dépendances requises. Utilisez le fichier `environment.yml` pour créer l'environnement :

```conda env create -f environment.yml```

Ensuite, il faut activer l'environnement avec la commande suivante :
```conda activate sclEnv```

## Instructions d'Utilisation
### Création des Spectrogrammes
Tout d'abord, nous créons les spectrogrammes de l'ensemble d'entraînement :
```create_train.py``` : avec l'argument ```--traindir``` il est possible de donner le chemin vers le Training_Set

### Entrainement de l'extracteur de caractéristique
```train.py``` : avec les arguments ```--traindir``` pour donner le chemin vers le Training_Set et pour changer les hyperparamètres il faut les modifier dans le fichier ```args.py```.

### Validation du modèle 
```evaluate.py``` : avec l'argument  ```--valdir``` qui permet de donner le chemin vers le Validation_Set.

### Récupération des scores 
```evaluation_metrics/evaluation.py``` : qui prend comme argument ```-pred_file``` pour le chemin vers le fichier csv créé par ```evaluate.py```, ```-ref_files``` chemin vers le validation_Set, and ```-save_path``` pour le chemin vers le fichier json qui contiendra les scores.