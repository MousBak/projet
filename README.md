# Base de Données Diabetes

La base de données **"Diabetes"** est disponible sur [Kaggle](https://www.kaggle.com/). Elle contient des informations sur des patientes féminines, âgées d'au moins 21 ans et issues de populations amérindiennes Pima. Ces patientes ont été examinées pour déterminer si elles avaient un diabète de type 2.

## Contenu de la Base de Données
La base de données comprend les colonnes suivantes :

- **Grossesses** : Nombre de grossesses.
- **Glucose** : Concentration de glucose dans le plasma sanguin à jeun.
- **Pression artérielle** : Pression artérielle diastolique (mm Hg).
- **SkinThickness** : Épaisseur du pli cutané tricipital (mm).
- **Insuline** : Taux d'insuline sérique de 2 heures (µU/ml).
- **IMC** : Indice de masse corporelle (kg/m²).
- **DiabetesPedigreeFunction** : Fonction pedigree du diabète.
- **Âge** : Âge en années.
- **Résultat** : Variable cible indiquant si le patient est diabétique (0 = non diabétique, 1 = diabétique).

## Objectif de l'Analyse

L'objectif de cette analyse est de construire un modèle de classification pour prédire si un patient est atteint de diabète de type 2 en fonction de ses caractéristiques cliniques.

Les étapes clés incluent :
- Division de la base de données en ensembles d'apprentissage et de test.
- Entraînement du modèle.
- Évaluation des performances du modèle.

## Processus d'Analyse

1. **Importation et Nettoyage des Données** :
   - Chargement des données depuis le fichier source.
   - Traitement des valeurs manquantes et des anomalies.

2. **Division de la Base de Données** :
   - Séparation des données en ensembles d'apprentissage (train) et de test.

3. **Préparation des Données pour le Modèle** :
   - Normalisation et encodage des variables si nécessaire.

4. **Modélisation Random Forest (Forêt Aléatoire)** :
   - Construction d'un modèle en utilisant une forêt aléatoire.

5. **Modèle avec Optimisation en Utilisant les Seuils Pratiques** :
   - Ajustement des paramètres tels que `max_features` et `n_estimators` pour améliorer les performances.

6. **Entraînement du Modèle** :
   - Entraînement sur l'ensemble d'apprentissage.

7. **Prédiction sur les Bases Train et Test** :
   - Utilisation du modèle pour prédire les résultats sur les deux ensembles.

8. **Performances du Modèle** :
   - Évaluation des performances à l'aide de métriques telles que la précision, le rappel et le F1-score.

9. **Importance des Variables** :
   - Analyse des variables ayant le plus d'influence sur les prédictions.

## Modèle avec Optimisation des Seuils Pratiques

Lorsque l'on utilise une forêt aléatoire, il est essentiel d'optimiser certains paramètres pour améliorer les performances du modèle. Les deux paramètres clés sont :

1. **max_features** :
   - Contrôle la profondeur maximale de chaque arbre de décision dans la forêt.
   - Une valeur courante est la racine carrée du nombre de variables utilisées, ce qui limite la complexité et prévient le surapprentissage.

2. **n_estimators** :
   - Détermine le nombre d'arbres de décision dans la forêt.
   - Un nombre plus élevé peut améliorer les performances mais augmente le temps de calcul.
   - Il est important de trouver un compromis entre performance et efficacité.

### Meilleures Pratiques
- Ajustez les paramètres de manière adaptée pour obtenir une forêt bien équilibrée.
- Évitez d'augmenter inutilement les arbres (« n_estimators ») lorsque les gains en performances deviennent marginaux.

En suivant ces recommandations, il est possible de construire un modèle robuste et performant pour prédire le diabète de type 2.

