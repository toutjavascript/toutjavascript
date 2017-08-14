# Node.js

## Introduction

[**Node.js**](https://nodejs.org/fr/) permet d'exécuter du Javascript en dehors du contexte du navigateur,
comme on pourrait lancer un programme en PHP ou Python en ligne de commande.

Fonctionne sur les principaux systèmes (MacOS, Linux, Windows).

Il suffit de [télécharger](https://nodejs.org/fr/download/) puis d'installer **Node.js** sur sa machine.
Rédiger son code dans un fichier, puis lancer ce dernier en lançant simplement la commande :

    > node monfichier.js

Attention, certaines fonctionnalités habituelles de Javascript (accès aux éléments HTML, taille de la fenêtre courante,
gestion des Cookies...) seront inopérantes, puisque nous ne sommes pas ici dans le contexte d'un navigateur.

L'instruction `console.log(...)`, au lieu d'écrire dans la [console Javascript](http://www.toutjavascript.com/savoir/navigateur-console-javascript.php)
du navigateur, va afficher les informations directement à l'écran. Ainsi, lancer un fichier `bonjour.js`
contenant uniquement la ligne `console.log('bonjour !');` va donner :

    > node monfichier.js
    bonjour !

## Eléments spécifiques

### Modules



## Utilisations courantes

### Scripts "seuls"



### Partie serveur d'une application web


