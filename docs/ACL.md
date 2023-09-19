# **Liste des ACL misent en place**

ACL : Access control list. Les Access lists permettent de filtrer les entrées et sorties.

### Commande utiliser 
après la connexion au switch `enable` et `conf t` <br>
utilisation de la commande `access-list 100 permit tcp any any eq 22` 
puis `access-list 100 deny ip any any`
pour definir l'ACL 100 qui empêchera toute communication sauf le ssh.
On configure le vlan 230 `int vlan 230`
et on lui assigne l'ACL 100 avec `ip access-group 100 in`

| N°ACL | Application | ACL |  |
|---------------|---------|------------|------|
| 100 | Vlan 230 | Refuse les entrées et autorise SSH |

