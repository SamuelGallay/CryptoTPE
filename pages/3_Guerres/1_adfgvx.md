---
title: ADFGVX durant la Première Guerre Mondiale
permalink: /adfgvx/
suivante: /enigma-contexte/
partie: "La Première Guerre Mondiale"
---

## Eléments de contexte 

A la fin du 19ème, la cryptanalyse des chiffres polyalphabétiques par Babbage et Kasiski met la cryptographie en mauvais état, plus aucun des chiffrements n'est sûr.
En même temps, en Grande-Bretagne, Marconi inventa la Télégraphie Sans Fil (TSF, 1894) qui permettait d'envoyer sans câble des messages sur de très grandes distances. Un premier message sur 2km, puis un par dessus la Manche, et enfin un d'un bout à l'autre de l'Atlantique, en 1901. On ne comprit pas tout de suite comment une onde parvenait à franchir la ligne d'horizon (la courbure de la Terre pose un problème), mais il fut montré plus tard que la couche ionisée de l'Atmosphère (60 km d'altitude) agit comme un miroir pour les ondes radio.

A l'aube de la première Guerre Mondiale, les militaires virent tout de suit l'enjeux de cette découverte qui permettait de rester en contact avec les bataillons ou la flotte où qu'ils soient. Mais toutes ces signaux, magiquement transmis à travers l'éther, sont reçus aussi bien par les alliés que par les ennemis… Cela renforce le besoin d'un cryptage efficace.
De 1914 à 1918 les chiffrements n'ont que peu progressé et la plupart d'entre eux ne vécurent que le temps de les déchiffrer. On peut noter l'un des plus fameux, le code ADFGVX mis en place par les allemands alors qu'ils n'étaient qu'à 100km de Paris début juin 1918. Pour savoir où les troupes allemandes comptaient frapper, les français étaient contraints de déchiffrer leurs communications. Ils possédaient par chance une arme secrète, le lieutenant George Painvin. Après des nuits de travail, il réussit enfin à décrypter le code ennemi éclairant les français sur tous les agissements allemands.

## Fonctionnement et exemple

On établit d'abord une grille de 6x6 remplie des 26 lettres de l'alphabet et des 10 chiffres. Les lignes et les colonnes sont indexées par les lettres ADFGVX. La disposition de la grille est la clef secrète. Pour chiffrer un message, on note uniquement la lettre correspondant à la ligne et celle correspondant à la colonne. (un peu comme dans le carré de Polybe) Nous avons pour l'instant une simple substitution monoalphabétique, et l'analyse des fréquences en viendrait à bout facilement.

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

La seconde étape est une transposition. On choisit un mot clef connu des deux correspondants et lui aussi secret.  On crée ensuite un tableau avec autant de colonnes que la longueur de la clef. On inscrit alors le message avec un caractère par colonne, sur plusieurs lignes. Enfin on permute les colonnes de telle sorte que les lettres du mot clef soient rangées dans l'ordre alphabétique, on peut donc transmettre le message par radio.

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

Le code ADFGVX est typique de ceux de la première Guerre Mondiale, ce ne sont que des variantes ou des combinaisons de ceux déjà déchiffrés au 19ème siècle. Ils peuvent en apparence offrir une grande sécurité mais les cryptanalystes finissent toujours par avoir le dernier mot.

### Le télégramme de Zimmermann

On notera aussi le célèbre télégramme de Zimmermann qui a, dans une certaine mesure, changé le cours de l'Histoire. Lorsque la guerre éclate, le 3 août 1914, le Président des États-Unis, Woodrow Wilson, souhaite observer une stricte neutralité et maintenir l'unité nationale d'un pays dont un habitant sur quatre est né à l'étranger ou de parents originaires des deux blocs antagonistes. En 1915, un sous-marin allemand coula le Lusitania un paquebot qui transportait entre autre 128 citoyens américains. Cela aurait dû décider les américains à signer leur déclaration de guerre, mais les allemands répétèrent maintes fois qu'à partir de maintenant, ils feraient attention à ne pas couler de bateaux civils.

<img src="{{ "/assets/3_Guerres/zimmermann.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> Dessin de Rollin Kirby paru dans The New York World peu après la révélation du télégramme </em> </p>

Le plan de Zimmermann, ministre des affaires étrangères allemand, était de rallier le Mexique et le Japon contre les Etats-Unis avant leur entrée en guerre. Il pensait que si les Américains étaient trop occupés à combattre sur leur territoire, ils ne pourraient pas aider les anglais qui seraient alors occupés par la nouvelle flotte de 200 sous-marins allemands abattant tous leurs navires de marchandises. Pour mettre en place ce plan, il devait contacter le Mexique par un câble sous-marin, écouté par les anglais. Il chiffra donc son message et celui-ci fut rapidement intercepté au bureau du chiffre de l'amirauté. Il fut déchiffré par le révérend Montgomery avec l'aide de Nigel de Grey. ...étapes intermédiaires…

Alors même que la guerre totale des sous-marins avait commencé, le Président Wilson ne décida toujours pas de la guerre. Le message de Zimmermann fut alors transmis par l’ambassadeur anglais à l’ambassadeur américain à Washington et publié dans les journaux. Les allemands exigeaient un combat direct. Le 6 avril 1917, le Congrès vote la guerre par 373 voix contre 50. Le président Wilson proclame alors : "L'Amérique doit donner son sang pour les principes qui l'ont fait naître..."

Pour les Alliés, I'entrée en guerre des Américains arrive au bon moment : la chute du tsarisme et les incertitudes qui pèsent sur l'avenir d'une Russie en proie au désordre et à l'agitation révolutionnaire, le réveil des tensions sociales et la fin de l'Union sacrée, l'échec sanglant de l'offensive Nivelle dans le secteur du Chemin des Dames et les mutineries sur le front ont en effet de quoi inquiéter. L'annonce de l'intervention américaine vient à point nommé ranimer l'espoir des hommes et la certitude des gouvernants qu'avec le temps "on les aura". Prenant le commandement de l'armée française, le général Pétain peut ainsi annoncer, au printemps 1917, qu'il "attend les Américains et les chars". L'année 1917 voit ainsi la mise en place de la machine de guerre des États-Unis qui, pour la première fois, interviennent dans un conflit à l'échelle mondiale et s'imposent comme une grande puissance.
