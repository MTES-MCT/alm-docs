# Import de données transport

[point]: ../../../img/picto-point.png
[ligne]: ../../../img/picto-ligne.png
[surface]: ../../../img/picto-surface.png

L'import des arrêts de transport permet d'initialiser la base de données d'AccesLibre Mobilités avec des objets de transport.

Les objets suivants peuvent ainsi être créés à partir d'un import :

| Objet     | Géométrie                                   | Exemples                                                            |
| --------- | ------------------------------------------- | ------------------------------------------------------------------- |
| Quay      | ![point] point                              | arrêts de bus, quais de tramway, quais de métro, quais de gare, etc |
| StopPlace | ![surface] surface<br> ![point] point sinon | gare, station de métro, station de tramway                          |
| Entrance  | ![point] point                              | entrée de gare, bouche de métro                                     |

## Sources et formats supportés

Les sources suivantes sont supportées :

- [données NeTex](imports-transport-netex.md) : il s'agit ici d'utiliser les données publiées sur le Point d'Accès National
- [données OpenStreetMap](imports-transport-osm.md) : il s'agit ici d'utiliser les données du projet OpenStreetMap, le wikipédia des cartes

## Autres

Si vous disposez d'un jeu de données en interne d'une source ou d'un format non décrits ci-dessus, voici quelques options :

### L'affichage du jeu de données dans l'éditeur web

L'éditeur web permet d'afficher des couches de données externes en superposition du graphe. Cette option peut être pertinente par exemple si vous disposez d'une liste des abribus avec leur position et qu'ils sont peu nombreux / qu'ils n'ont pas ou peu d'attributs que l'on souhaite récupérer dans AccesLibre Mobilités.
Dans ce cas, il est possible d'afficher ce jeu de données et de "recopier" les informations qui nous intéressent.
Vous pouvez réaliser cette étape en toute autonomie : cf page afficher des données externes dans l'éditeur web (TODO lien vers page de doc à créer)

<figure markdown>
  ![capture d'écran de Yukaidi](../../../img/yukaidi_custom-layer.png)
  <figcaption>Ici, un jeu de données contenant des points a été ajouté à l'éditeur web sous la forme d'une couche de "données de carte personnalisées" (affiché en rose). On peut alors visualiser la position de chaque point et consulter ses attributs en cliquant dessus.</figcaption>
</figure>

### L'intégration du jeu de données à OpenStreetMap

AccesLibre Mobilités permet d'importer des arrêts depuis OpenStreetMap, le wikipédia des cartes.

Cette option peut notamment être pertinente si vous disposez d'un jeu de données open data publiés par l'opérateur de transport mais dont le positionnement des arrêts laisse à désirer. Si vous en avez les compétences, vous pouvez alors éditer OpenStreetMap et compléter les arrêts et les attributs déjà existants en utilisant votre jeu de données, puis réaliser un [import OpenStreetMap](imports-transport-osm.md) en autonomie.

<figure markdown>
  ![capture d'écran de Map Contrib Jungle Bus](https://nlehuby.5apps.com/images/20200901_gtfs/stops_mapcontrib_2.png)
  <figcaption>Il existe déjà des outils pour compléter OpenStreetMap en utilisant les données de transport disponibles en open data.</figcaption>
</figure>

Notre équipe peut également vous [proposer un accompagnement](../../../contact.md) pour contribuer à OpenStreetMap.

### La réalisation d'un nouveau module d'import de données transport

Si vos données sont standardisées ou normalisées ou issues d'un logiciel fréquemment utilisés par les utilisateurs d'AccesLibre Mobilités, il peut être pertinent de créer un nouveau module d'import afin de pouvoir gérer durablement ce format de données.

Notre équipe peut vous [proposer un accompagnement](../../../contact.md) pour créer ce nouveau module d'import.
