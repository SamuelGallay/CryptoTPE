---
title: "Le DES : Un chiffrement symétrique"
permalink: /des/
suivante: /diffie-hellman/
partie: "L'ère d'Internet"
menu: /internet/
---

Jusque dans les années 1970, seules les hautes instances de l’Etat utilisaient la cryptographie. Elle était réservée à des applications principalement militaires et diplomatiques. Mais le besoin de protéger les communications et les données personnelles mémorisées sur les ordinateurs se fait de plus en plus pressant et pousse en 1973 le NBS (National Bureau of Standards) à publier un appel à contributions pour définir un algorithme  de  chiffrement  standard, qui serait utilisable par les entreprises qui ont besoin de protéger les fichiers et les communications sensibles.

Cet appel d'offre a conduit à la standardisation en 1976 d'un algorithme de chiffrement pour l'usage civil, le DES (Data Encryption Standard).
L’algorithme de chiffrement choisi comme système standard était une conception de la firme américaine IBM (International Business Machines) appelée Lucifer. Il avait été établi par Hort Feistel, un émigré allemand arrivé en Amérique en 1934.

Lucifer crypte les messages de la façon suivante. D’abord, le message est traduit en une longue suite de nombres binaires (bits). Cette suite est répartie en blocs de 64 bits et le cryptage est effectué séparément pour chaque bloc. En s’intéressant à un seul bloc, on brasse les 64 bits, puis on les sépare en deux demi-blocs de 32 appelé Gauche0 et Droite0 (G0 et D0). On applique ensuite à D0 une fonction de permutation qui change les bits selon une substitution complexe. Le D0 est, après cette intervention, ajouté au G0 pour constituer un nouveau demi-bloc de 32 bits appelé D1. Le D0 d’origine est rebaptisé G1. On appelle cet enchaînement d’opérations un cycle. Les processus est répété pour un deuxième cycle, qui part des nouveaux demi-blocs G1 et D1 et qui termine en G2 et D2. Ce processus est répété seize fois en tout.



<img src="{{ "/assets/4_Internet/des1.png" | relative_url }}" alt="des1" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> Schéma de l'algorithme du DES </em> </p>


Les modalité précises de la fonction de transformation peuvent varier et sont déterminées par une clef choisie par l'émetteur et le receveur. Les clefs utilisées dans la cryptographie par ordinateur sont des nombres. L’envoyeur et le receveur doivent donc fixer ce nombre pour décider de la clef. Ensuite, pour chiffrer, l’envoyeur entre le nombre-clef et le message dans Lucifer, qui émet le texte chiffré. Pour décrypter, le receveur entre la même clef et le texte chiffré dans Lucifer, qui ressort le texte original.

Le nombre de clefs possibles est l’un des composants les plus important pour la sécurité d’un chiffrement. Un cryptanalyste essayant de déchiffrer un message crypté peut tenter de vérifier toutes les clefs possibles. Or, plus le nombre de clefs est élevé, plus ces vérifications demanderont du temps. La NSA plaida donc pour une limitation du nombre de clefs à environ 100 000 000 000 000 000 (soit 56 bits). Elle semblait croire qu’une telle clef apporterait une confidentialité suffisante pour le public, car aucun organisme privé ne disposait d’un ordinateur capable de vérifier un tel nombre de clefs en un temps raisonnable. En revanche, la NSA serait en capacité de lire les messages qui l’intéressent.

Ce qui a signé la fin du DES est l'extraordinaire progression de la puissance des ordinateurs. Le 17 juin 1997, le DES est cassé en 3 semaines par une fédération de petites machines sur Internet. Et on estime très officiellement (dans un rapport présenté au Sénat Américain) à cette date à quelques secondes le temps nécessaire à un Etat pour percer les secrets d'un message chiffré avec le DES. Ainsi, le DES a progressivement été abandonné à partir de la fin des années 1990 et définitivement remplacé en 2001.

Cette première publication à grande échelle d'un algorithme de chiffrement marque l'entrée de la cryptologie dans le domaine public ainsi que la preuve que le procédé de chiffrement peut être connu de tous. Toutefois, malgré la standardisation et la force du DES, on se trouvait devant un autre problème majeur, celui de la distribution de la clef.

Imaginons qu’une banque souhaite envoyer à un client des données confidentielles par téléphone, mais craigne une écoute sur la ligne. La banque choisit une clef et utilise le DES pour crypter les données. Pour pouvoir les lire, il faut que le client ait connaissance de cette clef. La banque doit ainsi la lui transmettre, mais pas par téléphone puisqu’il y a un risque d’espionnage. Le seul moyen vraiment sûr serait de lui remettre la clef en main propres. Une méthode moins sûre, mais plus pratique est d’utiliser la poste. Dans les années 70, les banques essayèrent de faire distribuer les clefs par des coursiers spécialement sélectionnés, qui comptaient parmi les employés les plus sûrs de l’entreprise. Ces messagers devaient courir le monde munis de cartables cadenassés et remettre en main propres les clefs aux destinataires des messages de la banque. Plus les contacts se multipliaient, plus les réseaux s’étendaient, et tant de clefs durent être distribuées que la logistique nécessaire, avec ses frais prohibitifs, devint un véritable cauchemar.

Le problème de distribution de la clef a été le problème constant des cryptographes au cours de l’histoire. Pendant la seconde guerre mondiale, le haut commandement allemand devait ainsi distribuer le registre mensuel des clefs quotidiennes à tous les opérateurs d’Enigma, ce qui constituait un problème de logistique considérable.

La distribution des clefs constitua le problème primordial pour les cryptographes de l’après-guerre. La cryptologie était vouée à se développer pour des applications civiles et quotidienne, telles que le commerce, l’échange d’e-mail, etc. via internet. Il fallait pour cela qu’elle soit capable d’assurer son objectif premier, c’est-à-dire protéger la confidentialité des données. Pour les transactions commerciales, le dilemme se posait clairement : si les gouvernement, avec tout leur argent, avaient peine à garantir la sécurité de leurs clefs, comment des entreprises civiles pourraient-elles jamais espérer jouir d’une distribution de clefs sûre et non ruineuse ?
