# Formattage d'une carte SDXC pour une utilisation de NOOBS

Conformément aux [spécifications SD](https://www.sdcard.org/developers/overview/capacity/), toute carte SD plus grande que 32Go est une carte SDXC et doit être formattée avec le système de fichier exFAT. Ce qui signifie que l'outil officiel de formattage formattera *toujours* une taille de 64Go ou plus.

Le bootloader du Raspberry Pi, construit dans le GPU et non modifiable, ne peut utiliser que le système de fichier FAT (FAT16 et FAT32), et ne peut démarrer depuis un système de fichier exFAT. Donc si vous souhaitez utiliser NOOBS sur une carte ayant 64Go, ou plus, vous devrez la reformatter d'abord en FAT32 avant d'y copier les fichiers NOOB.

## Linux et Mac OS

Les outils standards de formattage disponibles avec ces système d'exploitation sont capables de créer des partitions FAT32; elles seront labellisées FAT ou MS-DOS. Supprimez simplement la partition exFAT puis créez et formattez une nouvelle partition primaire en FAT32, avant de d'exécuter les autres [instructions NOOBS](noobs.md). Sur un Mac, vous utiliserez l'application Disk Utility.

## Windows

Les outils standards disonibles sous Windows sont limités, puisqu'ils ne permettent que des partitions jusqu'à 32Go formattée en FAT32, donc pour formatter une partition de 64GB en FAT32 vous devez utiliser un outil tiers. Un outil simple qui permet cette opération est [FAT32 Format](http://www.ridgecrop.demon.co.uk/guiformat.htm) disponible en téléchargement sous forme d'un simple fichier nommé `guiformat.exe` - aucune installation n'est nécessaire.

Exécutez l'outil [SD Formatter](https://www.sdcard.org/downloads/formatter_4/) une première fois pour vous assurer que tout partition existante sur la carte sera supprimée. Puis lancez l'outil de formattage FAT32 (guiformat.exe), en vérifiant que vous choisissez la bonne lettre d'identification du disque, laissez les autres options à leurs valeurs par défaut, puis appuyez sur "Start". Après avoir terminé, vous pouvez procéder aux autres [instructions NOOBS](noobs.md).

Si l'outil FAT32 Format ne fonctionne pas pour vous, vous pourriez utiliser [MiniTool Partition Wizard Free Edition](http://www.minitool.com/partition-manager/partition-wizard-home.html) et [EaseUS Partition Master Free](http://www.easeus.com/partition-manager/epm-free.html) qui proposent une version "familiale" de leurs outils d'édition de partition, et pas trop difficle à utiliser.
