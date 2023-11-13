 
 
#  DNS redirecteur  

 
    --------------------------------------------------------------------
    options {
            directory "/var/cache/bind";

            recursion yes;

            //autorisation de redirection des ip 
            allow-query { 172.28.64.0/19; 127.0.0.1; 192.168.28.0/24; };
            forwarders {
                    121.183.90.205;
            };

            dnssec-validation no;

            listen-on {any;};
    };