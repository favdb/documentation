# Installation d'images de système d'exploitation

Voici comment installer un système d'exploitation pour le Raspberry Pi sur une carte SD. Vous aurez besoin d'un autre ordinateur avec un lecteur de carte SD pour installer l'image.

Nous recommandons à la plupart des utilisateurs de télécharher [NOOBS](../noobs.md), qui est spécialement conçu pour être simple à utiliser. De toute façon, pour les utilisateurs avancés, il sera intéressant de lire ceci pour installer une image particulière.

## Télécharger l'image

Les images officielles pour les systèmes d'exploitation recommandés sont disponibles en téléchargement depuis le site Raspberry Pi, voir la [page de téléchargement](https://www.raspberrypi.org/downloads/).

Des distributions alternatives sont mis à disposition par d'autres revendeurs.

Si vous n'utiliseez pas Etcher (voir plus loin), vous aurez besoin de décompresser les fichiers `.zip` téléchargés pour récupérer un fichier image (`.img`) à écrire sur votre carte SD.

**Note**: l'image Raspbian avec PIXEL contient une archive ZIP de 4Go et utilise le format [ZIP64](https://en.wikipedia.org/wiki/Zip_(file_format)#ZIP64). Pour décompresser l'archive, un outil de décompression supportant le ZIP64 est nécessaire. Les outils suivants supportent le ZIP64:

- [7-Zip](http://www.7-zip.org/) (Windows)
- [The Unarchiver](http://unarchiver.c3.cx/unarchiver) (Mac)
- [Unzip](http://www.info-zip.org/mans/unzip.html) (Linux)

## Ecrire une image sur la carte SD

Vous devrez utiliser un outil d'écriture pour installer une image, que vous avez téléchargé, sur votre carte SD.

**Etcher** est un outil graphique pour carte SD qui fonctionne sous Mac OS, Linux et Windows, il est simple et facile à mettre en oeuvre pour la plupart des utilisateurs. Etcher supporte aussi l'écriture directe des images depuis le fichier zip, sans décompression préalable. Pour écrire votre image avec Etcher:

- Téléchargez [Etcher](https://etcher.io/) et installez le.
- Connectez un lecteur de carte SD, et insérez votre carte.
- Ouvrez Etcher et sélectionnez le fichier image du Raspberry Pi (`.img` ou `.zip`) que vous souhaitez écrire sur la carte SD.
- Selectionnez la carte SD sur laquelle écrire l'image.
- Vérifiez vos sélections et appuyez sur 'Flash!' pour commencer l'écriture des données sur la carte SD.

Pour le contrôle avancé du processus, reportez-vous à notre guide spécifique à votre système:

- [Linux](linux.md)
- [Mac OS](mac.md)
- [Windows](windows.md)
