

ACL : Access control list. Les Access lists permettent de filtrer les entrées et sorties.

### ACL 


`100` : N° de l' ACL


`Permit` ou `Deny`


`in` ou `out` 



## **Liste des ACL misent en place**

| N°ACL | Application | ACL |équipement|
|---------------|---------|------------|----|
| 100 | Vlan 230 | Refuse toute les entrées et autorise le SSH  | switch |
| 10 | Vlan 233 | autorise les membres du Vlan pour accéder à internet | routeur |

</br>
ACL 100 : `permit tcp 172.28.64.0 any eq 22 ` et ` deny ip any any `


ACl 10 : `permit 172.28.64.0 0.0.31.255`