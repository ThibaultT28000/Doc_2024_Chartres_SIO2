# Activation GLBP 


## Étapes :

**Configuration de l'interface pour GLBP :**

`Gi0/0.233 (notre interface de transport)`


Definit l'adresse VIP (Virtual IP) GLBP à 172.28.71.254 


`glbp 1 ip 172.28.71.254` 


`glbp 1 preempt` 

Permet de mettre le load-balancing en round-robin

`glbp 1 load-balancing round-robin`


Sur le routeur 2 , il faut faire :


`glbp 1 ip 172.28.71.254`

`glbp 1 load-balancing round-robin`

Et voilà , GLBP est desormais actif et fonctionnel .
