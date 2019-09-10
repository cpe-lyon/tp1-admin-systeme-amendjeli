# Compte Rendu TP1

## Exercice 2

### Manuel

#### 1) A l’aide du manuel, identifiez le rôle de la commande which

* **which** retourne le chemin des fichiers qui seraient exécutés dans l'environnement courant si ses arguments avaient été donnés comme commandes dans un interpréteur de commandes strictement conforme à POSIX. Pour ce faire, **which** cherche dans la variable PATH les fichiers exécutables correspondants aux noms des arguments.

#### 2) Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option ?

* Il suffit de preceder le terme recherché par un **'/'** 
  >`/option`

#### 3) Comment quitte-t-on le manuel ?

* En appuyant sur la touche **q**

#### 4) Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?

* il suffit d'écrire
    >`man 6 intro`

    Cette section parle des jeux-vidéos et d'autres petits programmes

### Navigation dans l’arborescence des fichiers

#### 1) allez dans le dossier /var/log

*   >`cd /var/log`

#### 2) remontez dans le dossier parent (/var) en utilisant un chemin relatif

*   >`cd ..`

#### 3) retournez dans le dossier personnel
*   >`cd ../home/asseel` 

#### 4) revenez au dossier précédent (/var)

*   >`cd ../../var` 

#### 5) essayez d’accéder au dossier /root ; que se passe-t-il ?

*   >`cd /root` 

    Le terminal affiche permission refusée

#### 6) essayez la commande sudo cd /root ; que se passe-t-il ? Expliquez

*   >`sudo cd /root` 

    Cela ne marche pas car cd est une commande interne et non un programme

#### 7) à partir de votre dossier personnel, créez l’arborescence suivante :

*   >`cd ../home/asseel` 

    >`cd ../home/asseel`

    >`mkdir Dossier1`

    >`cd Dossier1/`

    >`touch Fichier1`

    >`cd ..`

    >`mkdir Dossier2`

    >`cd Dossier2`

    >`mkdir Dossier2.1`

    >`mkdir Dossier2.2`

    >`cd Dossier2.2`

    >`touch Fichier2`

    >`touch Fichier3` 

#### 8) revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1 ; que se passe-t-il ?

*   >`cd ../..`

    >`rm Fichier1`

 Il refuse de supprimer le Fichier1, il ne trouve pars le fichier/repertoire

   >`rm Dossier1`

 Il refuse de supprimer Dossier1 car c'est un dossier

#### 9) quelle commande permet de supprimer un dossier ?

* >`rmdir `

#### 10) que se passe-t-il quand on applique cette commande à Dossier2 ?

* >`rmdir Dossier2`

    Il est impossible de suppprimer le dossier car il n'est pas vide

#### 11) comment supprimer en une seule commande Dossier2 et son contenu ?

* >`rm -r Dossier2`

### Commandes importantes

#### 1) Quelle commande permet d’afficher l’heure ? A quoi sert la commande time ?

* >`date`

    La commande time donne le temps necessaire pour que l'ordinateur utiliser la commande associée a "time" tel 

    >`time ls`

#### 2) Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire sur les fichiers commençant par un point ?

* On peut en deduire que les fichier commencant par un point sont des fichier cachés

#### 3) Où se situe le programme ls ?

* Le programme **ls** se situe dans le dossier personnel.

#### 4) Que fait la commande ll ?

* Affiche des informations détaillées sur les fichiers

#### 5) Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?


* **ls** mais il sera necessaire d'utiliser la pour afficher les dossiers cachés

#### 6) Que fait la commande ls .. ?

*  **ls** .. permet de voir les fichiers contenus dans le dossier precedant le notre

#### 7) Quelle commande donne le chemin complet du dossier courant ?

*  la commande **pwd**

#### 8) Que fait la commande echo 'yo' > plop exécutée 2 fois ?

* Cette commande crée un fichier plop avec ecrit 'yo' dedans, la deuxiele execution ecrit yo a la place du yo preécédant

#### 9) Que fait la commande echo 'yo' >> plop exécutée 2 fois ?

* Cette commande crée un fichier plop avec ecrit 'yo' dedans, la deuxiele execution ecrit yo au dessous du yo precedant dans le fichier

#### 10) A quoi sert la commande file ? Essayez la sur des fichiers de types différents.

file est une commande UNIX qui permet de déterminer le type d'un fichier.

#### 11) Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi : qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?

* >`echo 'Hello Toto !' > toto`

    >`ln toto titi`

    >`cat toto`

    Apres la commande cat le text du fichier est affiché et affiche **Hello Toto**

    >`cat titi`

    Le meme texte est affiché

    >`echo 'Hello Titi !' > toto`

    >`cat titi`

    Cette fois **Hello titi** est affiché

    >`rm toto`

    >`cat titi`

    Le fichier s'affiche meme apres la suppression du fichier originel

#### 12) Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle conséquence cela a-t-il sur tutu ?

* >`-s titi tutu`

    >`cat tutu`

    Apres la commande cat le text du fichier est affiché et affiche **Hello Tutu**

    >`cat titi`

    Le meme texte est affiché

    >`echo 'Hello Titi !' > tutu`

    >`cat titi`

    Cette fois **Hello tutu** est affiché
    cela marche aussi dans le sens inverse 

    >`rm titi`

    >`cat tutu`

    Le fichier s'affiche meme apres la suppression du fichier originel

#### 13) Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ?

* pour interrompre l'ecran : 

    >'Ctrl+s'

    Pour revenir au défilement : 

    >'Ctrl+q'

#### 14) Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20.

* Pour afficher les 5 premières lignes du fichier var/log/syslog il faut effectuer la ligne de commande suivante :

    >`head -5 /var/log/syslog`

    Pour afficher les 15 dernières lignes du fichier var/log/syslog il faut effectuer la ligne de commande suivante :

    >`tail -15 /var/log/syslog`    

    Pour afficher les lignes 10 à 20 du fichier var/log/syslog il faut effectuer la ligne de commande suivante :

    >`head -n 10 /var/log/syslog | tail -n 20`

#### 15) Que fait la commande dmesg | less ?

* Cette commande permet de visualiser la memoir tampon du noyeau

#### 16) Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page de manuel de ce fichier ?

* Le fichier **/etc/passwd** contient des informations liés aux utilisateurs de type login, mots de passe, etc... Il est accessible via la commande :

    >`cat /etc/passwd`

    Pour ouvrir le manuel il faut effectuer la commande suivante :

    >`man passwd`

#### 17) Affichez seulement la première colonne triée par ordre alphabétique inverse

*  >`sort +0 -r /etc/passwd`

    Cette commandepermet d'afficher seulement la première colonne triée par ordre alphabétique inverse.

#### 18) Quelle commande nous donne le nombre d’utilisateurs ?

* >`wc -l /etc/passwd`

    il y a donc 30 utilisateurs.

#### 19) Combien de pages de manuel comportent le mot-clé conversion dans leur description ?

* >`man -k conversion`

    4 pages du manuel comportant le mot "conversion".

#### 20) A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine

* >`find / -name passwd`

    Cette commande permet de lister tout les fichiers se nommant **passwd** 

#### 21) Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null

* >`find / -name passwd > ~/list_passwd_files.txt 2>> /dev/null`

    Cette commande permet de repertorier tout les fichiers se nommant **passwd** dans le fichier ~/list_passwd_files.txt et de rediriger les erreurs dans le fichier /dev/null

#### 22) Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment

* >`grep -ll`

    l'alias **ll** est défini dans grep [OPTION]... PATTERNS[FILE]...

#### 23) Utilisez la commande locate pour trouver le fichier history.log

* >`locate history.log`

    history.log est situé :
    
    >/var/log/apt/history.log

#### 24) Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ?

Le fichier n'apparaît pas car il n'est pas inclus dans la base de données des fichiers indéxés.

## Exercice 4

#### 1) Commencez par créer une copie de ce fichier, que vous appellerez .bashrc_bak

* >`cp ~/.bashrc .bashrc_bak`

#### 2) Editez le fichier .bashrc avec nano et décommentez la ligne force_color_prompt=yes pour activer la couleur. Enregistrez le fichier et quittez nano.

* >`nano ~/.bashrc`

#### 3) Le fichier .bashrc est lu au démarrage du shell ; pour le recharger, il faudrait donc se déconnecter puis se reconnecter ; mais il existe un autre moyen : la commande source .bashrc. Testez-la, l’invite de commande devrait immédiatement passer en couleurs.

* >`source .bashrc`

    L'invité de commande devient en effet vert

#### 4) Modifiez l’invite de commande pour qu’elle s’affiche sous la forme suivante : [heure] - user@host:chemin_courant$

* Pour cela il faut replacer cette sequence

>`\[\033[1;32m]\u@\h\[\033[00m\] `

    par celle-ci dans le PS1= :

>`\[\e[35m\A\e[0m-\[\033[1;32m]\u@\h\[\033[00m\] ` 

    puis activer les changements

>`source .bashrc`

Le resultat est donc conforme a ce qui est attendu.
