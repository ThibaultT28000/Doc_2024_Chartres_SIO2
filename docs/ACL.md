# **Liste des ACL misent en place**

ACL : Access control list. Les Access lists permettent de filtrer les entrées et sorties.

### Comment utiliser les ACL 
Après la connection au switch , passer en mode admin avec `enable` et en mode config avec `conf t` <br>
nous utilisons la commande`access-list 100 permit tcp any any eq 22` 
puis `access-list 100 deny ip any any`
pour définir l'ACL 100 qui empéchera toute communication sauf le ssh.
On configure le vlan 230 `int vlan 230`
et on lui assigne l'ACL 100 avec `ip access-group 100 in`

| N°ACL | Application | ACL |  |
|---------------|---------|------------|------|
| 100 | Vlan 230 | Refuse les entrées et autorise SSH |

