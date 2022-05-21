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
| L'acheteur doit récupérer le site sur un module spécifique                                                                                                | Une image Docker sera stockée sur un registry privé<br>afin de protéger le code du site                                                                        |                             |                        |
| Notre hébergeur doit traiter le contenu volumineux                                                                                                        | Nous mettrons en place des serveurs de fichiers et<br>des serveurs de DB afin de prendre en charge les contenus<br>volumineux                                  |                             |                        |
| Le client doit pouvoir choisir d'héberger des données qu'il juge <br>sensibles sur sa propre infrastructure                                               | Mise en place d'une option sur les site atoms les plus sensibles<br>qui permettrait de choisir de garder chez soi les données relatives<br>à ce site atom      |                             |                        |
| Différenciation des serveurs d'infrastructure et d'administration<br>sur nos hébergeurs et des serveurs contenant des données sensibles<br>chez le client | Lancement des mises à jour avec l'outil de commande kubectl après validation du client |                             |                        |
| Toute mise à jour devra être effectuée sur nos serveurs sur demande<br>de l'acheteur                                                                      | Update des images Docker et répucération sur le private regitry via la ligne de commande kubectl |                             |                        |
| Les mises à jour seront centralisées et envoyées à tous nos clients <br>en même temps.                                                                    |                                                                                                                                                                |                             |                        |

**Solution privilégiant l'aspect commercial:**

![Shéma récapitulatif de la solution privilégiant l'apect commercial](../../../Images/diagrammeSolutionCommerciale.png "Shéma récapitulatif de la solution privilégiant l'apect commercial")

Cette solution présente de nombreux avantages:
- Sa mise en place nécéssite très peu de préparation
- Le client peut choisir de façon personalisée les serveurs coté Webstreet et donc scale le plus précisement possible son application
- Nous pouvons vendre des serveurs web au client

Nous avons choisi l'utilisation de Docker Swarm pour cette solution étant donné sa facilité à être mie en place. Cet outil d'orchestration convient très bien pour les clusters de faible taille.

Cependant, cette solution demendera des actions de devops plus conséquente pour la mise en place de chaque application client. Il faudra en effet à chaque fois récréer un cluster Docker Swarm

| Exigence                                                                                                                                                  | Solution apportée                                                                                                                                              | Points forts de la solution | Lacunes de la solution |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|------------------------|
| L'acheteur doit récupérer le site sur un module spécifique                                                                                                | Une image Docker sera stockée sur un registry privé<br>afin de protéger le code du site                                                                        |                             |                        |
| Notre hébergeur doit traiter le contenu volumineux                                                                                                        | Nous mettrons en place des serveurs de fichiers et<br>des serveurs de DB afin de prendre en charge les contenus<br>volumineux                                  |                             |                        |
| Le client doit pouvoir choisir d'héberger des données qu'il juge <br>sensibles sur sa propre infrastructure                                               | Mise en place d'une option sur les site atoms les plus sensibles<br>qui permettrait de choisir de garder chez soi les données relatives<br>à ce site atom      |                             |                        |
| Le client doit avoir à sa disposition l'application lui permettant de<br>stocker les données qu'il a jugé trop sensible                                   |                                                                                                                                                                |                             |                        |
| Différenciation des serveurs d'infrastructure et d'administration<br>sur nos hébergeurs et des serveurs contenant des données sensibles<br>chez le client | Mise en place de serveurs cloud hébergeant le site de plusieurs<br>clients en même temps qui communiquent par API avec les serveurs<br>du client               |                             |                        |
| Toute mise à jour devra être effectuée sur nos serveurs sur demande<br>de l'acheteur                                                                      | Nous mettrons en place des outils de devops sur nos outils<br>de communication qui permettront aux clients de créer <br>automatiquement de nouvelles pipelines |                             |                        |
| Les mises à jour seront centralisées et envoyées à tous nos clients <br>en même temps.                                                                    |                                                                                                                                                                |                             |                        |
