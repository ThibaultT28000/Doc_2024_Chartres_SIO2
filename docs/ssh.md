# Activation du SSH sur un Cisco Catalyst 3750-X

![Image d'un catalyst 3750-X](./img/catalyst.avif)
## Étapes :

**Configuration du nom d'hôte :** 

`hostname SW-CHA`

**Configuration du nom de domaine:** 

`ip domain-name chartres.sportludique.fr` 

**Génération des clés SSH :**  

`crypto key generate rsa 2048`

**Configuration des paramètres SSH :** 

`ip ssh version 2`


`line vty 0 4`


`transport input ssh`


`login local`

**Creation Compte ssh :** 

`username admin password P@ssw0rd123456!`


![switch](./img/putty.png)
