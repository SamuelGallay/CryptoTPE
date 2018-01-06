---
title: "La Cryptographie Quantique"
precedente: /ecc/
permalink: /quantique/
partie: "L'ère d'Internet, et après ?"
---

La *Cryptographie Quantique* que nous allons vous exposer n'est pas a proprement parler une nouvelle forme de cryptographie dans le sens où elle n'offre pas de nouveau protocole de chiffrement. Elle offre en revanche un moyen extrêmement sécurisé de transmettre un message aléatoire et secret entre deux correspondants. On parle de *distribution quantique des clefs.*

Ce protocole de distribution quantique des clefs nécessite un canal de communication quantique, comme une fibre optique, où peuvent circuler des éléments quantiques polarisés, comme des photons.

## Petit rappel sur la polarisation...

<img src="{{ "/assets/4_Internet/polarisation1.png" | relative_url }}" alt="polarisation1" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Schéma d'une onde lumineuse polarisée de manière rectiligne, passant par des filtres polarisants</em> </p>

Il existe plusieurs types de polarisation des ondes, rectiligne, circulaire ou elliptique. C'est la polarisation rectiligne qui nous intéresse.
La lumière peut être polarisée de manière rectiligne selon tous les axes du plan d'onde par des filtres polarisants.

La seule chose à connaitre est que les photons sont certains de passer un filtre polarisant si et seulement si ils sont polarisés dans la même direction. Un photon polarisé "verticalement" (90°) traversera un filtre polarisant "vertical" (90°), mais sera arrêté par un filtre polarisant "horizontal" (0°), car leurs polarisations sont perpendiculaires l'une à l'autre.

### Des polarisations rectilignes ou diagonales

Dans le protocole que nous allons vous présenter, les photons pourrons prendre 4 polarisations différentes : 0°, 90°, 45° et 135°.


<img src="{{ "/assets/4_Internet/polarisation2.png" | relative_url }}" alt="polarisation2" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Les 4 polarisations différentes : 0°, 90°, 45° et 135°</em> </p>

Il est évident qu'un photon polarisé à 45° ne traversera pas un filtre polarisé à 135° puisque ces deux derniers sont polarisés de manière perpendiculaire. Mais qu'en est-il s'il essaye de traverser un filtre polarisé à 0° ou 90° ? La réponse est qu'il a exactement une chance sur deux.

Voici le tableau complet des 16 combinaisons possibles de photons et de filtres.

|Photon\Filtre|0°  | 90°| 45°|135°|
|-------------|----|----|----|----|
| **0°**      | 1  | 0  | 0,5| 0,5|
| **90°**     |  0 | 1  | 0,5|0,5 |
| **45°**     | 0,5| 0,5| 1  |  0 |
| **135°**    |0,5 |0,5 |  0 | 1  |

Dans notre protocole nous utiliserons deux filtres seulement, un filtre  dont la polarisation est rectiligne (0° ou 90°)  et un laissant passer ceux dont la polarisation est diagonale (45° ou 135°).

|Photon\Filtre| 0°     | 45°      |
|-------------|--------|----------|
| **0°**      |  1     | 0,5      |
| **90°**     |  0     | 0,5      |
| **45°**     | 0,5    |  1       |
| **135°**    | 0,5    |  0       |

*1 : le photon passe,\\
0 : il ne passe pas\\
O,5 : il a une chance sur deux*

## Mais à quoi cela nous sert-il ?

Dans la situation soumise à notre étude, il y a deux correspondants. Au hasard Alice veut envoyer des informations secrètes à Bob. Alice et Bob vont aussi avoir besoin d'un canal de transmission traditionnel, pas forcément sécurisé mais authentifié (Alice doit être absolument certaine qu'elle parle à Bob et vice-versa) où ils pourront discuter des modalités de la mise en place de l'échange quantique des clefs.

<img src="{{ "/assets/4_Internet/quantique1.png" | relative_url }}" alt="quantique1" style="margin: 0 auto;display: block;"/>
<p align="center"> <em>Schéma illustrant la situation étudiée</em> </p>

La clef qu'ils vont se transmettre va être composée de nombres binaires, des 0 et des 1. Ils vont se dire que les photons polarisés à 0° ou 45° représentent des 0 tandis que ceux polarisés à 90° ou 135° représentent des 1. Alice va envoyer sur le canal quantique des photons polarisés aléatoirement dans chacune des 4 polarisations proposées.

Connaitre la polarisation d'un photon est impossible. La seule chose que Bob peut faire est de placer au hasard un de ses 2 filtres (rectiligne ou diagonal) et détecter si le photon est passé ou non. Si Bob a choisi le "bon" filtre, diagonal si c'était la polarisation initiale du photon ou rectiligne si cette dernière l'était, alors la mesure de Bob sera certaine et il connaitra la polarisation initiale du photon. Si Bob a choisi le "mauvais" filtre, alors il possède autant de chance d'obtenir un 0 ou un 1, aléatoirement et indépendamment de la polarisation initiale du photon.

On voit que une mesure de Bob sur deux est inutile, il faut donc les éliminer. C'est pour cela que Bob va envoyer a Alice quel filtre il a utilisé pour chaque photon, sur un canal clair. Et Alice va lui répondre pour chaque photon si Bob a utilisé le "bon" ou le "mauvais" filtre. Ils vont ensemble ignorer et oublier chacun des photons pour lesquels Bob a choisi le "mauvais" filtre.

Alice et Bob sont donc chacun en possession d'une série de nombres binaires identiques.

## Pourquoi ce chiffrement est il sûr ?
