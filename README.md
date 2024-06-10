# TIPS : GIT (BASH & GUI) 
Les meilleurs astuces git


## Les commandes les plus fréquentes

- Utilisez les commandes suivantes lorsque vous voulez faire un *"commit"* depuis votre dépôt local vers celui distant.
  ```
  git add .
  git commit -m "Votre message de commit"
  git push origin main
  ```


# Compilation des Commandes Git

Ce document regroupe et organise les commandes Git discutées, offrant une référence complète pour la gestion de projets avec Git.

## Configuration et Initialisation

- Configurer le nom d'utilisateur et l'email :
  ```
  git config --global user.name "Votre Nom"
  git config --global user.email "votre.email@example.com"
  ```

- Initialiser un nouveau dépôt Git :
  ```
  git init
  ```

## Gestion de Commits

- Ajouter des fichiers à l'index :
  ```
  git add <fichier> ou git add .
  ```

- Commit les changements :
  ```
  git commit -m "Message de commit"
  ```

- Commit sans changement (commit vide) :
  ```
  git commit --allow-empty -m "Message de commit"
  ```

- Modifier le dernier commit :
  ```
  git commit --amend
  ```

- Réutiliser le message du dernier commit :
  ```
  git commit --amend -C HEAD
  ```

## Branches et Fusion

- Créer une branche :
  ```
  git branch <nom_de_la_branche>
  ```

- Changer de branche :
  ```
  git checkout <nom_de_la_branche>
  ```

- Fusionner une branche :
  ```
  git merge <nom_de_la_branche>
  ```

- Fusionner `master` et `main` :
  ```
  git checkout master # ou main
  git merge <nom_de_la_branche_source>
  ```

## Annulation et Révision

- Annuler des changements (fichier spécifique) :
  ```
  git checkout -- <fichier>
  ```

- Annuler le dernier commit (garde les changements) :
  ```
  git reset --soft HEAD~1
  ```

- Supprimer définitivement le dernier commit :
  ```
  git reset --hard HEAD~1
  ```

## Travail avec les Remotes

- Ajouter un dépôt distant :
  ```
  git remote add <nom_court> <url>
  ```

- Pousser les changements vers le dépôt distant :
  ```
  git push <nom_court> <nom_de_la_branche>
  ```

- Forcer le push (après amend ou rebase) :
  ```
  git push --force # ou --force-with-lease pour plus de sécurité
  ```

## Nettoyage et Maintenance

- Nettoyer les fichiers non suivis :
  ```
  git clean -fd
  ```

- Compresser le dépôt local :
  ```
  git gc
  ```

## Bonnes Pratiques

- Utilisez `git commit --amend` et `git push --force` avec prudence, surtout dans des environnements de travail partagés pour éviter de perturber le travail des autres.

- Effectuez des commits fréquents avec des messages descriptifs pour une meilleure traçabilité et collaboration.

- Utilisez des branches pour organiser les fonctionnalités, corrections, et expérimentations, fusionnez régulièrement pour minimiser les conflits.

# Gestion de conflits repo locla VS repo distant


# Gestion de fichiers volumineux (en cas de problèmes)

 ```git
# Installer et initialiser Git LFS
git lfs install

## Suivre les fichiers volumineux
git lfs track "*.dll"
git lfs track "*.lib"

# Ajouter et commiter les fichiers suivis par Git LFS
git add .gitattributes
git add .env_win/Lib/site-packages/llvmlite/binding/llvmlite.dll
git add .env_win/Library/bin/mkl_avx512.2.dll
git add .env_win/Library/bin/mkl_core.2.dll
git add .env_win/Library/bin/mkl_intel_thread.2.dll
git add .env_win/Library/bin/mkl_pgi_thread.2.dll
git add .env_win/Lib/site-packages/torch/lib/torch_cpu.dll
git add .env_win/Lib/site-packages/torch/lib/dnnl.lib
git commit -m "Add large files with Git LFS"

# Pousser les modifications vers le dépôt distant
git push origin main
 ```

---
Ce document vise à servir de référence rapide pour les commandes Git essentielles et avancées, facilitant la gestion efficace des projets de développement.
