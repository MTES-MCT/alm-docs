# La création du graphe piéton dans l'éditeur web

Le graphe piéton désigne le réseau des trottoirs, passages piétons et autres cheminements et constitue la base de la collecte d'information dans AccesLibre Mobilités.

!!! abstract "Conseil"

    Créer un "bon" graphe piéton est un pré-requis indispensable à la réussite de votre projet de création de données d'accessibilité. Mais le dessin d'un graphe piéton complet est aussi une opération très chronophage : il est donc vivement conseillé d'avoir recours à un [import](../imports/index.md) dès que des données sont pré-existantes.

Voici les différentes étapes à suivre pour créer un bon graphe piéton avec l'éditeur web.

## Étape 1 : suivre le tutoriel de l'éditeur web

Le tutoriel vous est proposé lors de votre première utilisation de l'éditeur web.

Si vous souhaitez le refaire, vous pouvez cliquer à tout moment sur "Aide", puis commencer le guide.

## Étape 2 : les objets de transport

Commencez par renseigner les arrêts de transport:

| Objet                | Géométrie                                                                              |
| -------------------- | -------------------------------------------------------------------------------------- |
| arrêt de bus, de car | ![point] point                                                                         |
| arrêt de tramway     | ![point] point, ou ![surface] surface si on peut tracer précisément le contour du quai |

Puis renseignez les gares et stations :

| Objet         | Géométrie          | Remarque                                                                   |
| ------------- | ------------------ | -------------------------------------------------------------------------- |
| Gare routière | ![surface] surface | bien englober tous les arrêts de bus et car qui en font partie             |
| Gare          | ![surface] surface | bien englober tous les éléments de la gare : quais, bâtiment voyageur, etc |
| Station de métro |  ![surface] surface | dessiner l'emprise extérieure s'il s'agit d'une station aérienne. <br>Si la station est entièrement souterraine, un tracé approximatif reliant les bouches de métro peut suffire dans un premier temps |

Tracez également les quais de train et métro (![surface] surface) s'ils sont visibles, ou approximativement sinon.

Enfin, si vous en connaissez la position, tracez les bouches de métro, accès de gare et autres entrées, sous la forme de ![point] point, si possible situé sur le contour de la gare.

## Étape 3 : les ERP (Établissement Ouvert au Public)

Renseignez ensuite les ERP : commerces, services publics, musées, lieux de culte, etc

Utilisez de préférence une ![surface] surface, en englobant tout le contour de l'ERP. Si ce n'est pas possible, un ![point] point peut être utilisé.

Ajoutez les entrées si vous en connaissez la position, sous la forme d'un ![point] point sur le contour de l'ERP.

Enfin, les places de stationnement PMR sont parfois également visibles sur l'imagerie et peuvent être positionnées sous forme de ![point] point.

## Étape 4 : les cheminements

Il s'agit à présent de relier les arrêts de transports et les ERP, mais aussi tous les autres éléments que vous avez déjà renseignés.

Seuls les cheminements à destination des piétons doivent être tracés : trottoir, rue piétonne, chemin, escalier, passage piéton, etc

Pour les cheminements, on utilisera toujours des ![ligne] lignes.

Tracez le cheminement au moins jusqu'aux entrées des ERP et des gares.

N'oubliez pas également de relier les places PMR au reste du cheminement.

## Étape 5 : affinez

D'autres objets peuvent également être tracés, bien que plus difficiles à voir sur l'imagerie :

| Objet         | Exemples           | Géométrie          | Remarque                                                                   |
| ------------- | ------------------ | ------------------ | -------------------------------------------------------------------------- |
| les équipements | sanitaires, banc, abri voyageur, défibrillateur, guichet d'ERP, etc | ![point] point | ils peuvent être en extérieur mais aussi à l'intérieur des gares et ERP |
| les obstacles au cheminement | ressaut, poteau, barrière, etc | ![point] point positionné sur le ![ligne] cheminement où il fait obstacle | Les obstacles peuvent être également des équipements |
| les bandes d'éveil à la vigilance | | ![point] point positionné à l'extrémité du ![ligne] trottoir | |

## À tout moment

Si vous n'êtes pas sûrs, pensez à le signaler !

Lorsque l'incertitude est trop importante pour permettre de tracer un élément, vous pouvez [créer une note](astuces.md/#travailler-avec-les-notes)

!!! example "Exemples"

    * "Y a t-il un trottoir le long de cette rue ? L'imagerie aérienne ne permet pas de le voir du fait de la présence d'arbres"
    * "Vérifier si cet escalier existe toujours"

Vous pouvez également ajouter un champ "À Corriger" (tag `FixMe`) sur n'importe quel objet pour indiquer que quelque chose doit être vérifié. Par exemple : "vérifier le contour exact du quai".

## Ressources complémentaires

L'aide dans l'éditeur (raccourci clavier `H`) est un guide précieux : elle fournit des rappels utiles et des astuces sur le fonctionnement de l'éditeur. N'hésitez pas à vous y référer.

La [documentation complète du modèle de données WDM](https://gitlab.com/yukaimaps/yukaidi-tagging-schema/-/blob/main/doc/Walk_data_model.md) peut également être utile si vous avez un doute sur comment représenter tel ou tel objet.

[point]: ../../img/picto-point.png
[ligne]: ../../img/picto-ligne.png
[surface]: ../../img/picto-surface.png
