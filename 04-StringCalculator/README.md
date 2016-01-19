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
