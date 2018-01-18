---
title: Histoire de la Cryptographie
permalink: index.html
partie: "Accueil • Travail Personnel Encadré"
---

## Introduction

De tout temps l'homme a eu besoin de communiquer. Ce besoin a permis l'émergence de langues, ensemble de signes associés chacun à une signification particulière. Pour matérialiser ces langues, au IVe millénaire avant notre ère, l'écriture est inventée en Mésopotamie. Rudimentaire au départ (l'écriture cunéiforme consiste à graver sur des tablettes d'argile), son application était limitée : textes de lois, documents comptables par exemple.
Puis l'écriture s'est répandue, et il est devenu possible plus aisément d'échanger des messages.
Mais comment faire pour préserver la confidentialité du message ?

L’art, ou la science de cacher des messages a connu plusieurs formes au cours de l’histoire :

- La première a été de cacher le message aux yeux de ceux ne connaissant pas la méthode : c’est de la stéganographie.

- La seconde consiste à protéger un message en le chiffrant par le biais de clefs (secrètes ou publiques) qui le rendent incompréhensible : c'est de la cryptographie, sujet de notre TPE.

Mais les techniques de cryptographie ont été vaincues au cours de l'histoire par des cryptanalystes. On parle de cryptanalyse, discipline inverse de la cryptographie qui consiste à retrouver les messages sans connaître la clef ou la méthode de chiffrement. Ces deux disciplines réunies composent la cryptologie.


**Nous allons voir comment la cryptographie s'est adaptée à l'évolution des besoins en communication.**


<link rel="stylesheet" href="{{ '/assets/css/timeline.css' | relative_url }}">
<div class="timeline">

 <div class="container left">
  <a href="{{ "/antiquite/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">L'Antiquité et le Moyen-Âge</h2>
     <p>Du V<SUP>ème</SUP> avant notre ère au IX<SUP>ème</SUP> siècle de notre ère</p>
   </div>
  </a>
 </div>

 <div class="container right">
 <a href="{{ "/temps-modernes/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">La Renaissance et les Temps Modernes</h2>
     <p>Du XV<SUP>ème</SUP> au XIX<SUP>ème</SUP> siècle</p>
   </div>
   </a>
 </div>

 <div class="container left">
 <a href="{{ "/guerres/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">Les Guerres Mondiales</h2>
     <p>De 1914 à 1945</p>
   </div>
   </a>
 </div>

 <div class="container right">
 <a href="{{ "/internet/" | relative_url }}">
   <div class="content">
     <h2 style="color:white;">L'ère d'Internet</h2>
     <p>De l'après-guerre à nos jours</p>
   </div>
   </a>
 </div>

</div>

## Conclusion :


## Regardez aussi :
* Notre [Compte-Rendu](experience) de l'expérience !
* Nos [Sources](sources)
* Et notre [Glossaire](glossaire) !

* Notre [Page d'exemple](exemple), pour tester n'importe quoi !


## Travail à faire
* Je vous propose la chose suivante : boutons suivants et précédents en bas et en haut 8 boutons pour faire un menu : Accueil/Antiquité/Renaissance/Guerres/Internet/Bilan-Conclu/Glossaire/Sources !

## Remarques d'un relecteur externe :

### La cryptanalyse du chiffre de Vigenère
  * "la distance entre elles" : peu clair.
  * "En calculant l’indice de coïncidence pour toutes les lettres du message
  modulo la taille de la clef que l’on veut tester" : expliquer bien mieux,
  non compréhensible en l'état !
  * vaut si n suffisamment grand ??

### Le contexte de la seconde Guerre Mondiale : page à relire !!
  * "la conquête de l'Axe" : paragraphe au titre étrange, et à la rédaction à relire !
  * cependant chaque armée avait sa propre clef : phrase en suspens
  * l’efficience du projet Ultra : ce projet n'est pas mentionné au préalable
  * Le graphique bateaux/sous-marins n'indique rien.
  * Le Japon ne participait pas à ce moment à la guerre : à quel moment ??

### Le fonctionnement d'Enigma
  * Calcul du nombre de clefs potentielles avec 3 rotors : Les exposants n'apparaissent pas correctement
  * Il faut absolument dire que le cryptage est symétrique (involutif).
  * Le fonctionnement du tableau de connexion n'est pas expliqué, donc on ne comprend pas les calculs combinatoires qui suivent.
  * *Je pense qu'il faut plus parler de la méthode d'utilisation d'énigma par les allemands, quelle est la clef du jour, quelle est la clef de trois lettres au début de chaque message car c'est très important pour comprendre la cryptanalyse (Samuel)*


### L'ère d'internet
  * Ajouter un paragraphe d'introduction

### Le DES : Un chiffrement symétrique
  * Mentionner brièvement comment déchiffrer un message chiffré avec Lucifer, de façon à justifier l'appellation "chiffrement symétrique"
  * Préciser qui est la NSA (Glossaire ?)

### Le RSA
  * Il manque de la ponctuation un peu partout, et la présentation est un peu chaotique.
  * La démonstration suppose, je crois, que M est premier avec n.
  * puis que l’on chiffre : où est passé le conditionnel
  * "Mathématiquement du, Informatiquement, de" : tournure bizarre
  * Eve peut aisément, sans factoriser n, retrouver le message : comment ?
  * On parle de Kerckoffs ???

### La Cryptographie Quantique
  * ces deux derniers sont polarisés ??
  * ils seront sûrs de la sûreté... à modifier.

### Compte-rendu d'expérience
  * l’étendue de la fréquence est de 6,5 % : cela signifie quoi ?
  * je ne comprends pas la figure 2
  * Cela nécessite de calculer pour le texte ?
  * elles sont en couleur dans le texte ci-dessous : pas chez moi !
  * (surlignées en jaune dans le texte suivant) : pas chez moi...
