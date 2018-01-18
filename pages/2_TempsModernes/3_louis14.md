---
title: Le grand chiffre de Louis XIV
permalink: /louis14/
precedente: /vigenere/
suivante: /cryptanalyse-vigenere/
partie: Les temps Modernes
menu: /temps-modernes/
---
## Eléments de contexte

Dans un contexte de ravivement des guerres de religion après la mort prématurée d’Henri IV dont le règne avait permis d’apaiser les tensions entre catholiques et protestants, le Cardinal de Richelieu, premier ministre de Louis XIII, traque activement les huguenots. Il assiège la Rochelle, bastion huguenot, pendant plusieurs mois, en vain. Ayant intercepté un message à déchiffrer et ayant entendu parler par une lettre du prince de Condé des talents d’un décrypteur, Antoine Rossignol, qui avait assuré à Condé la prise de la ville de Réalmont (1626) en déchiffrant un message, il demande au jeune homme de déchiffrer le message. Rossignol y parvient : il rentre ainsi au service du Chiffre de la Couronne et devient le cryptologue le plus réputé de son temps. Il sert la diplomatie de Louis XIII, puis de Louis XIV pendant cinquante ans. Signe de son rang, son bureau est contigu à celui du Roi-Soleil. Son rôle est de décrypter les messages ([cryptanalyse]({{ "/glossaire/" | relative_url }})) et d’améliorer les principes cryptographiques existants.

<img src="{{ "/assets/2_TempsModernes/rochelle.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block; width:400px; "/>
<p align="center"> <em> Richelieu au siège de la Rochelle, Henri-Paul Motte, 1881 </em> </p>

Son oeuvre majeure est l’invention, avec son fils Bonaventure, d’un code inviolable, le “grand chiffre”. Utilisé pour les affaires du royaume comme pour la correspondance secrète du Roi, ce code tient en échec toutes les tentatives de déchiffrement ennemies et des cryptanalystes modernes car après la mort du petit-fils d’Antoine Rossignol (il y avait bien une lignée de cryptologues), la clef a été perdue. Ce n’est que dans les années 1890 qu’Etienne Bazeries, militaire français, parvient à déchiffrer le fameux Chiffre et la correspondance de Louis XIV est enfin dévoilée. Il réalisa pour cela une [attaque par mot probable]({{ "/glossaire/" | relative_url }}) en supposant que la séquence 124-22-125-46-345 correspondaient aux syllabes les-en-ne-mi-s, s étant codé seul par 345. Peu à peu, il en déduisit les autres syllabes jusqu'à déterminer l'intégralité du répertoire et ainsi permettre aux historiens d'avoir accès à la correspondance du Roi, et de s'intéresser à l'énigme de l'homme au masque de fer.

<img src="{{ "/assets/2_TempsModernes/rossignol.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block; width:300px; "/>
<p align="center"> <em> Antoine Rossignol </em> </p>

## Fonctionnement

Ce système est un codage par répertoire désordonné : chaque nombre correspond à une syllabe ou parfois à une lettre. Ainsi 124 signifiait “les”, 22 “en”, 345 “s”. Le nombre 57 signifie même qu’il faut effacer le précédent. Les correspondants doivent chacun posséder un exemplaire du répertoire permettant de chiffrer et déchiffrer les messages.

<img src="{{ "/assets/2_TempsModernes/grand-chiffre.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block; width:400px; "/>
<p align="center"> <em> Répertoire du grand chiffre de Louis XIV </em> </p>

## Enjeux

Ce chiffre a été utilisé par Louis XIV tant pour ses correspondances privées (il a mené une vie amoureuse très dissolue comme chacun le sait) que pour ses correspondances politiques avec ses ministres, militaires et ambassadeurs.

<img src="{{ "/assets/2_TempsModernes/rigaud.jpg" | relative_url }}" alt="diffie" style="margin: 0 auto;display: block; width:300px; "/>
<p align="center"> <em> Louis XIV en costume de sacre par Hyacinthe Rigaud, 1701 </em> </p>

Le Roi-Soleil conduit une politique étrangère très ambitieuse, et passe la majeure partie de son règne en phase de guerre (guerre de Dévolution, guerre de Hollande, guerre de succession d’Espagne). Pour préserver son pré carré, il dirige une politique militaire belliqueuse. Il est donc crucial pour lui de s’assurer que les autres puissances européennes qui se sont liguées contre lui n'interceptent pas ses missives à caractère tactique.

La cryptologie prend avec Rossignol en France une importance inédite, puisque Louvois, ministre de la guerre de Louis XIV, crée un bureau spécialisé. À la fin du XVIIe et au cours du XVIIIe siècle, les cabinets noirs sévissent dans toute l’Europe. Celui de Vienne, le Geheime Kabinetskanzlei, est le plus efficace : en moins de deux heures, tout le contenu du sac postal est ouvert, recopié, et recacheté. Cela permet à l’Autriche-Hongrie de mener une politique étrangère très efficiente. L’invention du télégraphe et donc l'augmentation spectaculaire de la quantité de messages échangés sonne la fin des cabinets noirs au milieu du XIXe siècle.
