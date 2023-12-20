

ACL : Access control list. Les Access lists permettent de filtrer les entrées et sorties.

## **Liste des ACL misent en place**

| N°ACL | Vlan |équipement|
|-------|--------|---------|
| 105 | Vlan 230 | switch  |
| 10 | Vlan 230 | routeur |
| 10 | Vlan 230 | routeur |

</br>

| N°ACL | action |protocole|IP|port|
|-------|--------|---------|---------|---------|
| 105 | permit | tcp  | 10.28.64.0  | 22 |
| 105 | permit | tcp  | 172.28.64.0 | 22 |
| 10 | permit | any  | 172.28.64.0 | any |
