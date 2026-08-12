# Olist E-Commerce — Projet Power BI

Projet de préparation à la certification **Microsoft PL-300 (Power BI Data Analyst)**, construit sur le jeu de données public [Brazilian E-Commerce by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (100 000 commandes, 2016-2018).

## Objectif

Reproduire un cas d'usage BI de bout en bout : ingestion de données brutes, modélisation en étoile, écriture de mesures DAX, et construction d'un rapport interactif — avec une attention particulière portée aux points couverts par l'examen PL-300 (transition de contexte, sens de filtrage, time intelligence, gouvernance).

## Structure du modèle

Le modèle suit un schéma en étoile classique :

- **Table de faits centrale** : `olist_orders_dataset`
- **Faits secondaires** : `olist_order_items_dataset`, `olist_order_payments_dataset`, `olist_order_reviews_dataset`
- **Dimensions** : `olist_customers_dataset`, `olist_products_dataset`, `olist_sellers_dataset`, `product_category_name_translation`
- **Table de dates** : `DimDate`, générée en DAX (`CALENDAR`), marquée officiellement comme table de dates

17 mesures DAX couvrant : agrégations de base, time intelligence (YTD, MTD, comparaisons de périodes), classements (`RANKX`, `TOPN`), part du tout (`ALL`), et gestion du sens de filtrage (`CROSSFILTER`).

## Rapport (4 pages)

| Page | Contenu |
|---|---|
| Accueil | KPIs clés, évolution du CA dans le temps |
| Tendances | Comparaison CA vs année précédente, croissance YoY |
| Vendeurs | Top 10 vendeurs, decomposition tree par catégorie |
| Satisfaction | Notes clients, délais de livraison, taux de retard |

## Stack

Power BI Desktop · DAX · Power Query · format `.pbip` (versionnable en TMDL)

## Source des données

[Olist Store — Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), licence CC BY-NC-SA 4.0 (usage non-commercial).

## Statut

Projet en cours, dans le cadre d'une préparation active à la certification PL-300.