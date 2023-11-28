

ACL : Access control list. Les Access lists permettent de filtrer les entrées et sorties.

### ACL 


`100` : N° de l' ACL


`Permit` ou `Deny`


`in` ou `out` 



## **Liste des ACL misent en place**

| N°ACL | Application |équipement|
|-------|--------|---------|
| 100 | Vlan 230 | switch  |
| 105 | Vlan 230 | routeur |
| 101 | Vlan 230 | routeur |

</br>
ACL 100 : `access-list 100 permit tcp 172.28.64.0 any eq 22 ` et ` deny ip any any `


ACl 105 : `access-list 105 permit tcp 10.28.64.0 0.0.0.255 eq 22 172.28.64.0 0.0.0.255`


ACl 105 : `access-list 105 permit tcp 172.28.64.0 0.0.0.255 any eq 22`


acl 101 : `permit udp 172.28.64.0 any eq 69`