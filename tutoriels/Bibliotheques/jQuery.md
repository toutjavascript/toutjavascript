# jQuery

## Introduction

Les forces de cette bibliothèque : **simplifier** l'écriture pour des besoins très fréquents en JavaScript,
tout en garantissant une **compatibilité** confortable avec les principaux navigateurs, y compris d'anciennes versions (IE 9+).

Au programme :

- Sélection d'éléments de page web
- Requêtes [Ajax/XMLHTTP](http://www.toutjavascript.com/savoir/xmlhttprequest.php3)
- Animations et effets graphiques
- Gestion d'événements

Très en vogue au début des années 2010, le recours à cette bibliothèque devient moins systématique,
notamment grâce à l'évolution des navigateurs vers un meilleur support des nouveaux standards (surtout JavaScript et CSS).

En effet, le coût de jQuery est :
- Un chargement de ressource supplémentaire (certes réduit à 32 Ko compressé),
- De moins bonnes performances d'exécution par rapport à du JavaScript natif (à relativiser, car avant
que la différence soit détectable par l'utilisateur, il y a quand même une sacrée marge).

Voir [cette question StackOverflow](https://stackoverflow.com/q/41948057/488666) (en anglais).

## Mise en route

Créez un fichier HTML vide classique.

Téléchargez [la dernière version de jQuery](http://jquery.com/download/) (un des deux premiers liens de "download" conviendra très bien)
et déplacez le fichier `jquery-x.y.z.js` ou `jquery-x.y.z.min.js` dans le même répertoire.

Entre les balises `<body>`, rajouter le chargement du fichier JavaScript contenant la bibliothèque.

Ce qui donne (adapté de l'[exemple du site officiel](https://learn.jquery.com/about-jquery/how-jquery-works/)) : 

    <!doctype html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>Test jQuery</title>
    </head>
    <body>
        <script src="jquery-x.y.z.js"></script>
        <script>
            // Votre code ici
        </script>
    </body>
    </html>

A présent pour essayer jQuery, nous allons créer un `<div>`, auquel nous allons attacher un événement `click()`
pour afficher "Bonjour" dans un autre `<div>` lors de ce clic.

En HTML nous rajoutons donc :

    <div id="cliquable">Clique moi</div>
    <div id="affichage">...</div>

Et à la place de `Votre code ici`, mettons :

    $(document).ready(function() { // la page et les images sont chargées et manipulables avec jQuery
        $('#cliquable').click(function() {
            $('#affichage').html('Bonjour');
        });
    });

[Voir la démonstration](https://jsfiddle.net/dL4sgf6a/1/).

Remarques :

- `$` représente l'objet global jQuery.

- On voit d'emblée qu'il est possible de **désigner** des éléments HTML et de leur appliquer
des fonctionnalités JavaScript, de la même manière qu'on applique des styles en CSS.
Il est possible de le faire également en natif avec `document.querySelector()` et `document.querySelectorAll()`
mais jQuery va plus loin, comme nous le verrons ensuite.


## Exemples d'utilisation courants

### Requêtes Ajax

    // A créer
    var URL = 'http://www.toutjavascript.com/savoir/Bibliotheques/jQuery-exemple-news.json';
    
    $.ajax({
        url: URL,
        method: 'GET'
    }).then(function(data) {
        ...
    });

Ici un exemple qui crée des `<div>` cliquables à partir de données JSON :
https://jsfiddle.net/FrostyZ/b8do9eyp/2/

### Sélection


### Animations


## Plugins




## Compléments

### Sizzle

Permet de charger uniquement la partie "sélecteur" de jQuery (par ex. `Sizzle('.conteneur .element')`),
qui pèse seulement 4 Ko compressée.

Pour correspondre à la syntaxe courante jQuery, on peut faire un `var $ = Sizzle;` au début du script.

Attention : retourne un tableau d'objets HTML natifs, et non d'objets jQuery. On ne peut donc pas y appliquer
les méthodes de jQuery telles que `.click()`, `.css('propriété', 'valeur')`, `.each()`, etc.

Voir : https://sizzlejs.com/

### Zepto

Une bibliothèque presque équivalente à **jQuery**, en faisant quelques sacrifices sur la compatibilité avec les anciens navigateurs,
ce qui lui permet d'être encore plus légère : moins de 10 Ko compressée.
Voir : http://zeptojs.com/

### Puis-je me passer de jQuery ?

Liste des opérations courantes avec jQuery et leur équivalent en natif.
Permet d'éviter de recourir à jQuery si on n'a besoin que d'une poignée de fonctions.
Voir (en anglais) : http://youmightnotneedjquery.com/

### jQuery UI

### jQuery Mobile
