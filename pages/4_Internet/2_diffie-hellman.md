---
title: "Le Diffie-Hellman"
precedente: /des/
permalink: /diffie-hellman/
suivante: /rsa/
partie: "L'ère d'Internet"
---

Dans les années 70, une nouvelle problématique émerge : bien que les chiffrements symétriques soient efficaces pour chiffrer et déchiffrer rapidement de longs messages, il faut au préalable que les deux correspondants se soient échangés une clef.

Avec l’informatique, ils doivent pouvoir s’échanger au travers de messages (de fait publics) la clef.

Les deux mathématiciens s’appuient sur l’arithmétique modulaire (fréquemment utilisée en cryptologie).


<img src="{{ "/assets/4_Internet/diffie-hellman1.png" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> Une analogie avec de la peinture pour comprendre </em> </p>


Modélisation mathématique :
* Alice et Bob veulent s’échanger une clé
* Alice choisit un nombre premier p et une base g
* Elle choisit un nombre secret a
* Elle envoie à Bob le nombre $$ A = g^a \bmod p $$
* Bob choisit à son tour le nombre secret b
* Il envoie à Alice $$ B = g^b \bmod p $$
* Alice peut déterminer la clé secrète : $$ B^a \bmod p = (g^a)^b \bmod p = g^{ab} \bmod p $$
* Bob en fait de même et obtient la clé identique : $$ A^b \bmod p = (g^b)^a = g^{ba} \bmod p = g^{ab} \bmod p $$
