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

Une analogie avec de la peinture pour comprendre :

Modélisation mathématique :
* Alice et Bob veulent s’échanger une clé
* Alice choisit un nombre premier p et une base g
* Elle choisit un nombre secret a
* Elle envoie à Bob le nombre A = ga [mod p]
* Bob choisit à son tour le nombre secret b
* Il envoie à Alice B = gb [mod p]
* Alice peut déterminer la clé secrète : (B)a [mod p]
* Bob en fait de même et obtient la clé identique : (A)b [mod p]
