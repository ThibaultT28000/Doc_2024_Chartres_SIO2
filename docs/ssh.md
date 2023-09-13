# Compte Rendu de l'Activation du SSH sur un Cisco Catalyst 3750-X

Il nous a été demandé d'activer le service ssh afin de pouvoir administrer le switch à distance et de pouvoir eviter d'utiliser le cable série et d'avoir toujours un moyen d'administrer le switch
![Image d'un catalyst 3750-X](img\catalyst.avif)
## Étapes :

1. **Connexion à la console :** Pour accéder au commutateur, j'ai utilisé un câble de console série et un programme de terminal série, tel que PuTTY sur mon ordinateur.


2. **Accès au mode de configuration :** À partir de l'interface CLI, j'ai exécuté la commande `enable` pour accéder au mode de configuration privilégié.

3. **Configuration du nom d'hôte :** J'ai configuré le nom d'hôte du commutateur en utilisant la commande `hostname [nom-du-commutateur]`. Cela m'a permis d'identifier clairement le commutateur dans le réseau.

4. **Génération des clés SSH :** Pour activer le service SSH, j'ai généré les clés SSH en utilisant la commande `crypto key generate rsa`. J'ai spécifié la taille de la clé (ici 2048 bits mais 1024 suffisait)

5. **Configuration des paramètres SSH :** Ensuite, j'ai configuré les paramètres SSH en utilisant la commande `ip ssh version 2` pour activer la version 2 du protocole SSH, qui est plus sécurisée que la version 1. J'ai également défini les options de sécurité appropriées, telles que le timeout de connexion SSH , et également desactivé la connexion avec telnet qui n'est plus sécurisé donc une faille potentielle

6. **Identification :** Ensuite il faut donc ajouter un utilisateur qui sera `admin` et son mot de passe `P@ssw0rd123456!` grâce à la commande suivante:  username `admin` et le mot de passe `P@ssw0rd123456!` .


7. **Vérification de la configuration :** Avant de quitter le mode de configuration privilégié, j'ai utilisé la commande `show running-config` pour vérifier que toutes les modifications étaient correctement enregistrées.

8. **Enregistrement de la configuration :** Enfin, j'ai enregistré la configuration en utilisant la commande `write memory` pour m'assurer que les changements étaient persistants, même en cas de redémarrage du commutateur.

Après avoir suivi ces étapes, le service SSH était activé avec succès sur le Switch que nous avons pu verifier avec putty 
![switch](img\putty.png)
