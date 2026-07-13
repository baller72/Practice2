# 📝 Notes de Développement

## Objectif

Ce document regroupe les différentes notes prises au cours du développement du projet. Il sert de carnet de bord technique et permet de conserver les décisions importantes concernant le nettoyage des données, le choix des modèles et les expérimentations réalisées.

---

# Journal de progression

## Phase 1 — Prise en main des données

- Chargement des deux jeux de données.
- Inspection des types de données.
- Vérification des valeurs manquantes.
- Identification des variables numériques et catégorielles.

---

## Phase 2 — Prétraitement

### Dataset Housing

Actions réalisées :

- Suppression de `IdentifiantMaison`
- Imputation des variables numériques par la médiane
- Imputation des variables catégorielles par le mode

Remarque :

L'identifiant ne possède aucune valeur prédictive.

---

### Dataset Employee

Actions réalisées :

- Suppression de `ID_Employe`
- Encodage de la variable cible (`Satisfait`)
- Encodage Ordinal
- Encodage Binaire
- One-Hot Encoding

Remarque :

Chaque méthode d'encodage a été choisie selon la nature de la variable.

---

# Analyse Exploratoire

Observations intéressantes

## Housing

- Les maisons les plus grandes présentent généralement un loyer plus élevé.
- Les quartiers influencent fortement les prix.
- La présence d'un jardin ou d'un parking augmente souvent le loyer.

---

## Employee

- Les employés ayant davantage d'heures supplémentaires semblent moins satisfaits.
- L'équilibre vie professionnelle / vie personnelle paraît fortement corrélé avec la satisfaction.
- Les absences sont généralement plus nombreuses chez les employés non satisfaits.

---

# Expérimentations

## Régression

Modèle testé :

- Linear Regression

Améliorations possibles :

- Random Forest Regressor
- Gradient Boosting
- XGBoost
- LightGBM

---

## Classification

Modèles testés :

- Logistic Regression
- Decision Tree

Modèles à tester ultérieurement :

- Random Forest
- Support Vector Machine (SVM)
- K-Nearest Neighbors
- XGBoost Classifier
- CatBoost

---

# Améliorations futures

## Data Engineering

- Ajouter davantage d'observations.
- Détecter automatiquement les valeurs aberrantes.
- Mettre en place un pipeline reproductible.

---

## Feature Engineering

Idées :

- Prix au m²
- Ancienneté normalisée
- Ratio salaire/ancienneté
- Variables d'interaction

---

## Machine Learning

Tester :

- Validation croisée
- Grid Search
- Random Search
- Feature Importance
- SHAP Values

---

# Bonnes pratiques retenues

Toujours :

- Séparer Train/Test avant l'entraînement.
- Éviter toute fuite de données.
- Utiliser des Pipelines Scikit-Learn.
- Sauvegarder les modèles.
- Versionner le code avec Git.

---

# Idées d'évolution

Le projet pourrait évoluer vers :

- une API REST avec FastAPI ou Flask ;
- une interface Streamlit pour les prédictions ;
- un tableau de bord Power BI ou Tableau ;
- un déploiement dans le cloud (Docker + Render, Railway ou Azure).

---

# Notes personnelles

Points à retenir :

- Toujours commencer par comprendre les données avant de choisir un modèle.
- Un modèle performant dépend davantage de la qualité des données que de sa complexité.
- Les métriques doivent être choisies selon le problème étudié.