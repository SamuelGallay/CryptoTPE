---
title: "Le RSA"
precedente: /diffie-hellman/
permalink: /rsa/
suivante: /ecc/
partie: "L'ère d'Internet"
---

# Les chiffrements asymétriques perfectionnés : l'exemple du RSA

## Eléments de contexte

Dans la lignée de leurs contemporains mathématiciens-cryptographges Diffie et Hellman, trois chercheurs du MIT, Rivest, Shamir et Adleman créent en 1977 un nouvel algorithme de cryptographie asymétrique, nommé par leurs trois initiales : le RSA. \\
Cet algorithme est encore utilisé aujourd'hui notamment pour le comerce électronique 

## Modélisation mathématique et fonctionnement 

Bob détermine 4 nombres $$ p, q, e $$ et $$ d $$ tel que 
* p et q soient deux nombres premiers ; n est le produit pq
* e soit un entier premier avec (p-1)(q-1)
* d respecte l'égalité $$ ed = 1 \bmod (p-1)(q-1) $$ ce qui équivaut à dire que $$ ed-1 $$ est un multiple de $$ (p-1)(q-1) $$
On peut utiliser l'algorithme d'Euclide pour déterminer d à partir des trois autres nombres (remarque : il existe un unique d respectant l'égalité) \\
Bob a donc une **clé publique (n ; e)** et une **clé privée, secrète (n ; d)** \\
Alice pour envoyer un message à Bob a accès à sa clé publique \\
Ce message constituera en un ou plusieurs entiers codés de la façon suivante :
* Elle choisit un nombre M tel que $$ 0 \leq M \leq n-1 $$
* Elle calcule le nombre $$ C = M^e \bmod n $$ qu'elle envoie à Bob \\
Bob de son côté calcule $$ D = C^d \bmod n $$ or d'après le théorème d'Euler : \\
$$ D = C^d \bmod n = (M^e)^d \bmod n = \color{red} {M^{ed}\bmod n} \color{red} {=} \color{red} {M \bmod n}  $$ \\
Bob a bien retrouvé le message d'Alice \\
Il n'est pas inutile de préciser que l'on peut faire correspondre un nombre à une lettre via sa position dans l'alphabet ou encore la norme ASCII. Il est en outre primordial de découper les lettres dans leur équivalent chiffré en bloc de 3, sinon on aurait à faire à une substitution monoalphabétique ce qui briserait tout l'intérêt de cet algorithme. 

Le RSA repose donc sur deux fondements :
* Mathématiquement du théorème d'Euler, généralisation du petit théorème de Fermat, qui permet l'égalité écrite ci-dessus en rouge
* Informatiquement, de l'impuissance des ordinateurs de décomposer $$ n $$ en le facrorisant par $$ p $$ et $$ q $$, lorsque ceux-ci sont grands 

## Exemple

* Bob choisit deux nombres premiers :
$$ p = 11 $$ et $$ q = 19 $$ alors $$n = pq = 209 $$
* Bob choisit par exemple 7 qui est premier avec 180 $$ (180 = (p-1)(q-1)) $$
**La clé publique est (7 ; 209).**
* Bob calcule maintenant d tel que le reste de 7d, dans la division par 180, soit 1. \\
Il trouve 103 : **La clé secrète est (103 ; 209)**
* Alice choisit le nombre 63.
* Elle a reçu la clé publique (7 ; 209) et calculer donc $$ 63^7 \bmod 209 = 123 $$
* Elle envoie cette valeur à Bob 
* Bob reçoit 123. Il utilise sa clé secrète 103 et calcule $$ 123^{103} \bmod 209 = 63 $$
* Il a bien retrouvé le nombre choisi par Alice.

## Limites du RSA

La seule méthode connue à ce jour pour casser le RSA est de factoriser n en p et q, et en déduire l'exposant secret d. \\
Une fois que l'on connaît d, il est aisé d'en déduire tout le reste.
Aujourd'hui les ordinateurs peuvent factoriser des nombres produits de deux premiers jusqu'à environ 300 chiffres ; toutefois, si l'on prend $$ n $$ suffisamment grand, et qu'on utilise correctement l'algorithme, il est a priori sûr.
Samuel tu avais dit que ce n'était plus l'enjeu



