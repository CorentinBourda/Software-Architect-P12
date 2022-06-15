# Solution Building Blocks

**Templates by Industry:** une matrice qui décrit les standarts utilisés dans l'industrie. Elle oit être utilisée lors de la contruction du site du client selon son industrie. Voir exemple [ici](../../../Images/33_Building_Block_Templates_By_Industry.png).


**Solution privilégiant l'apect technique:**

Afin de pouvoir propoer cette solution , il sera néssécaire de faire quelques développements préliminaires:
Il faudra mettre en place un cluster Kubernetes custom qui sera en charge de répartir les charges de travail entre les différentes nodes. Ce serveur kubernetes aurra des master nodes qui seront à même de faire l'orchestration
De plus, il faudra développer un système permettant de choisir les site atoms à stocker dans le serveur client et créer l'image de la DB en conséquence

Building blocks de la solution commerciale:

Un cluster kubernetes:
La mise en placeen place d'un cluster kerbenetes à cnfigurer entièrement pour répondre aux exigences de sécurité et de "cloisonement" des pods entre les différents clients peut se révéler assez complexe. C'est pour cela que nous aurront besoin d'un Devops expert sur cette technologie qui sera capable d'exploiter les possibilités offertes par l'outil Kubernetes.

Ajout des machines de webstreet dans le cluster Kubernetes:
Les machines de webstreet seront ajoutées au cluster en tant que worker nodes et master nodes. Nous devront donc les ajouter au fur et à mesure de l'évolution desbesoins de Webstreet en terme d'infrastructure, qui grandiront avec l'arrivée de nouveaux clietns. Cette tâche doit être réalisée par un SysAdmin

Ajout des machines du client et support:
Le client devra lui aussi ajouter se machines au cluster Kubernetes. Afin de l'aider le mieux possible, nous fournirons à son service informatique une documentation claire sur la configuration des machines à mettre en place ainsi que de comment rejoindre le cluster une fois la configuration prête. Sile client échoue dans ces opérations et ne peut pas rejoindre le cluster, nous mettrons en place un support payant à 80€ par heures de la part d'un SysAdmin

Séparation des building blocks:
Les développeurs backend devront permettre au client de choisir ,lors de configuration de son site web, de choisir parmis certains site atoms, lesquels pourront être hébergés chez lui. Cela demanera de mettre en place des communications entre les DB hébergées chez le client et celles de Webstreet.

**Solution privilégiant l'aspect commercial:**
La solution privilégiant l'aspect commercial néssécitera également de pouvoir séparer les sites atoms choisis par le client afin de les héberger séparement, cela demendera un travail de développement backend qui sera fourni par nos dévelppeurs.
De plus, la solution exigera de mettre en place un cluster Docker Swarm pour chaque client. La création d'un tel cluster devra être automatisée le plus possible afin de nous faireéconomiser des ressources DevOps

Automatisation de la création des clusters swarm:
Afin de nousfaire économiser des ressrouces de SysAdmin/ Devops, il sera important de mettre en place un process d'ajout des clusters Docker swarm qui demandera le moins d'intervention humaine possible. Il sera donc très important de pouvoir s'appuyer sur un Devops senior qui aurra la charge de concevoir un tel procesus.

Ajout des machines et support:
Un cluster Docker swarm est plus facile à rejoindre qu'un cluster kubernetes étant donné qu'il suffit que les outils Docker soient installé sur une machine Linux. Il sera tout de même nécéssaire de mettre en place une documentation à destination des services informatique des clients et de propser un SysAdmin en support payant.

Séparation des building blocks:
Idem à la séparation des sites atoms de la première solution
