---
title: Vigenere est fantastique
permalink: /vigenere/
---
# Les Temps Modernes

## Le carré de Vigenère

En s’inspirant des travaux d’un bénédictin allemand, Johannes von Heidenberg, surnommé Trithème, que Blaise de Vigenère élabore son fameux carré. En effet le moine avait eu l’idée “mettre en carré” les roues d’Alberti, ce qui aboutissait à un tableau de 26 lignes, la première étant composée d’un alphabet ordinaire, les autres d’un alphabet décalé à chaque fois d’un rang vers la gauche. Il chiffrait la première lettre du message avec la première ligne du tableau, la deuxième lettre avec la deuxième ligne et ainsi de suite jusqu’au moment où, parvenu à la dernière ligne du tableau, il repart à la première. Ceci correspond à une clé littérale de 26 lettres “ABCD...Z”. Le carré n’est pas alors exploité à son maximum : la notion de clé littérale émerge au début du XVIe siècle avec l’italien Belaso qui parle de “mot de passe”. Vigenère fait la synthèse des deux en reprenant le tableau de Trithème et en l’utilisant avec le principe de clé de Belaso : il change donc d’alphabet à chaque nouvelle lettre. 

**Image**

Fonctionnement : les correspondants définissent préalablement une clé qui servira à chiffrer et déchiffrer leurs messages. Ils répètent la clé autant que nécessaire et décalent la lettre du message du nombre associé à la lettre de la clé (A associé à 1, B à 2, etc…).

Exemple : Vigenère est remarquable 
clé : crypto

**Tableau**

Modélisation mathématique à ajouter 

Vigenère tire son savoir des cryptologues italiens qu’il a rencontrés lors de séjours diplomatiques à Rome : il expose sa théorie dans le Traité des chiffres ou secrètes manières d’écrire paru en 1585. Au plus la clé est grande, au plus le niveau de sécurité est élevé : si la clé de chiffrement est aussi longue que le message, et totalement aléatoire, le chiffre de Vigenère est inviolable : on parle de méthode du masque jetable, de chiffrement de Vernam, ou de One-Time Pad utilisé pour le téléphone rouge et encore aujourd’hui dans les ambassades. 
