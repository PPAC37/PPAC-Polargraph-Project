# Analyse des besoins 

...

Limites physique 

Definition d'un profil de machine (polargraph) Fortement lié a la réalité physique et au firmware utilisé.
* Ecarte Moteurs
* Longeur de courroie
* Poséde ou non des endstop
* ....
* 
* ( ... vitesses, acceleration, sacades 

Définition de l'outils en cours d'usage ( un peux comme le profile de l'extrudeur et du filament sur le fdm)
* Taille de la pointe du stylot
* Couleur
* ... forme de la pointe "." ou "-" ou "/" ...
* debit maxi ( pour déterminer la vitesse de G1/G2/G3 ( quand le pen is down)
* ? indice de diffusion de l'encre ( ? pour eviter/controller le fait de faire une pause sur une coordonée et finalement se retrouveer avec une diffusion de l'encre sur le papier )
* volume dencre avant epuisement ( pour savoir si on a suffisament d'encre ... ?


Difinition de la zone d'impression utilisablent ( equivalent en fdm a la taille du plateau / les contrainte physique lié a l'imprimante)
* espace atégniable lié a la définition du profil machine ( pour la limite physique des zones utilisablent) 
  * avec un polargraph de base pas simple d'imprimer deriere le tableau 
  * de sortire de la zone délimiter sur les coté par la distance entre les moteurs (points polaire) limité par la gravité flexibilité de la courroie.
* 
* position du home
* Là une subtilité quand a la taille/forme du papier placé sur cette zone ( lui aussi rajout une contrainte)
  * Peut on imprimer sur une surface convex / concave  (un tube ? convexité maximum ? ) ou seulement sur un plan dbien plat.
* Peut on deplacer le papier automatiquement ou manuellement( si un roulot de papier , ou un grand format ) pour combiner plusieur impressions) 
  * seulement si on a parfaitement bien ajusté / fait correspondre exactement les réalite pysiquement au valeur utilisé par le/les logiciellement .... 
    * taillle de


Définition de besoins logiciel pour la generation de fichier .gcode ( utilisabel par marlin)
* Le jeu de commande g-codes disponible selon le firmware et version du firmware
* Le capacité du firmware a rapporter ou non les paramétre de la machine ( taille du plateau , feedrate , ...)

? Vue en couche conceptuel de traitements

image / geerative algo

Vector path for ploter commandes
* ? decoupable ( peut on facilement d'une suite de position, deplacement, actions  decpouper pour segmenter sur plusieur impression ( feuilles différente ) ?

Ploter commandes / g-code
* ? masque de zones a imprimer ( même difficulté que plus haut ... ? )
Firmware coordinate offset
* limite logiciel et physique ( endstop definition) quelle resultat dans les cas limites / hors limites ? peut on en jouer ?

Quelle implication de pouvir generer a la fois du en mode de coordonné relative et/ou absolut ?



Référence


Quand on voie se qui existe pour traceusse de découpe, imprimante 3D et cnc c'est vite trés complexe.

Ex 

https://vevor.fr/products/machine-de-traceur-de-coupe-de-vinyle-traceur-plotter-de-decoupe-720-mm-128k-2m -> applicatif https://www.google.com/search?q=SIGNMASTER

CNC laser -> LaserGRBL / CNCjs / CAMOAtics? / ...

FDM -> Ultimaker Cura / PrusaSlicer / IdeaMaker / ...


