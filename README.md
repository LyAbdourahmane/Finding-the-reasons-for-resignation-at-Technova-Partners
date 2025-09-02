# Analyse des causes de démission chez **TechNova Partners**

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)  
![Poetry](https://img.shields.io/badge/Poetry-dependencies-brightgreen?logo=poetry)  
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter)  
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-green?logo=pandas)  
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikit-learn)  
![SHAP](https://img.shields.io/badge/Explainability-SHAP-red)  

---

## Contexte

Vous êtes mandaté en tant que **Consultant Data Scientist** par le département RH de **TechNova Partners**, une ESN spécialisée dans la transformation digitale et la vente d’applications SaaS.  

L’entreprise fait face à un **turnover anormalement élevé** et souhaite :  
- Identifier les **causes racines des démissions**  
- Construire un **modèle prédictif explicable** pour anticiper les départs  
- Proposer des **recommandations RH actionnables** basées sur l’analyse  

---

## Objectifs du projet

1. **Analyse exploratoire** des données issues de 3 sources (SIRH, évaluations de performance, sondage interne).  
2. **Nettoyage et préparation** d’un dataset central exploitable.  
3. **Première modélisation baseline** (Dummy, Régression Logistique, Random Forest).  
4. **Modélisation avancée** avec gestion du déséquilibre, fine-tuning et interprétabilité.  
5. **Interprétation des résultats** via SHAP et importance des features.  
6. **Recommandations RH** concrètes pour réduire l’attrition.  

---

## Structure du projet

```

.
├── fichiers/              # Jeux de données (SIRH, évaluations, sondage)
├── notebooks/             # Notebooks d'analyse & modélisation
│   ├── EDA.ipynb          # Analyse exploratoire
│   ├── ModelisationSansStrategie.ipynb   # Baseline
│   ├── ModelisationStrategique.ipynb     # Modèle final
│   └── Ly\_Abdourahamane\_presentation.pdf # Support de présentation
├── poetry/
│   ├── pyproject.toml     # Gestion des dépendances
│   └── poetry.lock
└── README.md

````

---

## Installation

### Cloner le projet
```bash
git clone https://github.com/LyAbdourahmane/Finding-the-reasons-for-resignation-at-Chea-Technova-Partners.git
cd Finding-the-reasons-for-resignation-at-Chea-Technova-Partners
````

### Créer l’environnement avec **Poetry**

```bash
poetry install
```

### Activer l’environnement

```bash
poetry shell
```

### Lancer Jupyter

```bash
jupyter lab
```

---

## Étapes principales

### 1. **Exploration des données (EDA)**

* Jointure des 3 sources (SIRH, évaluations, sondage).
* Statistiques descriptives & visualisations.
* Tests statistiques (Chi², ANOVA).
* **Insights clés** :

  * Variables catégorielles (département, statut marital, heures supplémentaires) fortement liées au départ.
  * Certaines variables supprimées pour éviter la multicolinéarité (poste, domaine d’étude).

---

### 2. **Première modélisation (baseline)**

* Modèles testés :

  * Dummy Classifier
  * Régression Logistique
  * Random Forest
* But : établir un **point de comparaison** pour mesurer l’apport de stratégies plus avancées.

---

### 3. **Modélisation stratégique finale**

* Gestion du **déséquilibre des classes** (SMOTETomek – Imblearn).
* Algorithmes testés : Gradient Boosting, Balanced Random Forest, Logistic Regression.
* **Gradient Boosting** retenu pour son **équilibre entre rappel et précision**.
* Performances :

  * Recall (classe démissionnaire) ≈ **70%**
  * AUC-ROC ≈ **0.84**

---

### 4. **Interprétabilité & SHAP**

* Importance globale :

  * **Participation PEE**, **satisfaction**, **heures supplémentaires** → variables déterminantes.
  * Les données démographiques jouent un rôle secondaire.
* Importance locale (Waterfall plots) → explication personnalisée des risques individuels.

---

## Recommandations RH

**Encourager la participation au PEE** → facteur de rétention majeur.
**Suivi de la satisfaction** via mini-sondages trimestriels.
**Gérer la charge de travail** → politique claire sur les heures supplémentaires.
**Suivi des parcours professionnels** → mobilité interne, missions transversales.
**Outil de scoring RH** → utiliser le modèle Gradient Boosting comme outil d’alerte mensuel.

---

## Résultats livrables

*  **Dataset central** prêt pour la modélisation
*  **Notebooks** : EDA, baseline, modèle final
*  **Support de présentation** (PDF) pour communication RH
*  **Modèle explicable** (SHAP) pour identifier les causes racines

---

## Auteur

**Abdourahamane LY**
 [lyabdourahamane@gmail.com](mailto:lyabdourahamane@gmail.com)
 Data Scientist | Machine Learning | HR Analytics

---
