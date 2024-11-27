# Présentation des composants

![Architecture Accèslibre Mobilités](../../img/AcceslibreMobilités.drawio.png)


## Le portail

Le point d'entrée d'une instance Accèslibre Mobilités est une interface web 
permettant aux utilisateurs de configurer leur instance et de réaliser des 
imports et exports de données.

Cette interface permet également d'accéder à l'éditeur web ainsi que de 
télécharger l'application mobile.

Elle développée en javascript avec le framwork React.

- Dépôt : [Yukaimaps Home](https://www.gitlab.com/yukaimaps/yukaimaps-home)


## Les Interfaces utilisateurs

Il existe deux interfaces utilisateurs dédiées à la saisie et à la collecte de 
données.

### L'éditeur web

Interface permettant la saisie du graphe piéton et les attributs 
d'accessibilité au bureau, en s'aidant de couches cartographiques.

Il s'agit d'une version modifiée de l'éditeur 
[iD](https://github.com/openstreetmap/iD) développé par la communauté 
OpenStreetMap.

- [Documentation utilisateur](<../../usage/web>)
- Dépôt : [Yukaidi](https://gitlab.com/yuakaimaps/yukaidi)

### L'application mobile

Application Android (smartphone et tablette), permettant de compléter sur le 
terrain les attributs d'accessibilité et de remonter des photos.

Il s'agit d'une version modifiée de 
l'application
[StreetComplete](https://github.com/streetcomplete/StreetComplete) développée 
pour la communauté OpenStreetMap.

- [Documentation utilisateur](<../../usage/mobile>)
- Dépôt : [Yukaimaps Android](https://gitlab.com/yuakaimaps/yukaimaps-android)


## Les API

Ces interfaces communiquent avec plusieurs API pour la gestion de la donnée et 
de la configuration de la plateforme.

## API métier

API Rest permettant de gérer la configuration de l'instance, les photos, ainso 
que les tâches d'import et d'export.

Il s'agit d'un développement spécifique en Python avec le framwork FastAPI.

- Dépôt : [Yukaimaps backend](https://gitlab.com/yukaimaps/yukaimaps-backend)


## API de données

API permettant de lire, stocker et mettre à jour les données d'accessibilités 
au format CNIG - Accessibilité.

Il s'agit d'une version modifiée de l'[API 
OpenStreetMap](https://github.com/openstreetmap/openstreetmap-website).

- Dépôt : [Yukaimaps website](https://gitlab.com/yukaimaps/yukaimaps-website).


## Les services


### Stockage

Le stockage de la donnée nécessite un serveur 
[PostgreSQL](https://www.postgresql.org) (version > 11).

### Authentification

L'ensemble des applications s'appuient sur le protocole OpenID Connect pour 
l'authentification. Un déploiement classique d'Accèslibre Mobilités utilise un 
serveur [Keycloak](https://www.keycloak.org) (version > 20).


### Diffusion de la donnée cartographique

Certains interfaces dont l'application mobile ont besoin d'accéder à la donnée 
selon les standards OGC (WFS, WMTS). Un déploiement classique d'Accèslibre 
Mobilités utilise un serveur [Mapserver](https://www.mapserver.org) branché sur 
la base de données PostgreSQL.


### Reverse Proxy

Dans un déploiement classique d'Accèslibre Mobilités les différents composants 
seront servis derrière un reverse proxy 
[Nginx](https://nginx.org/en/index.html).

