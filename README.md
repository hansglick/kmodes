# Implémentation de l'algorithme de clustering Kmodes en python (quick and dirty version)


## Motivation
Ce repo contient une implémentation quick and dirty de l'algorithme K-modes d'après l'article https://shapeofdata.wordpress.com/2014/03/04/k-modes/ . La fonction principale __kmodes__ est utilisée pour répondre au test technique de Aquila. La distance utilisée correspond au nombre de mismatchs entre deux observations. Ex :
 * **Observation A** : (*Paris*,Riche,*Foot*)
 * **Observation B** : (*New York*,Riche,*Basket*)
 * dist(**A**,**B**) : 2



## La fonction principale kmodes
La fonction prend comme argument un dataframe pandas dont les colonnes sont des dummy variables. Elle renvoie deux objets :
 * Objet 1 : un dataframe contenant les résultats du clustering, un index et un label représentant la classe issue du clustering
 * Objet 2 : un dataframe contenant des métriques permettant de caractériser les clusters. Ces métriques correspondent aux odds ratio cluster / global. Par exemple : si un cluster comprend 70% de _Paris_ alors que l'attribut _Paris_ n'est présent que dans 35% de la population alors l'attribut _Paris_ est représenté par la métrique 2 (70/35)

## Les arguments de la fonction principale kmodes
* `df` : Dataframe, une ligne égale à un individu, les colonnes doivent uniquement être au format OHE
* `k = 2` : Nombre de clusters, ici seulement 2 est possible
* `threshold = 1` : Valeur représentant la difference existante entre les modes issus de deux itérations successives. En dessous de cette valeur, on stope les itérations
* `iterations = 10` : Nombre d'itérations maximum
* `verbose = True` : Afficher certaines informations sur les itérations en cours
* `n_clusterings = 5` : Afin d'éviter de tomber dans un minimum local, on lance __n_clusterings__ k-modes clusterings et on ne renvoie les résultats que du clustering dont la performance est la meilleure


## Instructions
 * Cloner le repo : `git clone https://github.com/hansglick/kmodes.git`
 * Afin de cloner l'environnement : `conda env create -f env/environment.yml`
 * Activer l'environnement : `source activate test_aquila`