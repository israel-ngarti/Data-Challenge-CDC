# Data-Challenge-CDC
## 📌 Overview

Ce projet a été réalisé dans le cadre d’un data challenge portant sur l’intégration des risques climatiques physiques dans l’analyse d’un portefeuille de crédit.

L’objectif est de transformer des données climatiques publiques en scores d’exposition exploitables financièrement, puis de mesurer l’exposition effective d’un portefeuille selon différents horizons temporels.

## 🎯 Objectifs

- Construire des scores climatiques communaux normalisés

- Intégrer ces scores à un portefeuille de crédit

- Assurer la cohérence entre horizon climatique et maturité financière

- Mesurer l’exposition des encours aux aléas climatiques

- Produire une base exploitable pour une future intégration dans un modèle de risque

## 📊 Données utilisées
### 🌦 Données climatiques

- Sources publiques (DRIAS)

- Indicateurs d’aléas physiques (ex : sécheresse)

- Points géolocalisés

### 🏘 Données territoriales

- Shapefiles communes (INSEE)

- Jointures spatiales (points → communes)

### 💼 Portefeuille de crédit

- Code INSEE

- Encours (M€)

- Maturité du prêt

- Secteur d’activité (NACE)

## ⚙️ Méthodologie
### 1️⃣ Agrégation spatiale

Jointure spatiale des points climatiques vers les communes
Calcul de la valeur moyenne par commune et par horizon (H1, H2, H3)

### 2️⃣ Construction des scores climatiques

- Normalisation Min-Max par horizon

- Construction d’un score d’exposition

- Classification en classes : Faible / Intermédiaire / Élevé

### 3️⃣ Alignement horizon financier – horizon climatique

**Mapping des maturités de prêts vers les horizons climatiques** :

- H1 : court terme

- H2 : moyen terme

- H3 : long terme

### 4️⃣ Jointure portefeuille – climat

**Jointure stricte sur** :

- Code INSEE

- Horizon climatique

### 5️⃣ Mesure d’exposition

- Taux de matching

- Identification des communes absentes

- Analyse de la part d’encours exposée

##  📈 Résultats clés

- 99 actifs analysés

- Mapping horizon réussi (0% valeurs manquantes)

- Mise en évidence d’un faible taux de matching strict (~23%), révélant :

- Des incohérences territoriales

- Des limites structurelles de couverture climatique

- Un enjeu majeur de qualité de données ESG

Ce résultat met en lumière un point crucial en modélisation climatique :
la qualité et la cohérence des données sont souvent plus déterminantes que l’algorithme lui-même.

## 🛠 Technologies

- Python

- Pandas

- GeoPandas

- Jupyter Notebook

## 🚀 Perspectives

- Extension multi-aléas

- Pondération sectorielle (NACE)

- Stress testing climatique

- Intégration dans un cadre IFRS 9 / modèle interne

- Scénarios NGFS
