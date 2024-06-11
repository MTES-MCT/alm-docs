# Votre projet de cartographie de l'accessibilité

Réaliser la collecte des données d'accessibilité à l'échelle d'un territoire est une tâche qui ne s'improvise pas. Cette page décrit les étapes à suivre et des scénarios d'usage.

## Étapes

Un projet typique avec Accèslibre Mobilités est constitué de plusieurs étapes :

* l'installation de l'outil
* la configuration initiale : pour renseigner la zone géographique concernée, ainsi que les zones de travail
* les [imports](imports/index.md) : pour initialiser la base de données avec des données déjà existantes en interne ou en open data
* la [création du graphe piéton](web/graphe.md) : pour initialiser le réseau des trottoirs et des passages piétons, qui servira de support à la collecte terrain
* la collecte terrain : pour compléter les attributs d'accessibilité
* l'export puis la publication des données

La création du graphe piéton se fait dans [l'éditeur web](web/index.md). Il s'agit alors de créer les objets sur lesquelles des informations seront collectées : les arrêts de transport, les trottoirs, les traversées, etc

!!! abstract "Conseil"

    Créer un "bon" graphe piéton est un pré-requis indispensable à la réussite de votre projet de création de données d'accessibilité.
    
    Pour faciliter la suite de votre projet, ce graphe devra être le plus complet possible en terme d'objets, et le plus précis possible en terme de positionnement.

[La phase d'import](imports/index.md) peut permettre de raccourcir sensiblement l'étape de création du graphe dans l'éditeur web. En effet, il est possible d'importer des données déjà existantes sur les arrêts de transport, les ERP et les cheminements.

Dans certains cas, il peut même être plus pertinent d'ajouter vos données dans OpenStreetMap, d'y créer le graphe piéton puis de réaliser un import OpenStreetMap au lieu d'effectuer la saisie du graphe dans l'éditeur web Accèslibre Mobilités.

La phase de collecte terrain se fait à l'aide de l'application mobile Accèslibre Mobilités.
Le graphe piéton y est représenté et des questions (appelées quêtes) permettent de renseigner les attributs d'accessibilité.
