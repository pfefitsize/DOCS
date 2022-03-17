# Rapport final

## Rappel du sujet

### Contexte

L'avènement des boutiques de prêt à porter en ligne à apporter de nouveaux besoins aux consommateurs. La solution FitSize a été imaginée pour répondre à ces besoins en facilitant au maximum le choix de la taille de nos vêtements de rêve et en limitant le nombre de retours.

### Présentation de la solution

La solution FitSize comme nous l’avons imaginé est composé de 3 applications :
Une application mobile permettant à l’utilisateur d’enregistrer ses modèles. L’utilisateur sera amené à prendre une photo de son vêtement accompagné d’un objet témoin (carte de crédit, pièce de monnaie…) sur une surface plane. Il indiquera ensuite la dimension de l’objet témoin ainsi que ses limites en plaçant 2 points sur l’image. Enfin, il placera des points de repères déterminant les dimensions de l’habit en se basant sur une photo guide.
Un serveur où seront effectués les calculs et qui enregistrera les données dans la base de données.
Un plugin web qui permet à un utilisateur de trouver la taille idéale pour le modèle qu’il consulte sur un site marchand.

Au cours de ce projet, nous avons travaillé sur l'application mobile ainsi que le backend, mais pas sur le plugin web.

## Architecture technique
### Frontend
Le frontend est la partie avec laquelle l’utilisateur va interagir et se présente ici sous la forme d’une application mobile. 
Nous avons utilisé Le framework Flutter, avec le langage Dart pour le développement de cette application. Cette technologie n’a pas été un choix de notre part, mais de la part du client. L’avantage majeur de cette technologie est qu’elle permet le développement multiplateforme. En effet, le client souhaitait que l’application soit disponible sous android et sous IOS.
L’utilisation souhaitée de cette application est de permettre à l’utilisateur de prendre en photo un habit avec un objet témoin placé à côté de ce dernier. Il faut ensuite placer des points de repères aux endroits stratégiques sur la photo, comme indiqué dans l’exemple. L’application va alors envoyer les coordonnées des points à la partie backend pour que celle-ci calcul les dimensions de l’habit. Une fois enregistré l’utilisateur pourra alors retrouver ses modèles sur la page principale de l’application. Les modèles sont enregistrés sur la base de données du serveur afin que l’utilisateur puisse changer de téléphone ou encore supprimer et réinstaller l’application sans perdre ses données. L’accès à ces données se fait donc par le biais d’une authentification sur l’application.




## Réalisations techniques
### Frontend

Nous allons vous présenter les différentes interfaces ainsi que leur fonctionnement. L’application est globalement constitué de 4 interfaces différentes qui ne sont malheureusement pas toutes terminées par manque de temps. 


#### 1. Interface de connexion

Voici l’interface de connexion d’un utilisateur. Elle ne représente pas le cœur de notre projet, c’est pourquoi nous ne l’avons pas fait de manière exhaustive. En effet, celle-ci ne réalise pas une authentification complète. Elle ne communique pas avec le Backend et redirige simplement sur l’espace l’écran d'accueil qui n’est donc pas personnalisé.


#### 2. Écran d’accueil

Voici l’interface qui permet à l'utilisateur de visualiser les modèles qu’il à déja enregistrés. Cette page affiche de manière itérative les modèles contenus dans un tableau. La version que nous aurions voulu réaliser aurait fait un appel au backend pour récupérer les modèles de l’utilisateur connecté, et ensuite pouvoir afficher les modèles de l’utilisateur courant.
Lorsque celui-ci veut enregistrer un nouveau modèle, il peut alors le faire en appuyant sur le bouton flottant avec l’appareil photo.

#### 3. Prise de photo

Pour enregistrer un nouveau modèle, l’utilisateur doit avant tout prendre son habit en photo. Cette interface est un appareil photo intégré à l’application qui affiche à l’écran directement ce que voit la caméra. Pour ceci, flutter permet d’initialiser les caméra du téléphone grâce à ses librairies.
Avant d’afficher l’appareil photo nous aurions voulu mettre une page d’informations qui permettrait d’expliquer à l’utilisateur de bien poser l’habit à plat, de prendre la photo d’au dessus, et de poser l’objet témoins à coté.

#### 4. Placement des points de repère

Après avoir pris la photo, l’utilisateur arrive sur l’interface où il devra placer les différents points de repères en suivant les instructions. 
En effet, nous aurions voulu insérer un onglet coulissant qui expliquerait comment placer les points. Il faudrait les placer dans un ordre précis selon le type d’habit, et surtout à des endroits bien précis en suivant l’exemple que nous proposerions. 
L’utilisateur peut donc placer ses points les uns après les autres, et une fois ceci terminé il peut alors valider en appuyant sur suivant.
Pour chaque point placé, les coordonnées de ces derniers sont enregistrées dans un tableau.


#### 5. Validation et objet de référence

Lorsque l’utilisateur appuie sur le bouton “suivant” de l’interface précédente, une fenêtre de dialogue apparaît alors pour demander à l’utilisateur la taille de l’objet de référence qu’il à indiquer sur l’image. La taille de l’objet est la distance entre les deux extrémités indiqués par les deux points de repères placés sur ce dernier. Cette distance sera donc la distance de référence et qui permettra alors au backend de mesurer toutes les autres dimensions nécessaires.
Lorsque l’utilisateur valide la taille qu’il a saisie, l’application envoie une requête au backend contenant les coordonnées de tous les points par rapport à l’image ainsi que la taille de l’objet de référence. Lorsque la réponse que l’application reçoit atteste que la requête a fonctionné comme il le faut, alors nous sommes redirigés sur l’écran d'accueil. 
Nous aurions souhaité pouvoir effectuer un vrai enregistrement de modèle afin que l’on puisse ensuite voir le nouveau modèle s’afficher sur l’écran d'accueil.


## Gestion de projet

### Suivi de projet

Tout au long de ce projet, nous avons rempli un document répertoriant nos avancées du jour, nos blocages, nos interrogations…

### Conception

Nous avons débuté ce projet par une phase de conception, au cours de laquelle nous avons exploré de nombreuses solutions techniques potentiellement intéressantes pour notre application. Nous avons effectué plusieurs brainstorming lors de cette phase afin d’amplifier notre créativité et découvrir des solutions innovantes.

### Backlog

Une fois la phase de conception terminée, nous avons mis en place un backlog afin de répertorier les différentes tâches nécessaires à la réalisation de ce projet. Pour chaque tâche, nous avons associé une quantité d’effort estimée ainsi qu’une priorité.

### Division des tâches

Un fois le backlog écrit, nous avons pu nous répartir les tâches. Téva Geitner a travaillé sur l’application mobile tandis que Yaël Para et Jules Gonzalez ont travaillé sur la partie backend. Au sein du backend, le travail a également été réparti pour la découverte de Django Rest Framework ainsi que pour la mise en place de l’application.

### Github

Nous avons utilisé l’outil github afin de partager le code et les documents produits. 3 dépôts ont été ouverts, le premier pour la documentation, le second pour l’application mobile (frontend) et le troisième pour le serveur (backend). Nous avons utilisé de nouvelles branches pour chaque fonctionnalité, et avons effectué des revus de code à chaque merge vers la branche principale.

### Pair programming

Pour certaines tâches, comme le calcul des dimensions et l’enregistrement du modèle utilisateur, nous avons travaillé en pair programming. Pour ce faire, nous avons mis en place des sessions de programmation partagée via l’extension Live Share présente dans visual studio code. Ces sessions nous ont permis de travailler sur le même code depuis deux machines différentes, et d’expliquer certains points de manière beaucoup plus efficace grâce à la fonction de suivi qui permet de voir les actions des autres participants en temps réel.

### Communication interne

Nous avons utilisé l’outil Discord pour la communication interne à notre équipe. Un canal vocal nous a servi quand nous travaillions à distance, et des canaux écrits étaient présents pour notifier les autres de nos avancés et blocages dans les différentes parties du projet.

### Communication client

Notre communication avec le client s’est principalement effectuée à travers des réunions bihebdomadaires à travers le service Google Meet. Ces réunions duraient entre 30 et 60 minutes. Elles avaient pour objectif de tenir le client au courant de nos avancées, de discuter des choix techniques que nous devions prendre et d’obtenir un feedback sur notre travail.

## Outils

## Métriques logiciels

## Conclusion
