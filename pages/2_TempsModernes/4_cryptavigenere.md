---
title: La cryptanalyse du chiffre de Vigenère
permalink: /cryptanalyse-vigenere/
suivante: /experience/
precedente: /louis14/
partie: Les Temps Modernes
menu: /temps-modernes/
---

## Cryptanalyse du chiffre de Vigenère

La "méthode historique" fut inventée par le mathématicien britannique Charles Babbage, connu notamment pour ses machines à différence, vers 1854 mais sa découverte resta ignorée en l'absence d'écrit. Pendant ce temps, un officier prussien à la retraite, Friedrich Kasiski, parvint au même résultat et publia en 1863 "Die Geheimschriften und die Dechiffrir-Kunst".

Pour déchiffrer un tel code, la première étape est de déterminer la longueur du mot-clef. Avec un chiffre de Vigenère, si une même séquence de lettres dans le texte en clair a été cryptée avec une même partie de mot-clef, elle donnera alors une même séquence de lettres cryptées. Si une séquence de lettres en clair est fréquente dans le texte alors la probabilité qu’elle soit codée avec une même partie du mot-clef sera plus forte, ce qui permet de détecter sa présence en recherchant des séquences de lettres identiques dans le texte chiffré. Pour faire cette détection de façon statistiquement fiable, une séquence d’au moins trois lettres est préférable et doit se répéter plusieurs fois dans le texte. De telles séquences varient suivant le type de texte, mais par exemple, en français, la séquence « LES » peut se retrouver assez souvent dans la plupart des textes.

Babbage et Kasiski se sont donc tous deux appuyés sur la répétition d’une séquence de 3 lettres dans le message chiffré et ont calculé la distance entre elles dans le message, ce qui revient à calculer par combien de lettres elles sont séparées l'une de l'autre ? En calculant le PGCD des distances on obtient la longueur probable de la clef.
En pratique, étant donné un message chiffré comportant deux séquences répétées S et T, on note l'emplacement dans le message de leurs répétitions S1, S2, T1 et T2. La longueur probable de la clef est PGCD (S2-S1 ; T2-T1)

Il faut ensuite déterminer le mot-clef grâce à l'analyse des fréquences et déchiffrer le texte avec le mot-clef.

## L'indice de coïncidence

En 1920, le cryptologue de l’armée américaine Willian Friedman met au point l’indice de coïncidence. Avec un texte de n lettres et $$ n_{i} $$ occurences d'une lettre donnée dans le message, on a :

$$ IC =\sum_{i=a}^z \frac{n_{i}(n_{i}-1)}{n(n-1)} $$

En calculant l'indice de coïncidence pour toutes les lettres du message modulo la taille de la clef que l'on veut tester, on peut, pour la taille de la clef où cet indice est anormalement grand, affirmer que ceci est la taille de la clef du message. En effet, prendre une lettre sur n lorsque n est la longueur de la clef revient à prendre une série de lettres toujours chiffrée avec le même décalage, l’indice de coïncidence est donc égal à celui du texte clair.

$$ IC =\sum_{i=a}^z \frac{n_{i}(n_{i}-1)}{n(n-1)} = \sum_{i=a}^z \frac{n_{i}^2-n_{i}}{n^2-n} \approx \sum_{i=a}^z \frac{n_{i}^2}{n^2} = \sum_{i=a}^z (\frac{n_{i}}{n})^2 $$

vaut si n suffisamment grand \\
où n est la longueur du texte et $$ n_{i} $$ la fréquence d’apparition de la lettre i dans le texte

Notre [expérience]({{ "/experience/" | relative_url }}) est un déchiffrage à la main d'un message chiffré avec le chiffre de Vigenère. Nous avons pour ce faire utilisé la méthode de Babbage et Kasiski.
