#  Projet Power BI – Nettoyage et Analyse de Données Produits eCommerce

## Objectif

L'objectif de ce projet est de **préparer**, **nettoyer**, **enrichir** et **analyser** un jeu de données e-commerce contenant des informations sur des produits. Le tout est visualisé dans Power BI pour en faciliter l'interprétation

## Étapes réalisées

### Niveau 1 — Préparation des données

* Suppression de la colonne `ProductSubcategoryKey`
* Remplacement des valeurs nulles dans `ProductColor` par `"Unknown"`
* Standardisation des types de données (`ProductCost`, `ProductPrice` en décimal ; `ProductSize` en texte)
* Remplacement des valeurs `0` dans :

  * `ProductSize` → `"Not specified"`
  * `ProductStyle` → `"Standard"` ; `"U"` → `"Unisex"`

### Niveau 2 — Enrichissement

* Création d’une colonne `ProfitMargin` = `ProductPrice - ProductCost`
* Création d’une colonne `Rentabilite` :

  * `"Rentable"` si la marge > 20
  * Sinon `"Faible marge"`
* Nettoyage des espaces dans `ProductDescription`

### Niveau 3 — Analyse et filtrage

* Filtrage des produits avec une marge > 50
* Liste des produits avec couleur `"Unknown"`
* Identification des modèles avec des prix différents

## Visualisations & KPI Power BI

### A. KPI Cards

* **Nombre total de produits** : `COUNT(ProductKey)`
* **Coût moyen** : `AVERAGE(ProductCost)`
* **Marge moyenne** : `AVERAGE(ProfitMargin)`

### B. Graphiques

* Moyenne de `ProfitMargin` par `ModelName`
* Nombre de produits par `Rentabilite` et `ProductStyle`
* Moyenne de prix et coûts par `ProductColor`
* Variantes par `ModelName` et `ProductStyle`
* Hiérarchie de produit : `ModelName > ProductName > ProductSKU`

