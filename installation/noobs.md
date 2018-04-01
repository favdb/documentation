# NOOBS

**New Out Of Box Software (NOOBS)** est un installateur de système d'exploitation pour le Raspberry Pi.

![NOOBS OS selection](images/noobs.png)

## Comment obtenir NOOBS

### Acaht d'une carte pré-installée

Les cartes SD avec NOOBS pré-installé sont disponible auprès de nombreux disributeurs et revendeurs indépendants, y compris  [Pimoroni](https://shop.pimoroni.com/products/noobs-8gb-sd-card), [Adafruit](https://www.adafruit.com/products/1583), et [Pi Hut](http://thepihut.com/collections/raspberry-pi-sd-cards-and-adapters/products/noobs-preinstalled-sd-card).

### Téléchargement

Sinon, NOOBS est disponible en téléchargement depuis le site du Raspberry Pi: [raspberrypi.org/downloads](https://www.raspberrypi.org/downloads/)

#### Comment installer NOOBS sur une carte SD

Après avoir téléchargé le fichier zip de NOOBS, vous devez copier le contenu sur une carte SD formattée.

Pour créer une carte SD vide avec NOOBS:

- Formattez une carte SD d'une taille de 8Go en FAT. Voir les instructions ci-après.
- Téléchargez le fichier zip NOOBS et décompressez le.
- Copiez les fichiers extraits sur la carte SD que vous avez formattée, ainsi ce fichier se trouve à la racine de votre carte SD. Notez que dans certains cas les fichiers sont extraits dans un dossier; si c'est votre cas, copiez le fichiers contenus dans ce dossier plutôt que le dossier lui-même.
- AU premier démarrage, la partition "RECOVERY" sera automatiquement retaillée à minima, et une liste des systèmes d'exploitation disponibles sera affichée..

#### Comment formatter une carte SD en FAT

**Note:** Si vous formattez une carte SD (ou micro SD) ayant une capacité de plus de 32Go (comme 64Go et plus), alors voyez les instructions spécifiques au [formattage SDXC](sdxc_formatting.md).

##### Windows

Si vous êtes un utilisateur de Windows, nous vous recommandons de formatter votre carte SD en utilisant SD Association's Formatting Tool, qui peut être téléchargé depuis [sdcard.org](https://www.sdcard.org/downloads/formatter_4/). Les instructions pour utiliser cet outil sont disponible sur ce même site.

##### Mac OS

Le [SD Association's Formatting Tool](https://www.sdcard.org/downloads/formatter_4/) est aussi disponible pour les utilisateurs de Mac, bien que l'utilitaire disque de OS X puisse aussi formatter la totalité du disque. Pour ça, sélectionnez la carte SD et choisissez la fonction `Erase` avec le format `MS-DOS`.

##### Linux

Pour les utilisateurs de Linux nous recommandons d'utiliser `gparted` (ou la version en ligne de commande `parted`). Norman Dunbar a écrit les [instructions](http://qdosmsq.dunbar-it.co.uk/blog/2013/06/noobs-for-raspberry-pi/) pour les utilisateurs Linux.

## Que contient NOOBS

Les systèmes d'exploitation suivants sont inclus dans NOOBS:

- [Raspbian](http://raspbian.org/)
- [Pidora](http://pidora.ca/)
- [LibreELEC](https://libreelec.tv/)
- [OSMC](https://osmc.tv/)
- [RISC OS](https://www.riscosopen.org/wiki/documentation/show/Welcome%20to%20RISC%20OS%20Pi)
- [Arch Linux](http://archlinuxarm.org/platforms/armv6/raspberry-pi)

Depuis la version v1.3.10 (September 2014), seul Raspbian est installé par défaut dans NOOBS. Les autres systèmes peuvent être installés via une connexion réseau.

## NOOBS et NOOBS Lite

NOOBS est disponible sous deux formes: installation hors-ligne et en réseau, ou installation en réseau seulement.

La version complète dispose de Raspbian, aussi il est possible de procéder à l'installation depuis la carte SD sans réseau, alors que NOOBS Lite ou l'installation de tout autre système d'exploitation nécessitera une connexion Internet.

Notes que l'image du système d'exploitation de la version complète peut être périmée si une nouvelle version a été publiée, mais si vous êtes connecté à Internet il vous sera proposé de télécharger la dernière version si elle est disponible.

## Développement de NOOBS

### Dernière version NOOBS

La dernière version de NOOBS est la **v2.7.0**, publiée le **14 Mars 2018**.

(Depuis la version v1.4.0, NOOBS Lite partage les deux premiers nombres du numéro de version, par exemple v1.4)

### Documentation NOOBS

Plusieurs documentation, dont la configuration avancée de NOOBS, sont disponibles sur [GitHub](https://github.com/raspberrypi/noobs/blob/master/README.md).

### Code source de NOOBS

Voir le code source de NOOBS sur [GitHub](https://github.com/raspberrypi/noobs).
