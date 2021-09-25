
# project_calculatrice
## Week 4 project -  group 1 : Anh + Marius

Enoncé : Implémenter une calculatrice

On commencera par définir une fonction computer qui prend en argument un string de type "a * (b + c) - d" avec a, b, c, d digits entiers (0 à 9) et retourne la valeur calculée.

La fonction doit gérer les potentielles erreurs dans les inputs de l'utilisateur

Les cas à gérer sont les suivants (Avec d = digit et op = +,-,*,/) :
* d op d
* d op d op d
* d op (d op d)
* d op (d op d) op d

Le style du code sera inspecté et devra respecter PEP : https://cheatography.com/jmds/cheat-sheets/python-pep8-style-guide/

## Solution :


### I) Gestion des erreurs 

La première partie du code est destinée à la gestion des erreurs : 

* Lettres et caractères spéciaux non autorisés (hors +,-,*,/,.,(,))
* Position des parenthèses (parenthèses isolées ou doubles parenthèses)
* Position des opérateurs et du point de séparation des flottants


### II) Code principal

L'approche de la solution est une gestion des priorités de manière décroissante puis le remplacement dans l'opération du résultat.

* Gestion des parenthèses : Identification de la parenthèse ouvrante puis exécution des opérations à l'intérieur
* Gestion des opérations prioritaires (*,/) : à cette étape toutes les opérations entre parenthèses ont été remplacées par leur résultat
* Gestion des opérations non prioritaires : à cette étape toutes les opérations prioritaires ont été traitées et l'exécution se fait de gauche à droite
    
    
### III) Limites de la solution

Le code produit peut gérer plusieurs opérations non prioritaires à la suite mais ne gère pas les cas suivants :
* Plus de trois opérations dont plus d'une prioritaires
* Plus d'une opération entre parenthèses dans la string
* Plus d'une opération à l'intérieur des parenthèses
