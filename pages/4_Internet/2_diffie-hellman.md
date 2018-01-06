---
title: "Le Diffie-Hellman"
precedente: /des/
permalink: /diffie-hellman/
suivante: /rsa/
partie: "L'ère d'Internet"
---

## Le protocole d'échange de clefs Diffie-Hellman

### Eléments de contexte


Dans les années 70, une nouvelle problématique émerge : bien que les chiffrements symétriques soient efficaces pour chiffrer et déchiffrer rapidement de longs messages, il faut au préalable que les deux correspondants se soient échangés une clef.

Avec l’informatique, ils doivent pouvoir s’échanger au travers de messages (de fait publics) la clef.

Avec l'ère d'Interne, les mathématiciens s'intéressent particulièrement à la cryptograhie. \\
Ce sont deux américains, Whitfield Diifie et Martin Hellman de l'Université de Stanford qui en 1976, créent une nouvelle forme de cryptographie, dite asymétrique ou à clef publique. Ils recevront par la suite nombre de prix pour cette découverte. 


<img src="{{ "/assets/4_Internet/diffie-hellman1.png" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> Une analogie avec de la peinture pour comprendre </em> </p>

### Modélisation mathématique 

* Alice et Bob veulent s’échanger une clé
* Alice choisit un grand nombre premier p et une base g avec g inférieur à p
* Elle choisit un nombre secret a
* Elle envoie à Bob le nombre $$ A = g^a \bmod p $$
* Bob choisit à son tour le nombre secret b
* Il envoie à Alice $$ B = g^b \bmod p $$
* Alice peut déterminer la clé secrète : $$ B^a \bmod p = (g^a)^b \bmod p = g^{ab} \bmod p $$
* Bob en fait de même et obtient la clé identique : $$ A^b \bmod p = (g^b)^a = g^{ba} \bmod p = g^{ab} \bmod p $$ \\
Ceci est rendu possible par la commutativité de la fonction puissance ! \\
En connaissant p, g, A et B, il faudrait tout de même résoudre des calculs fort complexes pour trouver la clé secrète $$ g^{ab}
