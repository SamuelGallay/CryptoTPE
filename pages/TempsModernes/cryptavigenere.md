---
title: La cryptanalyse du chiffre de Vigenère
permalink: /cryptanalyse-vigenere/
---

# Les Temps Modernes

## Cryptanalyse du chiffre de Vigenère 

Babbage et Kasiki se sont appuyés sur la répétition au moins deux fois dans le message chiffré d’une séquence de 3 lettres et calculer la distance entre elles. En calculant le PGCD des distances on obtient la longueur probable de la clé. 
Soit un message chiffré comportant deux séquences répétées S et T. On note leurs répétitions S1, S2, T1 et T2. La longueur probable de la clé est PGCD (S2-S1 ; T2-T1)/ 
PLus tard, en 1920, le cryptologue de l’armée américaine Friedman met au point l’indice de coïncidence. Avec un texte de n lettres et une clé de k lettres, on a : 

**Formules**

Bon, L’Indice de Coïncidence, c’est à peu de choses près la somme des “fréquences au carré” de chaque lettres dans le texte

**Formules**

vaut si n suffisamment grand
où n est la longueur du texte et ni la fréquence d’apparition de la lettre i dans le texte 
