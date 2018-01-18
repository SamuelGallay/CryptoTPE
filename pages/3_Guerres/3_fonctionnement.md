---
title: "Le fonctionnement d'Enigma"
permalink: /enigma-fonctionnement/
precedente: /enigma-contexte/
suivante: /enigma-cryptanalyse/
partie: "Seconde Guerre Mondiale"
menu: /guerres/
---

### Principe général 

La machine Enigma était faite de composants ingénieux combinés dans une incroyable machine à chiffrer. Toutefois, si on les prend un à un, ses principes de base deviennent compréhensibles. Enigma est la première méthode de cryptographie électronique.

<img src="{{ "/assets/3_Guerres/enigma.jpeg" | relative_url }}" alt="Enigma" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Machine Enigma avec ses parties légendées</em> </p>

Dans sa forme élémentaire, Enigma consiste en trois éléments reliés par des câbles : un clavier pour entrer chaque lettre du texte clair, un brouilleur qui crypte chaque lettre du texte clair en une lettre chiffrée, et un tableau lumineux fait d’un certain nombre de lampes pour afficher la lettre du texte crypté. Pour crypter une lettre du texte clair, on envoie une impulsion électrique qui passe dans le brouilleur puis allume une lampe du tableau, qui indique la lettre correspondante du texte chiffré. On y ajoutera par la suite le tableaux de connexions pour augmenter le nombres de possibilités

### Le tableau de connexions : il permet d'échanger des paires de l'alphabet, deux à deux.



La partie centrale de la machine, le brouilleur, est un tambour en matériau isolant portant sur chaque face des contacts électrique. Chaque lettre du clavier est reliée à une entrée de ce tambour. Venant du clavier, les fils pénètrent dans le tambour en 26 points, font à l’intérieur un parcours animé de boucles et de virages, et ressortent sur l’autre face en 26 autres points. Ces 26 autres points allument sur le tableau lumineux la lettre cryptée. Les montages internes déterminent ainsi comment les lettres du texte clair seront cryptées. Ce brouilleur peut se diviser en deux parties.

<img src="{{ "/assets/3_Guerres/tableaudeconnection.png" | relative_url }}" alt="Enigma1" style="margin: 0 auto;display: block;"/>

### Les rotors


Ils sont passés de 3 à 6 au cours de la guerre. A chaque lettre entrée correspond une autre lettre. De plus, à chaque lettre frappée, un ou plusieurs des rotors mobiles tourne, changeant la substitution qui sera opérée à la prochaine touche pressée.


<img src="{{ "/assets/3_Guerres/rotors.png" | relative_url }}" alt="Enigma2" style="margin: 0 auto;display: block;"/>

### Le réflecteur


Au bout des 3 rotors se situe une dernière permutation qui permet de revenir en arrière. On permute une dernière fois les lettres 2 par 2, et on les fait retraverser les rotors, et le tableau de connexion.

<img src="{{ "/assets/3_Guerres/reflecteur.png" | relative_url }}" alt="Enigma3" style="margin: 0 auto;display: block;"/>

Dans la position du schéma ci-dessous, la lettre A sera codée C.

<img src="{{ "/assets/3_Guerres/fonctionnement.png" | relative_url }}" alt="Enigma4" style="margin: 0 auto;display: block;"/>

De cette manière une lettre ne peut jamais être codé par la même lettre. Cela est une faiblesse de la machine car ça enlève un certain nombre de possibilités à tester pour les cryptanalystes.

### Calcul du nombre de clefs potentielles avec 3 rotors :

1. Orientation des brouilleurs
  * Chacun des rotors peut être réglé sur 1 des 26 positions. Il y a donc $$ 26 \times 26 \times 26 = 17 576 $$ dispositions
2. Disposition des brouilleurs
  * Les trois rotors (ici nommés A, B, C) peuvent être placés selon les 6 dispositions suivantes : ABC, ACB, BCA, BAC, CAB, CBA ce qui fait $$ 3! = 6 $$ dispositions
3. Tableaux de connexions
  * Le nombre de branchements possibles en appairant 6 fois 2 lettres prises parmi les 26 lettres de l’alphabet est énorme.
  * D’abord il faut choisir 12 lettres parmi 26 : pour la première lettre, on a 26 possibilités mais pour la deuxième lettre plus que 25, puis pour la troisième lettre 24, pour la quatrième 23, … et pour la douzième 15 possibilités. Cela fait $$ 26 \times 25 \times 24 \times 23 \times 22 \times 21 \times 20 \times 19 \times 18 \times 17 \times 16 \times 15 = 4, 626053752 \times 10^{15} $$ possibilités.  Cependant, comme l’ordre des 12 lettres n’a pas d’importance, il faut diviser ce nombre par 12! ce qui fait $$ 9,6577 \times 10^{6}. $$
  * Maintenant, il faut choisir 6 paires de lettres parmi 12, soit $$ 12!/6! = 6,6528 \times 10^{5}
9,6577 \times 10^{6} \times 6,6528 \times 10^{5} = 6, 425074656 \times 10^{12} $$
Enfin, comme la paire (A,B) donne la même connexion que (B,A), il faut diviser par 2 pour chaque fils c’est à dire par 26 :

$$ 6, 425074656 \times 10^{12} / 26 = 100 391 791 500 $$

On peut résumer ces calculs avec le calcul suivant :

$$ \frac{26!}{14! \times 6! \times 26}  = 1, 003917915 \times 10^{11} $$

Le nombre total de clefs est égal au produit de ces trois facteurs
$$ 17 576 \times 6 \times 100 391 791 500 = 1,058691676 \times 10^{16} $$ ce qui est environ égal à $$ 10^{16} $$ possibilités, ce qui est énorme pour l’époque.
