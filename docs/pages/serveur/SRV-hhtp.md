


Login : user


Mdp : Passw0rd123456!

Ajout de 2 routes permettant d'éviter d'être bloqué par le pare-feu StormShield qui croit a une attaque [ICMP redirect](https://fr.wikipedia.org/wiki/Attaque_par_redirection_ICMP) qui sont les suivantes:

    up route add -net 172.28.0.0/16 gw 192.168.28.1 dev ens3
    up route add -net 192.168.128.0/24 gw 192.168.28.1 dev ens3
