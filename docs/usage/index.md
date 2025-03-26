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

La phase de collecte terrain se fait à l'aide d'une des applications de relevés proposées par Accèslibre Mobilités :

- l'**application de collecte didactique** se veut simple à utiliser y compris pour des utilisateurs non experts en accessibilité. Cette application mobile (disponible sur Android uniquement) affiche le graphe piéton et propose des questions (appelées quêtes) qui permettent de renseigner les attributs d'accessibilité.
- l'**application de collecte industrielle** est à destination des utilisateurs déjà experts en accessibilité et fin connaisseurs du modèle de données CNIG. Cette application web affiche le graphe piéton et propose des formulaires compacts listant les attributs obligatoires à collecter.

## Scénarios d'usage

Il existe plusieurs manières de mener votre projet de collecte de données d'accessibilité, en fonction du périmètre, de votre budget, des données déjà disponibles en interne au moment du lancement du projet, de vos outils habituellement utilisés par vos équipes, etc

Voici quelques exemples :

- mener tout votre projet avec Accèslibre Mobilités

AccèsLibre Mobilités vous permet de définir vos zones de travail, d'importer des données déjà disponibles, de tracer un graphe piéton et propose plusieurs outils pour réaliser la collecte sur le terrain des attributs d'accessibilité.

- faire tout ou partie du projet avec OpenStreetMap

OpenStreetMap est une base de données géographique mondiale et elle permet notamment de décrire la voirie. La plupart des attributs attendus en terme d'accessibilité peuvent être décrits dans OpenStreetMap. Accèslibre Mobilités, qui permet d'importer les données OpenStreetMap d'un territoire, peut venir compléter la démarche.

- faire tout ou partie du projet avec QAccess

!!! bug "Attention"

    Cette démarche est encore expérimentale.

Nous vous conseillons d'être [accompagnés](../contact.md) en amont de votre projet afin de choisir la stratégie la plus adaptée à vos besoins et contraintes.