# Solution Building Blocks

**Templates by Industry:** une matrice qui décrit les standarts utilisés dans l'industrie. Elle oit être utilisée lors de la contruction du site du client selon son industrie. Voir exemple [ici](../../../Images/33_Building_Block_Templates_By_Industry.png).


**Solution privilégiant l'apect technique:**

Afin de pouvoir propoer cette solution , il sera néssécaire de faire quelques développements préliminaires:
Il faudra mettre en place un cluster Kubernetes custom qui sera en charge de répartir les charges de travail entre les différentes nodes. Ce serveur kubernetes aurra des master nodes qui seront à même de faire l'orchestration
De plus, il faudra développer un système permettant de choisir les site atoms à stocker dans le serveur client et créer l'image de la DB en conséquence

**Solution privilégiant l'aspect commercial:**
La solution privilégiant l'aspect commercial néssécitera également de pouvoir séparer les sites atoms choisis par le client afin de les héberger séparement, cela demendera un travail de développement backend qui sera fourni par nos dévelppeurs.
De plus, la solution exigera de mettre en place un cluster Docker Swarm pour chaque client. La création d'un tel cluster devra être automatisée le plus possible afin de nous faireéconomiser des ressources DevOps
