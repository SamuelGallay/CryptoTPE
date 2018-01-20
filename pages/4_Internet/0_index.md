---
title: L'ère d'Internet
permalink: /internet/
precedente: /guerres/
---

Depuis les années 70, avec la naissance d'Internet et jusqu'à nos jours, les communications connaissent un formidable essor.
De nouveaux chiffrements doivent être créés pour s'adapter aux transmissions binaires entre ordinateurs.
C'est alors que voit le jour [le DES]({{ "/des/" | relative_url }}), pour *Data Encryption Standard*, un chiffrement symétrique qui permit aux internautes d'assurer leurs communications.

Malheureusement il nécessite de partager la clef, un secret commun entre les utilisateurs.
Cela posa un problème à tout le monde, distribuer les clefs par la poste n'était pas sûr, et même les Etats peinaient à transmettre leurs clefs rapidement sans crainte d'être espionnés.
Deux mathématiciens cryptologues américains inventèrent une nouvelle forme de cryptographie dite asymétrique.
Ils nommèrent de leurs noms [le Diffie-Hellman]({{ "/diffie-hellman/" | relative_url }}), un protocole de transmission de clefs entre utilisateurs pouvant ne jamais s'être rencontrés pour partager un secret.

L'année suivante, en 1977 trois chercheurs du Massachusetts Institute of Technology publient un véritable chiffrement asymétrique, [le RSA]({{ "/rsa/" | relative_url }}) qui est encore utilisé couramment aujourd'hui sur Internet.

Parallèlement à la croissance d'Internet, la puissance de calcul des ordinateurs a énormément augmenté. C'est ainsi que le DES fut progressivement abandonné au profit d'autres chiffremenst symétriques plus efficaces. Les clefs utilisées dans le RSA augmentent elles aussi.
Si aujourd'hui les cryptanalystes ne peuvent rivaliser avec la force des chiffrements actuels s'ils sont bien utilisés, l'avenir leur réserve peut être encore des heures de gloire. Avec le développement des ordinateurs quantiques, maintenant une réalité, les chiffrements comme RSA pourraient devenir inefficaces.

Conscients de cette menace, les cryptolographes orientent leurs recherches dans principalement deux autres directions :
* [La cryptographie quantique]({{ "/quantique/" | relative_url }}), qui est prouvée sécurisée par les lois de la physique mais qui nécessites d'autres canaux de transmission que ceux d'Internet.
* La cryptographie post-quantique tente de rivaliser avec les ordinateurs quantiques en utilisant les ordinateurs traditionnels.

Parallèlement, l'utilisation du cloud pose de nouveaux problèmes. Les utilisateurs aimeraient que leurs données soient chiffrées, mais aussi pouvoir effectuer des calculs sur ces données chiffrées... C'est le domaine de recherche des chiffrements homomorphes.
<link rel="stylesheet" href="{{ '/assets/css/timeline.css' | relative_url }}">
<div class="timeline">

 <div class="container left">
 <a href="{{ "/des/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">Le DES</h2>
     <p>De 1975 à 2001</p>
   </div>
   </a>
 </div>

 <div class="container right">
 <a href="{{ "/diffie-hellman/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">Le Diffie-Hellman</h2>
     <p>De 1976 à nos jours</p>
   </div>
   </a>
 </div>

 <div class="container left">
 <a href="{{ "/rsa/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">Le RSA</h2>
     <p>De 1977 à nos jours</p>
   </div>
   </a>
 </div>

 <div class="container right">
 <a href="{{ "/quantique/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">La Cryptographie Quantique</h2>
     <p>Aujourd'hui et demain</p>
   </div>
   </a>
 </div>

</div>


