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