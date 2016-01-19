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
