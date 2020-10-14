# Javascript 

Ce langage a été créé au milieu des années 90 spécifiquement pour rendre les pages web plus interactives.
Initialement il est apparu avec le navigateur Netscape1 mais a rapidement été intégré aux navigateurs les plus importants.
Son usage a depuis été étendu à d’autres domaines que celui des navigateurs et il est possible de l’utiliser pour d’autres types d’applications, notamment côté “serveur” avec par exemple Node.js.

## Principe de base de la programmation en Javascript

Comme la plupart des languages de programmation, le Javascript (souvent abrégé en **js**) se lis et s'exécute de haut en bas dans l'ordre des lignes (sauf dans certains cas plus avancés appelés *fonctions asynchrones* que nous n'allons pas détailler ici).

### Syntaxe
Contrairement à d'autres languages, la syntaxe en Javascript est très flexible. Le code se structure à l'aide de parenthèses (), de crochets [] et d'accolades {}. Les parenthèses sont souvent utilisées pour spécifier des paramètres dans des méthodes ou des fonctions, les  crochets permettent d'indiquer la valeur lue dans une liste ou un dictionnaire (voir suite du cours) et les accolades délimitent les **blocs de code**. Le double slash // permet de mettre des commentaires, c'est à dire du texte qui ne sera pas pris en compte par le programme.
À l'inverse du Python dans lequel l'indentation est très importante, en Javascript le code peut être écrit à peu près n'importe comment.

Par exemple cette fonction : 
```js
function pair(x) {
    if(x % 2 === 0) {
        return true;
    }
    else {
        return false:
    }
}
```
Peut aussi s'écrire :
```js
function pair(x) { if(x % 2 === 0) { return true; } else { return false; } }
```

Ou encore :

```js
let pair = (x) => x % 2 === 0;
```

On peut en théorie écrire tout un programme sur une ligne mais par soucis de compréhension et de lisibilité, la plupart des développeurs respectent les règles d'indentation communes à tous les languages.

Notez qu'ici : 
- Les accolades permettent de délimiter les instructions contenues dans la fonction.
- Les ; permettent de bien séparer les commandes. Même si sur la version de la fonction sur une ligne ils sont nécessaires, en vérité ils ne sont pas obligatoires et de nombreux développeurs de les mettent pas. Malgré tout, les mettre est considéré comme une des meilleures habitudes à prendre pour un(e) développeur(euse) et c'est une pratique grandement valorisé.

### Nommer ses éléments

En javascript et comme dans tous les languages de programmation, le nom des éléments doit respecter certaines conventions afin d'être lisibles et compréhensibles. La nomenclature la plus répandue est appellée **camelCase**. Elle consiste à retirer les espaces et mettre les premières lettres de chaques mots, excepté le premier, en majuscule. Si votre programme est destiné à être partagé, vous pouvez nommer en anglais. Voici quelques exemples de bon et de mauvais noms :

- Tout d'abord un nom d'élément doit être descriptif de ce qu'il représente. Il faut qu'en le lisant, n'importe qui sache à quoi il sert et comment il le fait. 
    ```js
    // mauvais
    var value = 'Robin';
 
    // mauvais
    var val = 'Robin';
 
    // bien
    var firstName = 'Robin';
    ```

- Ensuite, respecter la **camelCase** est une très bonne pratique, cela rends les noms plus simples à lire.
    ```js
    // mauvais
    var firstname = 'Robin';
 
    // mauvais
    var first_name = 'Robin';
 
    // mauvais
    var FIRSTNAME = 'Robin';
 
    // mauvais
    var FIRST_NAME = 'Robin';
 
    // bien
    var firstName = 'Robin';
    ```

- Pour nommer des booléens ou des listes (voir dans la suite de ce cours), il est important que le nom respecte une certaine logique en ajoutant des mots clés ou bien en mettant les mots au pluriel
    ```js
    // mauvais
    var visible = true;
 
    // bien
    var isVisible = true;

    // mauvais
    let fruit = ['apple', 'banana', 'peach'];

    // bien
    let fruits = ['apple', 'banana', 'peach'];
    ```

Pour en savoir plus sur les conventions de nommenclature, vous pouvez vous renseigner grâce aux liens ci-dessous :

[Lien 1 - Anglais](https://hackernoon.com/the-art-of-naming-variables-52f44de00aad)

[Lien 2 - Français](http://snowdream.github.io/javascript-style-guide/javascript-style-guide/fr/nantions.html)

[Lien 3 - Anglais](https://www.robinwieruch.de/javascript-naming-conventions)

> Il existe plusieurs autres styles de nomenclature comme PascalCase, snake_case, ou alors kebab-case. Leurs noms sont assez descriptifs de ce qu'ils représentent.

## Fonctionnalités en Javascript

### Les variables 

Une variable peut être vue comme un espace mémoire dans lequel on peut stocker des informations pour les réutiliser plus tard. Il en existe de nombreux types mais nous nous contenteront ici d'énumérer les principales.

En Javascript, la gestion des variables est automatique, c'est à dire que lors de la déclaration d'une variable, vous n'êtes pas obligé de spécifier son type (au contraire du C par exemple).

ainsi on peut écrire le code suivant :
```js
    let x = 14; // x est une variable contenant un nombre
    let y = "Hello world!"; // y est une variable contenant une chaine de caractère
    let z = [1 , 2, "3"]; // z est une variable contenant une liste
```

#### Différentes manières de déclarer une variable

Les variables sont la plupart du temps déclarées à l'aide de 3 mots clés : **var**, **let**, ou **const**.

- **var** et **let** se ressemblent beaucoup mais on préfèrera l'utilisation de let. Leurs différences sont subtiles mais peuvent être sources de bugs, voir [ici](https://qr.ae/pNKyyV).

- **const** permet de définir une variable qu'on ne modifiera pas. On peut dire que c'est une variable invariable mais en vérité elle ne l'est pas complètement. On peut utiliser let ou var à la place mais par souci d'optimisation il vaut mieux y penser.

#### Différents types de variables

Il existe de nombreux types différents de variables, en voici une courte liste non-exhaustive :
- **Variable booléenne** (boolean) : Elle vaut soit vrai (true) ou soit faux (false).

- **Entier** : Les entiers sont des nombres entiers relatifs (positifs ou négatifs et correspondant donc à l'ensemble Z en mathématiques)

- **Chaine de caractères** : Souvent appelée "string" en anglais, elle contient du texte. Une chaine de caractère se note entre guillemets `' '` ou guillemets doubles `" "`.

- **Liste** :  Aussi appelée Array, une liste peut contenir une grande quantité d'éléments (jusqu'à 2<sup>32</sup> éléments !). Un élément peut être une variable, une fonction, ... Le premier élement d'une liste est à l'index (=position) 0, on y accède donc avec liste[0]. L'index du dernier élément vaut donc la longueur de la liste moins 1.
Elle se note avec des crochets `[élément1, élément2, ...]` et possède ses propres méthodes comme la méthode `.length` qui permet d'obtenir la longueur de la liste.

- **Dictionnaire** : Aussi considérée comme une array, c'est une liste dont chaque élément est introduit par une "clé". Un dictionnaire se note avec des accolades :
    ```js
    let dictionnaire = {
        "clé": valeur,
        "clé2": valeur2
    }
    ```
    Le système d'index est similaire aux listes mis à part qu'on peut accéder à un élément en utilisant sa clé entre guillemets. Dans l'exemple ci dessus ont peut donc accéder à l'élément "valeur2" en utilisant sa clé `dictionnaire["clé2"]` ou bien son index `dictionnaire[1]`.

- **undefined** : Si on ne défini pas une variable ou bien qu'elle n'existe pas, celle-ci vaudra `undefined`. Cela peut être voulu ou bien source d'erreur. Exemple :
    ```js
    let a; // a vaut undefined
    let a = a + b // Cette opération retournera une erreur car a et b ne sont pas définis
    ```
    > Il ne faut pas confondre `undefined` et `null`. Même si ils sont semblables leur utilisation n'est pas totalement la même.

### Les fonctions

Une fonction est un ensemble d'instructions contenues dans un bloc de code (donc entre {}) que l'on peut réutiliser autant de fois qu'on le souhaite après l'avoir déclaré. Faire des fonctions est une pratique très utile dans le cas ou un algorithme nécessite d'être exécuté plusieurs fois.

#### Déclarer une fonction

Pour déclarer une fonction en javascript on suit la notation suivante :
```js
function nom() {
    // code
}
```
Le mot clé `function` permet d'introduire la fonction. Les parenthèses à côté du nom sont là pour spécifier les paramètres (si il n'y en a pas il suffit de les laisser vides). 
Le corps de la fonction est un bloc de code délimité par des accolades {}

On peut déclarer une fonction avec des paramètres, c'est à dire en spécifiant des variables qui devront être spécifiées lors de l'appel de la fonction et qui pourront être utilisées dans le corps de la fonction. Ces paramètres se placent entre les parenthèses.

Exemple: 
```js
function puissance(x, y = 2) {
    return x ** y;
}
```
Cette fonction, appelée puissance permet d'obtenir la valeur de x à la puissance y. Le premier paramètre, ici appelé x est utilisé dans la fonction. Le deuxième paramètre, ici appelé y, vaut par défaut 2. L'affectation de paramètres par défaut se fait grâce au caractère `=`.

#### Appeler une fonction

Pour appeler une fonction, il suffit d'écrire son nom suivi des différents paramètres dans l'ordre entres parenthèses. Pour appeler la fonction définie dans l'exemple ci-dessus avec comme paramètre le chiffre 2, il faudrai donc taper `puissance(2)`. On peut ne pas spécifier le deuxième paramètre  car il est optionnel (voir ci-dessus). L'ensemble des variables déclarées à l'intérieur d'une fonction sont **locales**, c'est à dire qu'on ne peut y accéder qu'à l'intérieur du bloc de code de la fonction. En dehors de la fonction ces variables n'existent tous simplement pas.
> Les variables locales s'opposent aux variables **globales**, qui sont accessibles partout dans le programme.

Il est tout à fait possible de déclarer une fonction à l'intérieur même d'une fonction ou bien d'appeler une fonction à l'intérieur d'elle même. Ces pratiques peuvent provoquer des *boucles récursives*, qui peuvent être source de bugs.

### Les instructions conditionnelles

Les expressions conditionnelles permettent de faire prendre des décisions au programme en fonction d'un test ou d'un paramètre.
Cela peut se résumer à quelque-chose comme "Si [condition], alors [action], sinon [action 2]"

#### Les opérateurs de comparaison

Pour introduire les expressions conditionnelles, il est essentiel de comprendre le concept des opérateurs de comparaison. Ci dessous vous trouverez une courte liste des principaux opérateurs de comparaisons :
- **===** : Permet de tester si deux expressions sont strictement égales.
- **!==** : Permet de tester si deux expressions ne sont pas strictement égales.
- **>** : Permet de tester si un nombre est supérieur à un autre.
- **<** : Permet de tester si un nombre est inférieur à un autre
- **>=** : Permet de tester si un nombre est supérieur ou égal à un autre.
- **<=** : permet de tester si un nombre est inférieur ou égal à un autre.
- **!<variable>** : Permet de tester si une variable vaut `false`.

Dans les cas des test booléens (vrai ou faux), toute valeur autre que `false`, `undefined`, `null`, `0`, `NaN` (Not a Number) ou une chaîne vide  (`""`) renvoie true lorsqu'elle est testée dans une structure conditionnelle, vous pouvez donc simplement utiliser un nom de variable pour tester si elle est vaut true, ou même si elle existe (c'est-à-dire si elle est définie).

Il est possible de créer une grande condition à partir de plusieurs en utilisant les **opérateurs logiques** :
- ET logique (&&) : Renvoie `true` si les deux expressions logiques séparées par && sont vérifiées.
- OU logique (||) : Renvoie `true` si au moins une des deux expressions logiques séparées par || est vérifiée.
- NON logique (!) ; Renvoie `true` si l'élément accolé juste après le point d'exclamation (!element) vaut false ou n'existe pas.

Pour mieux comprendre les opérateurs de comparaisons, référez vous à [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Op%C3%A9rateurs/Op%C3%A9rateurs_logiques).

#### Instruction if...else

Les mots clés `if` et `else` permettent d'effectuer des tests. Ils correspondent respectivement à "si" et "sinon". Leur utilisation en pseudo-code ressemble à l'exemple ci-dessous :
```js
if(condition) {
    // code
}
else {
    // code
}
```

La condition peut être une comparaison de deux variables, un test d'existence d'une variable, un test utilisant une fonction, ...

Il est possible d'enchainer une infinité de else ou bien de retester une condition en utilisant le mot clé `else if`. 
Si une des conditions est vérifiée, le code correspondant s'exécutera puis le programme "sautera" toutes les autres éventualités.

### Les boucles

Les boucles sont des structures très utiles qui permettent de répéter un certain nombre de fois un bloc de code. Il en existe plusieurs mais nous allons ici nous concentrer sur les principales : les boucles `while` et `for`.

#### La boucle while

La boucle while peut se traduire par une boucle "tant que". Le contenu de son bloc de code s'exécutera tant qu'une condition est vérifiée. Dès lors que la condition ne sera plus vérifiée, le programme passera à la suite du code.
Exemple de boucle while : 
```js
let x = 0;
while(x < 10) {
    x++; // ++ permet d'incrémenter de 1 la variable
}
```
Ici, la boucle s'exécutera tant que la variable x sera plus petite que 10. La boucle s'exécutera donc 10 fois, et à la fin de la boucle, x vaudra 10.

> Attention, si la condition passée dans le while est toujours valable, cela créera une boucle infinie qui pourrai faire planter votre programme.

#### La boucle for

La boucle for propose une plus grande maitrise de ses conditions d'exécutions. Elle prends 3 paramètres : une expression initiale, une condition d'arrêt, et une expression incrément. Cela permet de contrôler précisément combien de fois la boucle s'exécutera. 
En vérité, ces trois arguments sont optionnels mais il est déconseillé de ne pas les utiliser sans les remplacer, pour en savoir plus cliquez [ici](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Instructions/for).

Exemple de boucle for :
```js
for(let i = 0; i < 5; i++) {
    // code
}
```
Ici le contenu de la boucle s'exécutera tant que i est plus petit que 5, et à chaque itération, i sera incrémenté de 1.

#### L'instruction break

L'instruction `break` permet de provoquer la fin de l'exécution d'une boucle. Cela permet d'éviter les boucles infinies par exemple.
```js
for (i = 0; i < a.length; i++) {
  if (a[i] === valeurTest) {
    break;
  }
}
```
Dans l'exemple ci-dessus, on parcout l'ensemble des éléments d'un tableau (appelé a) jusqu'à en trouver un qui est strictement égal à la variable valeurTest. La boucle s'arrête à l'instant ou on trouve une valeur qui correspond, même si il y en a d'autres après. 
> Construire cette boucle en utilisant for plutôt que while permet de s'assurer que, si aucune valeur de la liste ne correspond, la boucle s'arrête bien.

Il existe aussi une instruction `continue` qui permet de reprendre une boucle, mais nous n'allons pas la détailler ici.

## Analyse d'un programme Javascript

Nous allons donc maintenant analyser un programme contenant la plupart des notions vues durant cette courte introduction au Javascript.
> L'instruction `console.log()` permet d'afficher des éléments dans la console. 
```js
function multiplede3(x) {
    if(x % 3 === 0) { // L'opérateur % permet d'obtenir le reste d'une division Euclydienne
        return true;
    }
    else {
        return false;
    }
}

console.log('Les multiples de 3 dans les chiffres de 1 à 10 sont : ');

let liste = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

for(let i = 0; i < liste.length - 1; i++) {
    élément = liste[i];
    if(multiplede3(élément) === true) {
        console.log(élément)
    }
}
```
Dans la première partie de ce programme, on déclare une nouvelle fonction appellée multiplede3 et prenant pour paramètre une variable. La condition présente à l'intérieur de cette fonction vérifie que le reste de la division de x par 3 est égal à 0, si cette condition est vérifiée, alors la fonction vaudra `true`, sinon, elle vaudra `false`.

Ensuite, on défini une liste contenant 10 chiffres allant de 1 à 10.

On a ensuite une boucle qui s'exécute autant de fois qu'il n'y a d'éléments dans la liste. À chaques itérations de la boucle, on teste avec un `if` si l'élément est un multiple de 3 ou non. Si ca l'est, alors on l'affiche dans la console, sinon on continue. 

Le résultat de ce script dans la console est donc :
```
Les multiples de 3 dans les chiffres de 1 à 10 sont : 
3
6
9
```

En réalité il serait possible d'obtenir le même résultat avec un code beaucoup plus court mais ce n'est pas le but ici.

Si vous le souhaitez, vous pouvez tester ce script sur une plateforme comme [playcode](https://playcode.io/) ou bien [jseditor](https://jseditor.io/).

## Conclusion

Vous connaissez maintenant les bases de Javascript et êtes sûrement capable d'écrire un script basique contenant des fonctions, des expressions conditionnelles et des boucles. La plupart des programmes ont un squelette composé de ces différents éléments et vous êtes donc en mesure de lire et comprendre le fonctionnement de la plupart d'entre eux. Pour approfondir vos connaissances, vous pouvez apprendre à utiliser le javascript pour rendre une page web plus dynamique ou bien l'utiliser pour interagir avec d'autres services au travers d'APIs, grâce à des clients côté serveurs comme NodeJS.

Si tous ces mots compliqués ne vous ont pas effrayés et au contraire attisent votre curiosité, libre à vous de vous renseigner sur le sujet en cliquant sur un des liens accessible en bas de page.

Bien à vous,

Simon.

## Liens utiles

NodeJS - Client côté serveur qui supporte de nombreux modules et est extrêmement polyvalent : https://nodejs.org/fr/

StackOverflow - Un forum ou des passionnés répondront à toutes vos questions et vous aideront dans vos projets : https://stackoverflow.com/

Google - Un merveilleux site qui saura répondre à toutes les questions trop simples ou évidentes pour être posées à d'autres personnes sans les exaspérer : https://google.fr

Mon serveur Discord - Un lieu rempli de 0 et de 1 ou vous trouverez de l'aide et de nouveaux amis : https://discord.gg/zU9q7g

:)
