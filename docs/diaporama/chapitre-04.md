<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="chapter" -->

## 4

### Les dépôts distants

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Dépôt distant

L'interêt de Git est de permettre de:

- travailler à plusieurs sur un meme projet
- avec une copie de son travail enregistrée ailleurs qu'en local

**Vive les dépôts distants :**

- chaque développeur possède son propre dépôt lié à un dépôt distant commun à tous
- chaque développeur pourra envoyer (**push**) au depôt distant les commits qu'il a fait sur son dépôt Local
- chaque développeur pourra récupérer (**pull**) les commits partagés par les autres

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Dépôt distant

Le dépôt distant sert de pivot pour partager le code entre tous les dépôts locaux.
Il est source de vérité pour le code.

<div class="center">
    <img src="./images/depot-distant.png" style="width:350px;"/>
</div>

Ici on peut imaginer que :

- Arthur travaille sur AUS
- Mathieu est sur son poste
- Tom est en télé-travail

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Dépôt distant

Le lien entre le dépôt local et le dépôt distant est une **remote**.
Une **remote** est une URL qui pointe vers le dépôt distant.

Pour lister les remotes de votre dépôt :

```bash
git remote # lister le noms des remotes
git remote -v # lister le nom et l'url des remotes
```

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Travailler avec un dépôt distant

Il y a 2 opérations principales :

- récupérer les modifications
- pousser vos modification vers le dépôt distant.

#### Récupérer :

Il s'agit de la commande

```bash
git pull
```

Elle effectue `git fetch` et `git merge` à la suite.
`git fetch` récupère toutes les modifications dans votre dépôt local et `git merge` met à jour / fusionne votre copie de travail avec la dernière version de votre depôt local.

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Travailler avec un dépôt distant

#### Pousser :

Il s'agit de la commande :

```bash
git push
```

On l'execute pour envoyer nos commits du dépôt local vers le dépôt distant afin de partager notre travail.

<sub>_**Note :** toujours faire git pull avant de faire git push quand vous travaillez à plusieurs afin d'éviter au maximum les conflits_</sub>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Travailler avec le dépôt distant : bilan

<div class="center">
    <img src="./images/data-git.png" style="width:800px;"/>
</div>
%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### TP 2 : Faire mon premier commit sur un dépôt distant

A faire à la console / avec GitHub Desktop (pas l'étape 3)

<!-- .element: class="simple-list" -->

- &#10112; Créer un dépôt distant sur votre espace [GitLab](https://git.stable.innovation.insee.eu) (avec un README.md)
- &#10113; Cloner ce dépôt sur votre poste
- &#10114; Modifier le README.md
- &#10115; Pousser vos modification sur le dépôt distant
- &#10116; Constater l'état de votre dépôt distant

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

<div class="center">
<video controls loop="true">
  <source src="./videos/git-tp2.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### TP 3 : Travailler à plusieurs sur un dépôt distant

A faire à la console / avec GitHub Desktop

<!-- .element: class="simple-list" -->

- &#10112; Clonez le dépôt distant `[git@git.stable.innovation.insee.eu:22222]:formation-git-sndi-lille/travaux-pratiques.git`
- &#10113; Ajoutez un fichier votre_idep.md avec votre nom et prénom dans le dossier students

<sup><sup>
_**Aide :** Pour créer le fichier, tapez à la console au niveau du dossier students :_
</sup></sup>

```bash
touch votre_idep.md
```

<sup><sup>
_puis pour le modifier : bloc notes, notepad++, VSCode, Atom, ..._
</sup></sup>

- &#10114; Poussez vos modifications sur le dépot distant

<sup><sup>
_**Note :** assurez-vous d'avoir la dernière version avant de pousser, les autres peuvent être plus rapide que vous_
</sup></sup>

- &#10115; Quand tout le monde a terminé, mettez à jour votre dépôt local
- &#10116; Constater l'état de votre dépôt local et du dépôt distant

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

<div class="center">
<video controls loop="true">
  <source src="./videos/git-tp3.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
</div>
%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->
<!--
### TP 4 : Travailler sur un cas réel de façon collaborative sur GitLab

Projet "volontaire" : _**patrimoine HVP**_

Merci à l'équipe de Romain !

%%% -->

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Travailler avec le dépôt distant : ignorer des fichiers

Certains fichiers ne doivent pas être versionnés, par exemple :

- fichiers issues d'une compilation
- fichiers de bibliothèques/dépendances
- etc ...

Pour ignorer ces fichiers/dossiers présent sur votre copie de travail et ne pas les transmettre au dépôt, on les précise dans un fichier **.gitignore** à la racine du projet.

- créer le fichier dans la console : `touch .gitignore`
- ignorer des dossier : _dossier/_
- ignorer certains fichiers avec une extension : _\*.tmp_
- ne pas ignorer certains fichiers (ajouter un "!" devant le chemin): !chemin/vers/fichier.txt
