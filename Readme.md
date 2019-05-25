# Execution

L'énoncé parlait d'un "classeur iPython" pour le livrable sans plus de
précisions.
Le notebook jupyter a été utilisé pour faire cette exercice.
Le fichier ipynb contient à la fois le code et le rapport détaillé, et doit
être executé avec le notebook jupyter.

Afin de rester dans l'esprit de l'exercice, les fonctions ont été implémentées
en faisant le moins possible appel à des librairies annexes. J'ai néamoins
utilisé la fonction disk de scikit-image car je voulais comparer les résultats
entre des fenêtres carrées et des disques. Cette fonction sert juste à générer des
elements structurels sphériques au lieu de carrés.

L'implémentation n'utilise pas de librairies avec des fonctions de filtrages
optimisées et je fais appel à pas mal de boucles pour afficher les performances
des filtrages en fonction des paramètres, doncl'execution peut être un peu
longue, en fonction de la puissance de calcul de votre machine.

# Résultats

Bruit gaussien:
* filtre moyenneur : MSE < 100
* filtre gaussien :  MSE < 100
* filtre median :    MSE = 160

Bruit Poivre et sel
* filtre moyenneur : MSE = 270
* filtre gaussien :  MSE = 250
* filtre median :    MSE = 220

Speckle
* filtre moyenneur : MSE = 690
* filtre gaussien :  MSE = 680
* filtre median :    MSE = 770

Les filtrages moyenneurs et gaussiens offrent des performances similaires. Le
filtre moyenneur est plus efficace pour supprimer le bruit gaussien mais induit
un flou plus important que le filtre gaussien.
Pour un bruit de type poivre et sel, le filtre median est le plus efficace et 
permet de restituer une image visiblement débruitée et peu floue, bien que
l'erreur quadratique moyenne montre qu'elle est dégradée (perte des details,
lissage des textures)

Les filtres sont trop simples pour traiter efficacement un bruit complexe comme
le speckle mais permettent néamoins d'améliorer le rendu.


