Contexte général


WebStreet est une agence Web spécialisée dans la création rapide de sites Web pour les clients en utilisant des modèles de secteur et de style. Les équipes en développement ont été dépassées par l'augmentation des ventes de nos services à des clients du monde entier. Plusieurs années de développement ont abouti à un environnement logiciel complexe, qui ne s'adapte clairement pas à l'entreprise et qui pourrait entraver notre croissance.

Les temps de développement doivent être réduits et optimisés avec de nouveaux outils et techniques afin que nos développeurs soient en mesure de livrer plus rapidement et à moindre coût en utilisant des blocs de construction et des modèles pour les sites Web. Les composants logiciels de WebStreet sont appelés les Site Atoms. La diminution des temps de livraison ne pourra être atteinte que grâce à une nouvelle architecture logicielle qui créera un environnement agile et permettra une communication fluide et un langage commun entre nos équipes de développement partout dans le monde.


Stratégie de l’entreprise


Nous prévoyons de réduire de moitié les temps de cycle. Le délai typique de livraison aux clients est de 72 heures, nous souhaitons raccourcir ce cycle à 36 heures. Notre processus de livraison a toujours été basé sur le principe "Follow The Sun": le client commande un site Web et notre Master Team commence à le développer dès le premier jour, où que se trouve l'équipe. Si l'équipe Master termine son travail à la fin de la première journée, elle transfère le package de développement à une autre équipe située à 8 à 12 heures de distance. S'ils ne terminent pas le premier jour, ils travaillent sur le paquet un jour de plus. Le package peut être transféré plusieurs fois dans le cycle de développement jusqu'à ce que le site soit terminé. L'équipe principale doit approuver l'ensemble du cycle à la fin et informer le client.

Il faut réussir à ne transférer les packages de développement que 3 à 4 fois au lieu de 6 à 7 fois comme aujourd'hui. Nous avons besoin d'une nouvelle architecture logicielle pour y parvenir.

Ce projet doit être complété en 8 semaines (voir [plan d’architecture à haut niveau](../../Images/13_High_level_plan.png)). Une équipe projet, des porteurs de projet et des prestataires externes ont été désignés pour participer. D'autres domaines clés de l'organisation seront impliqués (voir [matrice RACI](../../Images/11_RACI.xlsx) et le [plan des parties prennantes](../../Images/12_Stakeholders_Map.png)).


Architecture actuelle

L'architecture actuelle de WebStreet est variable et ne suit pas un modèle commun. Les développeurs de sites s'appuient sur leurs propres templates et en demandent généralement dans leur entourage. Cela pose des problèmes lors du transfert du package : la nouvelle équipe dans un autre pays doit "découvrir" quels modèles ont été utilisés et doit lire une grande quantité de documentation avant de commencer à coder. Ce fait retarde le cycle de livraison d'au moins 12 heures. Pour décrire clairement l'architecture actuelle, nous pourrions dire "l'architecture actuelle n'était basée sur aucune conception, elle est le résultat de mesures rapides pour gérer une croissance exponentielle".

Pour un schéma décrivant l’architecture actuelle voir [framework d’architecture sur mesure](../Tailored%20Architecture%20Framework/README.md)


Agilité Business

Toutes nos activités seront basées sur des sites atoms et des templates. Nous avons besoin d'une nouvelle architecture non seulement comme point de départ, mais aussi comme plateforme pour de nouveaux outils, templates, conceptions et sites atoms. La nouvelle architecture doit prendre en charge notre variété croissante de sites, notre large couverture des différentes industries et les nouveaux outils techniques qui apparaissent sur le marché.

Tout en fournissant la capacité exacte requise il y a trois ans, la plate-forme actuelle a été conçue de manière à rendre très difficile la modification de l'une de ces décisions historiques. La nouvelle plate-forme devrait permettre à nos équipes produits d'innover rapidement en matière de technologies et de méthodes.


Contraintes organisationnelles

Voici quelques contraintes organisationnelles importantes que nous devons prendre en compte pour ce projet :


1. Bien que notre personnel consacre de nombreuses heures à ce projet, nous ne pouvons pas ignorer nos délais constants avec les clients. Servir nos clients et répondre à leurs attentes dans les délais, le budget et la qualité a été et sera toujours notre priorité n°1. Nos opérations de service normales ne peuvent pas être interrompues à cause de ce projet.

2. Nous n'avons pas toutes les connaissances et l'expérience requises pour ce projet au sein de notre organisation. Nous embaucherons des PME externes (experts en la matière) en tant que pigistes pour certains aspects techniques de ce projet.

3. Les sponsors du projet et l'équipe du projet s'accorderont sur la fréquence, la dynamique et les documents de support des réunions d'état du projet au début du projet. Toutes les parties prenantes se conformeront à ces principes convenus (Voir [matrice RACI](../../Images/11_RACI.xlsx) et [le plan des parties prennantes](../../Images/12_Stakeholders_Map.png)).


Problèmes à résoudre

Voici quelques problèmes ouverts qui n'ont pas encore été résolus :

1. Certains clients auront besoin d'un haut niveau de personnalisation. Nous ne pourrons pas utiliser nos Atomes de site et nos modèles pour ces clients. Voulons-nous d'eux comme clients ?

2. Nous avons actuellement des Atomes de site et des modèles uniquement pour les langues de gauche à droite (anglais, français, espagnol, russe, etc.). Notre architecture, nos Atomes de site et nos modèles doivent-ils prendre en charge les langues qui s'écrivent de droite à gauche ? (arabe, farsi, hébreu, etc.)

3. Si nous découvrons de nouvelles technologies, méthodes ou outils sur le marché, nous n'avons actuellement pas de critères clairs de conformité avec notre architecture : que se passe-t-il si l'outil change la façon dont nous traitons Site Atoms ? Et si la nouvelle technologie nous faisait changer la façon dont les modèles sont construits ?

