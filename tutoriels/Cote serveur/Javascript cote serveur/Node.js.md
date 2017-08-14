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

## Utilisations courantes

### Scripts isolés

Traitements en tous genres, calculs, pouvant être lancés à intervalles réguliers
comme tout programme exécutable en ligne de commande.

Par exemple, [celui-ci](https://gist.github.com/RandomEtc/1803645) convertit un fichier CSV en page HTML.

### Partie serveur d'une application web

A l'aide des bibliothèques de base fournies avec **Node.js**, il est possible d'écrire un serveur web (voir [cet exemple très simplifié](https://blog.risingstack.com/your-first-node-js-http-server/)).

Des frameworks spécifiques à **Node.js** comme [Express](http://expressjs.com/fr/) disposent de cette fonctionnalité "serveur web".

Ainsi, en installant seulement **Node.js** et ce type de framework, on peut démarrer un projet d'application web en écrivant la partie serveur en Javascript, comme si on installait [XAMPP](https://www.apachefriends.org/fr/index.html) (Apache, PHP, MySQL) pour développer en PHP.

Après avoir installé **Node.js** :

* Créer un nouveau répertoire pour son projet et y ouvrir un terminal.

* Lancer la commande `npm init`, ce qui permettra d'installer des **[packages npm](https://www.npmjs.com/)** pour votre projet. <!-- TODO lien vers tuto npm lorsqu'il sera rédigé --> Dans le cadre d'un projet test, vous pouvez ignorer toutes les questions posées en appuyant sur entrée.

* Dans le répertoire de votre projet, vous constaterez que le lancement de `npm init` a créé un fichier `package.json`. Les futurs **packages npm** associés à votre projet y seront listés.

* Installer **Express** en faisant `npm install express --save`. Cela va créer un sous-répertoire `node_modules` contenant le code des packages installés, et mettre à jour le fichier `package.json`.

* Créer un fichier `app.js` contenant :

        // Exemple adapté de la mise en route d'Express: http://expressjs.com/fr/starter/hello-world.html
        var express = require('express');
        var app = express();

        // '/' est la route racine
        app.get('/', function (req, res) {
            res.send('Bonjour !');
        });

        app.listen(3000, function () {
            console.log("Application d'exemple écoutant sur le port 3000!");
        });

* Lancer `app.js` ce qui lancera le serveur web

        > node app.js
        Application d'exemple écoutant sur le port 3000!
    
* Ouvrir un navigateur et aller à l'adresse http://localhost:3000 ; le message `Bonjour !` doit s'afficher.

## Eléments spécifiques

### Modules

Afin d'organiser votre code, il est possible d'utiliser la fonctionnalité de modules proposée par **Node.js** pour réutiliser un groupe de fonctions dans plusieurs fichiers.

Par exemple : créer un fichier `module.js` comportant une fonction "exportée" :

    function fonctionTresUtile() {
        console.log("Ceci s'affiche depuis une fonction exportée !");
    }
    
    exports.fonctionTresUtile = fonctionTresUtile;

Dans le même répertoire, créer un fichier `script.js` contenant :

    const module = require('module'); // permet l'accès aux fonctions définies dans module.js
    module.fonctionTresUtile(); // exécute la fonction exportée

Lancer `script.js` :

    > node script.js
    Ceci s'affiche depuis une fonction exportée !
