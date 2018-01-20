---
title: "La cryptanalyse d'Enigma"
permalink: /enigma-cryptanalyse/
precedente: /enigma-fonctionnement/
partie: "Seconde Guerre Mondiale"
menu: /guerres/
---

Dès 1920, plusieurs réseaux de renseignements se sont attaqués à la version commerciale d’Enigma, mais aucune méthode de cryptanalyse traditionnelle n’a abouti et le chiffrement a été considéré comme inviolable.

## L’inlassable effort des Polonais

La Pologne étant un pays limitrophe de l’Allemagne, dès que Enigma fut mise en service dans l’armée allemande, les Polonais se sont sentis très concernés. Malheureusement pour eux, les circuits intérieurs de la machine adoptée par l’armée ont considérablement été améliorés par rapport aux versions commerciales de la machine.

Il s’ensuivit alors une longue période de recherche des évolutions qu’avait reçues Enigma, et
grâce à leur service de renseignement, le bureau du chiffre récupéra un manuel d’utilisation d’Enigma comportant un message clair avec un message chiffré et sa clef.

### La recherche des rotors
Marian Rejewski a alors découvert une faille dans les message d’Enigma. Elle ne venait pas du système lui même, mais de l’utilisation qu’en avait l’armée allemande : la clef de 3 lettres était répétée deux fois au début de chaque message.


<img src="{{ "/assets/3_Guerres/Marian_Rejewski.jpg" | relative_url }}" alt="Marian_Rejewski" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Marian Rejewski</em> </p>

| **Message clair :**   | `U G A U G A`|
| **Message Chiffré :** | `A X L Q P B`|

Cette répétition de 3 lettres permit à Marian Rejewski de retrouver l’ordre dans lequel étaient placées les lettre autour des rotors. En effet :
* La lettre ‘U’ est chiffrée par la lettre ‘A’ quand le rotor est en première position mais est chiffrée par ‘Q’ quand le rotor est en 4ème position.
* On peut en déduire que quand le 1<SUP>er</SUP> rotor tourne de 3 crans, il passe de la lettre ‘A’ à ‘Q’. Donc on a une information sur le câblage interne du rotor.

L’astuce révolutionnaire de Rejewski consiste à séparer le problème de la recherche de l’ordre des lettres sur le rotor de celui de la recherche des associations sur le tableau de fiches. Le tableau de fiches augmente en effet le nombre de clefs possibles d’environ 1,5 x 10<SUP>14</SUP>.
On peut rechercher la position des lettres sur les rotors sans se soucier des fiches, car le tableau de connection, contrairement au rotors est immobile. Dans la même journée, une lettre ‘A’ entrant dans le tableau de fiches ressortira transformée en une autre, comme ‘H’, mais cette association persistera tout au long du message.

En analysant les 6 premiers caractères de plusieurs dizaines de messages de la même journée, Rejewski parvint à un tableau associant chaque lettre chiffrée avec le rotor en 1<SUP>ère</SUP> position à la même lettre chiffrée avec le rotor en 4ème position.

| **1ère lettre** |A|B|C|D|E|...|X|Y|Z|
| **4ème lettre** |Q|G|I|Z|N|...|P|X|P|


Mais ces associations, bien que importantes ne permettent pas de retrouver la composition interne du premier rotor. Rejewski écrivit alors des équations permettant de la retrouver, mais ne parvint pas à les résoudre. Ces équations se basaient sur des chaînes dans le tableau supérieur. Il prenait une lettre de la première ligne, par exemple ‘a’ et sa lettre associée sur la deuxième ligne, ici ‘Q’. Ensuite, il recherchait à quelle lettre la lettre ‘Q’ de la première ligne était associée, et ainsi de suite jusqu’à retomber sur le ‘a’ initial. Pour contenir toutes les lettres de l’alphabet, plusieurs chaînes se formaient. Rejewski parvint à prouver que ces chaînes pouvaient donner des informations qui étaient indépendantes de la clef du jour et à les exploiter pour former ses équations.

C’est à ce moment qu’un espion allemand, Hans-Thilo Schmidt, travaillant pour les Alliés fit parvenir au service de renseignement français un manuel d’utilisation d’Enigma ainsi que d’autres informations sur la structure interne d’ Enigma.

Cela facilita considérablement la résolutions des équations de Rejewski qui comportaient quatres inconnues étant chacunes une permutation des 26 lettres de l’alphabet.


Cela permit au bureau du chiffre de Pologne de déterminer la composition du premier rotor. Malheureusement, Enigma était composée de 3 rotors et seul le rotor de droite, le rotor rapide, qui tourne à chaque lettre saisie du message était maintenant connu. Heureusement pour la cryptanalyse alliée, l’ordre des 3 rotors (3! = 6 possibilités) était changé tous les quelques mois, et en décembre 1932, la composition interne des 3 rotors fut connue des cryptanalystes polonais.

### La recherche de la clef du jour
A ce moment, décembre 1932, les spécialistes du chiffre polonais étaient en état de construire une version de l’Enigma militaire. Ils étaient alors incapables de retrouver la clef du jour, qui était composée, rappelons-le de la permutation de l’ordre des rotors, de la position initiale de chacun de ces rotors et des association du tableau de connection (ou du tableau de fiches).

A cette même époque, Hans-Thilo Schmidt donna au services de renseignement français les listes des clefs du jour utilisées durant les trois prochains mois. Les Français ne surent les exploiter ne connaissant pas la composition interne des rotors. Ils décidèrent de les partager avec les Anglais qui ne purent rien en faire de plus. En désespoir de cause, ils les partagèrent avec les Polonais qui furent alors capables de déchiffrer les messages des mois suivants exactement comme le faisaient les milliers d’opérateurs radio de l’armée allemande quotidiennement.

Mais le bureau du chiffre polonais ne souhaitait pas devenir dépendant des renseignements que leur donnaient les Français et les Polonais souhaitaient être capable de déterminer eux même la clef du jour.

Dans les faits, une fois que les positions initiales des rotors et leur ordre ont été déterminés, les paires du tableau de connection peuvent être déterminées grâce à une analyse des fréquences.
On peut alors rappeler le nombre de permutation possible de l’ordre des 3 rotors qui est de 3! = 1 x 2 x 3 = 6, ainsi que le nombre de positions initiales des 3 rotors possibles qui est de 26<SUP>3</SUP> = 17 576.

Il y a donc 3! x 26<SUP>3</SUP> = 105 456  combinaisons possibles de l’ordre des rotors et de leurs positions. Ce nombre peut paraître ridicule quand on raisonne au XXI<SUP>ème</SUP> siècle, où dans chaque ordinateur, smartphone, télévision, ou même frigidaire connecté il y a un processeur capable d'effectuer plus d’un milliard d’opérations en l’espace d’une seconde, mais à l’époque, tel n’était pas le cas, et tester 105 000 combinaisons n’était pas possible à la main.

Les Polonais s’attelèrent alors à un travail de longue haleine, celui de recenser et d’indexer pour les 105 000 combinaisons, les chaînes qu’elles entrainaient. Ce travail leur prit une année entière. Ils obtinrent alors un registre des 105 000 chaînes et des clefs du jour qui leur correspondaient. Il suffisait alors d’une “simple” analyse des fréquence en prenant compte de la combinaisons des rotors du brouilleurs pour déterminer les associations du tableau de connection. Ils étaient alors en mesure de déchiffrer toutes les communications allemandes (1938).

Les Polonais avaient cassé l’inviolable Enigma, une prouesse de cryptanalyse. À la différence des méthodes de cryptanalyse utilisées auparavant qui reposaient principalement sur des statistiques, les méthodes que Marian Rejewski et les autres membres du Bureau du Chiffre polonais reposaient sur des mathématique beaucoup plus complexes comme la théorie des permutations.

### La fin de l’âge d’or de la cryptanalyse polonaise…
Les Allemands apportèrent des modifications au brouilleur, mais les cryptanalystes polonais ne se découragèrent pas. Loin de là, à la place de se réatteler à la longue tâche de réécrire tout le registre des 105 000 chaînes et de leur clef associée, ils construisirent des machines capables de le faire à leur place. Ils les appelèrent les bombes cryptographiques, elles étaient capables de tester les 26<SUP>3</SUP> possibilités à leur place. Ils construisirent 6 bombes cryptographiques pour tester les 3! = 6 agencements des 3 rotors possibles. Ainsi, en l’espace de seulement quelques heures, les polonais étaient capables de retrouver la clef du jour et de déchiffrer tous les messages de la journée.

Malheureusement, en 1938, les allemands modifièrent le fonctionnement du brouilleur. À la place de disposer de 3 rotors et de les arranger selon les 6 positions possibles, ils disposaient alors de 5 rotors à arranger dans les 3 emplacements. Cela donne 60 possibilités.

Quand il y a un tirage d’une quantité d’objets dans l’ordre et que l’on ne peut pas tirer deux fois le même objet, on a :

$$ Possibilités =  \frac{(Ntotal !)}{(Ntotal - Ntirés)!} \\
= \frac{5!}{(5-3)!}\\
= 3 \times 4 \times 5 \\
= 60 $$

Cette modification décupla le nombre de bombes cryptographiques nécessaires à la recherche de la clef du jour, et cela était totalement hors du budget du bureau du chiffre polonais. De plus, les câblages internes des deux nouveaux rotors étaient encore inconnus. Les Polonais perdirent espoir.
La guerre menace la Pologne, et les cryptanalystes polonais envoient tous leurs travaux ainsi que deux copies d’Enigma militaires aux Français et aux Britanniques.
Le 1<SUP>er</SUP> Septembre 1939, la Pologne est envahie par l’armée allemande.

Ces nouvelles connaissances remontèrent le moral des cryptanalystes Alliés. Certes les nouvelles améliorations allemandes allaient compliquer la tâche, mais ils savaient maintenant que Enigma n’était pas invincible.

Les Anglais parvinrent de nouveaux à déchiffrer les messages allemands pendant quelques temps, ils améliorèrent même en les accélérant les méthodes polonaises, mais le 1<SUP>er</SUP> Mai
1940, les Allemands supprimèrent la répétition de la clef au début du message, l’ayant identifiée comme un risque potentiel. Alors tous les travaux des Polonais se réduisirent à néant. Mais cette suppression avait été prévue par Alan Turing, qui avait déjà commencé à chercher une autre méthode de cryptanalyse. La cryptanalyse d’Enigma allait devenir une affaire britannique !

## Alan Turing
<img src="{{ "/assets/3_Guerres/Alan_Turing.jpg" | relative_url }}" alt="Alan_Turing" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Alan Turing</em> </p>

Alan Turing est un mathématicien anglais qui très jeune est appelé à suivre le cours de la Governement Code & Cipher School, et qui la rejoint pour s’attaquer à la cryptanalyse d’Enigma au manoir de Bletchey Park.

<img src="{{ "/assets/3_Guerres/Bletchley_Park.jpg" | relative_url }}" alt="Bletchley_Park" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Manoir de Bletchey Park</em> </p>

On peut dire que Turing a transformé la cryptographie qui consistait en la recherche d’une clef parmi beaucoup d’autre en une branche des mathématiques où l’objectif était d’établir des méthodes mathématiques basés sur toutes les faiblesses possibles d’Enigma ainsi que les maladresses des chiffreurs allemands.

La faiblesse intrinsèque d’Enigma vient du réflecteur, aucune lettre ne peut être chiffrée par elle même. Enigma est donc bien la seule machine à écrire à ne jamais écrire un ‘a’ quand on tape un ‘a’.

Cette faiblesse mécanique couplée avec les maladresse des chiffreurs allemands peut aboutir à de très bons résultats. Par exemple il est arrivé que pour effectuer un test, un opérateur allemand envoya un message composé uniquement de ‘T’. Les cryptanalystes Alliés ayant reçu ce message remarquèrent aussitôt que le message chiffré ne présentait aucune occurrence de la lettre T, ils en déduisirent le message clair et la position des rotors, donc la clef du jour, par la même occasion.

Alan Turing développe la “bombe électromagnétique”, que l'on peut considérer comme le premier ordinateur. La ‘bombe’ permet premièrement d’identifier les emplacements possibles d’un mot probable, comme ‘Wetter’, ou encore ‘Heil Hitler’. Il faut que aucune des lettres du texte chiffré ne soit identique à celle du mot probable. Ensuite des hypothèses sont faites sur la position initiale des rotors et sont très rapidement analysées jusqu’à tomber sur une contradiction permettant de les réfuter.
Comme Turing travaille sur les chaînes, qui permettent de séparer le problème du brouilleur de celui du tableau de fiches. il montre que dès lors qu’une contradiction est détectée, on peut éliminer toutes les autres hypothèses qui entraînent celle-ci. Cela permit de minimiser considérablement le nombre de position des rotors à essayer.


<img src="{{ "/assets/3_Guerres/Bombe.jpg" | relative_url }}" alt="Bombe" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Les "bombes électromagnétiques" ont été détruites après la guerre, mais en voici une réplique</em> </p>

On peut aussi parler de la recherche de messages clairs qui était cruciale au fonctionnement des bombes électromagnétiques. Les anglais développèrent toutes sortes de stratégies pour retrouver un mot dans les messages. Ils allèrent même jusqu'à planter de mines aux yeux des Allemands dans l'espoir de retrouver le mot "Minen" dans les messages radios. Ils baptisèrent cette technique le jardinage.

Finalement, grâce à la puissance de centaines de bombes électromagnétiques, aux erreurs involontaires des opérateurs allemands et  à des recherches éreintantes de mots probables, les Alliés finirent par pouvoir déchiffrer la clef du jour en 20 minutes environ, ce qui permit aux Alliés d’avoir l’avantage sur les Allemands. Cependant au moment où le nombre de bombes devenait suffisant pour déchiffrer tous les messages, l’armée soviétique écrasait déjà la Wehrmacht sur le front oriental et la puissance industrielle des Alliés surpassait considérablement celle allemande.

Enigma reste donc aujourd’hui le plus célèbre chiffrement de tous les temps et la cryptanalyse de Alan Turing et de Marian Rejewski, si elle n’a apportée des avancées grandioses à la cryptologie, a révolutionné l’approche de la cryptanalyse en la rendant scientifique, mathématique. Enfin l’acte de briser un chiffrement précis, un des plus célèbre de tous les temps réduisant ainsi drastiquement la durée la guerre ainsi que le nombre colossal de victimes perdurera dans l’esprit du public et restera gravé dans la “mythologie” de la cryptanalyse comme un acte héroïque.
