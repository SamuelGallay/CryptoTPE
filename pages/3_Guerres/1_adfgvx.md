---
title: ADFGVX durant la Première Guerre Mondiale
permalink: /adfgvx/
suivante: /enigma-contexte/
partie: "La Première Guerre Mondiale"
menu: /guerres/
---

## Eléments de contexte

A la fin du XIXème siècle, la [cryptanalyse des chiffres polyalphabétiques]({{ "/cryptanalyse-vigenere/" | relative_url }}) par Babbage et Kasiski met à mal la cryptographie, plus aucun des chiffrements n'étant sûr.
En même temps, en Grande-Bretagne, Guglielmo Marconi inventa la Télégraphie Sans Fil (TSF, 1894) qui permettait d'envoyer sans câble des messages sur de très grandes distances. Un premier message sur 2km, puis un par-dessus la Manche, et enfin un d'un bout à l'autre de l'Atlantique, en 1901. On ne comprit pas tout de suite comment une onde parvenait à franchir la ligne d'horizon (la courbure de la Terre pose un problème), mais il fut montré plus tard que la couche ionisée de l'Atmosphère (60 km d'altitude) agit comme un miroir pour les ondes radio dans certaines gammes de fréquence.

<img src="{{ "/assets/3_Guerres/propaTSF.png" | relative_url }}" alt="propaTSF" style="margin: 0 auto;display: block; width:250px;"/>
<p align="center"> <em> Propagations des ondes dans l'atmosphère </em> </p>

A l'aube de la première guerre mondiale, les militaires virent tout de suite l'enjeu de cette découverte qui permettait de rester en contact avec les bataillons ou la flotte où qu'ils soient. Mais tous ces signaux, magiquement transmis à travers l'éther, sont reçus aussi bien par les alliés que par les ennemis… Cela renforce le besoin d'un cryptage efficace.
De 1914 à 1918 les chiffrements n'ont que peu progressé et la plupart d'entre eux ne vécurent que le temps de les déchiffrer. On peut noter l'un des plus fameux, le code ADFGVX mis en place par les Allemands alors qu'ils n'étaient qu'à 100km de Paris début juin 1918. Pour savoir où les troupes allemandes comptaient frapper, les Français étaient contraints de déchiffrer leurs communications. Ils possédaient par chance une arme secrète, le lieutenant Georges Painvin. Après des nuits de travail, il réussit enfin à décrypter le code ennemi éclairant ainsi les Français sur tous les agissements allemands.

## Fonctionnement et exemple

On établit d'abord une grille de taille 6x6 remplie des 26 lettres de l'alphabet et des 10 chiffres. Les lignes et les colonnes sont indexées par les lettres ADFGVX. La disposition de la grille est la clef secrète. Pour chiffrer un message, on note uniquement la lettre correspondant à la ligne et celle correspondant à la colonne (un peu comme dans le [carré de Polybe]({{ "/polybe/" | relative_url }})). Nous avons pour l'instant une simple substitution monoalphabétique, et l'analyse des fréquences en viendrait à bout facilement.

|   | A | D | F | G | V | X |
|---|---|---|---|:-:|---|---|
| A | V | J | Y | Q | 1 | R |
| D | D | U | 2 | N | I | H |
| F | 9 | O | F | 6 | W | 8 |
| G | E | T | P | B | G | Z |
| V | X | A | 7 | 0 | 5 | M |
| X | K | 3 | C | S | L | 4 |


Chiffrons `Attaque à l’aube`

| Clair   | A  | T  | T  |  A | Q  | U  | E  | A  | L  | A  | U  | B  | E  |
|---------|----|----|----|:--:|----|----|----|----|----|----|----|----|----|
| Chiffré | VD | GD | GD | VD | AG | DD | GA | VD | XV | VD | DD | GG | GA |

Message chiffré : `VDGDGDVDAGDDGAVDXVVDDDGGGA`

La seconde étape est une transposition. On choisit un mot-clef connu des deux correspondants et lui aussi secret.  On crée ensuite un tableau avec autant de colonnes que la longueur de la clef. On inscrit alors le message avec un caractère par colonne, sur plusieurs lignes. Enfin on permute les colonnes de telle sorte que les lettres du mot-clef soient rangées dans l'ordre alphabétique, on peut donc transmettre le message par radio.

Exemple du message précédent avec la clef : “CLEF”

| C | L | E | F |
|---|---|---|---|
| V | D | G | D |
| G | D | V | D |
| A | G | D | D |
| G | A | V | D |
| X | V | V | D |
| D | D | G | G |
| G | A |   |   |

On permute les colonnes alphabétiquement:

| C | E | F | L |
|---|---|---|---|
| V | G | D | D |
| G | V | D | D |
| A | D | D | G |
| G | V | D | A |
| X | V | D | V |
| D | G | G | D |
| G |   |   | A |


On obtient donc le message chiffré : `VGDDGVDDADDGGVDAXVDVDGGDGA`

Le code ADFGVX est typique de ceux de la première guerre mondiale, ce ne sont que des variantes ou des combinaisons de ceux déjà déchiffrés au XIXème siècle. Ils peuvent en apparence offrir une grande sécurité mais les cryptanalystes finissent toujours par avoir le dernier mot.

### Le télégramme de Zimmermann

On notera aussi le célèbre télégramme de Zimmermann qui a, dans une certaine mesure, changé le cours de l'Histoire. Lorsque la guerre éclate, le 3 août 1914, le Président des États-Unis Wilson, souhaite rester neutre et maintenir l'unité nationale d'un pays riche de nombreuses et variées immigrations européennes. Le 15 mai 1915, le paquebot Lusitania (transportant entre autres 128 citoyens américains) est coulé par un sous-marin allemand. Cela aurait dû décider les Américains à signer la déclaration de guerre, mais les allemands répétèrent maintes fois qu'à partir de maintenant, ils feraient attention aux bateaux civils.

<img src="{{ "/assets/3_Guerres/zimmermann.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> Dessin de Rollin Kirby paru dans The New York World peu après la révélation du télégramme </em> </p>

Le plan de Zimmermann, ministre des affaires étrangères allemand, était de rallier le Mexique et le Japon contre les Etats-Unis avant leur entrée en guerre. Il pensait que si les Américains étaient trop occupés à combattre sur leur territoire, ils ne pourraient pas aider les Anglais, alors sous la menace d'une nouvelle flotte de 200 sous-marins allemands. Pour mettre en place ce plan, il devait contacter le Mexique par un câble sous-marin, écouté par les Anglais. Il chiffra donc son message et celui-ci fut rapidement intercepté au bureau du chiffre de l'Amirauté britannique. Il fut déchiffré par le révérend Montgomery avec l'aide de Nigel de Grey.

Depuis le 31 janvier 1917, l’Allemagne a repris la guerre sous-marine à outrance. Mais cela ne suffit pas encore aux Etats-Unis pour entrer en guerre. Le télégramme de Zimmerman fut alors transmis par les Anglais à l’ambassade américaine et diffuser dans les journaux. Cela fut sans doute l'élément déclancheur de l’entrée en guerre des Etats-Unis, le 2 avril 1917.. Le président Wilson déclare alors, en référence aux idéaux défendus par les Pères fondateurs des États-Unis : "L'Amérique doit donner son sang pour les principes qui l'ont fait naître..."

Cette déclaration est salvatrice pour des Alliés en mauvaise posture. En effet, l’année 1917 est celle de la révolution russe qui apporte de nombreuses incertitudes, de la fin de l’Union sacrée, de l’apparition de tensions sociales et du douloureux échec de l’offensive du Chemin des Dames. Celle-ci conduit à des pertes catastrophiques mais aussi à des mutineries de la part des soldats, qui ne veulent plus de cette guerre qui s’éternise. Une prochaine intervention militaire massive des  Américains ravive l’espoir des combattants et du gouvernement. C’est ainsi que le général Pétain déclare : « j’attends les Américains et les chars ». Pour la première fois, on peut observer la machine de guerre américaine intervennant dans un conflit de grande ampleur et s'imposant ainsi comme puissance à l'échelle mondiale.
