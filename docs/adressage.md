
# **Plan d'adressage du réseau**


### **Réseau de Chartres**

| Nom de Réseau | @Réseau | @Diffusion | CIDR |      
|---------------|---------|------------|------|      
| Chartres | 172.28.64.0 | 172.28.95.255 | /19|


### Routeurs

| routeur | @Ip | interface |      
|---------|---|-----------|      
| R1-CHA | 172.28.71.10 | Gi 0/0.233|
| R1-CHA | 172.28.64.10 | Gi 0/0.230|
| R1-CHA | 221.87.128.1 | Gi 0/1
| R2-CHA | 172.28.71.20 | Gi 0/0.233|
| R2-CHA | 172.28.64.20 | Gi 0/0.230|
| R2-CHA | 183.44.28.1  | Gi 0/1
 
# Vlan

| Nom Vlan | @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----|----------|--------|----------------|----------------------|
| Management | 172.28.64.0 | 172.28.64.255 | /24 | 230
| SRV | 172.28.65.0 | 172.28.65.255 | /24 | 231
| AcInternet | 172.28.71.0 | 172.28.71.255 | /24 | 233
| DMZ | 192.168.28.0 | 192.168.28.255 | /24 | 234
| Utilisateurs | 172.28.85.0 | 172.28.85.255 | /24 | 235
| firewall | 172.28.70.0 | 172.28.70.255 | /24 | 237

### VLAN 230 Management

| Nom Hôte | @IP |
|----------|-----|
| Switch   | 172.28.64.1                
| Stormshield | 172.28.64.154 
| PFS |172.28.64.254
| DNS-local | 172.28.64.100
| DNS-DMZ | 172.28.64.110
| R1-CHA | 172.28.64.10  
| R2-CHA| 172.28.64.20 

</br>
Interface disponible pour le `Management` : ` Gi 1/0/1 à 1/0/4 ` Et ` Gi 2/0/1 à 1/0/4 ` 




### VLAN 231 Serveurs Locaux

| Nom Hôte | @IP | Passerelle|
|----------|-----|--------|
| SRV | 172.28.65.1 | 172.28.65.254 | 
| Switch | 172.28.65.254 | 

</br>
Interface disponible pour le `Serveur` : ` Gi 1/0/23 à 1/0/24 ` Et ` Gi 2/0/23 à 1/0/24 ` 


### VLAN 233 AcInternet

| Nom Hôte | @IP |  
|----------|-----|
|PFS|172.28.71.30
| VIP | 172.28.71.254 | 
| R1-CHA | 172.28.71.10 |
| R2-CHA | 172.28.71.20 |


</br>
Interface disponible pour l' `AcInternet` : ` Gi 1/0/13 à 1/0/16 ` Et ` Gi 2/0/13 à 1/0/16 ` 


Interface en mode Trunk : ` Gi 1/0/13 ` Et ` Gi 2/0/13 `


VIP : ` 172.28.71.254 ` 


### VLAN 234 DMZ

| Nom Hôte | @IP 
|----------|-----
| stormshield  | 192.168.28.1 |
| PFS  | 192.168.28.254 |

</br>
Interface disponible pour la `DMZ` : ` Gi 1/0/5 à 1/0/8 ` Et ` Gi 2/0/5 à 1/0/8 ` 



### VLAN 235 Utilisateur

| Nom Hôte | @IP | Passerelle    | DNS | 
|----------|-----|---------------|-----|
| Switch | 172.28.85.254 |
| Utilisateur Test | DHCP (.85.0) | 172.28.85.254 | 172.28.65.1 |

</br>
Interface disponible pour l' `Utilisateur` : ` Gi 1/0/17 à 1/0/18 ` Et ` Gi 2/0/17 à 1/0/18 ` 


### VLAN 237 StormShield

| Nom Hôte | @IP               | Passerelle    |  
|----------|-------------------|---------------|
| Switch   | 172.28.70.1     | 172.28.70.1 |  
| stormshield | 172.28.70.253 | 172.28.70.254 | 


</br>
Interface disponible pour l' `StormShield` : ` Gi 1/0/9 à 1/0/12 ` Et ` Gi 2/0/9 à 1/0/12 ` 


Interface en mode Trunk : ` Gi 1/0/9 ` Et ` Gi 2/0/9 `


### DNS

nom de domaine réseau privé : local.chartres.sportludique.fr
