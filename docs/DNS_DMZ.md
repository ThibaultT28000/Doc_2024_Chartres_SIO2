#DNS Redirecteur#
VM linux. Configuration DNS avec BIND9

###named.conf.local###

    -----------------------------------------------------------
    //zone extérieur
    view "outside" {

        //Sauf 172.28.64.0/19, rediriger vers l'ip publique
        match-clients { !172.28.64.0/19; };

        zone "chartres.sportludique.fr." {

            type master;

            file "/etc/bind/db.www.chartres.sportludique.fr";

        };

    };



    view "inside" {

        match-clients { 172.28.64.0/19; };

        zone "chartres.sportludique.fr." {

            type master;
            
            file "/etc/bind/db.www.chartres.sportludique.fr.internal";

        };

    };


###named.conf.default-zones###
Toutes les lignes du fichier `named.conf.default-zones` sont mises `en commentaire` pour désactiver le DNS global. Cela permet de configurer les zones DNS de manière sélective en utilisant la fonctionnalité `view`.

###Fichier de zones###

#####Zone externe (outside)#####

    ----------------------------------------------------------------------------------------
    ; BIND data file for local loopback interface
    ;
    @       IN      SOA     ns1.chartres.sportludique.fr. admin.chartres.sportludique.fr. (
                2023101701      ; Serial
                604800          ; Refresh
                86400           ; Retry
                2419200         ; Expire
                604800 )        ; Negative Cache TTL
    ;
    @       IN      NS      ns1.chartres.sportludique.fr.
    ns1     IN      A       183.44.28.1
    www     IN      A       221.87.128.2
    www     IN      A       183.44.28.1


#####Zone interne (inside)#####

    ----------------------------------------------------------------------------------------
    ;
    ; BIND data file for local loopback interface
    ;
    @       IN      SOA     ns1.chartres.sportludique.fr. admin.chartres.sportludique.fr. (
                2023101701      ; Serial
                604800          ; Refresh
                86400           ; Retry
                2419200         ; Expire
                604800 )        ; Negative Cache TTL
    ;
    @       IN      NS      ns1.chartres.sportludique.fr.
    ns1     IN      A       192.168.28.115
    www     IN      A       192.168.28.120