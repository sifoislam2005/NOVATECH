# Réponses TP Git — NovaTech

## Mission 5
1. Premier commit : 2a212f7
2. Commit d'ajout de la page Contact : 21cda75 "Creation de la page Contact"
3. Nombre de commits : <résultat de git rev-list --count HEAD>
4. Historique graphique : git log --oneline --graph --all
Commande pour examiner un commit Contact : git show 404a2ad

## Mission 8
Commande : git reset --soft HEAD~1
Elle deplace HEAD d'un commit en arriere sans toucher au repertoire de travail,
donc la modification de style.css est toujours présente
`git reset --hard HEAD~1` aurait supprime le commit et la modification du fichier

## Mission 9
Commande : git revert HEAD
Le commit etant deja partage on ne doit pas reecrire l'historique, revert cree un nouveau commit qui annule
les changements 

## Mission 11
Commande : git cherry-pick 4e85b97
Commit récupere : 4e85b97 "Correction du titre de l'accueil"
Un merge aurait importé les 3 commits, dont les deux expérimentaux non voulus

## Mission 12
Commandes : git tag -a v1.0.0 -m "Premiere version stable de NovaTech" puis git show v1.0.0

1.0.0 = MAJEUR.MINEUR.CORRECTIF
1er chiffre (majeur) : changements incompatibles avec la version précédente
2eme chiffre (mineur) : nouvelle fonctionnalite compatible
3eme chiffre (correctif) : correction de bug

Correction de bug mineur : 1.0.1
Nouvelle fonctionnalité compatible : 1.1.0
Refonte majeure incompatible :: 2.0.0

## Mission 13
Fichier .gitignore contenant : debug.log, cache/, .env
Verification avec git status : seul .gitignore apparaît comme nouveau fichier

## Questions finales

1. La zone de travail c'est mes fichiers tels qu'ils sont sur mon PC, avec les modifs en cours. Le staging c'est ce que j'ai préparé avec git add pour le prochain commit. L'historique c'est tous les commits déjà enregistrés dans le dépôt.

2. Travailler sur une branche à part permet de garder main propre et fonctionnelle. Je peux tester ma fonctionnalité, faire des erreurs ou même l'abandonner sans casser le projet principal, et je fusionne seulement quand c'est fini.

3. Dans la mission 8 j'ai utilisé git reset : le commit disparaît de l'historique, donc on réécrit l'historique. Ça marche seulement si le commit est resté en local. Dans la mission 9 j'ai utilisé git revert : il crée un nouveau commit qui fait l'inverse, sans rien supprimer. C'est ce qu'il faut faire quand le commit a déjà été partagé avec l'équipe.

4. Quand je suis en train de travailler sur quelque chose qui n'est pas fini et qu'on me demande une correction urgente ailleurs. Avec git stash je mets mon travail de côté, je fais la correction, puis je reprends où j'en étais.

5. Parce que parfois une branche contient un seul commit utile au milieu d'autres commits de test. Avec le cherry-pick je prends juste celui dont j'ai besoin, alors qu'un merge aurait tout ramené, même ce que je ne voulais pas.

6. HEAD indique où je me trouve dans le dépôt : c'est le commit (et la branche) sur lequel je travaille en ce moment.

7. HEAD~2 c'est le commit qui se trouve deux commits avant celui où je suis.

8. Un tag sert à marquer un commit important, en général une version du projet comme v1.0.0. Comme ça on retrouve facilement cette version plus tard.

9. Avec des petits commits clairs, on comprend facilement ce qui a été fait et quand. Si un bug arrive, c'est plus simple de trouver d'où il vient et d'annuler ou récupérer juste le bon commit.

10. Certains fichiers n'ont rien à faire dans le dépôt : les logs et le cache sont générés automatiquement et changent tout le temps, et le .env contient des infos sensibles comme des mots de passe. Les versionner alourdirait le projet et pourrait exposer des données privées.