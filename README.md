# Arborescence DD&RS
Cette arborescence a pour objectif de parcourir le schéma directeur DD&RS 2024-30, de l'université Gustave Eiffel, de manière interactive. 

*****A vérifier !!!*****
Respect des indicateurs mis aléatoirement

## Composition du projet 
Le projet est composé de plusieurs fichiers : 1 fichier HTML, 3 fichiers JSON et ce fichier README

Le **fichier index.html** est le coeur du projet, puisque c'est celui qui va s'executer et qui va relier tous les fichiers. 
Toutes les modifications concernant l'estethique ou le fonctionnement de l'arborescence devront être faite dans ce fichier.  

Les **fichiers JSON** constituent la base de donnée de l'arborescence. En effet c'est là où sont disposés toutes les données utilisés dans le projet, allant de la strcture de l'arborescence elle même, jusqu'au indicateurs et aux actions utilisées.
Pour rajouter ou mettre à jour les informations qu apparaissent il faut se rendre dans ces fichiers. 

## Programmation 
Voici la syntaxe qui faut respecter pour chaque fichier :

Le fichier **actions.json** concerne, comme son nom l'indique, les actions réalisés par l'université associés à un sous axe (type: 1.2.3) et à un ou plusieurs ODD (Objectifs de Développement Durable). 
Le fichier se présente comme un tableau d'actions, avec chaque action ayant plusieurs attributs. 

### syntaxe globale tableau :
```json
[{action1},{action2},...,{actionX}]
```
Pour rajouter une action il suffit de bien se placer dans le tableau, c'est à dire en dehors des actions existantes (entre 2 actions par exemple)

### Syntaxe pour chaque action :
```json
{
    "axe": "1.1.1",
    "num": [
      16,12,4
    ],
    "titre": "Construction d'une politique DD&RS 2023-2025",
    "description": "Alimentée par les échanges des groupes de travail thématiques et par une grande consultation à..."
}
```
Tous les attributs d'une actions sont de type *STRING* excepté *num* qui est un tableau de *NOMBRE* 

Le fichier **indicators.json** rassemble les indicateurs recensés pour connaitre le niveau d'avancement d'un axe. Chaque indicateur va donc être associé un sous axe (type: 1.2.3).
Le fichier se présente également comme un tableau, avec chaque indicateur ayant plusieurs attributs.

### Syntaxe globale tableau :
```json
[{indicateur1},{indicateur2},...,{indicateurX}]
```
Pour rajouter un indicateur il faut suivre la même démarche que pour les actions. 


### Syntaxe pour chaque indicateur :
```json
{
    "axe": "1.1.1",
    "titre": "Renouvellement labellisation",
    "cible": "garantie du renouvellement du label",
    "respecte": false
}
```
Tous les attributs d'une actions sont de type *STRING* excepté *respecte* qui est un *BOOLEEN* (accepte que false ou true) 

Le fichier **data.json** décrit la structure de l'arborescence, de 3 étages, ainsi que le nom de tous les axes et sous axes.
Le fichier est sous forme d'arbre hierarchique, ce qui le rend différend des 2 autres fichiers JSON.

### Syntaxe arbre :
```json
  {
    "name": "SCHEMA DIRECTEUR DD&RS",
    "children": [{ Axe principale 1 [{Axe secondaire1[{sousaxe1},{sousaxe2}]},{Axe secondaire2[{...}]}...]}, {Axe principale 2[{...}]}    ]
}
```
Pour rajouter une branche quelque part, il faut donc bien se placer dans l'arborescence et ne pas oublier les delimiteurs : *[]* et *{}* 
