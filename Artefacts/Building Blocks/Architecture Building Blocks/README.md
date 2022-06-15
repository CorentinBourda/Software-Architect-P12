# Architecture Building Blocks
**Solution privilégiant l'apect technique:**

![Shéma récapitulatif de la solution privilégiant l'apect technique](../../../Images/diagrammeSolutionTechniqueWebstreet.png "Shéma récapitulatif de la solution privilégiant l'apect technique")
Cette solution visant à fournir une répone technique à la probèmatique consiste à mettre en comun des ressources d'infrastructure réseau entre les différents sites des clients par le moyen d'un cluster Kubernetes:
Nous mettrons à disposition des serveurs de très grande capacité qui seront partagées entre les clients. Chaque client se vera attribuer un minimum de 2 nodes qui seront dans des serveurs situés dans des availaibility zones différentes
Cette solution présente de nombreux avantages:
- Une fois la solution mise en place, la mise en place d'une nouvelle application d'un client est très rapide, il suffit de faire entrer le serveur du client dans le cluster kubernetes et de créer les pods coté Webstreet en ligne de commande
- L'utilisation de grands serveurs coté webstreet permet de grandement faciliter le scale des applications, une applicatiopn peut absorber un pic de connexion plus élevé si les autres ont peu de connexion
- Kubernetes est un système d'orchestration des nodes qui sait gérer les ressources de façon inteligente et  optimisée
- En mettant les ressource en comun nous réaliserons des économies sur les frais liés à l'infrastructure

Nous pouvons cependant relever que cette solution prendra beaucoup de temps et de resources pour qu'elle soit mise en place étant donnée la complexité de la mise en place d'un serveur Kubernetes custom

Nous avons choisi Kubernetes comme outil d'orchestration pout cette solution étant donné sa puissance pour gérer des clusters de très grande taille

Les images de l'application seront stockées de façon sécurisée sur un registry Docker privé créé pour l'ocasion.

| Exigence                                                                                                                                                  | Solution apportée                                                                                                                                              | Points forts de la solution | Lacunes de la solution |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|------------------------|
| L'acheteur doit récupérer le site sur un module spécifique                                                                                                | Une image Docker sera stockée sur un registry privé<br>afin de protéger le code du site                                                                        |Le Registry privé est une solution sécurisée pour stocker des images docker|Un registry privé peut être long à mettre en place|
| Notre hébergeur doit traiter le contenu volumineux                                                                                                        | Nous mettrons en place des serveurs de fichiers et<br>des serveurs de DB postgreSQL afin de prendre en charge les contenus<br>volumineux                                  |Les serveurs de fichier et les serveurs postgres sont à même de traiter des informations très volumineuses  |Postgres n'étant pas serverless, cela exige de mettre en place un ou plusieurs serveurs pour chaque client     |
| Le client doit pouvoir choisir d'héberger des données qu'il juge <br>sensibles sur sa propre infrastructure                                               | Mise en place d'une option sur les site atoms les plus sensibles<br>qui permettrait de choisir de garder chez soi les données relatives<br>à ce site atom      |Les client peuvent choisir eux même les sites atoms à garder sur leur infrastructure    |Cela demande du travail de la part des backend|
| Différenciation des serveurs d'infrastructure et d'administration<br>sur nos hébergeurs et des serveurs contenant des données sensibles<br>chez le client | Lancement des mises à jour avec l'outil de commande kubectl après validation du client |Kuernetes peut gérer les mies à jour sot aucune interuption de fonctionement des pods|Kubernetes sait gérer les upgrades de façon inteligente et automatisée                        |
| Toute mise à jour devra être effectuée sur nos serveurs sur demande<br>de l'acheteur                                                                      | Update des images Docker et récupération sur le private regitry via la ligne de commande kubectl |Docker nous permet de proposer les mises à jour en remote sans envoyer quoique se soit au client                             |                        |
| Les mises à jour seront centralisées et envoyées à tous nos clients <br>en même temps.                                                                    | Update de toutes les images Docker simultanément                                                                                                                                                               |                             |                        |

**Solution privilégiant l'aspect commercial:**

![Shéma récapitulatif de la solution privilégiant l'apect commercial](../../../Images/diagrammeSolutionCommerciale.png "Shéma récapitulatif de la solution privilégiant l'apect commercial")

Cette solution présente de nombreux avantages:
- Sa mise en place nécéssite très peu de préparation
- Le client peut choisir de façon personalisée les serveurs coté Webstreet et donc scale le plus précisement possible son application
- Nous pouvons vendre des serveurs web au client

Nous avons choisi l'utilisation de Docker Swarm pour cette solution étant donné sa facilité à être mie en place. Cet outil d'orchestration convient très bien pour les clusters de faible taille.

Cependant, cette solution demendera des actions de devops plus conséquente pour la mise en place de chaque application client. Il faudra en effet à chaque fois récréer un cluster Docker Swarm.

| Exigence                                                                                                                                                  | Solution apportée                                                                                                                                              | Points forts de la solution | Lacunes de la solution |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|------------------------|
| L'acheteur doit récupérer le site sur un module spécifique                                                                                                | Une image Docker sera stockée sur un registry privé<br>afin de protéger le code du site                                                                        |Le Registry privé est une solution sécurisée pour stocker des images docker|Un registry privé peut être long à mettre en place|
| Notre hébergeur doit traiter le contenu volumineux                                                                                                        | Nous mettrons en place des serveurs de fichiers et<br>des serveurs de DB afin de prendre en charge les contenus<br>volumineux                                   |Les serveurs de fichier et les serveurs postgres sont à même de traiter des informations très volumineuses  |Postgres n'étant pas serverless, cela exige de mettre en place un ou plusieurs serveurs pour chaque client     |
| Différenciation des serveurs d'infrastructure et d'administration<br>sur nos hébergeurs et des serveurs contenant des données sensibles<br>chez le client | Mise en place d'un cluster Docker Swarm qui peut organiser l'orchestration des serveurs de WebStreet et du client  |Docker Swarm est très simple à mettre en place pour chaque client  |Docker Swarm n'est pas l'outil d'orchestration le plus puissant |
| Communication entre les serverus du client et ceux de WebStreet | Mise en place d'un network overlay dans le cluster Swarm  |Le network overlay est fait pour permettre une comunication sécurisée entre des containers sur des machines séparées | |
| Toute mise à jour devra être effectuée sur nos serveurs sur demande<br>de l'acheteur                                                                      | Nous utiliserons les lignes de commandes du cluster et nous changerons les images Docker pour lancer les mises à jours |Les images Docker permettent de faire les mises à jur sans envoyer les nouveaux fichiers au clients ou à nos machines      |Cela néssécite des actions manuelles pour faire les mises à jour pour chaque client    |
