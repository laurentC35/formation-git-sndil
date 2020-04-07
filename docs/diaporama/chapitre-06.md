<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="chapter" -->

## 6

### Les branches

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Pourquoi utiliser des branches ?

- Pour commencer un nouveau un développement pour un correctif ou une nouvelle fonctionnalité
- Pour séparer le nouveau développement des branches communes
- Pour faire cohabiter plusieurs versions d'un projet et les faire évoluer séparément

Les branches de correctif/fonctionnalité peuvent ensuite être **réintroduites** dans les branches communes à l'aide de fusion ou de rebase. (vu plus tard)

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Qu'est ce qu'une branche ?

Une branche dans Git est simplement un pointeur léger et déplaçable vers un commit

À chaque nouveau commit, la branche « avance »

- elle pointe vers le dernier commit

Pour créer un nouvelle branche :

- `git branch <nom_de_la_branche>` : créer une nouvelle branch et reste dans celle courante
- `git checkout <nom_de_la_branche>` : pour basculer de branche
- `git checkout -b <nom_de_la_branche>` : Commande plus rapide et équivalent au deux

Lorqu'on bascule dans une autre branche, git change notre copie de travail.
On ne bascule dans une autre branche que lorqu'on est sûr qu'il n'y a pas de risque de perdre son travail (_commit_ avant ou _stash_)

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Exemple 1

<sub>
Le dépôt avec une seule branche :
La branche 'master' n'est pas particulière elle est :
- la branche créée lors d'un git init 
- la branche extraite par défaut lors d'un `git clone`</sub>
</sub>

<div class="center">
    <img src="./images/one-branch.png" style="width:600px;"/>
</div>
<sub>
Etat du dépôt après un `git checkout -b new`
</sub>
<div class="center">
    <img src="./images/checkout-b.png" style="width:600px;"/>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->
<sub>

A chaque commit, on fait avancer la branche new (tant qu'on est situé sur la branch new (pointeur HEAD))
</sub>

<div class="center">
    <img src="./images/branch-new-avance.png" style="width:800px;"/>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Commande de bases

- `git branch -v` : lister les branches
- `git branch -d <nom_de_la_branche>` : supprimer une branche

<sub><sub>
_**Note** : si la branche n'a pas été fusionné, on peut perdre des données, la commande pour ignorer l'avertissement :_
</sub></sub>

- `git branch -D <nom_de_la_branche>`

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Intégrer le travail d'une branche dans une autre (fusionner les branches)

On se place dans la branche cible et on intègre la branche développée:

Exemple 2 :

- `git checkout master`
- `git merge new`

<div class="center">
    <img src="./images/simple-fusion.png" style="width:700px;"/>
</div>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Travailler avec un dépôt distant

Toutes les commandes qu'on vient de voir se passe en local, les commandes pour partager le travail sur le dépôt distant sont les suivantes :

#### &#10112; Se placer sur une branche existante du dépôt distant

<sub>Commande si elle n'a pas déjà été récupérée (sinon un `git checkout` suffit)</sub>

```bash
git checkout -b <nom_de_la_branche> origin/<nom_de_la_branche>
```

#### &#10113; Créer une nouvelle branche et la pousser sur le dépôt distant

```bash
git checkout -b <nom_de_la_branche>
git push -u origin <nom_de_la_branche>
```

#### &#10114; Supprimer une branche et la supprimer sur le dépôt distant

```bash
git branch -D <branch_name> # supprime la branche en local
git push origin --delete <branche_name> # supprime la branche sur le dépot Git distant
```

<sub>_**Note :**origin peut-être remplacer par une autre **remote**_</sub>

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Pourquoi et quand utiliser les branches ?

Pourquoi ? :

- pour séparer les développement sans empieter sur les autres
- Avec git c'est recommandé
- car git est optimisé et rapide pour:
  - la création de branches
  - le passage d'une branche à l'autre
  - la fusion de branches

Quand ? :

- une branche par fonctionnalité (vie courte)
- une branche par ticket/bug (vie très courte)
- branches plus ou moins stable (vie longue)
- branche protégée (vie très longue)
- une branche par environnement (dev, qf, prod, etc ...)

_**Note :** Comme pour les commits, les noms de branches doivent être explicites_

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### TP 4

A faire à la console / avec GitHub desktop

- &#10112; reprener votre dépôt créé dans le TP 2
- &#10113; créer une nouvelle branche 'add-idep'
- &#10114; ajouter un fichier votre_idep.md avec nom et prénom dans cette branche

```bash
Nom Prénom
```

- &#10115; pousser cette branche sur votre dépot distant
- &#10116; vérifier sur GitLab votre travail et constater la différence entre 'master' et 'add-idep'
- &#10117; revener sur votre branche 'master' en local
- &#10118; intégrer les modifications de 'add-idep' dans 'master'
- &#10119; pousser les modifications sur votre dépot distant

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

<div class="center">
<video controls loop="true">
  <source src="./videos/git-tp4.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
</div>
