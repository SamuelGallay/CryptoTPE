---
title: Le chiffre de César
permalink: /cesar/
precedente: /polybe/
suivante: /al-kindi/
partie: "L'Antiquité"
menu: /antiquite/
---

## Elements de contexte

Le plus populaire des chiffrements est sûrement le chiffre de César. Il fut utilisé, si ce n’est inventé, par Jules César lors de la Guerre des Gaules.

![cesar]({{ "/assets/1_Antiquite/cesarstatue.png" | relative_url }}){: .center-image }
<p align="center"> <em>Jules César par Nicolas Coustou, 1696, Musée du Louvre</em> </p>

Cette dernière opposa les tribus gauloises à l’armée romaine de 58 à 51 avant J.-C. Appelées à l'aide contre les Helvètes par les Eduens «amis et alliés du peuple romain», les troupes romaines de Jules César pénètrent dans la Gaule Chevelue en 58 avant J.-C.

Elles vont progressivement, en plusieurs campagnes annuelles, se rendre maîtresses de la Gaule. Une tentative d'invasion de la Grande Bretagne se soldera par un échec.

En 52 avant J.-C., un jeune chef arverne du nom de Vercingétorix tente de restaurer à son profit l'autorité du Brenn et suscite un soulèvement général des peuples de la Gaule contre l'occupant. Contre les Romains, Vercingétorix applique la tactique de la terre brûlée. Il est victorieux à Gergovie, ville du pays des Arvernes. César assiège la ville, mais est repoussé par une audacieuse sortie de la cavalerie gauloise.


César réagit : il traverse les Cévennes, prend Avaricum (Bourges) et bat la cavalerie gauloise de Vercingétorix grâce à ses cavaliers germains. Vercingétorix fait ensuite une erreur tactique en se laissant enfermer dans Alésia par César dans une double ligne de fortification. A l'issue d'un long siège, les assiégés doivent se rendre en 52 avant J.-C. La victoire de Jules César est assurée et la Gaule devient définitivement romaine.

<img src="{{ "/assets/1_Antiquite/alesia.jpg" | relative_url }}" alt="Carthage" style="margin: 0 auto;display: block;width: 600px;"/>
<p align="center"> <em>Vercingétorix jette ses armes aux pieds de César, Lionel Royer, 1899</em> </p>

Les *Commentaires sur la guerre des Gaules* de Jules César constituent une source presque unique de connaissance sur le déroulement de la conquête. C’est une source primaire qui est cependant à étudier avec un oeil critique car elle offre un point de vue subjectif. César cherche à y rehausser son mérite. II parle à la troisième personne, et utilise la forme impersonnelle pour évoquer les échecs. Il insiste sur la figure de Vercingétorix et tente de masquer le sens de l’organisation gauloise. Il n’évoque pas non plus les négociations, nombreuses, pour écourter des conflits, et il occulte le rôle des druides dans la société gauloise.

Pour garder contact avec ses généraux, César utilisait un procédé de chiffrement rendant le message, s’il était saisi, incompréhensible pour l'ennemi.

## Fonctionnement et exemple

Ce procédé, appelé chiffre de César, consiste à décaler les lettres de l'alphabet de quelques crans vers la droite ou vers la gauche : il s'agit d'un [chiffrement par substitution monoalphabétique]({{ "/glossaire/" | relative_url }}).

Il est décrit par l’historien romain Suétone dans son oeuvre biographique *Vies des douze Césars*, Livre premier, César, LVI publié entre 119 et 122 :
 > « Extant et ad Ciceronem, item ad familiares domesticis de rebus, in quibus, si qua occultius perferenda erant, per notas scripsit, id est sic structo litterarum ordine, ut nullum verbum effici posset: quae si qui investigare et persequi velit, quartam elementorum litteram, id est D pro A et perinde reliquas commutet. »

Ce qui donne en français :
> « On a conservé en outre ses lettres à Cicéron, et celles qu'il adressait à ses familiers sur ses affaires domestiques; quand il avait à leur faire quelque communication secrète, il usait d'un chiffre, c'est-à-dire qu'il brouillait les lettres de telle façon qu'on ne pût reconstituer aucun mot: si l'on veut en découvrir le sens et les déchiffrer, il faut substituer à chaque lettre la troisième qui la suit dans l'alphabet, c'est-à-dire le D à l'A, et ainsi de suite. »

La clef de déchiffrement est donc simple : connaissant la valeur de décalage de l’alphabet (trois rangs) il suffit de décaler pour avoir l’alphabet clair. Le message clair est à l’alphabet traditionnel ce que le message chiffré est à l’alphabet décalé.


| **Alphabet clair**   | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z |
|----------------------|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Alphabet chiffré** | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z | A | B | C |

Voici un message d'exemple :


| **Message clair**   | V | E | N | I |   | V | I | D | I |   | V | I | C | I |
|---------------------|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Message chiffré** | Y | H | Q | L |   | Y | L | G | L |   | Y | L | F | L |

## Modélisation mathématique

On peut aussi coder d’une autre façon, plus mathématique. On note A=0, B=1,C =3 ..., Z=25. On ajoute une constante (le décalage, précédemment 3) et pour conserver le résultat entre 0 et 25, on le réduit modulo 26 (longueur de l'alphabet)
Réduire modulo, c’est récupérer uniquement le reste de la division euclidienne : on note a mod b le reste de la division de a par b.  Ex : 7 mod 5 = 2
Soit k la longueur du décalage, $$ n_{i} $$ le nombre associé à la lettre claire, et $$ n_{f} $$ le nombre associé à la lettre chiffrée, on peut alors écrire :

$$ (n_{i} + k) \bmod 26 = n_{f} $$

## Exemple

`Dura lex, sed lex` (la loi est dure, mais c’est la loi)

* D=4, 4+3=7 et 7=G, donc on code D par G
* U=21, 21+3=24 et 24=X, donc on code U par X
* R=18, 18+3=21 et 21=U, donc on code R par U
* Pour X, X=23, 23+3=26 et 26 modulo 26 = 0, 0=A, donc on code X par A
* Dura lex, sed lex est chiffré `gxud oha, vhg oha`

## *Commentaires sur la Guerre des Gaules* de Jules César

Les *Commentaires sur la Guerre des Gaules* n’évoquent en réalité jamais le chiffre de César mais parlent bien d’un moyen de cacher les messages aux yeux de l’ennemi, comme dans cet extrait :
>"Il [César] persuade alors un cavalier gaulois, en lui promettant de grandes récompenses, de porter une lettre à Cicéron. Il envoie celle-ci écrite en lettres grecques, afin que, si elle est interceptée, nos desseins ne soient pas pénétrés par les ennemis."

La technique de chiffrement se borne ici à traduire le texte en grec. On peut supposer que Jules César considérait que les barbares auxquels il était confronté ne connaissaient pas l’écriture grecque. Cela ne l’empêchait pas, dans certains cas, d’utiliser une double protection grâce à la stéganographie : en effet le message chiffré envoyé à Cicéron était dissimulé sur la courroie d’une tragule (javelot).

Il semblerait même que Valérius Probus (50 - 150), critique et grammairien romain, ait écrit un traité complet sur “le sens caché des lettres dans l’écriture de la correspondance de Caius César”. Celui-ci n’a malheureusement pas été conservé jusqu’à nous. Il existe d’autres témoignages confirmant l’existence de ces techniques de chiffrement, notamment ceux d'érudits comme Aulu-Gelle et Dion Cassius.

Tous ces témoignages sur la cryptographie en usage chez les grands chefs romains montrent la réalité de l’existence d’une réflexion sur la sécurité des missives, même dans la correspondance privée. Leur position dans la société et leurs actes militaires ont fait que nous avons gardé des traces de leurs techniques cryptographiques mais il semble évident que, dans les milieux lettrés aussi, ces tentatives de protection du contenu des lettres par la substitution devaient exister.

### Faiblesse

Cependant, il n'y a que 26 façons différentes de chiffrer un message avec le code de César. Cela en fait donc un code très peu sûr, puisqu'il est très facile de le casser par [force brute]({{ "/glossaire/" | relative_url }}).

On peut également tenter sa cryptanalyse avec [l’analyse des fréquences]({{ "/al-kindi/" | relative_url }}) car c’est un chiffrement par substitution monoalphabétique. Pourtant, en raison de sa grande simplicité, le code de César fut encore employé par les officiers Sudistes pendant la guerre de Sécession, et même par l'armée russe en 1915.

### A vous de jouer !

Le message suivant a été codé avec le chiffre de César décalé de 3 rangs. Tentez de le déchiffrer.

dyh fdhvdu, prulwxul wh vdoxwdqw
