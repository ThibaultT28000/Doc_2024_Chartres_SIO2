# **Plan d'adressage du réseau**

L'entièreté des sites est basée sur l'adresse IP **`172.28.0.0 /16`**. 

Dû à la taille de l'entreprise, nous avons décidé d'utiliser comme masque de sous-réseau **`/19`**, permettant d'avoir 8 VLAN disponibles. 

Laissant ainsi à l'entreprise de la place pour se développer et intégrer de nouveaux sites à son infrastructure.


## **Réseau de Chartres**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.64.0 | 172.28.95.255 | /19 | 240 à 249 |

</br>
plage de Vlan : 230 à 239

    Vlan de management : 230
    Vlan : 231
    Vlan : 232
    Vlan : 233
    Vlan DMZ : 234

## **Réseau de Chateauroux**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.0.0 | 172.28.31.255 | /19 | 210 à 219 |

## **Réseau de Tours**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.32.0 | 172.28.63.255 | /19 | 220 à 229 |

## **Réseau d'Orléans**

| @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----------|--------|----------------|----------------------|
|172.28.96.0 | 172.28.127.255 | /19 | 240 à 249 |