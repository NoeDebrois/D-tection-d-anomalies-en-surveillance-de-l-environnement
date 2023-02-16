# Détection d'anomalies en surveillance de l'environnement
## Présentation du déroulement du projet :
Projet mené en équipe de 4 durant le deuxième semestre de ma 1A ainsi que le premier semestre de ma 2A à CentraleSupélec, en collaboration avec des chercheurs du laboratoire L2S de l'école. Ce fut un projet proposé par le pôle data sciences qui s'est avéré très enrichissant et qui nous a largement appris en manipulation de données ainsi qu'en IA (ML, RNN, LSTM). Il a fait l'objet de deux soutenances orales ainsi que la production de deux rapports (à la moitié du projet ainsi qu'à son terme). 

Vous trouverez dans ce dossier deux jupyter notebooks allègrement commentés qui présentent les deux approches que nous avons considérés durant notre année de travail (6 premiers mois : méthode "Matrix Profile" ; 6 derniers mois : "LSTM").

Merci à mes collègues et néanmoins ami(e)s de promotion à CentraleSupélec (P2024) : Marion Poirier, Damien Bouet et Pierre Chardin.

Pour toute question relative à ce projet, n'hésitez pas à me contacter à l'adresse mail suivante : noe.debrois@student-cs.fr

## Présentation du projet : détection et classification d'anomalies dans un signal de débit de dose.

- Auteurs : Noé DEBROIS, Damien BOUET, Pierre CHARDIN et Marion POIRIER
- Date : de Février 2022 à Janvier 2023
- Implication personnelle : 100 heures

### Contexte et objectifs

Ce projet a pour but de déployer et d'évaluer un système de détection d'anomalies dans une serie temporelle dans un contexte de surveillance de l'environnement (ou de l'atmosphère). Nous nous intéresserons ici à un signal de débit de dose, et séparerons le projet en 2 parties avec 2 approches différentes :

- La première partie, basée sur l'algorithme de la Matrix Profile, détectera dans le signal des motifs récurrents et les classifiera. Elle permettra ainsi de détecter les anomalies ou comportements du rayonnement qui se sont déjà produits dans le passé et de les classifier en différents groupes par ressemblance.

- La deuxième partie, basée sur la prédiction du signal par un réseau de neurones récurrents LSTM puis la comparaison entre le signal et le modèle, détectera toutes les anomalies majeures du signal. Elle permettra de détecter les anomalies, peu importe qu'elles se soient déjà produites ou non : cette deuxième approche permettra donc, entre autres, de détecter des anomalies qui ne se sont jamais produites, complétant ainsi les fonctionnalité de la première approche.

Ainsi, dans un contexte, par exemple, de surveillance nucléaire, ce système permettra de détecter en temps réel des potentielles anomalies ou comportements caractéristiques dans la mesure du rayonnement. Ce système pourra ainsi alerter les opérateurs qu'une anomalie est en train de se produire (2ème approche) et sera même capable d'indiquer de quel type d'anomalie ou de comportement il s'agit, dans l'hypothèse où une situation similaire s'est déjà produite dans le passé (1ère approche). Cette 1ère approche apportera même une aide aux experts, pour comprendre les comportements du système nucléaire étudié, en leur fournissant les motifs récurrents regroupés par catégories.

### Technologies utilisées

- 1ère approche : Matrix Profile, K-means
- 2ème approche : Réseau de neurones récurrents LSTM (Tensorflow), utilisation d'un seuil intelligent pour déduire les anomalies de l'erreur de prédiction, méthode de Pruning pour écarter les faux-positifs

### Références bibliographiques

- Yeh and al, “Matrix Profile I: all pairs similarity joins for time series: a unifying view that includes motifs discords and shapelets”, Proc of 16th IEEE ICDM, 2016,
- NASA Article : K. Hundman, V. Constantinou, C. Laporte, I. Colwell, and T. Soderstrom, “Detecting Spacecraft Anomalies Using LSTMs and Nonparametric Dynamic Thresholding,” in Proc. of the 24th ACM SIGKDD, 2018,
