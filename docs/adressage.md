# **Plan d'adressage du réseau**

L'entièreté des sites est basée sur l'adresse IP **`172.28.0.0 /16`**. 

Dû à la taille de l'entreprise, nous avons décidé d'utiliser comme masque de sous-réseau **`/19`**, permettant d'avoir 8 VLAN disponibles. 

Laissant ainsi à l'entreprise de la place pour se développer et intégrer de nouveaux sites à son infrastructure.

## **Réseau de Chartres**

| Nom de Réseau | @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----|----------|--------|----------------|----------------------|
| Management | 172.28.64.0 | 172.28.95.255 | /2 | 230
|  | 172.28..0 | 172.28..255 | /19 | 230
|  | 172.28..0 | 172.28..255 | /19 | 231
|  | 172.28..0 | 172.28..255 | /19 | 232
|  | 172.28..0 | 172.28..255 | /19 | 233
|  | 172.28..0 | 172.28..255 | /19 | 234
|  | 172.28..0 | 172.28..255 | /19 | 235
|  | 172.28..0 | 172.28..255 | /19 | 236
|  | 172.28..0 | 172.28..255 | /19 | 237
|  | 172.28..0 | 172.28..255 | /19 | 238
|  | 172.28..0 | 172.28..255 | /19 | 239