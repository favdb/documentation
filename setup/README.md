# Setup

A guide to setting up your Raspberry Pi

## De quoi avez-vous besoin

### L'Essentiel (pour un usage général)

- [Carte SD](../installation/sd-cards.md)
    - Il est recommandé d'utiliser une crte SD de 8Go classe 4, idéalement présintallée avec [NOOBS](../installation/noobs.md).
- [Affichage](monitor-connection.md)
    - Tout moniteur HDMI/DVI et n'importe quelle TV fonctionnera pour l'affichage. Pour de meilleurs résultats utilisez la solution HDMI, mais d'autres connexions sont possibles pour d'anciens matériels.
- Clavier et souris
    - Tout clavier ou souris USB fera l'affaire.
    - Les claviers, ou souris, sans fil fonctionneront aussi à condition d'être appairés.
    - Pour la configuration de la disposition du clavier voir [raspi-config](../configuration/raspi-config.md).
- [Alimentation électrique](../hardware/raspberrypi/power/README.md)
    - Le Pi est alimenté au moyen d'une prise Micro USB (comme pour la plupart des chargeurs de mobiles).
    - Vous aurez besoin d'une alimentation de bonne qualité fournissan au moins 2A sous 5V pour le modèle 3B, ou 700mA sous 5V pour les modèles plus récents.
    - Une alimentation de faible puissance (~700mA) sera suffisante pour un usage basique, mais ça risque de provoquer un reboot du PI si une puissance supplémentaire est demandée.

### Options

- Cable Ethernet (réseau) [Modèles B/B+/2/3 seulement]
    - Le cable Ethernet est utilisé pour connecter votre Pi à votre réseau local et à Internet.
- [Dongle USB sans fil](../configuration/wireless/README.md)
    - Vous pouvez aussi vous connecter à un réseau sans fil en utilisant un dongle USB, ce qui nécessitera une configuration spéciale.
- Audio
    - L'audio peut sortir via des haut-parleurs ou des écouteurs en utilisant une prise Jack standard 3.5mm.
    - Sans cable HDMI, un système audio externe sera nécessaire pour le son.
    - Toutefois vous n'avez pas besoin d'un système audio externe si vous utilisez le HDMI pour une connection à un moniteur équipé de haut-parleurs, puisque l'audio peut être restitué par celui-ci; mais il reste possible de connecter un système externe si vous le souhaitez - ça nécessitera une [configuration](../configuration/audio-config.md) spéciale.

## Difficultés

Pour tout problème de paramétrage cherchez la solution sur [les forums](https://www.raspberrypi.org/forums/). Si vous ne trouvez pas la réponse, postez votre problème en fournissant un maximum de détails.
