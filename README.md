#  Projet Python — Analyse de données commerciales avec Pandas

##  Objectif du projet
Ce projet vise à réaliser une analyse complète de données commerciales à l’aide de **Python et Pandas**, en respectant une démarche rigoureuse allant de l’audit des données brutes jusqu’à la production d’indicateurs clés de performance (ICP) et d’une table enrichie prête à l’analyse décisionnelle.

L’accent est mis sur la **qualité des données**, la **traçabilité des traitements** et la **cohérence méthodologique** des calculs.



##  Structure du projet

Mini_python_project

- data/
- │   ├── raw/                            
- │   └── processed/                       
- notebooks/
- │   ├── 00_main_execution.ipynb         
- │   ├── 01_data_audit.ipynb
- │   ├── 02_data_cleaning.ipynb
- │   ├── 03_ICP.ipynb
- │   └── 04_merge.ipynb
- reports/
- results/
- │   └── tables/
- .gitignore
- requirements.txt
- readme.md




##  Description des données

###  `customers.csv`
- Informations clients (âge, genre, ville, segment, date d’inscription)
- Nettoyage incluant :
  - conversion des types,
  - gestion des valeurs manquantes,
  - imputation statistique de l’âge basée sur l’asymétrie de la distribution.

###  `products.csv`
- Catalogue produits (catégorie, marque, nom, prix unitaire)
- Utilisé comme table de référence lors de l’enrichissement.

###  `order_lines.csv`
- Transactions de vente (quantité, prix, remise, montants, retours, avis clients)
- Base centrale pour le calcul du chiffre d’affaires et des ICP.



##  Étapes du projet

###  Audit des données (`01_data_audit.ipynb`)
- Analyse des dimensions, types de variables et valeurs manquantes
- Identification des anomalies potentielles

###  Nettoyage des données (`02_data_cleaning.ipynb`)
- Conversion des types (`datetime`, `numérique`)
- Traitement des valeurs manquantes
- Imputation statistiquement justifiée (moyenne ou médiane selon le coefficient d'asymétrie)
- Suppression des doublons
- Export des données propres dans `data/processed`

###  Calcul des ICP (`03_ICP.ipynb`)
- Chiffre d’affaires total et mensuel
- Panier moyen (AOV) global et mensuel
- Taux de remise (en valeur)
- Taux de retour (en valeur, global et par segment/catégorie/canal)
- Score d’avis moyen global, par catégorie et par délai de livraison
- Utilisation explicite de `groupby`, `agg`, `pivot_table`, `sort_values`, `nlargest`

###  Jointures et enrichissement (`04_merge.ipynb`)
- Jointures LEFT entre ventes, clients et produits
- Contrôle qualité des jointures
- Recalcul des montants financiers
- Détection des incohérences
- Analyse croisée du CA par segment client et catégorie produit
- Production de la table finale `orders_enriched.csv`



##  Résultats clés
- Aucune perte d’information lors des jointures
- Montants financiers cohérents après recalcul
- Forte concentration du chiffre d’affaires sur certaines catégories de produits
- Segments clients présentant des comportements d’achat différenciés

Les tables finales sont disponibles dans : results/tables



## Outils utilisés
- Python 3.13.9
- Pandas
- NumPy
- Jupyter Notebook
- Git & GitHub
- VS Code



## Exécution du projet
Pour reproduire l’analyse complète, exécuter le notebook : notebooks/00_main_execution.ipynb
Ce notebook appelle logiquement l’ensemble des étapes du projet.


## Auteurs 
- **Frantzdy DORIlUS**  

Projet réalisé dans le cadre d’un exercice académique d’analyse de données avec Python.


##  Remarque finale
Ce projet met l’accent sur la **rigueur méthodologique**, la **qualité des données** et la **reproductibilité des analyses**.

