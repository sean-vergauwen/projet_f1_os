# Consignes du Projet Système TP Janvier 2025
Le but du projet est de gérer un championnat de Formule 1.

Le championnat se compose d’une vingtaine de grands prix (entre 20 et 25). Cette saison comporte 24 grands prix.

<br>

Chaque grand prix se déroule sur un week-end, typiquement du vendredi au dimanche.

Il vous est demandé de gérer les grands prix depuis les séances d’essais du vendredi jusqu’à la course du dimanche, en passant par les essais du samedi et la séance de qualifications.

Il y a 20 voitures engagées dans un grand prix. 

Leurs numéros sont : 1, 11, 44, 63, 16, 55, 4, 81, 14, 18, 10, 31, 23, 2, 22, 3, 77, 24, 20, 27.

<br>

Un circuit de F1 est divisé en 3 secteurs (S1, S2, S3).
Il y a 2 formats de week-end.
Le  week-end « classique » s’établit comme suit :

    - Vendredi matin, une séance d’essais libres d’1h (P1)
    - Vendredi après-midi, une séance d’essais libres d’1h (P2)
    - Samedi matin, une séance d’essais libres d’1h (P3)
    - Samedi après-midi, la séance de qualifications, divisée en 3 parties :
        - Q1, durée 18 minutes, qui élimine les 5 dernières voitures (qui occuperont les places 16 à 20 sur la grille de départ de la course)
        - Q2, durée 15 minutes, qui élimine les 5 voitures suivantes (qui occuperont les places 11 à 15 sur la grille de départ de la course)
        - Q3, durée 12 minutes, qui permet de classer les 10 voitures restantes pour établir les 10 premières places sur la grille de départ de la course
    - Dimanche après-midi, la course en elle-même.


Il y a quelques week-end « spéciaux », avec une course sprint le samedi, pour lesquels on a :

    - Vendredi matin, une séance d’essais libres d’1h (P1)
    - Vendredi après-midi, une séance de qualifications pour le sprint (sprint shootout) suivant le format de qualifications habituel. Cependant les 3 sessions seront plus courtes : Q1 : 12 minutes, Q2 : 10 minutes, Q3 : 8 minutes
    - Samedi matin, une course « sprint » de 100 km environ.
    - Samedi après-midi, la séance de qualifications pour la course du dimanche, divisée en 3 parties, selon les mêmes modalités que pour un week-end classique
    - Dimanche après-midi la course en elle-même.


Votre projet devra prendre en charge les choses suivantes.

**Première partie** : gestion des séances d’essai, des qualifications et de la course

Lors des séances d’essais (P1, P2, P3) :

    • Relever les temps dans les 3 secteurs à chaque passage pour chaque voiture. Pour ce faire, vous devrez commencer par écrire un « générateur de temps » à l’aide du random. Le temps dans un secteur se situe entre 25 et 45 secondes, en gros.
    • Toujours savoir qui a le meilleur temps dans chacun des secteurs
    • Classer les voitures en fonction de leur tour complet le plus rapide
    • Indiquer la différence de temps avec la voiture qui précède
    • Savoir si une voiture est aux stands (P)
    • Savoir si une voiture est out (abandon de la séance)
    • Dans ces 2 derniers cas, on conserve toujours le meilleur temps de la voiture et celle-ci reste dans le classement
    • Conserver sur fichier le classement final à la fin de chaque séance ainsi que les meilleurs temps S1, S2 et S3 et le meilleur tour.


Lors des qualifications (Q1, Q2, Q3) :

    • Relever les temps dans les 3 secteurs à chaque passage pour chaque voiture
    • Toujours savoir qui a le meilleur temps dans chacun des secteurs
    • Classer les voitures en fonction de leur tour complet le plus rapide
    • Indiquer la différence de temps avec la voiture qui précède
    • Savoir si une voiture est aux stands (P)
    • Savoir si une voitures est out (abandon de la séance)
    • Dans ces 2 derniers cas, on conserve toujours le meilleur temps de la voiture et celle-ci reste dans le classement
    • A la fin de Q1, il reste 15 voitures qualifiées pour Q2 et les 5 dernières sont placées à la fin de la grille de départ (places 16 à 20)
    • A la fin de Q2, il reste 10 voitures qualifiées pour Q3 et les 5 dernières sont placées dans les places 11 à 15 de la grille de départ
    • Le classement de Q3 attribue les places 1 à 10 de la grille de départ
    • Conserver sur fichier le classement final à la fin des 3 séances (ce sera l’ordre de départ pour la course sprint s’il y en a une ou pour la course du dimanche ), ainsi que les meilleurs temps en S1, S2, S3 et le meilleur tour.

Attention ! Lors des essais et des qualifications, les voitures roulent quand elles veulent. Il n’y a pas un nombre déterminé de tours à faire.

Lors de la course sprint et de la course du dimanche  : (un nombre déterminé de tours !!!)

    • Le premier classement est l’ordre sur la grille de départ. Vous devez donc faire démarrer les voitures selon l’ordre de la grille de départ.
    • Le classement doit toujours être maintenu tout au long de la course (gérer les dépassements)
    • Indiquer la différence de temps avec la voiture qui précède
    • Relever les temps dans les 3 secteurs à chaque passage pour chaque voiture
    • Toujours savoir qui a le meilleur temps dans chacun des secteurs
    • Toujours savoir qui a le tour le plus rapide
    • Savoir si la voiture est out (abandon) ; dans ce cas, elle sera classée en fin de classement
    • Savoir si la voiture est aux stands (PIT), gérer le temps aux stands et faire sortir la voiture à sa place dans la course (généralement 2 ou 3 PIT par voitures)
    • Conserver sur fichier le classement final et les meilleurs S1, S2, S3 et le meilleur tour.

Remarque : les stands se trouvent toujours dans le secteur 3. Lors de la course du dimanche, 1 arrêt aux stands est obligatoire. Les voitures peuvent en faire plus. Pour la course sprint du samedi, il n’y a pas d’arrêt obligatoire aux stands. Le temps d’un arrêt aux stands se situe aux environs de 25 secondes.

Votre programme doit afficher régulièrement à l’écran les résultats en cours de séance. Cet affichage doit se faire sous forme d’un « refresh » régulier. Un affichage simple suffit.

<br>

**Gestion du championnat**

On vous demande de gérer l’évolution du classement des pilotes (voitures) tout au long de la saison.

Lors de la course sprint, les 8 premiers reçoivent des points (dans l’ordre décroissant de 8 à 1).

Lors de la course du dimanche, les 10 premiers reçoivent des points (25, 20, 15, 10, 8, 6, 5, 3, 2, 1).

Lors de la course du dimanche, celui qui réalise le meilleur tour (durant la course) reçoit 1 point au classement, pour autant qu’il soit dans les 10 premiers de la course.

<br>

De plus, il vous est demandé de paramétrer votre programme.

En effet, le format des grands prix peut varier (sprint ou non) et les circuits peuvent être de longueur très variable et, dès lors, le nombre de tours pour la course sprint et la course du dimanche varie également (on essaie que le nombre total de kilomètres soit toujours plus ou moins le même pour chacune des courses du calendrier : sprint environ 100 km et course du dimanche environ 300 km. On prendra le nombre de tours le plus proche >= à 100 ou 300 km en fonction de la taille du circuit.).

<br>

Remarque importante !!!
Un week-end de grand prix se déroule sur 3 jours. On doit donc pouvoir arrêter le programme après chaque séance et le relancer ensuite. (Vous n’imaginez pas lancer le programme le vendredi matin et le laisse tourner tout le week-end ???). 
Lors de la reprise du programme, il faut évidemment respecter la logique de la succession des épreuves (on ne peut pas lancer la Q3 si la Q1 et la Q2 n’ont pas été faites, par exemple).

<br>

On vous demande :

    • De réaliser le programme en C sous Linux
    • De synchroniser les processus de manière à gérer correctement les données des différentes séances. 

Bon courage.

