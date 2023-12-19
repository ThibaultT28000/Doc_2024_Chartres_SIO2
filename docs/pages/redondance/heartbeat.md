# Configuration de Heartbeat

## Prérequis
Installer Heartbeat sur les deux serveurs Proxy.
Intégrer les deux interfaces dans le fichier /etc/hosts

Exemple : ![fichier /etc/hosts](../../img/Redondance/Heartbeat/hosts.PNG)

Ce sera important pour le reste
### Fichiers de configuration de Heartbeat :

⚠️ Ne modifiez pas les fichiers présents dans /etc/heartbeat mais bien /etc/ha.d
⚠️ Ne surtout pas se tromper sur les noms des serveurs dans les fichiers
<br><br>
Fichier ha.cf :
![Fichier ha.cf](../../img/Redondance/Heartbeat/fichier_ha.PNG)
<br><br>
Fichier contenant la clé privée :
![Fichier clé](../../img/Redondance/Heartbeat/fichier_cle.png)
<br><br>
Fichier contenant haresources (interface VIP) :
![Fichier haresources](../../img/Redondance/Heartbeat/haresources.PNG)

<br>
Entrer la commande sudo invoke.rc heartbeat restart

Vérifiez si cela fonctionne en entrant ip a