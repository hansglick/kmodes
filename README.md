# Implémentation Quick and Dirty de l'algorithme K-Modes pour le Test_Aquila



## Motivation
Ce repo contient une implémentation quick and dirty de l'algorithme K-modes. La fonction principale __K-modes__ est utilisée pour répondre au test technique de Aquila. La distance utilisée correspond au nombre de mismatchs entre deux objets. Ex :
 * Objet A : (Paris,Riche,Foot)
 * Objet B : (New York,Riche,Basket)
 * dist(A,B) : 2



## Les arguments de la fonction principale k-modes
* **df** : Dataframe, une ligne égale à un individu, les colonnes doivent uniquement être au format OHE
* **k** = 2 : Nombre de clusters, ici seulement 2 est possible
* **threshold** = 1 : Valeur représentant la difference existante entre les modes issus de deux itérations successives. En dessous de cette valeur, on stope les itérations
* **iterations** = 10 : Nombre d'itérations maximum
* **verbose** = True : Afficher certaines informations sur les itérations en cours
* **n_clusterings** = 5 : Afin d'éviter de tomber dans un minimum local, on lance __n_clusterings__ k-modes clusterings et on ne renvoie les résultats que du clustering dont la performance est la meilleure