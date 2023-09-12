# **Plan d'adressage du réseau**
<br />
L'entièreté des sites est basée sur l'adresse IP **`172.28.0.0 /16`**. 
<br />
Dû à la taille de l'entreprise, nous avons décidé d'utiliser comme masque de sous-réseau **`/19`**, permettant d'avoir 8 VLAN disponibles. 
<br />
Laissant ainsi à l'entreprise de la place pour se développer et intégrer de nouveaux sites à son infrastructure.

## **Réseau de Chateauroux**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.64.0 | 172.28.95.255 | /19 | 210 à 219 |

## **Réseau de Tours**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.64.0 | 172.28.95.255 | /19 | 220 à 229 |

## **Réseau de Chartres**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.64.0 | 172.28.95.255 | /19 | 240 à 249 |

## **Réseau d'Orléans**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.64.0 | 172.28.95.255 | /19 | 240 à 249 |