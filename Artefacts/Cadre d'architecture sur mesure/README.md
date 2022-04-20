Cadre d’architecture sur mesure

WebStreet a un cadre d'architecture strict directement lié à l'entreprise. Ce framework est un avantage concurrentiel majeur pour l'entreprise puisqu'il permet de personnaliser et de mettre en place un site client en moins de 72 heures. La stratégie marketing WebStreet a toujours communiqué ce message au marché, et le marché a réagi. Le conseil d'administration de l'entreprise s'est toujours efforcé de sensibiliser les équipes techniques à cet avantage et de respecter les délais en conséquence.

Voici les principes de la méthodologie d'architecture de WebStreet :

1. Aucun code n'est écrit à partir de zéro. Toutes les personnalisations doivent maximiser l'utilisation de modèles et d'atomes de site.

2. Si une partie du site est personnalisée, elle doit être documentée au début du code à l'aide du document [CustomizationDictionary](../../Images/18_Customization_Dictionary.png),
qui décrit les personnalisations que nous avons effectuées pour un client, quel modèle ou Site Atom a été personnalisé et comment.

3. Toute la documentation doit être rédigée avec une approche d'équipe globale : plusieurs équipes WebStreet situées dans des fuseaux horaires différents vont développer le site Web pour un client spécifique et le maintenir plus tard.

4. Les modèles sont une collection d'atomes de site. Les modèles ne contiennent pas de code spécifique.

5. Les atomes du site peuvent recevoir des paramètres tels que la langue, la couleur, le style, le placement, etc.

6.Tous les sites Web des clients sont une collection de modèles plus une certaine personnalisation. Voir schéma [ici](../../Images/19_Website_Encapsulation.jpg).


Contenu de l’architecture sur mesure

Nos modèles et Atomes de site sont divisés en deux groupes :
1. Modèles principaux (procéduraux) et Atomes de site.
2. Modèles frontaux (graphiques) et atomes de site.

**Exemple de site atom back-end :** un objet d’authentification. Cet objet reçoit un nom d'utilisateur et un mot de passe et valide l'entrée dans une base de données d'utilisateurs.

**Exemple d'atomes de site front-end :** un en-tête de site. Cet objet affiche un en-tête de site avec un style, une couleur et une police standard. Il existe des en-têtes de site pour les pages de connexion, les pages de destination et les pages internes du site Web.

**Exemple de modèle back-end :** un nouvel enregistrement d'utilisateur. Ce modèle valide un nouvel utilisateur enregistré et envoie un e-mail pour valider que l'utilisateur est réel, demandant de changer le mot de passe pour un autre. Ce modèle utilise l'objet de connexion mentionné ci-dessus et d'autres sites atoms importants.

**Exemple de template front-end :** un design de site. Cet objet affiche une page entière du site Web à l'aide de blocs de construction frontaux tels que l'en-tête du site, le pied de page du site, la colonne de gauche du site, les menus déroulants, etc.


Outils configurés et déployés

Ces outils sont déployés dans l'organisation pour aider au développement et à la configuration du site Web. Ils sont disponibles pour toutes les équipes de développement :

***Dictionnaire des site atoms :** une base de données de tous les atomes du site pour commencer la conception et le développement d'un site Web pour un client. Voir exemple [ici](../../Images/20_Site_Atom_Dictionary.xlsx).
Chaque entrée du dictionnaire décrit l'objectif des Atomes du site, la description, les mises à jour du composant, les paramètres qu'il peut recevoir, l'utilisation typique et les liens vers des projets où ce composant a été utilisé.

**Dictionnaire de contrôle de configuration :** une base de données des relations entre les modèles et les atomes de site. Ce qui appelle quoi, ce qui est appelé par quoi. Voir schéma [ici](../../Images/15_Configuration_Control_Dictionary.png).

**Dictionnaire de personnalisation :** une description détaillée de toutes les personnalisations effectuées sur les clients WebStreet, avec des liens vers de vrais sites Web. Voir schéma [ici](../../Images/18_Customization_Dictionary.png).

Interface avec modèle de gestion

Cette méthode d'architecture stricte utilisée dans WebStreet ne pourrait être un avantage concurrentiel principal sans le soutien formel de l'organisation et de la culture interne. Voir la matrice RACI (../../Images/11_RACI.xlsx) et le plan des parties prenantes (../../Images/12_Stakeholders_Map.png). Les interfaces suivantes ont contribué à son succès et au succès de WebStreet sur le marché :

**Interface avec le Service Recrutement :** aucun programmeur ou designer n'écrit une ligne de code s'il n'est pas formé à la méthodologie de l'architecture WebStreet. Ceci est soigneusement synchronisé entre les équipes techniques et le service de recrutement de WebStreet (qui fait partie du service des ressources humaines).

**Interface avec AMG :** il existe un groupe dédié chez WebStreet appelé AMG (Architecture Method Guardians) dont la principale responsabilité est de maintenir la cohérence et d'améliorer le dictionnaire des Site Atoms et des templates. Le groupe AMG agit en tant que PME (Subject Matter Experts) sur des thèmes de modèles, des Atomes de site et des méthodes de construction. Des groupes techniques les consultent de manière informelle sur une variété de sujets. Le groupe AMG est généralement chargé de dispenser des cours sur la méthodologie de l'architecture WebStreet aux nouvelles recrues ainsi qu'aux développeurs expérimentés.

**Interface avec CMG :** il existe un autre groupe dédié appelé CMG (Customization Dictionary Guardians) dont la principale responsabilité est d'enregistrer toutes les personnalisations pour tous les clients. Ce groupe est un lien entre l'équipe technique de WebStreet qui a développé le site et l'équipe commerciale qui a été en contact avec le client. Ils rejoignent généralement la dernière partie du cycle de vente afin d'évaluer la quantité et la taille de la personnalisation pour un client particulier, et ils travaillent en cours de route avec les équipes techniques dans la documentation du processus de personnalisation. Aucun site Web n'est livré à un client sans l'approbation de la CMG.

**Interface avec le département des fournisseurs:** Tous les fournisseurs externes doivent être certifiés pour travailler avec notre architecture logicielle existante. Cette démarche de certification est mise en œuvre conjointement par la Direction des Achats et l'AMG.

**Interface avec le service commercial :** le groupe CMG participe activement au processus de vente et conseille l'équipe de vente dans les efforts de personnalisation.

**Interface avec l'E-PMO :** il existe un E-PMO (Enterprise Project Management Office) dans WebStreet qui gère un portefeuille de projets déployés dans tous les bureaux de l'entreprise. Ces projets sont internes et n'impliquent pas de clients. Ce projet devra être inclus dans ce portefeuille et sera observé et suivi par l'E-PMO.

