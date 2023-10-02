# Configuration DHCP

## Introduction
<br>
Après avoir installé le DNS, il faudra installer un service DHCP pour attribuer des adresses aux hôtes présents dans le réseau. Notamment ceux du VLAN 235 (Utilisateurs locaux du serveur privé) qui n'ont aucun serveur dans leur VLAN. Il faudra donc créer une plage s'adaptant au réseau que l'on a attribué à ce VLAN.
<br>

## Création de l'étendue

<br>

Après avoir installé le rôle, je vais créer l'étendue dans les paramètres du serveur DHCP.

<br>

| @Plage de début | CIDR | @Plage de fin | @Passerelle | @DNS | Plage exclue |
|-----------------|------|---------------|-------------|------|--------------|
| 172.28.85.1     | /24  | 172.28.85.253 | 172.28.85.254 | 172.28.65.1 | 85.1 - 85.10

<br>

Plage d'adresse mise en place :
<br>

![Plage d'adresses exclues](./img/DHCP/plage_exclue.PNG)
<br>

Configuration des autres paramètres sur l'étendue DHCP :

![Toutes les configurations apportées](./img/DHCP/config_resultats.PNG)

Désormais, il faut vérifier si le serveur a été configuré correctement. On va devoir réaliser un test sur une machine VirtualBox qui est connectée au VLAN 235 via nos switchs.

## Test du DHCP sur une machine cliente

Changement de l'@ IP sur la machine **`ipconfig/release`** et **`ipconfig/renew`** après avoir mis l'adresse du serveur DHCP en tant que DNS.

![Test ipconfig réussi](./img/DHCP/test_DHCP.png)