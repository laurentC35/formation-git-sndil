<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="chapter" -->

## 7

### La boîte à outils

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Remiser son travail : `git stash`

Changer de branche alors que la copie de travail est instable

- on est en plein milieu d’un travail
- valider ne serait pas une bonne idée

```bash
# Remiser les fichiers modifiés
git stash

# Remiser les fichiers modifiés et les fichiers ajoutés
git stash -u
```

Récupérer le contenu de la remise

```bash
git stash apply # Récupérer la dernière remise
git stash drop # Supprimer la dernière remise
git stash pop # Recupérer et supprimer la dernière remise
```

En général, git stash suivi peu après de git stash pop suffisent

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Étiquetage : git tag

**Pourquoi ?** : pour marquer un commit (ex:nouvelle version)

_**Note :** les tags font toujours référence au même commit (contrairement au branches qui avancent à chaque commit_

Commande :

```bash
git tag -a v2.1 -m "Message" # Créer une étiquette annotée
git tag v2.1 # Créer une étiquette légère
```

Pour un ancien commit :

```bash
git tag -a v2.1 9fceb02 -m "Message"
```

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Étiquetage : git tag

Partager ses tags :

```bash
git push origin v2.1 # Partager une étiquette
git push origin --tags # Partager tout ces tags
```

Supprimer des tags :

```bash
git tag -d v2.1 # Du dépôt local
git push --delete origin v2.1 # Du dépôt distant
```

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Zone de danger

Annuler un commit pas encore partager :

- Annuler le dernier commit `git reset HEAD~1`
- pour plus de détails : [documentation git](https://git-scm.com/book/fr/v2/Utilitaires-Git-Reset-d%C3%A9mystifi%C3%A9)

Annuler des modifications distantes : `git revert`

- annule un _commit_ ou une plage de _commits_
- création de nouveaux _commits_ qui annulent les modifications plus ancienne

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="slide" -->

### Zone interdite

Il très déconseiller de réécrire l'historique de git.
Lorsque ces commandes sont faites, il faut que les autres membre de l'équipe supprime leur dépôt et le re-clone.

L’option nucléaire : **filter-branch**

| Objectif                                          |     Filtre à utiliser |
| :------------------------------------------------ | --------------------: |
| modifier l’arborescence dans l’historique         |        --index-filter |
| modifier le contenu de fichiers dans l’historique |         --tree-filter |
| modifier les métadonnées de l’historique          |          --env-filter |
| faire d’un sous-répertoire la nouvelle racine     | --subdirectory-filter |
| modifier tous les messages de validation          |          --msg-filter |
