## Gauthier Donatien

#### Projet Python

### Hex Game

### Présentation du jeu

Hex est un jeu de stratégie, ou l'on doit traverser de bout en bout du tableau en relayant ses points placé dans chaque hexagone afin de créer une route.

### Comment on joue ?

A tour de rôle, les joueurs doivent placer un point dans un des hexagones du plateau stratégiquement afin de et relier un coté à l'autre mais aussi empécher l'adversaire de faire une route.

### Explication

## Jeu

- stocke la configuration (IA ou joueur) de chacun des joueurs
- matrice de Sommet utilisée dans les graphes et taille n\*n
- ajoute tous les sommets qui touchent un bord dans un Graphe correspondant
- ajoute les voisins correspondants pour chacun des Sommet
- afficher le menu de configuration de la partie
- valeur par defaut : joueur 1 IA
- verifier que les parametres saisis via le menu sont corrects
- verifier que la taille saisie est un entier
- commencer une partie
- Créer une nouvelle partie (réglages différents)
- verifier si la grille actuelle est gagnante pour un des joueur
- passer au tour suivant
- verifier si l'arbre des coups a jouer a deja ete genere, sinon le generer
- retourner l'index correspondant au plateau actuel
- retourner un code correspondant a l'etat de chacune des cases (0: LIBRE, 1: ROUGE, 2: BLEU)
- placer un pion (pour un joueur humain)
- verifier si l'endroit clique est une case et s'il n'y a pas de pion dessus

- si le prochain tour est un IA, le lancer
- placer un pion (pour une IA)
- si le plateau actuel est un plateau gagnant, jouer le coup correspondant
- sinon, jouer un coup aleatoire

## Hexagone

- un Hexagone est decrit par les coordonnes de ses 6 points et son centre
- creer un Hexagone a partir d'un seul point p et y associer un sommet
- un Sommet est associe a chaque Hexagone
- tracer l'Hexagone sur le canvas
- cree un cercle qui s'affiche quand l'Hexqagone est survole
- associer un Sommet a un Hexagone
- verifier si un Hexagone est libre (aucun pion n'y est pose)

## Point

- un Point est decrit par ses coordonnes X et Y
- calculer la distance entre 2 points
- tracer un cercle d'un certain rayon et d'une certaine couleur sur le canvas
- tracer un hexagone sur le canvas

## Grille

- une Grille est decrite par un ensemble d'Hexagone
- creer une Grille a partir d'un seul point p, de la dimension n et d'une matrice de sommets
- cree un tableau à 2 dimensions
- tracer tous les Hexagone qui composent la Grille ainsi que les bords
- trouver l'Hexagone correspondant à l'aide la distance entre le centre d'un hexagone et la zone cliquee
- placer un pion d'une certaine couleur sur un Hexagone

## Graphe

- un Graphe possède des sommets d'une même couleur qui sont reliés sur le plateau
- creer un Graphe a partir d'une couleur et de son bord (1: Bleu Haut, 2: Rouge Gauche, 4: Bleu Bas, 8: Rouge Droite)
- ajouter un Sommet à un Graphe (definit aussi le Graphe du Sommet)
- recuperer tous les Sommet d'un autre Graphe
- fusion des 2 graphes relie les 2 bords d'une couleur

## Sommet

- un Sommet est decrit par ses coordonnes i et j dans une matrice
- associer un Graphe a un Sommet
- ajouter un Sommet a la liste de voisins
- changer la couleur d'un Sommet et le fusioner avec les graphes voisins

## ArbreCoups

- recuperer le fichier "./plateaux/{n}/{coups}.txt" ou, s'il n'existe pas, le creer
- ecrire le contenu dans le fichier fd
- initialiser la variable globale voisins en fonction de la dimension n de la grille
- Transforme le code du plateau en une liste de caractères

- Change un caractere de ce code, correspond au pion joue
- Re-transforme le nouveau code obtenu en chaine de caractere
- Ajoute le plateau à la liste de suivants

- verifier si un joueur a relié les 2 bords d'une même couleur(Parcours en profondeur d'un bord à l'autre)
