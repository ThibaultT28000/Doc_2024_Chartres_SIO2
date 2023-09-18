# Création de VLANs sur un Cisco Catalyst 3750-X

Voici comment créer des VLANs (Virtual LANs) sur un switch Cisco Catalyst 3750-X:

1. **Connection au VLAN:** Tout d'abord nous allons nous connecter en serie ou en ssh 

2. **Accès au mode de configuration :** Une fois connecté, nous activerons le mode privilège en utilisant la commande `enable`.

3. **Accès au mode de configuration VLAN :** Ensuite, nous avons accédé au mode de configuration en utilisant la commande `configure terminal` ou `conf t`.

4. **Création d'un VLAN :** Nous avons créé un nouveau VLAN en utilisant la commande `vlan [numéro-du-vlan]`. nous avons  remplacé `[numéro-du-vlan]` par le numéro du VLAN que je souhaitais créer ici ce sera le vlan 230.

   `
   switch# configure terminal
   /
   switch(config)# vlan 230
   `

5. **Nommer le VLAN (facultatif) :** Nous modifirons également le nom du vlan par celui donné en annexe (ici ce sera Management)

   `
   switch(config-vlan)# name Management
   `

6. **Affectation des ports au VLAN :** Pour attribuer des ports spécifiques à ce VLAN, on utilisera la commande `int gi1/0/1`pour l'interface Gigabyte du switch 1 et port 1 et aprés nous utiliserons la commande `switchport access vlan 230`.

7. **Sortie et enregistrement de la configuration :** Pour quitter le mode de configuration, nous utiliserons la commande `exit` pour revenir au niveau de configuration global, puis on a sauvegardé la configuration en utilisant la commande `write memory`.

8. **Vérification de la configuration :** Après avoir créé les VLANs et attribué les ports, nous avons vérifié la configuration en utilisant la commande `show vlan` pour afficher la liste des VLANs créés et `show interfaces status` pour voir quels ports sont affectés à chaque VLAN.

9. **Enregistrement de la configuration :** Nous avons enregistrer la memoire afin que la config soit toujours dispo aprés une coupure d'electricité  `write memory`.

