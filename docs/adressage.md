# **Plan d'adressage du réseau**

L'entièreté des sites est basée sur l'adresse IP **`172.28.0.0 /16`**. 

Dû à la taille de l'entreprise, nous avons décidé d'utiliser comme masque de sous-réseau **`/19`**, permettant d'avoir 8 VLAN disponibles. 

Laissant ainsi à l'entreprise de la place pour se développer et intégrer de nouveaux sites à son infrastructure.
</br>
## **Réseau de Chartres**

| Nom de Réseau | @Réseau | @Diffusion | CIDR |
|---------------|---------|------------|------|
| Chartres | 172.28.64.0 | 172.28.95.255 | /19

</br>

| Nom Vlan | @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----|----------|--------|----------------|----------------------|
| Management | 172.28.64.0 | 172.28.64.255 | /24 | 230
|  | 172.28..0 | 172.28..255 | /24 | 231
|  | 172.28..0 | 172.28..255 | /24 | 232
|  | 172.28..0 | 172.28..255 | /24 | 233
| DMZ | 172.28.94.0 | 172.28.94.255 | /24 | 234
|  | 172.28..0 | 172.28..255 | /24 | 235
|  | 172.28..0 | 172.28..255 | /24 | 236
|  | 172.28..0 | 172.28..255 | /24 | 237
|  | 172.28..0 | 172.28..255 | /24 | 238
|  | 172.28..0 | 172.28..255 | /24 | 239

</br>
plage de Vlan : 230 à 239

    Vlan de management : 230
    Vlan : 231
    Vlan : 232
    Vlan : 233
    Vlan DMZ : 234

## DNS

nom de domaine réseau privé : local.chartres.sportludique.fr