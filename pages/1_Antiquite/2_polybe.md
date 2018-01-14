---
title: Le carré de Polybe
permalink: /polybe/
precedente: /scytale/
suivante: /cesar/
partie: "L'Antiquité"
menu: /antiquite/
---


Le carré de Polybe a été inventé aux environs de 150 avant J-C en Grèce. C'est le premier système de chiffrement par [substitution monoalphabétique]({{ "/glossaire/" | relative_url }}) connu.

## Eléments de contexte

### Polybe

Polybe (203 avant J-C - 126 av. J-C) était un historien grec à qui l’on doit une oeuvre considérable traitant notamment du fonctionnement de la République et de la Guerre Punique. Il est né en Arcadie mais fut pris comme otage par Rome en 167 av. J-C. Il devient, après sa libération, un proche de certaines élites de la République romaine. Il est mandaté comme diplomate par le Sénat en Espagne, en Gaule et en Mauritanie avant d’avoir la charge de négocier avec les cités du Péloponnèse. Il va ensuite en Orient puis, de retour à Rome, il observe le fonctionnement des institutions et écoute les conseils d’anciens militaires. Il devient alors le mentor de Scipion Emilien et participe avec lui à la destruction de Carthage.

<img src="{{ "/assets/1_Antiquite/scipion-polybe.jpg" | relative_url }}" alt="Carthage" style="margin: 0 auto;display: block;width: 300px;"/>
<p align="center"> <em>Scipion Emilien et Polybe dans Carthage, gravure de Jacob Buys, fin du XVIIIème siècle</em> </p>

### La chute de Cathage

Elle marque la fin d’un siège de trois ans ayant débuté en 149 av. J-C et la fin de la Troisième Guerre Punique. Au début, la ville, malgré son isolement, résiste à la pression militaire de Rome et connaît même quelques succès tactiques. Mais en 147-146, grâce à l'arrivée du nouveau chef romain Scipion Emilien, petit-fils adoptif de Scipion l’Africain, Carthage est méthodiquement investie. Prise d'assaut, la capitale punique est mise à sac, puis détruite. Jules César reconstruira plus tard une ville romaine sur son emplacement. Les possessions africaines de Carthage deviennent la province romaine d'Afrique. Désormais, et pour longtemps, rien ne résiste plus à Rome. Cette cité italienne parmi d'autres est devenue à la faveur des guerres puniques un empire à vocation universelle. L'année même où Carthage est rasée, les Romains s'emparent de Corinthe et transforment la Grèce prestigieuse en province ordinaire.

<img src="{{ "/assets/1_Antiquite/carthage.jpg" | relative_url }}" alt="Carthage" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Reconstitution de la ville antique de Carthage</em> </p>

## Fonctionnement et exemple

### Le carré initial

Le carré de Polybe est un système composé d’un carré de 25 cases dans lesquelles sont placées les lettres de l’alphabet (en français, le w est mis dans la même case que le v). Chaque lettre est représentée ses coordonnées dans ce carré : d’abord le chiffre de sa ligne puis celui de sa colonne. Ce système présente plusieurs avantages : la conversion de lettres en chiffres, la réduction du nombre de symboles utilisé pour coder (5) et la représentation de chaque lettre par deux éléments séparés.

|       | 1 | 2 | 3 | 4 | 5 |
|-------|---|---|---|---|---|
| **1** | A | B | C | D | E |
| **2** | F | G | H | I | J |
| **3** | K | L | M | N | O |
| **4** | P | Q | R | S | T |
| **5** | U | V | X | Y | Z | 

* Message en clair : `Polybe a eu accès à la bibliothèque de Persée`

* Message crypté : `413532541215 11 1551 1113131544 11 3211 122412322435452315425115 1415 411543441515`


| **Clair**   | P  | O  | L  | Y  | B  | E  | A  | E  | U  | A  | C  | C  | E  | S  |
| **Chiffré** | 41 | 35 | 32 | 54 | 12 | 15 | 11 | 15 | 51 | 11 | 13 | 13 | 15 | 44 |

### Variantes

Lorsqu’on sait que ce message a été codé avec le carré de Polybe, il est très facile de le décrypter. Il suffit de mettre les chiffres par groupes de deux et de regarder dans le tableau à quelles lettres correspondent ces coordonnées. 
Il existe donc plusieurs variantes à ce carré :
* remplacer les coordonnées par autre chose que les chiffres 1 2 3 4 5 (par exemple d’autres chiffres ou des lettres, voir )
* remplir les cases avec les lettres de l’alphabet, toujours, mais dans le désordre. Il devient alors plus compliqué de deviner à quelle lettre correspond chaque coordonnées de chiffres. 
* remplir le carré en commençant par un mot clé et compléter avec les lettres de l’alphabet restantes. \\
Reprenons l'exemple précédent avec cette dernière variante. 
On crée une grille avec un alphabet désordonné commençant par le mot “POLYBE”

|       | 1 | 2 | 3 | 4 | 5 |
|-------|---|---|---|---|---|
| **1** | P | O | L | Y | B |
| **2** | E | A | C | D | F |
| **3** | G | H | I | J | K |
| **4** | M | N | Q | R | S |
| **5** | T | U | V | X | Z |

Le message “bibliothèque de Persée” ne sera plus codé `122412322435452315425115 1415 411543441515` mais `153315133312513221435221 2421 112144452121`.

## Faiblesse

Il est aisé de briser ce chiffrement par [analyse des fréquences]({{ "/glossaire/" | relative_url }}) car une lettre est toujours remplacée par la même combinaison de chiffres. En dépit de sa grande faiblesse, il fut utilisé pendant très longtemps et notamment par les nihilistes russes au XIXe siècle, une organisation secrète dont le but était de tuer le tsar et ses représentants. Ils utilisaient ce code en prison en tapant contre le mur le nombre coups correspondant aux chiffres du messages. Cependant, une fois le système connu, n’importe qui peut déchiffrer le message.

## A vous de jouer !

Le message suivant a été codé avec le carré de Polybe « classique ». Tentez de le déchiffrer. Tous les coups sont permis : la fortune sourit aux audacieux !

11 51 14 11 13 15 44 - 21 35 43 45 51 34 11 - 25 51 52 11 45
