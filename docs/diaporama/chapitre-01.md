<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="chapter" -->

## 1

### Présentation générale de Git

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Qu'est ce que Git ?

Git est un outil qui va vous permettre de versionner votre code, c'est-à-dire gérer les versions de votre code au fur et à mesure que vous le modifiez.

Git est donc une système de gestion de version.

%%%

<!-- .slide: class="slide" data-background-image="images/logo-git.png" data-background-size="600px" -->

### Système de gestion de versions

Il permet de :

- revenir à une version spécifique
- revenir à une version antérieure d’un fichier spécifique
- retrouver la dernière modification qui a pu introduire un bug

De plus, on peut en général :

- partager ses modifications et de récupérer celles des autres

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Système de gestion de versions distribuée

Il existe de nombreux logiciels de gestion de version, qui peuvent être basés sur différents modèles :

- **Modèle centralisé** : un serveur central contrôle toute la base de code du logiciel. (ex:SVN)
- **Modèle distribué** : toutes les machines ont accès à la base de code, pas besoin de passer par un serveur central, comme **Git**

**Avantages du modèle distribué** &#9786;

- Moins de risques de perdre son code puisqu'il est accessible par plusieurs sources.
- On peut travailler plus rapidement et sans être connecté à Internet puisqu'il n'y a pas besoin de se connecter à un serveur central.

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

%%%

### Pourquoi versionner son code ?

- Parce que vous ne supportez plus les fichiers \_old et \_new de vos collègues ?
- modifications régulières du code
- modifications qui peuvent apporter des bugs

&xrArr; il peut être difficile de se souvenir des dernières modifications et de retrouver ses repères dans le code quelques jours ou même quelques heures après

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

Avec un logiciel de versioning comme Git, vous pouvez garder la trace de toutes les modifications faites sur votre code pour pouvoir vous y retrouver à tout moment.

À chaque fois que vous faites une série de modifications (créer un fichier, supprimer un fichier, modifier un texte dans un fichier, etc.), vous allez pouvoir enregistrer ces modifications dans un **commit**.
