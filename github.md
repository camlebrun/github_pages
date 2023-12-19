# Github 

## Historique
Linus Torvalds  a créé Git en 2005 pour gérer le développement du noyau Linux. Il a été conçu pour être un outil de bas niveau, permettant de gérer efficacement des projets de toute taille. Il est devenu depuis un outil incontournable pour les développeurs.
Son fonctionnement est basé sur un système de gestion de versions décentralisé. Cela signifie que chaque développeur possède une copie complète du projet sur son poste de travail. Les modifications sont ensuite synchronisées entre les différents développeurs. Cela permet de travailler en mode déconnecté et de pouvoir revenir à n'importe quelle version du projet.
Versionner son code permet de garder un historique des modifications et de pouvoir revenir à une version antérieure en cas de problème. Cela permet également de travailler à plusieurs sur un même projet sans risque de perdre des données.
Git est un logiciel libre, sous licence GPL v2. Il est disponible sur la plupart des systèmes d'exploitation (Linux, Mac OS X, Windows, etc.).
Il developper son propre sytheme de gestion de version, il a pris le meilleur de ce qui existait et a créé Git. Il a été conçu pour être un outil de bas niveau, permettant de gérer efficacement des projets de toute taille. Il est devenu depuis un outil incontournable pour les développeurs. Git signifie littéralement "abruti égocentrique et manipulateur" en argot britannique. Torvalds a nommé ainsi son logiciel en référence à lui-même, car il a créé Git pour gérer le développement du noyau Linux.

## Les outils de versionning
**Local, centralisé et distribué**

- Local: on a un dossier sur notre ordinateur. 
- Centralisé: on a un dossier sur un serveur, comme SVN. 
  - **Fichier indexé de maniére individuelle.** Mais toujours une dépendance au serveur, donc connexion internet obligatoire. Le trck est par fichier. Le binaire n'est pas versionné. On ne peux pas revenir en arrière.
- Distribué: on a un dossier sur notre ordinateur et sur un serveur.
  - On a un repo local et un repo distant. On peut travailler en local et en remote. Le workspace fait l'indexation avec le repo local puis on push sur le repo distant. 
  - GIT à une vision par snapshot.  Il réfléchie avec une vision d'ensemble. Il va prendre un instantané de l'ensemble du projet. Il va faire un hash de l'ensemble des fichiers. On peux donc revenir à l'état du système à un instant T.

## Etapes de travail
- `new_repo` : on crée un nouveau repo sur github
  - on un un remote avec l'url du repo : permet de faire le lien entre le repo local et le repo distant. La communication par **SSH** est plus sécurisé que par **HTTPS**. SSH signifie Secure Shell. C'est un protocole de communication sécurisé. Il permet d'établir une connexion chiffrée entre deux machines et d'effectuer des opérations à distance. Il est utilisé pour se connecter à un serveur distant et pour exécuter des commandes sur celui-ci. Il est également utilisé pour transférer des fichiers d'un ordinateur à un autre. 
    - clé publique : on la donne à github
    - clé privée : on la garde pour nous
- `git clone <url du repo>` : on clone le repo sur notre machine
  

## Les commandes de base

- `git init` : initialise un repo git dans le dossier courant
- `git status` : affiche l'état du repo
- `git add <nom du fichier>` : ajoute un fichier dans l'index
- `git commit -m "message"` : crée un commit avec les fichiers de l'index
- `git log` : affiche l'historique des commits
- `git checkout <hash du commit>` : se positionne sur un commit
- `git checkout <nom de la branche>` : se positionne sur une branche
- `git checkout -b <nom de la branche>` : crée une branche et se positionne dessus
- `git branch` : affiche la liste des branches
- `git merge <nom de la branche>` : fusionne une branche dans la branche courante
- `git remote add <nom du remote> <url du remote>` : ajoute un remote
- `git push <nom du remote> <nom de la branche>` : envoie les commits d'une branche locale vers une branche distante
- `git pull <nom du remote> <nom de la branche>` : récupère les commits d'une branche distante vers une branche locale
- `git clone <url du remote>` : clone un repo distant
- `git diff <nom du fichier>` : affiche les différences entre le fichier courant et le fichier dans l'index
- `git diff --staged <nom du fichier>` : affiche les différences entre le fichier courant et le fichier dans l'index
- `git diff <hash du commit> <nom du fichier>` : affiche les différences entre le fichier courant et le fichier dans le commit
- `git diff <hash du commit 1> <hash du commit 2>` : affiche les différences entre deux commits
- `git reset <nom du fichier>` : retire un fichier de l'index
- `git reset --hard` : annule tous les changements depuis le dernier commit
- `git reset --hard <hash du commit>` : annule tous les changements depuis le commit
- `git rm <nom du fichier>` : supprime un fichier
- `git mv <nom du fichier> <nouveau nom du fichier>` : renomme un fichier
- `git stash` : sauvegarde les changements non commités

## Les bonnes pratiques
- `main` ou `master` : branche principale du projet qui est protégée
- `dev` : branche de développement pour developper les fonctionnalités (user story)
  - Utilisation des conventions de commites : https://www.conventionalcommits.org/en/v1.0.0/
    - `feature/<nom de la fonctionnalité>` : branche de fonctionnalité pour développer une fonctionnalité
- `release` : branche de préparation de la release

### Les commandes avancées
- Rebase : permet de fusionner une branche dans une autre branche plus d'info [ici](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)
  - rebase interactif : permet de modifier l'historique des commits
  - rebase squash : permet de fusionner plusieurs commits en un seul
  - rebase fixup : permet de fusionner plusieurs commits en un seul en supprimant les messages des commits
- Cherry-pick : permet de récupérer un commit d'une branche dans une autre branche plus d'info [ici](https://www.atlassian.com/git/tutorials/cherry-pick)