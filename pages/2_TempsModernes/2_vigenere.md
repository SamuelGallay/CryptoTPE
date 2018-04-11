---
title: Le chiffrement de Vigenère
permalink: /vigenere/
precedente: /alberti/
suivante: /louis14/
partie: Les Temps Modernes
menu: /temps-modernes/
---

## Eléments de contexte

C'est en s’inspirant des travaux d’un bénédictin allemand, Johannes von Heidenberg, surnommé Trithème que Blaise de Vigenère élabora son fameux carré. En effet le moine avait eu l’idée “mettre en carré” les roues d’Alberti, ce qui aboutissait à un tableau de 26 lignes, la première étant composée d’un alphabet ordinaire, les autres d’un alphabet décalé à chaque fois d’un rang vers la gauche. Il chiffrait la première lettre du message avec la première ligne du tableau, la deuxième lettre avec la deuxième ligne et ainsi de suite jusqu’au moment où, parvenu à la dernière ligne du tableau, il repartait à la première. Le carré n’est pas alors exploité à son maximum : la notion de clef littérale émergea au début du XVIe siècle avec l’italien Belaso qui parlait de “mot de passe”. Vigenère fit la synthèse des deux en reprenant le tableau de Trithème et en l’utilisant avec le principe de clef de Belaso : il changea d’alphabet à chaque nouvelle lettre.

<img src="{{ "/assets/2_TempsModernes/vigenere2.png" | relative_url }}" alt="Vigenere2" style="margin: 0 auto;display: block; width: 300px;"/>
<p align="center"> <em>Blaise de Vigenère</em> </p>

## Modélisation mathématique et fonctionnement

Les correspondants définissent préalablement une clef qui servira à chiffrer et déchiffrer leurs messages. Le mot-clef est épelé bien clairement au-dessus du message, et répété en boucle de sorte que chaque lettre du message soit associée à une lettre de la clef. Ils décalent ensuite la lettre du message du nombre associé à la lettre de la clef correspondante (A associé à 0, B à 1, etc…).

Exemple : `Vigenère est remarquable` avec comme clef : `crypto`


| **Clair**   |V|I|G|E|N|E|R|E|E|S|T|R|E|M|A|R|Q|U|A|B|L|E|
| **Clef**     |C|R|Y|P|T|O|C|R|Y|P|T|O|C|R|Y|P|T|O|C|R|Y|P|
| **Chiffré** |X|Z|E|T|G|S|T|V|C|H|M|F|G|D|Y|G|J|I|C|S|J|T|

Dans le tableau de Vigenère, les lignes sont pour la clef et les colonnes pour l'alphabet clair. La lettre chiffrée se trouve à l'intersection entre la ligne de la clef et la colonne de la lettre claire. Pour chiffrer la première lettre, V, on identifie la lettre de la clef placée au-dessous, C, qui détermine la ligne. On repère ensuite la colonne commençant par V et on repère la lettre se trouvant à l'intersection de la ligne C et de la colonne V, c'est bien X.

<img src="{{ "/assets/2_TempsModernes/vigenere.png" | relative_url }}" alt="Vigenere" style="margin: 0 auto;display: block; width: 700px;"/>
<p align="center"> <em>La table de Vigenère</em> </p>

Voici donc une modélisation mathématique par une fonction, qui, définie sur les entiers de 0 à 25 associe au nombre correspondant à la lettre claire, le nombre correspondant à la lettre chiffrée

$$ f(l_{i}) = (l_{i} + k_{i} \bmod k) \bmod 26 $$

Où :

| \$$ i $$ | position de la lettre chiffrée et claire dans le message|
| \$$ l_{i} $$ | nombre associé à la lettre d'indice i |
| \$$ k_{i} $$  |  nombre associé à lettre de la clef d’indice i |
| \$$ k $$ | taille de la clef |

## Sécurité

Vigenère tire son savoir des cryptologues italiens qu’il a rencontrés lors de séjours diplomatiques à Rome : il expose sa théorie dans le *Traité des chiffres ou secrètes manières d’écrire* paru en 1585. C'est un [chiffrement polyalphabétique]({{ "/glossaire/" | relative_url }}) qui résiste donc à l'analyse des fréquences des cryptanalystes arabes. Plus la clef est grande, plus le niveau de sécurité est élevé. Donc si la clef de chiffrement est aussi longue que le message, et totalement aléatoire, le chiffre de Vigenère est inviolable : on parle de méthode du masque jetable, de chiffrement de Vernam, ou de One-Time Pad. Celui-ci est notamment utilisé pour le téléphone rouge et encore aujourd’hui dans les ambassades. Cependant pour utiliser le chiffrement de Vernam il faut au préalable transmettre à son correspondant une clef aléatoire aussi longue que le message. On ne fait donc que déplacer le problème, mais dans des cas comme celui du téléphone rouge, on peut se permettre de transmettre la clef par des valises diplomatiques.

## Pour chiffrer automatiquement :

<textarea id="myText"></textarea>
<div style="padding: 5px 0px">
  <label for="motClef">Le mot-clef (uniquement des lettres) :</label><br>
  <input id="motClef" onblur="majuscules()" value="A">
  <button onclick="chiffrer(false)">Chiffrer</button>
  <button onclick="chiffrer(true)">Déchiffrer</button>
</div>
<div style="padding: 5px 0px">
  <div><input type="radio" name="casse" id="1" checked> <label for="1">Sensible à la casse et ponctuation</label></div>
  <div><input type="radio" name="casse" id="2"> <label for="2">Majuscules et ponctuation</label></div>
  <div><input type="radio" name="casse" id="3"> <label for="3">Blocs de 5 et uniquement les lettres</label></div>
</div>
<textarea id="chiffre"></textarea>

## A vous de jouer !

Le message suivant a été codé avec la clef RABELAIS. Tentez de le déchiffrer.

Jcjiycm krnt gznauzeogp n'mkk qvi cuqfv df p'lmm


<!-- %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% -->
<script>
function majuscules() {
  var texte = "";
  var x=document.getElementById("motClef").value.toUpperCase();
  for(i=0; i<x.length; i++){
    if(x.charCodeAt(i) >= 65 && x.charCodeAt(i) <= 90){
        texte += x.charAt(i);
    }
  }
  if(texte == "") {texte = "A";}
  document.getElementById("motClef").value = texte;
}

function chiffrer(inverse) {
  var choix;
  if (document.getElementById("1").checked) {choix = 1;}
  if (document.getElementById("2").checked) {choix = 2;}
  if (document.getElementById("3").checked) {choix = 3;}
  var x=document.getElementById("motClef").value;
  var clef = [x.length];
  for(i=0; i<x.length; i++){
    clef[i] = x.charCodeAt(i)-65;
    if(inverse) {clef[i] = (26-clef[i])%26}
  }

  var propre = document.getElementById("myText").value.toUpperCase().latinise();
  var latin = document.getElementById("myText").value.latinise();
  var z = "";
  nLettres = 0;
  for (var i=0; i<propre.length; i++) {
    if(propre.charCodeAt(i) < 64 || propre.charCodeAt(i) > 90) { //Si pas une lettre
      if (choix != 3) {z += propre.charAt(i);} //si ponctuation
    }
    else { //Si une letre :
      if(latin.charCodeAt(i) > 90 && choix == 1) { //Si min + sensible
        z += String.fromCharCode((propre.charCodeAt(i)+clef[nLettres%x.length]-65) % 26 + 65).toLowerCase();
      }
      else { //Si maj ou insensible
        if (choix == 3 && z.length%6 == 5) {z += " ";} // Ajouter un espace si choix == 3
        z += String.fromCharCode((propre.charCodeAt(i)+clef[nLettres%x.length]-65) % 26 + 65);
      }
      nLettres++;
    }
  }
  document.getElementById("chiffre").value = z;
}


var Latinise={};Latinise.latin_map={"Á":"A","Ă":"A","Ắ":"A","Ặ":"A","Ằ":"A","Ẳ":"A","Ẵ":"A","Ǎ":"A","Â":"A","Ấ":"A","Ậ":"A","Ầ":"A","Ẩ":"A","Ẫ":"A","Ä":"A","Ǟ":"A","Ȧ":"A","Ǡ":"A","Ạ":"A","Ȁ":"A","À":"A","Ả":"A","Ȃ":"A","Ā":"A","Ą":"A","Å":"A","Ǻ":"A","Ḁ":"A","Ⱥ":"A","Ã":"A","Ꜳ":"AA","Æ":"AE","Ǽ":"AE","Ǣ":"AE","Ꜵ":"AO","Ꜷ":"AU","Ꜹ":"AV","Ꜻ":"AV","Ꜽ":"AY","Ḃ":"B","Ḅ":"B","Ɓ":"B","Ḇ":"B","Ƀ":"B","Ƃ":"B","Ć":"C","Č":"C","Ç":"C","Ḉ":"C","Ĉ":"C","Ċ":"C","Ƈ":"C","Ȼ":"C","Ď":"D","Ḑ":"D","Ḓ":"D","Ḋ":"D","Ḍ":"D","Ɗ":"D","Ḏ":"D","ǲ":"D","ǅ":"D","Đ":"D","Ƌ":"D","Ǳ":"DZ","Ǆ":"DZ","É":"E","Ĕ":"E","Ě":"E","Ȩ":"E","Ḝ":"E","Ê":"E","Ế":"E","Ệ":"E","Ề":"E","Ể":"E","Ễ":"E","Ḙ":"E","Ë":"E","Ė":"E","Ẹ":"E","Ȅ":"E","È":"E","Ẻ":"E","Ȇ":"E","Ē":"E","Ḗ":"E","Ḕ":"E","Ę":"E","Ɇ":"E","Ẽ":"E","Ḛ":"E","Ꝫ":"ET","Ḟ":"F","Ƒ":"F","Ǵ":"G","Ğ":"G","Ǧ":"G","Ģ":"G","Ĝ":"G","Ġ":"G","Ɠ":"G","Ḡ":"G","Ǥ":"G","Ḫ":"H","Ȟ":"H","Ḩ":"H","Ĥ":"H","Ⱨ":"H","Ḧ":"H","Ḣ":"H","Ḥ":"H","Ħ":"H","Í":"I","Ĭ":"I","Ǐ":"I","Î":"I","Ï":"I","Ḯ":"I","İ":"I","Ị":"I","Ȉ":"I","Ì":"I","Ỉ":"I","Ȋ":"I","Ī":"I","Į":"I","Ɨ":"I","Ĩ":"I","Ḭ":"I","Ꝺ":"D","Ꝼ":"F","Ᵹ":"G","Ꞃ":"R","Ꞅ":"S","Ꞇ":"T","Ꝭ":"IS","Ĵ":"J","Ɉ":"J","Ḱ":"K","Ǩ":"K","Ķ":"K","Ⱪ":"K","Ꝃ":"K","Ḳ":"K","Ƙ":"K","Ḵ":"K","Ꝁ":"K","Ꝅ":"K","Ĺ":"L","Ƚ":"L","Ľ":"L","Ļ":"L","Ḽ":"L","Ḷ":"L","Ḹ":"L","Ⱡ":"L","Ꝉ":"L","Ḻ":"L","Ŀ":"L","Ɫ":"L","ǈ":"L","Ł":"L","Ǉ":"LJ","Ḿ":"M","Ṁ":"M","Ṃ":"M","Ɱ":"M","Ń":"N","Ň":"N","Ņ":"N","Ṋ":"N","Ṅ":"N","Ṇ":"N","Ǹ":"N","Ɲ":"N","Ṉ":"N","Ƞ":"N","ǋ":"N","Ñ":"N","Ǌ":"NJ","Ó":"O","Ŏ":"O","Ǒ":"O","Ô":"O","Ố":"O","Ộ":"O","Ồ":"O","Ổ":"O","Ỗ":"O","Ö":"O","Ȫ":"O","Ȯ":"O","Ȱ":"O","Ọ":"O","Ő":"O","Ȍ":"O","Ò":"O","Ỏ":"O","Ơ":"O","Ớ":"O","Ợ":"O","Ờ":"O","Ở":"O","Ỡ":"O","Ȏ":"O","Ꝋ":"O","Ꝍ":"O","Ō":"O","Ṓ":"O","Ṑ":"O","Ɵ":"O","Ǫ":"O","Ǭ":"O","Ø":"O","Ǿ":"O","Õ":"O","Ṍ":"O","Ṏ":"O","Ȭ":"O","Ƣ":"OI","Ꝏ":"OO","Ɛ":"E","Ɔ":"O","Ȣ":"OU","Ṕ":"P","Ṗ":"P","Ꝓ":"P","Ƥ":"P","Ꝕ":"P","Ᵽ":"P","Ꝑ":"P","Ꝙ":"Q","Ꝗ":"Q","Ŕ":"R","Ř":"R","Ŗ":"R","Ṙ":"R","Ṛ":"R","Ṝ":"R","Ȑ":"R","Ȓ":"R","Ṟ":"R","Ɍ":"R","Ɽ":"R","Ꜿ":"C","Ǝ":"E","Ś":"S","Ṥ":"S","Š":"S","Ṧ":"S","Ş":"S","Ŝ":"S","Ș":"S","Ṡ":"S","Ṣ":"S","Ṩ":"S","Ť":"T","Ţ":"T","Ṱ":"T","Ț":"T","Ⱦ":"T","Ṫ":"T","Ṭ":"T","Ƭ":"T","Ṯ":"T","Ʈ":"T","Ŧ":"T","Ɐ":"A","Ꞁ":"L","Ɯ":"M","Ʌ":"V","Ꜩ":"TZ","Ú":"U","Ŭ":"U","Ǔ":"U","Û":"U","Ṷ":"U","Ü":"U","Ǘ":"U","Ǚ":"U","Ǜ":"U","Ǖ":"U","Ṳ":"U","Ụ":"U","Ű":"U","Ȕ":"U","Ù":"U","Ủ":"U","Ư":"U","Ứ":"U","Ự":"U","Ừ":"U","Ử":"U","Ữ":"U","Ȗ":"U","Ū":"U","Ṻ":"U","Ų":"U","Ů":"U","Ũ":"U","Ṹ":"U","Ṵ":"U","Ꝟ":"V","Ṿ":"V","Ʋ":"V","Ṽ":"V","Ꝡ":"VY","Ẃ":"W","Ŵ":"W","Ẅ":"W","Ẇ":"W","Ẉ":"W","Ẁ":"W","Ⱳ":"W","Ẍ":"X","Ẋ":"X","Ý":"Y","Ŷ":"Y","Ÿ":"Y","Ẏ":"Y","Ỵ":"Y","Ỳ":"Y","Ƴ":"Y","Ỷ":"Y","Ỿ":"Y","Ȳ":"Y","Ɏ":"Y","Ỹ":"Y","Ź":"Z","Ž":"Z","Ẑ":"Z","Ⱬ":"Z","Ż":"Z","Ẓ":"Z","Ȥ":"Z","Ẕ":"Z","Ƶ":"Z","Ĳ":"IJ","Œ":"OE","ᴀ":"A","ᴁ":"AE","ʙ":"B","ᴃ":"B","ᴄ":"C","ᴅ":"D","ᴇ":"E","ꜰ":"F","ɢ":"G","ʛ":"G","ʜ":"H","ɪ":"I","ʁ":"R","ᴊ":"J","ᴋ":"K","ʟ":"L","ᴌ":"L","ᴍ":"M","ɴ":"N","ᴏ":"O","ɶ":"OE","ᴐ":"O","ᴕ":"OU","ᴘ":"P","ʀ":"R","ᴎ":"N","ᴙ":"R","ꜱ":"S","ᴛ":"T","ⱻ":"E","ᴚ":"R","ᴜ":"U","ᴠ":"V","ᴡ":"W","ʏ":"Y","ᴢ":"Z","á":"a","ă":"a","ắ":"a","ặ":"a","ằ":"a","ẳ":"a","ẵ":"a","ǎ":"a","â":"a","ấ":"a","ậ":"a","ầ":"a","ẩ":"a","ẫ":"a","ä":"a","ǟ":"a","ȧ":"a","ǡ":"a","ạ":"a","ȁ":"a","à":"a","ả":"a","ȃ":"a","ā":"a","ą":"a","ᶏ":"a","ẚ":"a","å":"a","ǻ":"a","ḁ":"a","ⱥ":"a","ã":"a","ꜳ":"aa","æ":"ae","ǽ":"ae","ǣ":"ae","ꜵ":"ao","ꜷ":"au","ꜹ":"av","ꜻ":"av","ꜽ":"ay","ḃ":"b","ḅ":"b","ɓ":"b","ḇ":"b","ᵬ":"b","ᶀ":"b","ƀ":"b","ƃ":"b","ɵ":"o","ć":"c","č":"c","ç":"c","ḉ":"c","ĉ":"c","ɕ":"c","ċ":"c","ƈ":"c","ȼ":"c","ď":"d","ḑ":"d","ḓ":"d","ȡ":"d","ḋ":"d","ḍ":"d","ɗ":"d","ᶑ":"d","ḏ":"d","ᵭ":"d","ᶁ":"d","đ":"d","ɖ":"d","ƌ":"d","ı":"i","ȷ":"j","ɟ":"j","ʄ":"j","ǳ":"dz","ǆ":"dz","é":"e","ĕ":"e","ě":"e","ȩ":"e","ḝ":"e","ê":"e","ế":"e","ệ":"e","ề":"e","ể":"e","ễ":"e","ḙ":"e","ë":"e","ė":"e","ẹ":"e","ȅ":"e","è":"e","ẻ":"e","ȇ":"e","ē":"e","ḗ":"e","ḕ":"e","ⱸ":"e","ę":"e","ᶒ":"e","ɇ":"e","ẽ":"e","ḛ":"e","ꝫ":"et","ḟ":"f","ƒ":"f","ᵮ":"f","ᶂ":"f","ǵ":"g","ğ":"g","ǧ":"g","ģ":"g","ĝ":"g","ġ":"g","ɠ":"g","ḡ":"g","ᶃ":"g","ǥ":"g","ḫ":"h","ȟ":"h","ḩ":"h","ĥ":"h","ⱨ":"h","ḧ":"h","ḣ":"h","ḥ":"h","ɦ":"h","ẖ":"h","ħ":"h","ƕ":"hv","í":"i","ĭ":"i","ǐ":"i","î":"i","ï":"i","ḯ":"i","ị":"i","ȉ":"i","ì":"i","ỉ":"i","ȋ":"i","ī":"i","į":"i","ᶖ":"i","ɨ":"i","ĩ":"i","ḭ":"i","ꝺ":"d","ꝼ":"f","ᵹ":"g","ꞃ":"r","ꞅ":"s","ꞇ":"t","ꝭ":"is","ǰ":"j","ĵ":"j","ʝ":"j","ɉ":"j","ḱ":"k","ǩ":"k","ķ":"k","ⱪ":"k","ꝃ":"k","ḳ":"k","ƙ":"k","ḵ":"k","ᶄ":"k","ꝁ":"k","ꝅ":"k","ĺ":"l","ƚ":"l","ɬ":"l","ľ":"l","ļ":"l","ḽ":"l","ȴ":"l","ḷ":"l","ḹ":"l","ⱡ":"l","ꝉ":"l","ḻ":"l","ŀ":"l","ɫ":"l","ᶅ":"l","ɭ":"l","ł":"l","ǉ":"lj","ſ":"s","ẜ":"s","ẛ":"s","ẝ":"s","ḿ":"m","ṁ":"m","ṃ":"m","ɱ":"m","ᵯ":"m","ᶆ":"m","ń":"n","ň":"n","ņ":"n","ṋ":"n","ȵ":"n","ṅ":"n","ṇ":"n","ǹ":"n","ɲ":"n","ṉ":"n","ƞ":"n","ᵰ":"n","ᶇ":"n","ɳ":"n","ñ":"n","ǌ":"nj","ó":"o","ŏ":"o","ǒ":"o","ô":"o","ố":"o","ộ":"o","ồ":"o","ổ":"o","ỗ":"o","ö":"o","ȫ":"o","ȯ":"o","ȱ":"o","ọ":"o","ő":"o","ȍ":"o","ò":"o","ỏ":"o","ơ":"o","ớ":"o","ợ":"o","ờ":"o","ở":"o","ỡ":"o","ȏ":"o","ꝋ":"o","ꝍ":"o","ⱺ":"o","ō":"o","ṓ":"o","ṑ":"o","ǫ":"o","ǭ":"o","ø":"o","ǿ":"o","õ":"o","ṍ":"o","ṏ":"o","ȭ":"o","ƣ":"oi","ꝏ":"oo","ɛ":"e","ᶓ":"e","ɔ":"o","ᶗ":"o","ȣ":"ou","ṕ":"p","ṗ":"p","ꝓ":"p","ƥ":"p","ᵱ":"p","ᶈ":"p","ꝕ":"p","ᵽ":"p","ꝑ":"p","ꝙ":"q","ʠ":"q","ɋ":"q","ꝗ":"q","ŕ":"r","ř":"r","ŗ":"r","ṙ":"r","ṛ":"r","ṝ":"r","ȑ":"r","ɾ":"r","ᵳ":"r","ȓ":"r","ṟ":"r","ɼ":"r","ᵲ":"r","ᶉ":"r","ɍ":"r","ɽ":"r","ↄ":"c","ꜿ":"c","ɘ":"e","ɿ":"r","ś":"s","ṥ":"s","š":"s","ṧ":"s","ş":"s","ŝ":"s","ș":"s","ṡ":"s","ṣ":"s","ṩ":"s","ʂ":"s","ᵴ":"s","ᶊ":"s","ȿ":"s","ɡ":"g","ᴑ":"o","ᴓ":"o","ᴝ":"u","ť":"t","ţ":"t","ṱ":"t","ț":"t","ȶ":"t","ẗ":"t","ⱦ":"t","ṫ":"t","ṭ":"t","ƭ":"t","ṯ":"t","ᵵ":"t","ƫ":"t","ʈ":"t","ŧ":"t","ᵺ":"th","ɐ":"a","ᴂ":"ae","ǝ":"e","ᵷ":"g","ɥ":"h","ʮ":"h","ʯ":"h","ᴉ":"i","ʞ":"k","ꞁ":"l","ɯ":"m","ɰ":"m","ᴔ":"oe","ɹ":"r","ɻ":"r","ɺ":"r","ⱹ":"r","ʇ":"t","ʌ":"v","ʍ":"w","ʎ":"y","ꜩ":"tz","ú":"u","ŭ":"u","ǔ":"u","û":"u","ṷ":"u","ü":"u","ǘ":"u","ǚ":"u","ǜ":"u","ǖ":"u","ṳ":"u","ụ":"u","ű":"u","ȕ":"u","ù":"u","ủ":"u","ư":"u","ứ":"u","ự":"u","ừ":"u","ử":"u","ữ":"u","ȗ":"u","ū":"u","ṻ":"u","ų":"u","ᶙ":"u","ů":"u","ũ":"u","ṹ":"u","ṵ":"u","ᵫ":"ue","ꝸ":"um","ⱴ":"v","ꝟ":"v","ṿ":"v","ʋ":"v","ᶌ":"v","ⱱ":"v","ṽ":"v","ꝡ":"vy","ẃ":"w","ŵ":"w","ẅ":"w","ẇ":"w","ẉ":"w","ẁ":"w","ⱳ":"w","ẘ":"w","ẍ":"x","ẋ":"x","ᶍ":"x","ý":"y","ŷ":"y","ÿ":"y","ẏ":"y","ỵ":"y","ỳ":"y","ƴ":"y","ỷ":"y","ỿ":"y","ȳ":"y","ẙ":"y","ɏ":"y","ỹ":"y","ź":"z","ž":"z","ẑ":"z","ʑ":"z","ⱬ":"z","ż":"z","ẓ":"z","ȥ":"z","ẕ":"z","ᵶ":"z","ᶎ":"z","ʐ":"z","ƶ":"z","ɀ":"z","ﬀ":"ff","ﬃ":"ffi","ﬄ":"ffl","ﬁ":"fi","ﬂ":"fl","ĳ":"ij","œ":"oe","ﬆ":"st","ₐ":"a","ₑ":"e","ᵢ":"i","ⱼ":"j","ₒ":"o","ᵣ":"r","ᵤ":"u","ᵥ":"v","ₓ":"x"};
String.prototype.latinise=function(){return this.replace(/[^A-Za-z0-9\[\] ]/g,function(a){return Latinise.latin_map[a]||a})};
</script>
