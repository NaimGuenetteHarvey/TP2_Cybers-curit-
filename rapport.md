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
Ce correctif a pour objectif d'empêcher la modification du siteWeb à distance.
Les commandes utilisées sont "sudo chmod 750 /var/www/html" et "sudo chown -R www-data:www-data /var/www/html". 
La première commande chmod 750 permet de changer les permissions. Le 7 permet la lecture, écriture et l'exécution pour le propriétaire du dossier (www-data). Le 5 permet la lecture et exécution pour le groupe (www-data). Le 0 permet de donner aucun droit pour les autres utilisateurs comme bob. Pour la deuxième commande, elle permet de modifier le propriétaire et le groupe. Le -R applique le changement à tout le dossier. Cela permet au propriétaire d'avoir tout les permissions en retirant ceux de bob. 
Avant le correctif bob avait le droit de modifier le fichier web "Contact.html et realisation.html", car les permissions étaient pas limitées. Ensuite après avoir limiter les permissions, bob ne pouvait plus modifier les pages.
![Correctif 2 permission](Correctif 2 permission.png)


## Correctif 2 (indépendant du correctif 1)
L'endurcicement de SSH est le deuxième correctif. 
Les commandes utilisées pour mettre fin à l'étape 2/3 sont "sudo ufw status" pour pouvoir voir l'état du pare feu uwf. Il apparait "Statuts: Inactive donc il n'était pas activé. Par la suite, j'ai utilisé, "sudo ufw enable" pour activer le pare feu. Puis ensuite, j'ai utilisé "sudo ufw deny 22" pour bloquer tout le trafic qui se dirige vers le port 22 qui est le port (ssh).
Ce correctif ne permet plus à personne de se connecter à distance avec Putty, car bob se connectait au serveur grace à SSH. L'exploit est maintenant neutralisé. On peut l'appercevoir dans la photo ci-dessous, qu'il n'est pu possible d'avoir accès aux lignes de commandes.
Le site web reste accessible et continue de fonctionner puisque HTTP n'est pas affecté. 
![Correctif 1 SSH.png…]()
![SiteWeb Fonctionnel après correctif 1.png…]()


Capture d'écran de l'exploit qui ne fonctionne plus. 

## Correctif 3

Commandes à effectuer ou étapes à mettre en place. 

Capture d'écran de l'exploit qui ne fonctionne plus.
