---
title: Le chiffrement de Vigenère
permalink: /vigenere/
precedente: /alberti/
suivante: /louis14/
partie: Les Temps Modernes
menu: /temps-modernes/
---

## Eléments de contexte

C'est en s’inspirant des travaux d’un bénédictin allemand, Johannes von Heidenberg, surnommé Trithème que Blaise de Vigenère élabore son fameux carré. En effet le moine avait eu l’idée “mettre en carré” les roues d’Alberti, ce qui aboutissait à un tableau de 26 lignes, la première étant composée d’un alphabet ordinaire, les autres d’un alphabet décalé à chaque fois d’un rang vers la gauche. Il chiffrait la première lettre du message avec la première ligne du tableau, la deuxième lettre avec la deuxième ligne et ainsi de suite jusqu’au moment où, parvenu à la dernière ligne du tableau, il repart à la première. Ceci correspond à une clé littérale de 26 lettres “ABCD...Z”. Le carré n’est pas alors exploité à son maximum : la notion de clé littérale émerge au début du XVIe siècle avec l’italien Belaso qui parle de “mot de passe”. Vigenère fait la synthèse des deux en reprenant le tableau de Trithème et en l’utilisant avec le principe de clé de Belaso : il change donc d’alphabet à chaque nouvelle lettre.


<img src="{{ "/assets/2_TempsModernes/vigenere.png" | relative_url }}" alt="Vigenere" style="margin: 0 auto;display: block; width: 700px;"/>
<p align="center"> <em>La table de Vigenère</em> </p>

## Modélisation mathématique et fonctionnement

Les correspondants définissent préalablement une clef qui servira à chiffrer et déchiffrer leurs messages. Ils répètent la clef autant que nécessaire et décalent la lettre du message du nombre associé à la lettre de la clef correspondante (A associé à 1, B à 2, etc…).

Exemple : `Vigenère est remarquable` avec comme clef : `crypto`


| **Clair**   |V|I|G|E|N|E|R|E|E|S|T|R|E|M|A|R|Q|U|A|B|L|E|
| **Clef**     |C|R|Y|P|T|O|C|R|Y|P|T|O|C|R|Y|P|T|O|C|R|Y|P|
| **Chiffré** |X|Z|E|T|G|S|T|V|C|H|M|F|G|D|Y|G|J|I|C|S|J|T|



Modélisation mathématique par une fonction définie pour les entiers de 0 à 25 qui au nombre associé à la lettre claire associe le nombre associé à la lettre chiffrée

$$ f(l_{i}) = (l_{i} + k_{i} \bmod k) \bmod 26 $$

Où :

| \$$ i $$ | position de la lettre chiffrée et claire |
| \$$ l_{i} $$ | nombre associé à la lettre d'indice i |
| \$$ k_{i} $$  |  nombre associé à lettre de la clef d’indice i |
| \$$ k $$ | taille de la clef |

## Sécurité

Vigenère tire son savoir des cryptologues italiens qu’il a rencontrés lors de séjours diplomatiques à Rome : il expose sa théorie dans le *Traité des chiffres ou secrètes manières d’écrire* paru en 1585. C'est un [chiffrement polyalphabétique]({{ "/glossaire/" | relative_url }}) qui résiste donc à l'analyse des fréquences des cryptanalystes arabes. Au plus la clé est grande, au plus le niveau de sécurité est élevé : si la clé de chiffrement est aussi longue que le message, et totalement aléatoire, le chiffre de Vigenère est inviolable : on parle de méthode du masque jetable, de chiffrement de Vernam, ou de One-Time Pad utilisé pour le téléphone rouge et encore aujourd’hui dans les ambassades.


<img src="{{ "/assets/2_TempsModernes/vigenere2.png" | relative_url }}" alt="Vigenere2" style="margin: 0 auto;display: block; width: 300px;"/>
<p align="center"> <em>Blaise de Vigenère</em> </p>

A vous de jouer !

Le message suivant a été codé avec la clef RABELAIS. Tentez de le déchiffrer.

Jcjiycm krnt gznauzeogp n'mkk qvi cuqfv df p'lmm
