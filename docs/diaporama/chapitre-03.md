<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="chapter" -->

## 3

### Les opérations de bases

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Démarrer un dépôt Git

Vous pouvez principalement démarrer un dépôt Git de deux manières :

- prendre un projet ou un répertoire existant et l'importer dans Git
- cloner un dépôt Git existant (présent sur GitLab)

_**Note :** On utilisera quasiment toujours la deuxième solution_

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

#### Initialisation d'un dépôt Git dans un répertoire existant

Se placer dans le répertoire existant et faire la commande :

```bash
 git init
```

<!--
Cela crée un dossier .git qui contiendra tous le dépôt local (historique, versions,...).
Ce depôt créé ainsi n'est connecté à aucun dépôt distant.
Pour le lier à un dépôt vide distant :

```bash
git remote add origin [url]
git add .
git commit -m "Initial commit"
git push -u origin master
```
-->

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

#### Cloner un dépôt existant

Il faut au préalable récupérer l'url du dépôt distant

```bash
git clone [url]
```

**Remarque :** à l'Insee on va utiliser l'url en SSH

<div class="center">
    <img src="./images/clone-ssh.png" style="width:350px;"/>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

<div class="center">
<video controls loop="true">
  <source src="./videos/git-clone.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Opérations de base, travailler avec le dépôt Local

<div class="center">
    <img src="./images/operation-base.png" style="width:500px;"/>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Opérations de base, travailler avec le dépôt Local

**Git status**

Cette commande permet de lister les fichiers modifiés avant un commit.

Commande:

```bash
git status
```

**Git add**

L'index de Git est une zone d'attente avant un commit
Toutes les modifications du code passent obligatoirement dans l'**index**.

La commande pour ajouter les modifications à l'**index** est :

```bash
git add chemin/helloWorld.txt
git add * # ajoute toutes les modifications à l'index
```

Une fois ajoutées à l'index, les modifications peuvent être commitées.

Désindexer : `git reset`

```bash
git reset . # désindexer
```

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Opérations de base, travailler avec le dépôt Local

**Git commit**

Un commit doit représenter un ensemble cohérent de modifications. La commande permet d'enregistrer les modifcations au projet (**i.e** mettre à jour le dépôt Local par rapport à votre copie de travail)

Commande :

```bash
git commit -m "Création de fichier : helloWorld.txt"
```

Le message doit être **le plus clair possible**.

Exemple de règle : _Contexte : Mots-clés représentatif_ (ex de message clair : _"Boutique : passage francs->euros"_)

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### TP 1 : Faire mon premier commit

A faire à la console / avec GitHub desktop

<!-- .element: class="simple-list" -->

- &#10112; Initier un dépôt Local vide
- &#10113; créer un fichier helloWorld.txt
- &#10114; valider vos modifications dans votre dépôt Local
