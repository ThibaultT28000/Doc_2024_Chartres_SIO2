# Activation SSH

## Étapes :

**Configuration du nom d'hôte :** 

`hostname SW-CHA`

**Configuration du nom de domaine:** 

`ip domain-name chartres.sportludique.fr` 

**Génération des clés SSH :**  

`crypto key generate rsa 2048`

**Configuration des paramètres SSH :** 

Active la version 2 de ssh

`ip ssh version 2`

Configuration des ligne vty de 0 à 4 qui sont utilisés pour le management a distance

`line vty 0 4`


Cette ligne indique que seul le ssh est autorisé pour les connexions distantes 


`transport input ssh`


Cette ligne indique que l'appareil utilisera les compte locaux pour l'authentification


`login local`

**Creation Compte ssh :** 

`username admin password P@ssw0rd123456!`


![switch](./img/putty.png)
