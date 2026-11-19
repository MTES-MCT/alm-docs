# Exports

Une fois que votre collecte est terminée, vous pouvez exporter les données crées afin de les partager.

Plusieurs formats d'export sont disponibles.

## NeTEx Accessibilité

Le format **NeTEx Accessibilité** est le format d'échange qui a été retenu dans le cadre réglementaire en France pour publier des données d'accessibilité à la fois pour la voirie et pour les transports.
Ce format s'appuie sur NeTEx (Network Timetable Exchange), une norme européenne pour le partage d'informations de transport public sous forme de documents XML.

C'est donc le format à utiliser pour publier vos données en open data.

Plus d'informations : 

- [documentation du Point d'Accès National aux données de transport](https://doc.transport.data.gouv.fr/)
- [documentation du profil NeTEx accessibilité France](https://normes.transport.data.gouv.fr/normes/netex/accessibilite/)
- [documentation de NeTex](https://transmodel-cen.eu/index.php/netex/)


## CNIG Accessibilité

Le format **CNIG Accessibilité** est un format d'échange est un format d’échange de données
conforme au standard CNIG Accessibilité du cheminement en voirie implémenté dans
une version SIG au format GeoPackage.

ce format s'appuie sur Geopackage, un geostandard pour le stockage et l'échange de données
géographiques vectorielles.

C'est le format à utiliser pour visualiser les données dans un SIG tel que QGIS ou ArcGIS,
ou pour importer les données dans un autre logiciel de collecte compatible avec ce format.

Plus d'informations :

- [le standard CNIG Accessibilité](https://cnig.gouv.fr/ressources-accessibilite-a25335.html)
- [Le Format CNIG Accessibilité](https://github.com/cnigfr/schema-accessibilite-voirie/blob/main/Schema/format_cnig_accessibilite_geopackage/readme.md)


## Walk Data Model

Le format **Walk Data Model** est le format technique interne utilisé par AccèsLibre Mobilités.

Les données dans ce format n'ont pas vocation à ếtre publiées ou partagées.

C'est le format à utiliser pour débugger, ou pour sauvegarder les données de votre instance.

Plus d'informations :

- [modèle de données](../../datamodel)
