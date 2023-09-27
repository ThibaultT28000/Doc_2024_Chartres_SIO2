# **Liste des ACL misent en place**

ACL : Access control list. Les Access lists permettent de filtrer les entrées et sorties.

### Comment utiliser les ACL 
Après la connection à l'équipement, passer en mode admin avec `enable` et en mode config avec `conf t` <br>
Exemple : 
Nous utilisons la commande `access-list 100 permit tcp 172.28.64.0 any eq 22` 
on précise l'adresse source pour que seul les connection ssh venant du réseau `64.0` soit accepter
puis `access-list 100 deny ip any any`
pour définir l'ACL 100 qui empéchera toute communication, le ssh est implicitement autoriser.
On configure le vlan 230 `int vlan 230`
et on lui assigne l'ACL 100 avec `ip access-group 100 in` on bloque tout les entrées avec `in` alors que `out` bloque ce qui sort.

| N°ACL | Application | ACL |équipement|
|---------------|---------|------------|----|
| 100 | Vlan 230 | Refuse toute les entrées et autorise le SSH  | switch |
| 10 | Vlan 233 | autorise les membres du Vlan pour accéder à internet | routeur |

ACL 100 : `permit tcp 172.28.64.0 any eq 22 ` et ` deny ip any any `
</br>
ACl 10 : `permit 172.28.64.0 0.0.31.255`