# Les listes, les boucles, et mise en application.


Bonjour à tous, et bienvenue à ce cours. Nous allons aujourd'hui voir différentes fonctionnalités de Skript relativement méconnues.
En effet, beaucoup de personnes connaissent plus ou moins bien les boucles et listes de valeurs, mais il y a beaucoup de subtilités dans ce domaine permettant d'accomplir des tâches complexes de façon très simple et élégante.

Nous allons donc aborder différentes choses étroitement liées aujourd'hui:

- Tout d'abord, nous allons rapidement voir qu'est ce qu'une liste de valeurs.

- Ensuite nous verrons les boucles `loop`, et certaines de leurs applications spécifiques.

- Par la suite, nous nous intéresseront aux listes de variables.

- Enfin, nous transférerons nos acquis vus lors de ce cours dans le cas d'un exemple concret, une sauvegarde de structure tridimensionnelle.

## Les listes de valeurs

Attention, ici, je ne parle pas encore de ce que l'on appelle communément des variables listes, que nous verrons par la suite, mais bien de simple listes de valeurs, quelqu'elle soit.
On va commencer par le commencement: les listes de valeurs
Répondons donc à la question: qu'est ce que selon vous une liste de valeurs ?
Une liste de valeurs est simplement un ensemble de valeurs, étant généralement du même type (`player`, `items`, `entities`).

Une des valeurs d'une liste est appelée un élément
Vous avez sans doute déjà utilisé des listes de valeurs, une des plus connues est sans doute `all players`.

Vous pouvez d'ailleurs récupérer diverses listes de valeurs en utilisant l'expression `all <type au pluriel>`, cela permet de récupérer la liste des valeurs existantes d'un type donné.

Vous pouvez cependant manipuler facilement vos propres listes de valeurs, simplement en énonçant chacun des éléments de la liste, séparée de virgule entre chaque élément, avec entre les 2 derniers éléments un `and` comme ceci: `"a", "b", "c" and "d"`

Il existe également d'autres expressions permettant de récupérer des listes de valeurs, comme par exemple `split <text> at <delimiteur>` ou encore `integers between 0 and 5`.

Je pense que cette partie était relativement simple à comprendre, mais néanmoins nécessaire à la compréhension de la suite de ce cours. C'est pourquoi j'ai voulu refixer précisément la nature des listes de valeurs.


## Les boucles `loop`

Une `loop` est une méthode en Skript permettant d'appliquer une série d'opération à une liste de valeurs.
Voici comment se présente une boucle `loop`:
```
loop <liste de valeurs>:
	<instructions>
```
Cette forme est très basique. Dans la majorité des cas, on aura également besoin de pouvoir récupérer ce que l'on appelle communément la "valeur courante", c'est à dire la valeur de notre liste de valeurs que l'on va utiliser dans nos opérations.
La valeur courante peut être appelée avec `loop-value` ou bien `loop-<type de la valeur>`.

Histoire de contextualiser un peu la théorie, voici un exemple très simple:
```
loop all players:
	send "Tu joues actuellement sur le cube épique ! Rejoins nous sur TeamSpeak à cette adresse: xxx !" to loop-player
```

Dans ce code, on retrouve bien `loop all players:` avec `all players` comme liste de valeurs. Ensuite, dans nos instructions, nous utilisons `loop-player` comme valeur courante pour lui envoyer un message.

Il y a quelques subtilités intéressantes à noter au niveau des boucles `loop`, déjà, les boucles de liste de valeurs s'effectuent les uns après les autres, et non de façon simultanée.
De ce fait, si on utilise l'effet `wait` dans une boucle, il y aura un délai entre l'exécution du code pour chaque élément de la liste.

Il est donc très facile de créer un compteur par exemple:
```
loop 10 times:
	send "%loop-value%"
	wait 1 second
```

Ici, la liste de valeurs est `10 times`, qui renverra les nombres entiers de 1 à 10. On aurait pu avoir le même résultat en écrivant `integers between 1 and 10` ou alors en citant toutes les valeurs directement `1, 2, 3, 4, 5, 6, 7, 8, 9 and 10`. Le résultat sera un compteur de 1 à 10, à intervalle de 1 seconde donc.

Deuxième caractéristique des boucles `loop`, on peut les imbriquer, c'est à dire faire des boucles dans des boucles. Dans ce cas-ci, si l'on veut récupérer la valeur courante, on doit alors préciser la boucle en donnant le numéro de l'ordre de "création" de la boucle, de cette façon par exemple: `loop-value-3`. Si 2 boucles bouclent des types de valeurs différentes, on peut alors s'abstenir de préciser de quelle boucle vient la valeur courante à condition d'utiliser `loop-<type>`.
```
loop all players:
	loop all items of loop-player:
		broadcast "%loop-value-1% possède %loop-value-2%"
```

Dernière petite info, on peut arrêter prématurément une boucle avec `stop loop`, par exemple si on cherche une valeur dans une liste de valeurs, on peut arrêter la boucle dès qu'on a trouvé ce que l'on cherche.

Étant donné tout ce que l'on a vu jusqu'à présent, on peut se permettre de faire un petit exercice...

## Les listes de variables

*Alors tout d'abord, essayez de vous détacher de l'image que vous vous faîtes des variables listes; en effet, on se méprend souvent sur leur nature, donc écoutez ce que j'ai à dire, et ensuite vous poserez vos questions*

Attaquons le vif du sujet, les listes de variables (ou variables listes) !
Alors, comme vous avez l'avez entendu, je parle plutôt de liste de variables que de variables liste.
En effet, je trouve ce terme bien plus adapté que de dire "variables liste", car ce n'est pas une variable contenant une liste de valeurs, mais bien une liste de variables contenant chacune une valeur; chacune de ces variables étant rassemblées au même endroit.

L'utilité de rassembler des variables est très grande, en voici la liste:
* Supprimer toutes un liste de variables d'un coup
* Supprimer très simplement toutes les variables d'une liste qui ont une valeur précise
* Pouvoir utiliser une liste de variables comme une liste de valeurs, et donc les utiliser dans des boucles `loop`
* Utiliser des listes de variables pour former des tableaux de données.
