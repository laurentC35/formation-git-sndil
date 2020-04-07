<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="chapter" -->

## 5

### Conflits et fusion

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Exemple

<div class="center">
    <img src="./images/conflit-2.png" style="width:800px;"/>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Conflit

Lors d'un `git pull`, en général, git arrive à fusionner tout seul la dernière version recupérée et **votre** dernière version, il peut en revanche avoir des conflits.

Un conflit peut survenir quand la **même ligne** du **même fichier** a été modifiée différemment par deux personnes différentes.

Des marqueurs de conflits apparaissent dans les fichiers concernés :

```txt
<<<<<<< HEAD
J'aime bien les conflits
=======
J'aime les conflits
>>>>>>> origin/master
```

<sub>Entre _<<<<<<< HEAD_ et les _=_ ce sont vos modifications (le fichier local) et le reste sont les modifications du fichier que vous chercher à merger.</sub>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Résoudre un conflit

Pour résoudre un conflit, il suffit de :

- conserver seulement la(les) ligne(s) que vous voulez garder et supprimer les marqueurs de conflits.
- `git add .` pour ajouter les fichiers résolus dans l'index et `git commit` pour valider une fois que **TOUT** est résolu
- `git push` pour envoyer la fusion dans le dépôt distant

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Évitons les conflits

Mieux vaut les éviter que de les résoudre, pour cela il faut :

- commiter souvent (par des petits lots de modifications)
- préférer les petits fichiers
- communiquer avec les autres membres de l'équipe:
  - dire sur quoi on travaille
  - prévenir en cas de rafactoring important
- mettre à jour sa copie local très régulièrement : `git pull`

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### TP 5

#### Simuler un conflit

- &#10112; Reprener le dépôt `travaux-pratiques`
- &#10113; Je vais modifier la 1ère ligne du fichier helloWorld.txt et pousser mes modifications vesr le dépôt distant
- &#10114; Sans rafraichir votre dépôt, modifier aussi cette même ligne en incrivant votre nom et prénom par ex.

```bash
Bienvenue à la formation -> Bonjour je m'appelle ....
```

- &#10115; valider vos modifications (`commit` mais pas de `push`)
- &#10117; rafraichiser votre dépôt

#### Résoudre le conflit

- &#10112; résoudre le conflit (à vous de choisir qu'elle version vous voulez garder)
- &#10113; valider les modifications : bravo vous avez résolu le conflit

<sub>
_**Note :** ne pousser pas vos modifications vers le dépôts distant. Etant donné que nous sommes nombreux sur le projet, nous allons recrééer des conflits, puisque chaqu'un propose sa résolution du conflit._
</sub>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

<div class="center">
<video controls loop="true">
  <source src="./videos/git-tp5.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
</div>
