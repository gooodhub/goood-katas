# goood-katas

Pour les katas qu'on se fait entre nous

## 01 - FizzBuzz

**Règles :**

- tout nombre divisible par 3 doit être remplacé par "fizz"
- tout nombre divisible par 5 doit être remplacé par "buzz"
- les nombres divisibles par les 3 et 5 sont remplacés par "fizzbuzz"
	
Exemple en partant de 4 :
```
4, buzz, fizz, 7, 8, fizz, buzz, 11, fizz, 13, 14, fizzbuzz
```

## 02 - FOOBARQIX :

**Règles :**

- Écrivez un programme qui affiche les nombres de 1 à 100. Un nombre par ligne.
- Si le nombre est divisible par 3 ou contient 3, écrire "Foo" à la place de 3.
- Si le nombre est divisible par 5 ou contient 5, écrire "Bar" à la place de 5.
- Si le nombre est divisible par 7 ou contient 7, écrire "Qix" à la place de 7.

Voici un exemple de rendu :
```
1
2
FooFoo
4
BarBar
Foo
QixQix
8
Foo
Bar
...
```

Mise à jour : clarifications sur les règles

- On regarde les diviseurs avant le contenu (ex: 51 -> FooBar)
- On regarde le contenu dans l'ordre où il apparait (ex: 53 -> BarFoo)
- On regarde les multiples dans l'ordre Foo, Bar puis Qix (ex: 21 -> FooQix)

Donc, par exemple : 

- 13 contient, 3 donc s'écrit, "Foo"
- 15 est divisible par 3 et 5 et contient un 5 donc s'écrit "FooBarBar"
- 33 contient deux fois 3 et est divisible par 3 donc s'écrit "FooFooFoo"

## 03 - RPN Calculator :

RPN = Reverse Polish Notation

Un RPN Calculator est un programme qui fait des calculs sur des expressions écrites en RPN


Une expression RPN peut être :

- un nombre : dans ce cas, le résultat est ce même nombre
- une séquence de la forme "E1 E2 O" : 
	- avec E1 et E2 qui sont des expressions RPN 
	- et O qui est un opérateur arithmétique

Les expressions suivantes sont des expressions RPN :

```
20 5 /               => (20/5)         = 4
4 2 + 3 -            => (4+2)-3        = 3
3 5 8 * 7 + *        => 3*((5*8)+7)    = 141
```

Ecrivez un programme qui prend ces expressions en paramètre et qui affiche le résultat calculé.

## 04 - String Calculator :

Le but est de créer une calculatrice d'addition de chaines de caractères
Via une méthode `int Add(string numbers)` :

- La méthode peut prendre 0, 1 ou 2 nombres séparés par des virgules et retourner leur somme
- Une chaîne vide retourne 0

Exemples :
```
"" = 0
"1" = 1
"1,2" = 3
```

Commencer par le cas le plus simple (chaîne vide), puis 1 nombre, puis 2...
Rappelez-vous de :

- Résoudre les cas au fur et à mesure, le plus simplement possible
- En se forçant d'écrire le test avant le code
- Ne pas oublier de refactorer après chaque test vert

Améliorations suivantes :

- Permettre à la méthode `Add` de gérer une infinité de nombres
- Permettre à la méthode `Add` de gérer des sauts de ligne à la place des virgules
	- Exemple : `"1\n2,3" = 6`
	- Note : Ne tester que les cas valides (ainsi `"1,\n"` est invalide, mais on ne va pas le tester)
- Ajouter à la méthode `Add` la possibilité de spécifier un délimiteur.
Pour changer le délimiteur, la chaîne devra ressembler à `"//[delimiteur]\n[numbers]"`
	- Exemple : `"//;\n1;2" = 3` (on spécifie `;` en tant que délimiteur)
	- Note : la première ligne `//[delimiteur]` est facultative, tous les cas d'avant (avec `,` ou `\n`) doivent fonctionner
- Appeler la méthode `Add` avec un nombre négatif doit lever une exception :
`"Les nombres négatifs ne sont pas gérés : "` et lister tous les nombres négatifs
	- Exemple : `"-1,2"` throws `"Les nombres négatifs ne sont pas gérés : -1"`
	- ou `"2,-4,3,-5"` throws `"Les nombres négatifs ne sont pas gérés : -4,-5"`
- Modifier la méthode `Add` pour exclure les nombres plus grands que 1000.
	- Exemple : `"1001,2" = 2`
		
		
## 05 - Gilded Rose :

Ce Kata est un kata de refactoring d'une appli existante.
Le projet est un exécutable qui affiche dans la console l'évolution de la vie de différents produits.
Il est à télécharger sur le repository.

Aide à la mise en place :

- Commencer par faire des tests pour vérifier qu'au fur et à mesure de votre refactoring, tout fonctionne de la même manière. Pour se faire, utiliser [ApprovalTests](http://approvaltests.sourceforge.net/) via [Nuget](https://www.nuget.org/packages/ApprovalTests/)
- Refactoriser petit à petit, en s'assurant tout au long du refactoring que les tests sont toujours verts.

