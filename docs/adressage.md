# **Plan d'adressage du réseau**

L'entièreté des sites est basée sur l'adresse IP **`172.28.0.0 /16`**. 

Dû à la taille de l'entreprise, nous avons décidé d'utiliser comme masque de sous-réseau **`/19`**, permettant d'avoir 8 VLAN disponibles. 

Laissant ainsi à l'entreprise de la place pour se développer et intégrer de nouveaux sites à son infrastructure.
</br>

![Image du switch](\img\adressage.png)

## **Réseau de Chartres**

| Nom de Réseau | @Réseau | @Diffusion | CIDR |
|---------------|---------|------------|------|
| Chartres | 172.28.64.0 | 172.28.95.255 | /19

</br>

## VLANs assignés

| Nom Vlan | @Réseau | @Diffusion | CIDR |  VLANs assignés |
|----|----------|--------|----------------|----------------------|
| Management | 172.28.64.0 | 172.28.64.255 | /24 | 230
| Serveurs Locaux | 172.28..0 | 172.28..255 | /24 | 231
|  | 172.28..0 | 172.28..255 | /24 | 232
|  | 172.28..0 | 172.28..255 | /24 | 233
| DMZ | 192.168.28.0 | 192.168.28.255 | /24 | 234
|  | 172.28..0 | 172.28..255 | /24 | 235
|  | 172.28..0 | 172.28..255 | /24 | 236
|  | 172.28..0 | 172.28..255 | /24 | 237
|  | 172.28..0 | 172.28..255 | /24 | 238
|  | 172.28..0 | 172.28..255 | /24 | 239

## VLAN 230 (Management / Administration)

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|
| Switch   | 172.28.64.254  | /24 |     | | GigabitEthernet 1/0/1         
| Hôte Management | 172.28.64.2  | /24 |  |  | GigabitEthernet 1/0/
| CHA-DNS-DMZ | 172.28.64.20 | /24 |  |  | GigabitEthernet#/#/#
| CHA-DNS-local | 172.28.64.10 | /24 |  |  | GigabitEthernet#/#/#

## VLAN 231 (Serveurs Locaux)

| Nom Hôte | @IP | Passerelle| DNS | Port assigné |
|----------|-----|--------|---------------|-----|
| CHA-DNS-local | 172.28.65.1 | 172.28.65.254 | 127.0.0.1 | GigabitEthernet#/#/#

## VLAN 232

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|

## VLAN 233

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|

## VLAN 234 (DMZ)

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|
| CHA-DNS-DMZ      | 192.168.28.1 | /24 |   | 127.0.0.1 | GigabitEthernet#/#/#

## VLAN 235

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|

## VLAN 236

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|

## VLAN 237

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|

## VLAN 238

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|

## VLAN 239

| Nom Hôte | @IP | CIDR | Passerelle    | DNS | Port assigné |
|----------|-----|--------|---------------|-----|--------------|

## DNS

nom de domaine réseau privé : local.chartres.sportludique.fr