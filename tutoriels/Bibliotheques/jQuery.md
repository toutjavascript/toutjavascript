# jQuery

## Introduction

Les forces de cette bibliothèque : **simplifier** l'écriture pour des besoins très fréquents en JavaScript,
tout en garantissant une **compatibilité** confortable avec les principaux navigateurs, y compris d'anciennes versions (IE 9+).

Au programme : sélection d'éléments de page web, requêtes [Ajax/XMLHTTP](http://www.toutjavascript.com/savoir/xmlhttprequest.php3),
animations et effets graphiques, gestion d'événements.

Très en vogue au début des années 2010, le recours à cette bibliothèque devient moins systématique,
notamment grâce à l'évolution des navigateurs vers un meilleur support des nouveaux standards (surtout JavaScript et CSS).

En effet, il faut accepter le coût d'un chargement de ressource supplémentaire (certes réduit à 32 Ko compressé),
ainsi que de moins bonnes performances d'exécution par rapport à du JavaScript natif (à relativiser, car avant
que la différence soit détectable par l'utilisateur, il y a quand même une sacrée marge).
Voir (en anglais) [cette question StackOverflow](https://stackoverflow.com/q/41948057/488666).

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

A présent nous allons créer un `<div>`, auquel nous allons attacher un événement "click()"
et faire afficher "Bonjour" dans un autre `<div>`.

En HTML nous rajoutons donc :

    <div id="cliquable">Clique moi</div>
    <div id="affichage">...</div>

Et à la place de `Votre code ici` :

    $(document).ready(function() { // la page et les images sont chargées et manipulables avec jQuery
        $('#cliquable').click(function() {
            $('#affichage').html('Bonjour');
        });
    });

[Voir la démonstration](https://jsfiddle.net/dL4sgf6a/1/).

## Exemples d'utilisation courants



## Compléments

### Sizzle



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
