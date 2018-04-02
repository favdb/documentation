# Installation d'images de système d'exploitation en utilisant Windows

[Etcher](https://etcher.io/) est le moyen le plus simple pour la plupart des utilisateurs pour créer des images sur des cartes SD, mais voici une alternative sous Windows, vous pouvez utiliser `Win32DiskImager`:

## Win32DiskImager

- Insérez la carte SD dans votre lecteur. Vous pouvez utilisez le lecteur intégré, si vous en avez un, ou un lecteur externe brancheé sur une prise USB. Vérifiez la lettre assigné à la carte. Vous pouvez voir cette lettre dans la colonne de gauche de l'explorateur de fichier, par exemple **G:**
- Téléchargez l'utilitaire Win32DiskImager depuis [la page du projet sur Sourceforge](http://sourceforge.net/projects/win32diskimager/), et procédez à l'installation.
- Exécutez l'utilitaire `Win32DiskImager` depuis le menu.
- Selectionnez le fichier contenant l'image que vous avez extrait précédemment.
- Dans la fenêtre de périphérique sélectionnez la lettre affectée à la carte SD. Soyez attentif à bien sélectionner le bon périphérique; si vous vous trompez vous pourriez détruire les données de votre ordinateur! Si vous utilisez un lecteur intégré, et que vous ne pouvez pas voir sa lettre d'identification essayez un lecteur externe.
- Cliquez sur 'Write' et attendez que l'écriture se termine.
- Quittez le logiciel et éjectez la carte SD.

---

*Cet article utilise le contenu da la page wiki [RPi_Easy_SD_Card_Setup](http://elinux.org/RPi_Easy_SD_Card_Setup), qui est placée sous la licence [Creative Commons Attribution-ShareAlike 3.0 Unported license](http://creativecommons.org/licenses/by-sa/3.0/)*
