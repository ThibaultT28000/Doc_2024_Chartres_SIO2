# Ajout du service Reverse Proxy

Fichier de configuration du serveur Reverse Proxy [**ici**](../../utilitaire/nginx.conf)

    ------------------------------------------------------------------------------
    http {
	    server {
		    #Site WEB APACHE HTTP
		    listen 80;
		    server_name www.chartres.sportludique.fr;
            	# mettre key
    		location / {
    			proxy_pass http://192.168.28.120;
    			include /etc/nginx/proxy_params;
    		}
        }

    	server {
    		# Site WEB APACHE HTTPS
    		listen 443 ssl;
    		server_name www.chartres.sportludique.fr;

    		ssl_certificate /etc/certificats/certificat_siteweb.crt;
    		ssl_certificate_key /etc/certificats/privatekey_siteweb.key;

        # ... autres directives SSL (comme ssl_protocols, ssl_ciphers, etc.)

    		location / {
    			proxy_pass http://192.168.28.120;
    			include /etc/nginx/proxy_params;
    		}
    	}

    	server {
    		# Site WEB BLOG HTTP
    		listen 80;
    		server_name blog.chartres.sportludique.fr;
    		return 301 https://$host$request_uri;
    		location / {
    			proxy_pass http://192.168.28.120; 
    			include /etc/nginx/proxy_params;
    		}
    	}

	    server {
    		# Site WEB BLOG HTTPS
    		listen 443 ssl;
    		server_name blog.chartres.sportludique.fr;

	    	ssl_certificate /etc/certificats/certificat_blog.crt;
    		ssl_certificate_key /etc/certificats/privatekey_blog.key;

    		# ... autres directives SSL (comme ssl_protocols, ssl_ciphers, etc.)

    		location / {
	    		proxy_pass http://192.168.1.120;
    			include /etc/nginx/proxy_params;
	    	}
    	}

    	server {
    		#Site WEB DOCKER HTTP
    		listen 80;
    		server_name node.chartres.sportludique.fr;

	    	location / {
	    		proxy_pass http://192.168.28.125;  #
	    		include /etc/nginx/proxy_params;
            }
        }
}


⚠️ Ne surtout pas se tromper de certificats. Veuillez à mettre des noms de fichier permettant des les distinguer.