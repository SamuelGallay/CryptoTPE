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

Cette dernière opposa les tribus gauloises à l’armée romaine de 58 à 51 avant J.-C . Appelées à l'aide contre les Helvètes par les Eduens «amis et alliés du peuple romain», les troupes romaines de Jules César pénètrent dans la Gaule Chevelue en 58 avant J.-C.

Elles vont progressivement, en plusieurs campagnes annuelles, se rendre maîtresses de la Gaule. Une tentative d'invasion de la Grande-Bretagne se soldera par un échec.

En 52 avant J.-C., un jeune chef arverne du nom de Vercingétorix tenta de restaurer à son profit l'autorité du Brenn et suscita un soulèvement général des peuples de la Gaule contre l'occupant. Contre les Romains, Vercingétorix appliqua la tactique de la terre brûlée. Il fut victorieux à Gergovie, ville du pays des Arvernes. César assiègea la ville, mais fut repoussé par une audacieuse sortie de la cavalerie gauloise.

César réagit : il traversa les Cévennes, prit Avaricum (Bourges) et battit la cavalerie gauloise de Vercingétorix grâce à ses cavaliers germains. Vercingétorix fit ensuite une erreur tactique en se laissant enfermer dans Alésia par César dans une double ligne de fortification. A l'issue d'un long siège, les assiégés durent se rendre en 52 avant J.-C. La victoire de Jules César était assurée et la Gaule devint définitivement romaine.

<img src="{{ "/assets/1_Antiquite/alesia.jpg" | relative_url }}" alt="Carthage" style="margin: 0 auto;display: block;width: 600px;"/>
<p align="center"> <em>Vercingétorix jette ses armes aux pieds de César, Lionel Royer, 1899</em> </p>

Les *Commentaires sur la guerre des Gaules* de Jules César constituent une source presque unique de connaissance sur le déroulement de la conquête. C’est une source primaire qui est cependant à étudier avec un oeil critique car elle offre un point de vue subjectif. César cherche à y rehausser son mérite. II parle à la troisième personne, et utilise la forme impersonnelle pour évoquer les échecs. Il insiste sur la figure de Vercingétorix et tente de masquer le sens de l’organisation gauloise. Il n’évoque pas non plus les négociations, nombreuses, pour écourter des conflits, et il occulte le rôle des druides dans la société gauloise.

Pour garder contact avec ses généraux, César utilisait un procédé de chiffrement rendant le message, s’il était saisi, incompréhensible pour l'ennemi.

## Fonctionnement et exemple

Ce procédé, appelé chiffre de César, consiste à décaler les lettres de l'alphabet de quelques crans vers la droite ou vers la gauche : il s'agit d'un [chiffrement par substitution monoalphabétique]({{ "/glossaire/" | relative_url }}).

Il est décrit par l’historien romain Suétone dans son oeuvre biographique *Vies des douze Césars*, Livre premier, César, LVI publié entre 119 et 122 :
 > « Extant et ad Ciceronem, item ad familiares domesticis de rebus, in quibus, si qua occultius perferenda erant, per notas scripsit, id est sic structo litterarum ordine, ut nullum verbum effici posset: quae si qui investigare et persequi velit, quartam elementorum litteram, id est D pro A et perinde reliquas commutet. »

Ce qui donne en français :
> « On a conservé en outre ses lettres à Cicéron, et celles qu'il adressait à ses familiers sur ses affaires domestiques ; quand il avait à leur faire quelque communication secrète, il usait d'un chiffre, c'est-à-dire qu'il brouillait les lettres de telle façon qu'on ne pût reconstituer aucun mot : si l'on veut en découvrir le sens et les déchiffrer, il faut substituer à chaque lettre la troisième qui la suit dans l'alphabet, c'est-à-dire le D à l'A, et ainsi de suite. »

La clef de déchiffrement est donc simple : connaissant la valeur de décalage de l’alphabet (trois rangs) il suffit de décaler pour avoir l’alphabet clair. Le message clair est à l’alphabet traditionnel ce que le message chiffré est à l’alphabet décalé.


| **Alphabet clair**   | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z |
|----------------------|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Alphabet chiffré** | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z | A | B | C |

Voici un message d'exemple :


| **Message clair**   | V | E | N | I |   | V | I | D | I |   | V | I | C | I |
|---------------------|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Message chiffré** | Y | H | Q | L |   | Y | L | G | L |   | Y | L | F | L |

## Modélisation mathématique

On peut aussi coder d’une autre façon, plus mathématique. On note A=0, B=1,C =3 ..., Z=25. On ajoute une constante (le décalage, précédemment 3) et pour conserver le résultat entre 0 et 25, on le réduit modulo 26 (longueur de l'alphabet).
Réduire modulo, c’est récupérer uniquement le reste de la division euclidienne : on note $$ a \bmod b $$ le reste de la division de a par b.  Ex : $$ 7 mod 5 = 2 $$
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

La technique de chiffrement se borne ici à traduire le texte en grec. On peut supposer que Jules César considérait que les barbares auxquels il était confronté ne connaissaient pas l’écriture grecque. Cela ne l’empêchait pas, dans certains cas, d’utiliser une double protection : en effet le message chiffré envoyé à Cicéron était dissimulé sur la courroie d’une tragule (javelot).

Il semblerait même que Valérius Probus (50 - 150), critique et grammairien romain, ait écrit un traité complet sur “le sens caché des lettres dans l’écriture de la correspondance de Caius César”. Celui-ci n’a malheureusement pas été conservé jusqu’à nous. Il existe d’autres témoignages confirmant l’existence de ces techniques de chiffrement, notamment ceux d'érudits comme Aulu-Gelle et Dion Cassius.

Tous ces témoignages sur la cryptographie en usage chez les grands chefs romains montrent la réalité de l’existence d’une réflexion sur la sécurité des missives, même dans la correspondance privée. Leur position dans la société et leurs actes militaires ont fait que nous avons gardé des traces de leurs techniques cryptographiques mais il semble évident que, dans les milieux lettrés aussi, ces tentatives de protection du contenu des lettres par la substitution devaient exister.

### Faiblesse

Cependant, il n'y a que 26 façons différentes de chiffrer un message avec le code de César. Cela en fait donc un code très peu sûr, puisqu'il est très facile de le casser par une [attaque par force brute]({{ "/glossaire/" | relative_url }}).

On peut également tenter sa cryptanalyse avec [l’analyse des fréquences]({{ "/al-kindi/" | relative_url }}) car c’est un chiffrement par substitution monoalphabétique. Pourtant, en raison de sa grande simplicité, le code de César fut encore employé par les officiers Sudistes pendant la guerre de Sécession, et même par l'armée russe en 1915.

### Pour chiffrer automatiquement :

<textarea id="myText"></textarea>
<div style="padding: 5px 0px">
  <label>Clef : </label>
  <input id="clef" type="number" value="3">
  <button onclick="chiffrer(false)">Chiffrer</button>
  <button onclick="chiffrer(true)">Déchiffrer</button>
</div>
<div style="padding: 5px 0px">
  <div><input type="radio" name="casse" id="1" checked> <label for="1">Sensible à la casse et ponctuation</label></div>
  <div><input type="radio" name="casse" id="2"> <label for="2">Majuscules et ponctuation</label></div>
  <div><input type="radio" name="casse" id="3"> <label for="3">Blocs de 5 et uniquement des lettres</label></div>
</div>
<textarea id="chiffre"></textarea>

### A vous de jouer !

Le message suivant a été codé avec le chiffre de César décalé de 3 rangs. Tentez de le déchiffrer.

dyh fdhvdu, prulwxul wh vdoxwdqw

<script>

function chiffrer(inverse) {
  var choix;
  if (document.getElementById("1").checked) {choix = 1;}
  if (document.getElementById("2").checked) {choix = 2;}
  if (document.getElementById("3").checked) {choix = 3;}
  document.getElementById("clef").value =
    (document.getElementById("clef").value%26 + 26)%26;
  var clef = Number(document.getElementById("clef").value);
  if(inverse) {clef = (26-clef)%26;}
  var propre = document.getElementById("myText").value.toUpperCase().latinise();
  var latin = document.getElementById("myText").value.latinise();
  var z = "";
  for (var i=0; i<propre.length; i++) {
    if(propre.charCodeAt(i) < 64 || propre.charCodeAt(i) > 90) {
      if (choix != 3) {z += propre.charAt(i);}
    }
    else {
      if(latin.charCodeAt(i) > 90 && choix == 1) {
        z += String.fromCharCode((propre.charCodeAt(i)+clef-65) % 26 + 65).toLowerCase();
      }
      else {
        if (choix == 3 && z.length%6 == 5) {z += " ";}
        z += String.fromCharCode((propre.charCodeAt(i)+clef-65) % 26 + 65);
      }
    }
  }
  document.getElementById("chiffre").value = z;
}


var Latinise={};Latinise.latin_map={"Á":"A","Ă":"A","Ắ":"A","Ặ":"A","Ằ":"A","Ẳ":"A","Ẵ":"A","Ǎ":"A","Â":"A","Ấ":"A","Ậ":"A","Ầ":"A","Ẩ":"A","Ẫ":"A","Ä":"A","Ǟ":"A","Ȧ":"A","Ǡ":"A","Ạ":"A","Ȁ":"A","À":"A","Ả":"A","Ȃ":"A","Ā":"A","Ą":"A","Å":"A","Ǻ":"A","Ḁ":"A","Ⱥ":"A","Ã":"A","Ꜳ":"AA","Æ":"AE","Ǽ":"AE","Ǣ":"AE","Ꜵ":"AO","Ꜷ":"AU","Ꜹ":"AV","Ꜻ":"AV","Ꜽ":"AY","Ḃ":"B","Ḅ":"B","Ɓ":"B","Ḇ":"B","Ƀ":"B","Ƃ":"B","Ć":"C","Č":"C","Ç":"C","Ḉ":"C","Ĉ":"C","Ċ":"C","Ƈ":"C","Ȼ":"C","Ď":"D","Ḑ":"D","Ḓ":"D","Ḋ":"D","Ḍ":"D","Ɗ":"D","Ḏ":"D","ǲ":"D","ǅ":"D","Đ":"D","Ƌ":"D","Ǳ":"DZ","Ǆ":"DZ","É":"E","Ĕ":"E","Ě":"E","Ȩ":"E","Ḝ":"E","Ê":"E","Ế":"E","Ệ":"E","Ề":"E","Ể":"E","Ễ":"E","Ḙ":"E","Ë":"E","Ė":"E","Ẹ":"E","Ȅ":"E","È":"E","Ẻ":"E","Ȇ":"E","Ē":"E","Ḗ":"E","Ḕ":"E","Ę":"E","Ɇ":"E","Ẽ":"E","Ḛ":"E","Ꝫ":"ET","Ḟ":"F","Ƒ":"F","Ǵ":"G","Ğ":"G","Ǧ":"G","Ģ":"G","Ĝ":"G","Ġ":"G","Ɠ":"G","Ḡ":"G","Ǥ":"G","Ḫ":"H","Ȟ":"H","Ḩ":"H","Ĥ":"H","Ⱨ":"H","Ḧ":"H","Ḣ":"H","Ḥ":"H","Ħ":"H","Í":"I","Ĭ":"I","Ǐ":"I","Î":"I","Ï":"I","Ḯ":"I","İ":"I","Ị":"I","Ȉ":"I","Ì":"I","Ỉ":"I","Ȋ":"I","Ī":"I","Į":"I","Ɨ":"I","Ĩ":"I","Ḭ":"I","Ꝺ":"D","Ꝼ":"F","Ᵹ":"G","Ꞃ":"R","Ꞅ":"S","Ꞇ":"T","Ꝭ":"IS","Ĵ":"J","Ɉ":"J","Ḱ":"K","Ǩ":"K","Ķ":"K","Ⱪ":"K","Ꝃ":"K","Ḳ":"K","Ƙ":"K","Ḵ":"K","Ꝁ":"K","Ꝅ":"K","Ĺ":"L","Ƚ":"L","Ľ":"L","Ļ":"L","Ḽ":"L","Ḷ":"L","Ḹ":"L","Ⱡ":"L","Ꝉ":"L","Ḻ":"L","Ŀ":"L","Ɫ":"L","ǈ":"L","Ł":"L","Ǉ":"LJ","Ḿ":"M","Ṁ":"M","Ṃ":"M","Ɱ":"M","Ń":"N","Ň":"N","Ņ":"N","Ṋ":"N","Ṅ":"N","Ṇ":"N","Ǹ":"N","Ɲ":"N","Ṉ":"N","Ƞ":"N","ǋ":"N","Ñ":"N","Ǌ":"NJ","Ó":"O","Ŏ":"O","Ǒ":"O","Ô":"O","Ố":"O","Ộ":"O","Ồ":"O","Ổ":"O","Ỗ":"O","Ö":"O","Ȫ":"O","Ȯ":"O","Ȱ":"O","Ọ":"O","Ő":"O","Ȍ":"O","Ò":"O","Ỏ":"O","Ơ":"O","Ớ":"O","Ợ":"O","Ờ":"O","Ở":"O","Ỡ":"O","Ȏ":"O","Ꝋ":"O","Ꝍ":"O","Ō":"O","Ṓ":"O","Ṑ":"O","Ɵ":"O","Ǫ":"O","Ǭ":"O","Ø":"O","Ǿ":"O","Õ":"O","Ṍ":"O","Ṏ":"O","Ȭ":"O","Ƣ":"OI","Ꝏ":"OO","Ɛ":"E","Ɔ":"O","Ȣ":"OU","Ṕ":"P","Ṗ":"P","Ꝓ":"P","Ƥ":"P","Ꝕ":"P","Ᵽ":"P","Ꝑ":"P","Ꝙ":"Q","Ꝗ":"Q","Ŕ":"R","Ř":"R","Ŗ":"R","Ṙ":"R","Ṛ":"R","Ṝ":"R","Ȑ":"R","Ȓ":"R","Ṟ":"R","Ɍ":"R","Ɽ":"R","Ꜿ":"C","Ǝ":"E","Ś":"S","Ṥ":"S","Š":"S","Ṧ":"S","Ş":"S","Ŝ":"S","Ș":"S","Ṡ":"S","Ṣ":"S","Ṩ":"S","Ť":"T","Ţ":"T","Ṱ":"T","Ț":"T","Ⱦ":"T","Ṫ":"T","Ṭ":"T","Ƭ":"T","Ṯ":"T","Ʈ":"T","Ŧ":"T","Ɐ":"A","Ꞁ":"L","Ɯ":"M","Ʌ":"V","Ꜩ":"TZ","Ú":"U","Ŭ":"U","Ǔ":"U","Û":"U","Ṷ":"U","Ü":"U","Ǘ":"U","Ǚ":"U","Ǜ":"U","Ǖ":"U","Ṳ":"U","Ụ":"U","Ű":"U","Ȕ":"U","Ù":"U","Ủ":"U","Ư":"U","Ứ":"U","Ự":"U","Ừ":"U","Ử":"U","Ữ":"U","Ȗ":"U","Ū":"U","Ṻ":"U","Ų":"U","Ů":"U","Ũ":"U","Ṹ":"U","Ṵ":"U","Ꝟ":"V","Ṿ":"V","Ʋ":"V","Ṽ":"V","Ꝡ":"VY","Ẃ":"W","Ŵ":"W","Ẅ":"W","Ẇ":"W","Ẉ":"W","Ẁ":"W","Ⱳ":"W","Ẍ":"X","Ẋ":"X","Ý":"Y","Ŷ":"Y","Ÿ":"Y","Ẏ":"Y","Ỵ":"Y","Ỳ":"Y","Ƴ":"Y","Ỷ":"Y","Ỿ":"Y","Ȳ":"Y","Ɏ":"Y","Ỹ":"Y","Ź":"Z","Ž":"Z","Ẑ":"Z","Ⱬ":"Z","Ż":"Z","Ẓ":"Z","Ȥ":"Z","Ẕ":"Z","Ƶ":"Z","Ĳ":"IJ","Œ":"OE","ᴀ":"A","ᴁ":"AE","ʙ":"B","ᴃ":"B","ᴄ":"C","ᴅ":"D","ᴇ":"E","ꜰ":"F","ɢ":"G","ʛ":"G","ʜ":"H","ɪ":"I","ʁ":"R","ᴊ":"J","ᴋ":"K","ʟ":"L","ᴌ":"L","ᴍ":"M","ɴ":"N","ᴏ":"O","ɶ":"OE","ᴐ":"O","ᴕ":"OU","ᴘ":"P","ʀ":"R","ᴎ":"N","ᴙ":"R","ꜱ":"S","ᴛ":"T","ⱻ":"E","ᴚ":"R","ᴜ":"U","ᴠ":"V","ᴡ":"W","ʏ":"Y","ᴢ":"Z","á":"a","ă":"a","ắ":"a","ặ":"a","ằ":"a","ẳ":"a","ẵ":"a","ǎ":"a","â":"a","ấ":"a","ậ":"a","ầ":"a","ẩ":"a","ẫ":"a","ä":"a","ǟ":"a","ȧ":"a","ǡ":"a","ạ":"a","ȁ":"a","à":"a","ả":"a","ȃ":"a","ā":"a","ą":"a","ᶏ":"a","ẚ":"a","å":"a","ǻ":"a","ḁ":"a","ⱥ":"a","ã":"a","ꜳ":"aa","æ":"ae","ǽ":"ae","ǣ":"ae","ꜵ":"ao","ꜷ":"au","ꜹ":"av","ꜻ":"av","ꜽ":"ay","ḃ":"b","ḅ":"b","ɓ":"b","ḇ":"b","ᵬ":"b","ᶀ":"b","ƀ":"b","ƃ":"b","ɵ":"o","ć":"c","č":"c","ç":"c","ḉ":"c","ĉ":"c","ɕ":"c","ċ":"c","ƈ":"c","ȼ":"c","ď":"d","ḑ":"d","ḓ":"d","ȡ":"d","ḋ":"d","ḍ":"d","ɗ":"d","ᶑ":"d","ḏ":"d","ᵭ":"d","ᶁ":"d","đ":"d","ɖ":"d","ƌ":"d","ı":"i","ȷ":"j","ɟ":"j","ʄ":"j","ǳ":"dz","ǆ":"dz","é":"e","ĕ":"e","ě":"e","ȩ":"e","ḝ":"e","ê":"e","ế":"e","ệ":"e","ề":"e","ể":"e","ễ":"e","ḙ":"e","ë":"e","ė":"e","ẹ":"e","ȅ":"e","è":"e","ẻ":"e","ȇ":"e","ē":"e","ḗ":"e","ḕ":"e","ⱸ":"e","ę":"e","ᶒ":"e","ɇ":"e","ẽ":"e","ḛ":"e","ꝫ":"et","ḟ":"f","ƒ":"f","ᵮ":"f","ᶂ":"f","ǵ":"g","ğ":"g","ǧ":"g","ģ":"g","ĝ":"g","ġ":"g","ɠ":"g","ḡ":"g","ᶃ":"g","ǥ":"g","ḫ":"h","ȟ":"h","ḩ":"h","ĥ":"h","ⱨ":"h","ḧ":"h","ḣ":"h","ḥ":"h","ɦ":"h","ẖ":"h","ħ":"h","ƕ":"hv","í":"i","ĭ":"i","ǐ":"i","î":"i","ï":"i","ḯ":"i","ị":"i","ȉ":"i","ì":"i","ỉ":"i","ȋ":"i","ī":"i","į":"i","ᶖ":"i","ɨ":"i","ĩ":"i","ḭ":"i","ꝺ":"d","ꝼ":"f","ᵹ":"g","ꞃ":"r","ꞅ":"s","ꞇ":"t","ꝭ":"is","ǰ":"j","ĵ":"j","ʝ":"j","ɉ":"j","ḱ":"k","ǩ":"k","ķ":"k","ⱪ":"k","ꝃ":"k","ḳ":"k","ƙ":"k","ḵ":"k","ᶄ":"k","ꝁ":"k","ꝅ":"k","ĺ":"l","ƚ":"l","ɬ":"l","ľ":"l","ļ":"l","ḽ":"l","ȴ":"l","ḷ":"l","ḹ":"l","ⱡ":"l","ꝉ":"l","ḻ":"l","ŀ":"l","ɫ":"l","ᶅ":"l","ɭ":"l","ł":"l","ǉ":"lj","ſ":"s","ẜ":"s","ẛ":"s","ẝ":"s","ḿ":"m","ṁ":"m","ṃ":"m","ɱ":"m","ᵯ":"m","ᶆ":"m","ń":"n","ň":"n","ņ":"n","ṋ":"n","ȵ":"n","ṅ":"n","ṇ":"n","ǹ":"n","ɲ":"n","ṉ":"n","ƞ":"n","ᵰ":"n","ᶇ":"n","ɳ":"n","ñ":"n","ǌ":"nj","ó":"o","ŏ":"o","ǒ":"o","ô":"o","ố":"o","ộ":"o","ồ":"o","ổ":"o","ỗ":"o","ö":"o","ȫ":"o","ȯ":"o","ȱ":"o","ọ":"o","ő":"o","ȍ":"o","ò":"o","ỏ":"o","ơ":"o","ớ":"o","ợ":"o","ờ":"o","ở":"o","ỡ":"o","ȏ":"o","ꝋ":"o","ꝍ":"o","ⱺ":"o","ō":"o","ṓ":"o","ṑ":"o","ǫ":"o","ǭ":"o","ø":"o","ǿ":"o","õ":"o","ṍ":"o","ṏ":"o","ȭ":"o","ƣ":"oi","ꝏ":"oo","ɛ":"e","ᶓ":"e","ɔ":"o","ᶗ":"o","ȣ":"ou","ṕ":"p","ṗ":"p","ꝓ":"p","ƥ":"p","ᵱ":"p","ᶈ":"p","ꝕ":"p","ᵽ":"p","ꝑ":"p","ꝙ":"q","ʠ":"q","ɋ":"q","ꝗ":"q","ŕ":"r","ř":"r","ŗ":"r","ṙ":"r","ṛ":"r","ṝ":"r","ȑ":"r","ɾ":"r","ᵳ":"r","ȓ":"r","ṟ":"r","ɼ":"r","ᵲ":"r","ᶉ":"r","ɍ":"r","ɽ":"r","ↄ":"c","ꜿ":"c","ɘ":"e","ɿ":"r","ś":"s","ṥ":"s","š":"s","ṧ":"s","ş":"s","ŝ":"s","ș":"s","ṡ":"s","ṣ":"s","ṩ":"s","ʂ":"s","ᵴ":"s","ᶊ":"s","ȿ":"s","ɡ":"g","ᴑ":"o","ᴓ":"o","ᴝ":"u","ť":"t","ţ":"t","ṱ":"t","ț":"t","ȶ":"t","ẗ":"t","ⱦ":"t","ṫ":"t","ṭ":"t","ƭ":"t","ṯ":"t","ᵵ":"t","ƫ":"t","ʈ":"t","ŧ":"t","ᵺ":"th","ɐ":"a","ᴂ":"ae","ǝ":"e","ᵷ":"g","ɥ":"h","ʮ":"h","ʯ":"h","ᴉ":"i","ʞ":"k","ꞁ":"l","ɯ":"m","ɰ":"m","ᴔ":"oe","ɹ":"r","ɻ":"r","ɺ":"r","ⱹ":"r","ʇ":"t","ʌ":"v","ʍ":"w","ʎ":"y","ꜩ":"tz","ú":"u","ŭ":"u","ǔ":"u","û":"u","ṷ":"u","ü":"u","ǘ":"u","ǚ":"u","ǜ":"u","ǖ":"u","ṳ":"u","ụ":"u","ű":"u","ȕ":"u","ù":"u","ủ":"u","ư":"u","ứ":"u","ự":"u","ừ":"u","ử":"u","ữ":"u","ȗ":"u","ū":"u","ṻ":"u","ų":"u","ᶙ":"u","ů":"u","ũ":"u","ṹ":"u","ṵ":"u","ᵫ":"ue","ꝸ":"um","ⱴ":"v","ꝟ":"v","ṿ":"v","ʋ":"v","ᶌ":"v","ⱱ":"v","ṽ":"v","ꝡ":"vy","ẃ":"w","ŵ":"w","ẅ":"w","ẇ":"w","ẉ":"w","ẁ":"w","ⱳ":"w","ẘ":"w","ẍ":"x","ẋ":"x","ᶍ":"x","ý":"y","ŷ":"y","ÿ":"y","ẏ":"y","ỵ":"y","ỳ":"y","ƴ":"y","ỷ":"y","ỿ":"y","ȳ":"y","ẙ":"y","ɏ":"y","ỹ":"y","ź":"z","ž":"z","ẑ":"z","ʑ":"z","ⱬ":"z","ż":"z","ẓ":"z","ȥ":"z","ẕ":"z","ᵶ":"z","ᶎ":"z","ʐ":"z","ƶ":"z","ɀ":"z","ﬀ":"ff","ﬃ":"ffi","ﬄ":"ffl","ﬁ":"fi","ﬂ":"fl","ĳ":"ij","œ":"oe","ﬆ":"st","ₐ":"a","ₑ":"e","ᵢ":"i","ⱼ":"j","ₒ":"o","ᵣ":"r","ᵤ":"u","ᵥ":"v","ₓ":"x"};
String.prototype.latinise=function(){return this.replace(/[^A-Za-z0-9\[\] ]/g,function(a){return Latinise.latin_map[a]||a})};
</script>
