# B1 Réseau 2018 - TP3

## Créaton et utilisation simple d'une VM CentOS

### Configuration réseau d'une machine CentOS

a. Pour prouver la conection a internet depuis la VM il faut taper la commande
  `curl -SL www.google.com`
  
b. Pour prouver que la VM et ma machine communique il suffit de ping la VM avec la machine et inversement comme fait dans le TP précédent 

c. Pour afficher la table de routage il faut taper la commande
   `ip route`
   Je ne saurais expliquer les lignes que cette commande affiche 
   
### Faire joujou avec quelques commandes 

Pour le ping et l'affche de la table de routage cf plus haut
Pour télécharger un ficher depuis la VM il faut taper la commande
  `curl -SLO l'adresse a télécharger`
  
Pour utiliser la commande `dig` il faut d'abord l'installer. 
J'ai utilisé:
`sudo yum install bind-util`
Puis:
`dig ynov.com`
`dig google.com`

## Notion de ports et SSH

### Exploration des ports locaux

Pour lister les ports TCP sur lesquels la machine virtuelle écoute il faut utiliser la commande ss suivis des options:
* -t pour les ports TCP
* -l pour les ports en écoute
* -n pour le numéro du port
* -p pour l'application qui écoute

![screen_Nmap](/Images/1.png)

### SSH

![screen_Nmap](/Images/2.png)

### Firewall

A. `nano /etc/ssh/sshd_config` pour modifier le ficher, supprimer le diese devant "port" et mettre 2222.
Puis redémarrez le serveur SSH pour que le changement prenne effet: `systemctl restart sshd`
La connection au serveur en utilisant le client SSH ne fonctionne pas car il faut autoriser les connexions sur le port TCP 2222 :
`firewall-cmd --add-port=2222/tcp --permanent`

B.








