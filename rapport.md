# Travail 2 par Guenette-Harvey Naim 1020
## Attaqque (exploit)
Voici les étapes détaillées pour pouvoir modifier le courriel / téléphone sur la page demandée:
-En première étape, j'ai ouvert puTTY Configuration.
-En deuxième étape, j'ai inséré dans IP address -> 192.168.220.10, Port 22 et connecté au SSH.
-En troisième étape, je me suis connecté au compte bob avec le mot de passe que j'ai trouvé, car il n'était pas bien sécurisé(Sophie2014!).
-En quatrième étape, je me suis déplacé vers le fichier contenant les pages web grâce à la commande "cd /var/www/html/".
-En cinquième étape, j'ai utilisé la commande "ls -all" pour voir tous les pages html et voir à quoi j'avais accès.
-En sixième étape, j'ai utilisé la commande "nano contact.html" pour pouvoir modifier la page contact et changer le numéro de téléphone et le lien mailto.
-En septième étape, j'ai utilisé la commande "realisation.html" pour me permettre d'enlever les images dans la page réalisation.
- En rechargeant la page, on constate que le numéro de téléphone a été modifié, les images supprimées et le courriel changé.


## Correctif 1



Capture d'écran de l'exploit qui ne fonctionne plus.

## Correctif 2 (indépendant du correctif 1)
L'endurcicement de SSH est le premier correctif. 
Les commandes utilisées pour mettre fin à l'étape 2/3 sont "sudo ufw status" pour pouvoir voir l'état du pare feu uwf. Il apparait "Statuts: Inactive donc il n'était pas activé. Par la suite, j'ai utilisé, "sudo ufw enable" pour activer le pare feu. Puis ensuite, j'ai utilisé "sudo ufw deny 22" pour bloquer tout le trafic qui se dirige vers le port 22 qui est le port (ssh).

![Uploading Correctif 1 SSH.png…]()

Capture d'écran de l'exploit qui ne fonctionne plus. 

## Correctif 3

Commandes à effectuer ou étapes à mettre en place. 

Capture d'écran de l'exploit qui ne fonctionne plus.
