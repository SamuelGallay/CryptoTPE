---
title: La cryptanalyse du chiffre de Vigenère
permalink: /cryptanalyse-vigenere/
suivante: /experience/
precedente: /louis14/
partie: Les Temps Modernes
---

# Les Temps Modernes

## Cryptanalyse du chiffre de Vigenère

Babbage et Kasiki se sont appuyés sur la répétition au moins deux fois dans le message chiffré d’une séquence de 3 lettres et calculer la distance entre elles. En calculant le PGCD des distances on obtient la longueur probable de la clé.
Soit un message chiffré comportant deux séquences répétées S et T. On note leurs répétitions S1, S2, T1 et T2. La longueur probable de la clé est PGCD (S2-S1 ; T2-T1)/
PLus tard, en 1920, le cryptologue de l’armée américaine Friedman met au point l’indice de coïncidence. Avec un texte de n lettres et une clé de k lettres, on a :

**Formules**

Dans les années 20, Friedman, officier cryptologue de l'armée de terre américaine, met au point un indice mathématique, appelé indice de coïncidence. En calculant l'indice de coïncidence pour toutes les lettres du message modulo la taille de la clé que l'on veut tester, on peut pour la taille de la clé où cet indice est anormalement grand, affirmer que ceci est la taille de la clé du message. 

Formule : 

$$ IC =\sum_{i=a}^z n_i $$

**Formules**

vaut si n suffisamment grand
où n est la longueur du texte et ni la fréquence d’apparition de la lettre i dans le texte

# Partie de Manon
