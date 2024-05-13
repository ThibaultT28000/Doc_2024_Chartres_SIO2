# Ajout du service Reverse Proxy

## Pré-requis :
<br>
Installer le service Nginx sur la machine Debian

### Création des différents fichiers de configuration

⚠️ Ne surtout pas se tromper de certificats. Veuillez à mettre des noms de fichier permettant des les distinguer.

Il faut créer un fichier PAR site (HTTP et HTTPS peuvent être dans le même fichier tant que c'est le même site).

	---------------------------------------------------
	# FICHIER HTTP_WWW (il s'agit d'un éxemple, les autres fichiers seront juste en dessous de ça)
	upstream backend {
        server 192.168.28.120; # Adresse et port du premier serveur Apache
        server 192.168.28.121; # Adresse et port du deuxième serveur Apache
        # Ajoutez d'autres serveurs backend si nécessaire
	}

	#server {
			
	#		listen 80;
	#       server_name www.chartres.sportludique.fr;
	#       return 301 https://$host$request_uri;
	#       location / {
	#               proxy_pass http://192.168.28.120;
	#               include proxy_params;
	#       }
	#}

	server {

		    listen 443 ssl;
		    server_name www.chartres.sportludique.fr;
		    ssl_certificate /etc/certificats/www-chartres.pem;
    	    ssl_certificate_key /etc/certificats/www-chartres.pem;
    	    access_log /var/log/nginx/www_access.log;
    	    error_log /var/log/nginx/www_error.log;
    	    location / {
    	            proxy_pass http://backend;
    	            include proxy_params;
    	    }
	}

## LES FICHIERS DE CONFIGURATION

Ne pas oublier de faire de lien symbolique dans le répertoire sites-enabled

Les fichiers :

site WWW (HTTPS):

	server {

    	    listen 443 ssl;
    	    server_name www.chartres.sportludique.fr;
    	    ssl_certificate /etc/certificats/certificat_sites.pem;
    	    ssl_certificate_key /etc/certificats/passphrase.pem;
    	    location / {
        	        proxy_pass http://backend;
    	            include proxy_params;
        	}
	}

Site du Blog :

	server {

    	    listen 443 ssl;
    	    server_name blog.chartres.sportludique.fr;
    	    ssl_certificate /etc/certificats/certificat_sites.pem;
    	    ssl_certificate_key /etc/certificats/passphrase.pem;
    	    location / {
    	            proxy_pass http://192.168.28.120;
    	            include proxy_params;
    	    }
	}

Site d'Enzo :

	server {
	    listen 80;
    	server_name enzo.chartres.sportludique.fr;
	#    access_log /var/log/nginx/enzo_access.log;
	#    error_log /var/log/nginx/enzo_error.log;

	    location / {
	        proxy_pass http://192.168.28.122;
	        include proxy_params;
	    }
	}