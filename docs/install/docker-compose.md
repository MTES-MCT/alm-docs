Le moyen le plus simple d'installer la suite logicielle sur un serveur est 
d'utiliser la recette [Docker Compose](https://docs.docker.com/compose/) avec 
la recette fournie sur [Yukaimaps 
deploy](https://gitlab.com/yukaimaps/yukaimaps-deploy/-/tree/main/docker-compose).

Cette recette permet de déployer [l'ensemble des composants](architecture.md) 
derrière un reverse proxy Nginx.

Les variables d'environnement suivantes doivent être définies :


```
# Dossier sur le serveur hôte vers lequel stocker toute la donnée (fichiers, 
bases de données PostgreSQL)
STORAGE_PATH=/opt/alm/var/

# domaine sur lequel l'instance sera accessible
HOST=acceslibremobilites.someware.fr
# Url à laquelle l'instance sera accessible
BASE_URL=https://acceslibremobilites.someware.fr/

# Mot de passe administrateur sur le serveur keycloak
KEYCLOACK_ADMIN_PASSWORD=TgXpESo972f5
```

D'autres variables peuvent être définies pour personnaliser l'instance :

```
# Version des images docker à utiliser
YUKAIDI_VERSION=latest
YUKAIMAPS_HOME_VERSION=latest
YUKAIDI_TAGGING_SCHEMA_VERSION=latest
YUKAIDI_WEBSITE_VERSION=latest

# Sur quel port local exposer l'instance (par défaut : 8000)
EXPOSE_PORT=8000

# Depuis quel port l'instance va être accédée depuis l'extérieur si différents
# des classiques ports 80 ou 443.
# Par exemple en développement, l'instance n'est pas derrière un reverse proxy 
et on y accède directement depuis le port 8000.
HTTP_PORT=8000

# Personnalisation du client OpenID Connect utilisé par les composants
# pour l'authentification.
OAUTH_CLIENT_ID=dev.yukaimaps.someware.fr

# Personnalisation des clés publiques OAuth
OIDC_CERTS_FILE=/opt/yukaimaps/dev/oidc.yml

# Configuration de l'envoi d'emails
SMTP_RELAY=smtp-relay.gmail.com:465
SMTP_SENDER_DOMAIN=someware.fr
```

Lancement de l'instance

```
docker compose up
```

!!! bug "Attention"
    
    Le reverse proxy Nginx expose la suite sur le port `8000` en local, sans 
    SSL. Nous préconisons de placer devant un reverse proxy spécifique pour 
    effectuer la terminaison SSL.

Exemple de configuration nginx pour la terminaison SSL avec certificat SSL géré 
par [Certbot](https://certbot.eff.org/), permettant de servir l'instance sur 
l'url `https:///acceslibremobilites.someware.fr`.

```nginx
server {
    server_name acceslibremobilites.someware.fr;
    access_log /var/log/nginx/acceslibremobilites_access.log;
    error_log /var/log/nginx/acceslibremobilites_error.log;

	index index.html;

    location / {
        proxy_pass http://localhost:8000;

		proxy_read_timeout 3600;
		proxy_buffer_size          128k;
		proxy_buffers              4 256k;
		proxy_busy_buffers_size    256k;

		proxy_set_header Host $host;
		proxy_set_header X-Forwarded-Host $host;
		proxy_set_header X-Forwarded-PORT $server_port;
		proxy_set_header X-Real-IP $remote_addr;
		proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
		proxy_set_header X-Forwarded-Proto $scheme;
	}


    listen 443 ssl; # managed by Certbot
    ssl_certificate /etc/letsencrypt/live/acceslibremobilites.someware.fr/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/acceslibremobilites.someware.fr/privkey.pem; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot

}
# redirection systématique vers https
server {
    if ($host = acceslibremobilites.someware.fr) {
        return 301 https://$host$request_uri;
    } # managed by Certbot


    server_name acceslibremobilites.someware.fr;
    listen 80;
    return 404; # managed by Certbot
}
```


!!! abstract "Conseil"

    Pour pouvoir répondre à plusieurs utilisateurs simultanés, nous préconisons 
    les ressources matérielles suivantes :

    - Une machine virtuelle Linux (Debian stable ou Ubuntu LTS)
    - processeur x86-64 avec 8 cœurs
    - RAM 16 GB
    - Disque SSD 200 GB

