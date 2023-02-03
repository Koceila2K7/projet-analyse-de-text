# Projet statistiques / dimanche 02 avril avant 23h59 sinon pénalité
## Objectif : retrouver la langue maternelle (origine) de l'auteur d'un texte écrit en anglais
## Plan :
- svm vs logistic regression
- fonction d'évaluation des modèles
    - plusieurs métriques : accuracy, précision, recall, f1.
        - utiliser la 'macro' f-mesure pour voir l'evaluation de chaque categorie.
    - matrice de confusion sur toutes les origines.
        - essayer de regrouper les origines difficiles à séparer (former des sortes de petites matrices)
- bag of words vs tf-idf
- remove stop words or not
    - lister tous les mots du vocab avec les fréquences, pour trier une liste de mots outils (on se décide nous même de la liste), lemmatization nécessaire pour cette étape.
- lemmatization or not
    - logiquement dans notre cas d'usage, ne pas le faire car on se concentre sur la recherche de singularités, alors que la lemmatization recherche la généralité.
- stemming or not
    - pareil
- fonction qui liste tous les caractères et compte les fréquences, pour voir s'il y a des caractères bizarres (zero-width .. ?)
    - normalement pas de soucis car le prof a travaillé déjà dessus.
- séparation des mots
    - I’m, can’t : ne pas séparer pour notre cas d’usage.
- A explorer (on peut ajouter des choses dans le vecteur) :
    - on peut compter la ponctuation
        - visualisation possible avec des camemberts de couleurs
    - compter le nombre de caractères spéciaux (nombre d’apostrophes...)
        - aussi visualisation possible avec des camemberts de couleurs
    - longueur moyenne des phrases
    - nombre de mots différents dans le texte
    - fréquence de mot le plus utilisé
    - prendre chaque mot et voir s’il existe dans un dictionnaire, s’il n’est pas présent donc faute d'orthographe… puis peut être le nombre de fautes, ou faire le lien…
- avec un SVM on peut regarder les poids en sortie
- discrétisation ?
    - on peut dessiner une gaussienne avec les longueurs moyennes des phrases. si on a pas une gaussienne, regarder chaque catégorie
    
## Bilan :
dernière séance où on fera la liste de tout ce qu'on a testé pour voir pourquoi ça a marché ou cela n'a pas marché.

## Rendu
envoyer avec l'adresse paris saclay !
mettre dans le corps du message, dans le rapport, dans le code : les noms du binome.

### un seul format de rapport : PDF.
simple, propre et lisible.
pas la peine de reproduire le cours, on virect au but.
contenu : journal d'expérimentation:
1. idée de base qu'on veut tester.
2. hipothèse
3. implémentation (codée, existente, compliquée...)
4. résultat
5. analyse : le fait de faire ça nous a fait gagner 3 points de F-mesure, et en analysant .. on remarque que enlever/ajouter/modifier... a un effet sur qqchose..
avoir un aspect critique : pourquoi l'implémentation de départ ne marche pas.. observations..

### code (notebook..) : archive ZIP ou TGZ.
code python : notebook ou fichier
si besoin de lib qui ne sont pas dans la lib de base: mettre un readme pour préciser, pareil pour les versions.
si compliqué à lancer : expliquer dans le readme.
ne pas joindre les data ni les modèles.

base line du prof : 0.63 de f-mesure.
test sur 1100 textes (100 de chaque langue) (à voir  si on utilise cette info)
on fait tourner dessus on obtient les prédictions finales.

joindre un fichier .txt et sur chaque ligne y'a la prédiction (attention à l'ordre des lignes)
