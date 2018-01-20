---
title: "Le RSA : un chiffrement asymétrique"
precedente: /diffie-hellman/
permalink: /rsa/
suivante: /quantique/
partie: "L'ère d'Internet"
menu: /internet/
---

## Eléments de contexte

Dans la lignée de leurs contemporains mathématiciens-cryptographes Diffie et Hellman, trois chercheurs du Massachusetts Institute of Technology, Rivest, Shamir et Adleman créent en 1977 un nouvel algorithme de cryptographie asymétrique, nommé par leurs trois initiales : le RSA.

<img src="{{ "/assets/4_Internet/rsa.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block; width:400px; "/>
<p align="center"> <em> Shamir, Rivest et Adleman </em> </p>

Cet algorithme est encore utilisé aujourd'hui notamment pour le commerce électronique.

## Modélisation mathématique et fonctionnement

Bob détermine 4 nombres $$ p, q, e $$ et $$ d $$.
* $$ p $$ et $$ q $$ sont deux nombres premiers ; on note $$ n $$ leur produit ($$ n = pq $$)
* $$ \phi (n) = (p-1)(q-1) $$ : c'est l'indicatrice d'Euler, qui représente le nombre d'entiers inférieurs à $$ n $$ et premiers avec $$ n $$
* e est un entier premier avec $$ \phi (n) $$
* d vérifie l'égalité $$ ed = 1 \bmod \phi (n) $$ ce qui équivaut à dire que $$ ed-1 $$ est un multiple de $$ \phi (n) $$
On peut utiliser l'algorithme d'Euclide pour déterminer d à partir des trois autres nombres (remarque : il existe un unique d respectant l'égalité) \\
Bob a donc une **clef publique (n ; e)** et une **clef privée, secrète (n ; d)** \\
Alice utilisera la clef publique de Bob à laquelle elle a accès pour lui envoyer un message. \\
Pour ce faire Alice procède de la façon suivante :
* Elle choisit un nombre M tel que $$ 0 \leq M \leq n-1 $$ et que M soit premier avec n.
* Elle calcule le nombre $$ C = M^e \bmod n $$
* Elle envoie ce nombre à Bob.
* Bob de son côté calcule $$ D = C^d \bmod n $$ or d'après le théorème d'Euler : \\
$$ D = C^d \bmod n = (M^e)^d \bmod n = \color{red} {M^{ed}\bmod n} \color{red} {=} \color{red} {M \bmod n}  $$ \\
Bob a bien retrouvé le message d'Alice !

Il n'est pas inutile de préciser que dans le cas où l'on associerait à chaque lettre du message le nombre de la norme ASCII correspondant, puis que l'on chiffrerait, il suffirait à partir du message chiffré public de déchiffrer le message par analyse des fréquences. C'est pourquoi on ajoute des nombres aléatoires au sein de la suite de chiffres, ce qui résout de fait cet écueil.

Le RSA repose donc sur deux fondements :
* Mathématiquement, du théorème d'Euler, généralisation du petit théorème de Fermat, qui permet l'égalité écrite ci-dessus en rouge
* Informatiquement, de l'impuissance des ordinateurs de décomposer $$ n $$ en le facrorisant par $$ p $$ et $$ q $$, lorsque ceux-ci sont grands

## Exemple

* Bob choisit deux nombres premiers :
$$ p = 11 $$ et $$ q = 19 $$ alors $$n = pq = 209 $$
* Bob choisit par exemple 7 qui est premier avec 180 $$ (180 = (p-1)(q-1)) $$
**La clef publique est (7 ; 209).**
* Bob calcule maintenant d tel que le reste de 7d, dans la division par 180, soit 1. \\
Il trouve 103 : **La clef secrète est (103 ; 209)**
* Alice choisit le nombre 63.
* Elle a reçu la clef publique (7 ; 209) et calcule donc $$ 63^7 \bmod 209 = 123 $$
* Elle envoie cette valeur à Bob
* Bob reçoit 123. Il utilise sa clef secrète 103 et calcule $$ 123^{103} \bmod 209 = 63 $$
* Il a bien retrouvé le nombre choisi par Alice.

## Limites du RSA

La  méthode générale pour casser le RSA est de factoriser n en p et q, et en déduire l'exposant secret d. \\
Une fois que l'on connaît d, il est aisé d'en déduire tout le reste.
Aujourd'hui les ordinateurs peuvent factoriser des nombres produits de deux premiers jusqu'à environ 300 chiffres ; toutefois, si l'on prend $$ n $$ suffisamment grand, et qu'on utilise correctement l'algorithme, il est a priori sûr. \\
Néanmoins, il faut faire bon usage du RSA : si Alice envoie un même message avec le même $$ n $$ à Bob, Chris, et Daniel, Eve peut aisément, sans factoriser $$ n $$, retrouver le message. Elle utilisera pour cela le théorème des restes chinois, qui l'amènera non plus à calculer un logarithme discret, mais une racine cubique. \\
Nous précisons en outre que la méthode présentée ici est la primitive ; dans un souci de sécurité, elle s'est considérablement complexifiée au fil du temps, mais nous nous bornons au principe initial.

## Le principe de Kerckhoffs

La sécurité d'un chiffrement a longtemps reposé sur la méthode utilisée pour chiffrer. Ce fut le cas du chiffre de César, du grand chiffre de Louis XIV ou encore du chiffrement AFDGVX durant la Première Guerre mondiale. Cependant, cette sécurité est très précaire : il suffit que l'ennemi ait connaissance de la méthode pour qu'il soit en capacité de déchiffrer tous les messages.

Ainsi, la sécurité d'une méthode de chiffrement ne devrait pas dépendre de la méthode même, mais d'une clef que seules les correspondants connaissent et qui peut être modifiée comme on le souhaite.

En 1883, le linguiste et cryptologue néerlandais Auguste Kerckhoffs énonce le principe suivant : *la sécurité d'un système de cryptage ne doit reposer que sur le secret de sa clef.*

Nous pouvons donc dire que le RSA, et de façon plus générale les chiffrements depuis Enigma, respectent ce principe fondamental.


## De la théorie à la pratique...

Lorsque nous avons expliqués les systèmes de chiffrements comme le RSA, nous n'avons parlés que du coeur du système, de l'avancée mathématique fondamentale. On nomme ce principe fondamental la primitive du chiffrement. Dans la vie réelle, un système cryptographique doit respecter 4 principes qui sont les suivants :
* Le chiffrement doit être, s'il n'est pas incassable, très difficile à casser.
* Le message doit être authentifié, le receveur doit pouvoir être sûr de l'origine du message.
* Le receveur doit pouvoir vérifier l'intégrité du message, c'est à dire savoir si son contenu a été modifié.
* L'envoyeur ne doit pas pouvoir nier le fait qu'il a envoyé le message. (optionnel)

Ces principes ne sont pas inclus dans le RSA présenté ici, mais ils ont plus tard été implantés dans le protocole RSA que nous utilisons encore aujourd'hui.
