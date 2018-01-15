---
title: "Le Diffie-Hellman"
precedente: /des/
permalink: /diffie-hellman/
suivante: /rsa/
partie: "L'ère d'Internet"
menu: /internet/
---

## Le protocole d'échange de clefs Diffie-Hellman

### Eléments de contexte


Dans les années 70, une nouvelle problématique émerge : bien que les chiffrements symétriques soient efficaces pour chiffrer et déchiffrer rapidement de longs messages, il faut au préalable que les deux correspondants se soient échangés une clef.

Avec l’informatique, ils doivent pouvoir s’échanger la clef au travers de messages visibles de tous.

Avec l'ère d'Internet, les mathématiciens s'intéressent particulièrement à la cryptograhie. \\
Ce sont deux américains, Whitfield Diffie et Martin Hellman de l'Université de Stanford qui en 1976, créent une nouvelle forme de cryptographie, dite asymétrique ou à clef publique. Ils recevront par la suite nombre de prix pour cette découverte.

<img src="{{ "/assets/4_Internet/diffie-hellman.jpeg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> Whitfield Diffie (à gauche) et Martin Hellman (à droite) </em> </p>

Ils s'appuient pour leur protocole sur l'arithmétique modulaire, très utilisée en cryptographie moderne.

<img src="{{ "/assets/4_Internet/diffie-hellman1.png" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> Une analogie avec de la peinture pour comprendre </em> </p>

### Modélisation mathématique et fonctionnement

* Alice et Bob veulent s’échanger une clef
* Alice choisit un grand nombre premier $$ p $$ et une base $$ g $$ avec $$ g \leq p $$
* Elle choisit un nombre secret a
* Elle envoie à Bob le nombre $$ A = g^a \bmod p $$
* Bob choisit à son tour le nombre secret b
* Il envoie à Alice $$ B = g^b \bmod p $$
* Alice peut déterminer la clef secrète : $$ B^a \bmod p = (g^a)^b \bmod p = g^{ab} \bmod p $$
* Bob en fait de même et obtient la clef identique : $$ A^b \bmod p = (g^b)^a = g^{ba} \bmod p = g^{ab} \bmod p $$ \\
Ceci est rendu possible par la commutativité de la fonction puissance ! \\
En connaissant p, g, A et B, il faudrait en revanche effectuer des calculs fort complexes pour trouver la clef secrète $$ g^{ab} $$

### Exemple (on considérera des petits entiers par souci de simplicité)

* Alice et Bob définissent p = 41 et g = 6
* Alice choisit comme nombre secret a = 7
* Elle envoie à Bob le nombre $$ 6^7 \bmod 41 = 29 $$
* Bob choisit à son tour le nombre secret 15
* Il envoie à Alice $$ 6^{15} \bmod 41 = 3 $$
* Alice peut déterminer la clef secrète : $$ 3^7 \bmod 41 = 14 $$
* Bob en fait de même et obtient la clef identique : $$ 29^{15} \bmod 41 = 14 $$

Alice et Bob ont bien partagé la clef 14 !
