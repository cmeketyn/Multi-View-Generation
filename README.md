Les notebooks des différents modèles sont dans chaque dossier (GMV, CGMV et AECP).
Le notebook Multi_View_Generation.ipynb à la racine est un notebook courant et regroupe tous les modèles et toutes les fonctions d'entraînement et de test.

Tous les codes ont été utilisés sur Colab avec un Google drive. Pour lancer les codes sans avoir à les modifier :
- créer deux dossiers dans le Google drive : "3Dchairs" et "Sauvegardes_poids" ;
- mettre dans 3DChairs le fichier chaises.csv ;
- dans Sauvegardes_poids, créer deux dossiers "MNIST" et "3Dchairs", et dans chacun créer les dossiers "AECP", "GMV" et "CGMV".


Les différents notebooks sont organisés de la même manière :

- Importations et constantes : à lancer une seule fois au début
    - Installations et importations des modules : permet notamment de faire le lien avec le Google drive. Pour cela, il faut cliquer sur le lien en sortie de la 4ème cellule et s'identifier. Les cellules suivantes ne se lanceront pas tant que l'identification n'aura pas été faite (qu'elle soit réussie ou pas).
    - Constantes : les hyperparamètres tels que la taille des vecteurs latents et les learning rates y sont modifiables.
    - Importation des bases de données : importe MNIST. Les deux cellules en commentaires permettent de tester la lecture du fichier chaises.csv (mais il faut d'abord avoir lancé les cellules dans Fonctions).

- Fonctions : à lancer une seule fois au début, regroupe toutes les fonctions utilisées dans toutes les autres cellules.
    - Modèles : contient les architectures de tous les modèles (GMV, CGMV et AECP) pour les deux bases de données (il y a donc deux architectures GMV, etc.).
    - Entraînement : contient la fonction principale train ainsi que les trois fonctions spécifiques à chaque modèle.

- Entraînement : permet d'entraîner n'importe quel modèle. Le choix du modèle et de la base de données à utiliser se fait dans la première cellule. Les fonctions sont ensuite codées pour s'adapter à ces choix et il n'y a donc besoin que de changer leurs arguments. De la doc est écrite avant chaque utilisation d'une fonction pour expliciter les arguments.
Les réseaux sont initialisés avec la fonction create_model et sont stockés dans la variable list_models.
Les fonctions permettent de sauvegarder les poids des réseaux dans le Google drive, de les restaurer (il faut avoir initialisé list_models avec create_model avant), de modifier les learning rates, d'entraîner les réseaux, et d'afficher les différents graphiques.

- Tests : permet de tester n'importe quel modèle en utilisant des fonctions qui s'adaptent au modèle et la base de données choisis dans Entraînement.
