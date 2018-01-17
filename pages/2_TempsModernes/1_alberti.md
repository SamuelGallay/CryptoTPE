---
title: Le cadran d’Alberti et la mécanisation du chiffrement
permalink: /alberti/
suivante: /vigenere/
partie: Les Temps Modernes
menu: /temps-modernes/
---

# Le cadran d’Alberti : La mécanisation du chiffrement

## L'Italie de la Renaissance

Aux XIV et XVe siècles, l’Italie, territoire morcelé et fragmenté en de nombreuses cité-états indépendantes et rivales (son unité ne viendra qu’à la fin du XIXe siècle sous l’impulsion de Garibaldi), est le terrain propice pour un essor des écritures secrètes. Les villes marchandes, enrichies grâce au commerce, sont en conflit permanent. Il s’agit pour les souverains de fomenter en toute confidentialité des complots contre leurs adversaires d’une part et d’autre part d’intercepter et de déchiffrer les missives adverses pour déjouer les intrigues. Selon l’historien David Kahn, “le développement de la cryptologie est directement lié à l’épanouissement de la diplomatie moderne. Pour la première fois les Etats entretiennent des relations permanentes. Les ambassadeurs en poste - appelés “honorables espions” - envoient régulièrement des rapports qu’il est nécessaire de chiffrer en raison des jalousies, des suspicions et des intrigues qui empoisonnent les rapports entre les cités-états d’Italie.” La course au chiffrement commence : Venise se dote de secrétaires-chiffreurs ; ces “espions postaux” étudient les courriers destinés aux ambassadeurs des principautés voisines, suivie par ses rivales Florence, Gênes et Naples. Cette pratique se généralise en Europe, notamment en France et en Angleterre. En revanche, les pays d’Europe du Nord et de l’Est, tels que la Suède, la Pologne et l’Allemagne sont ignorants en la matière.

<img src="{{ "/assets/2_TempsModernes/italie-xv.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block;"/>
<p align="center"> <em> L'Italie au XVème siècle </em> </p>

L’usage de la cryptologie se répand en Italie aux XVe et XVIe siècles car les techniques en elles-mêmes connaissent de considérables innovations. On redécouvre les traités des arabes, pères de la cryptanalyse avec [Al-Kindi]({{ "/al-kindi/" | relative_url }}) au IXe siècle et en 1412 l’égyptien Al-Qalqashandi qui synthétise dans une encyclopédie en 14 volumes l’ensemble des connaissances de la civilisation arabe en cryptologie. La découverte de l’analyse des fréquences, qui met à mal les chiffrements par substitution monoalphabétique, bouleverse les habitudes des Occidentaux, qui se contentaient de cette technique jusqu’alors considérée comme infaillible.

<img src="{{ "/assets/2_TempsModernes/alberti2.jpg" | relative_url }}" alt="Cadran" style="margin: 0 auto;display: block; width: 300px;"/>
<p align="center"> <em>Leon Battista Alberti</em> </p>

C’est un architecte, mathématicien, linguiste, véritable archétype de l’humaniste de la Renaissance, Leon Battista Alberti, qui trouve la parade en 1467 avec son cadran chiffrant : c’est la naissance de la [substitution polyalphabétique]({{ "/glossaire/" | relative_url }}), qui dilue la fréquence d’apparition des lettres.

## Fonctionnement

<img src="{{ "/assets/2_TempsModernes/cadran.png" | relative_url }}" alt="Cadran" style="margin: 0 auto;display: block; width: 400px;"/>

L’instrument comporte deux disques de cuivres ; l’un, fixe, est gravé de l’alphabet (exceptées les lettres H, J, K, U, W et Y) et des chiffres 1, 2, 3 et 4 ; l’autre, mobile, est composé d’un alphabet de substitution en désordre (sauf le w, et le u remplace le v). Les deux correspondants sont équipés du même cadran et conviennent au préalable d’une lettre index. Le chiffreur choisit une lettre du disque mobile qu’il place sous la lettre index et l’indique en minuscule au début du message. Pour chiffrer, il suffit de remplacer les lettres originelles par celles du disque mobile : il s’agit alors d’une substitution monoalphabétique. Mais il suffit de changer la position du disque, en le précisant par une nouvelle minuscule, pour générer un nouvel alphabet : il s’agit alors d’un chiffrement polyalphabétique. Alberti va plus loin en associant aux groupes de chiffres de 11 à 4444 des significations particulières, établies sur un document préparé à l’avance : ainsi lorsque l’on obtient 14 après avoir déchiffré, cela signifie “passez à l’attaque”. On parle alors de “surchiffrement”, puisque l’on cumule plusieurs chiffrements différents successifs.

## Exemple

Exemple avec lettre index A et le disque mobile ci-dessus :
* message en clair : `Alberti est génial`
* Message codé : `x xekmbsl v dfc m aebgmq`


| **Clair**   |A |L|B|E|R|T|I|E |S|T|G |E|N|I|A|L|
| **Chiffre** |xX|E|K|M|B|S|L|vD|F|C|mA|E|B|G|M|Q|

On précisera que les minuscules ne sont pas des caractères correspondant à une lettre claire, mais des lettres qui indiquent que l'on doit tourner le cadran en alignant cette lettre index (ici A)
