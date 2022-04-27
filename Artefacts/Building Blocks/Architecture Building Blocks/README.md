# Architecture Building Blocks

**Site Atoms:** la plus petite entité pour la mise en place d'un site web. Voir exemple [ici](../../../Images/31_Building_Block_Site_Atom.png).

**Templates:** a set of Site Atoms that work together for a specific purpose. See example [here](../../../Images/32_Building_Block_Template.png).

Solution A:

![Shéma récapitulatif de la solution A](../../../Images/solutionAhighlevelarchitecture.drawio.png "Shéma récapitulatif de la solution A")

La solution A consiste à séparer l'application pour le client en deux sous applications:
- Une application devra stocker les informations dont le client a émis le souhait de gérer l'infrastructure
- Une autre application devra stocker le reste des informations et s'occuper de la communication avec le navigateur des utilisateurs

Afin de pouvoir faire coexister ces de ux applications, un système d'API devra être mis en place. Chaque site atoms présent sur l'application hébergé par le client devra pouvoir permettre de réaliseres actions de CRUD sauf cas spécifique de sécurité.

Dans le cas où le client souhaite conserver les informations d'authentification de ses utilisateurs,, l'API devra permettre de vérifier à partir des données rentrées dans l'IHM vérifier que les identifiants sont corrects.



Solution B:

![Shéma récapitulatif de la solution B](../../../Images/solutionBwebstreet.drawio.png "Shéma récapitulatif de la solution B")
