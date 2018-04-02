# Installation d'images de système d'exploitation sous Linux

[Etcher](README.md) est typiquement l'option la plus facile pour la plupart des utilisateurs pour écrire des images sur cartes SD, aussi voici le meilleur endroit pour commencer. Si vous cherchez des options avancées sous Linux, vous pouvez utiliser la ligne de commande comme suit.

**Note**: l'utilisation de l'outil `dd` peut écraser toute partition de votre machine. Si vous indiquez le mauvais périphérique dans les instructions qui suivent vous pourriez supprimer votre partition primaire contenant Linux. Soyez vigilent.

### Découverte du point de montage de la carte SD et son démontage
- Exécutez la commande `lsblk` pour voir quels sont les matériels actuellement connectés à votre machine.

- Si votre ordinateur dispose d'un lecteur de carte SD, insérez une carte. Sinon, insérerez une carte dans un lecteure externe et connectez le à votre ordinateur.

- Exécutez à nouveau la commande `lsblk`. Le nouveau périphérique qui apparaît est votre carte SD (vous pouvez aussi utiliser `tell` depuis la liste des périphérique). Le nom du matériel suit le format décrit dans le paragraphe suivant.

- La colonne de gauche de la liste restituée par la commande `lsblk` donne le nom de votre périphérique lecteur de carte SD, ainsi que le nom de toutes les partitions reconnues (habituellement il n'y en a qu'une, mais il paut aussi y en avoir plusieurs si la carte a déjà été utilisée). Ce sera listé sous la forme `/dev/mmcblk0` ou `/dev/sdX` (avec les noms de partition associées comme `/dev/mmcblk0p1` ou `/dev/sdX1`), où `X` est une lettre en minuscule indiquant le périphérique (par exemple `/dev/sdb1`). La colonne de droite indique la localisation du point de montage dans le système (un espace vide indique que le périphérique n'est pas monté).

- Si une partition de la carte SD est monté procédez à son démontage avec la commande `umount`, par exemple `umount /dev/sdX1` (remplacez `sdX1` par le nom de périphérique de votre carte SD, et changez le numéro de la partition en fonction des besoins). Répétez cette opération pour chaque partition de votre carte SD qui est montée.

### Copier l'image sur la carte SD

- Dans un terminal, écrivez l'image sur la carte avec la commde suivante, tout en vous assurant de bien remplacer l'argument `if=` du fichier d'entrée par votre fichier `.img`, et l'argument `of=` du fichier de sortie `/dev/sdX` par le nom de périphérique correcte. **Très important, vous pourriez perdre des données si vous commetez une erreur d'identification du périphérique.** Assurez-vous que le nom de périphérique est bien celui de la carte SD tel décrit précédemment. Par exemple: `sdd`, et pas `sdds1` ou `sddp1`; `mmcblk0`, et pas `mmcblk0p1`.

    ```bash
    dd bs=4M if=2018-03-13-raspbian-stretch.img of=/dev/sdX conv=fsync
    ```

- S'il vous plait, notez que la taille de bloc, qui est paramétrée à `4M`, fonctionnera dans la plupart des cas. Sinon, essayez  `1M`, mais dans ce cas le temps de traitement sera bien plus long.

- Notez aussi qui si vous n'êtes pas connecté en tant que root vous devrez préfixer votre commande par `sudo`.

### Copier une image décompressée sur la carte SD

Avec Linux il est possible de combiner la décompression avec le processus de copie SD en une seule commande, ce qui peut être très utile si l'image fait plus de 4Go (en FAT), notez aussi qu'une installation Linux n'utilise pas FAT et n'a donc pas cette  limitation.

La commande suivante décompresse le fichier zip (remplacez 2018-03-13-raspbian-stretch.zip par le nom approprié de votre fichier zip), et transmet directement le résultat à la commande dd. Ceci correspond à la copie sur carte SD comme décrit précédemment.
```
unzip -p 2018-03-13-raspbian-stretch.zip | sudo dd of=/dev/sdX bs=4M conv=fsync
```

### Vérification de la progression de la copie de l'image

- Par défaut, la commande `dd` ne donne pas d'indication sur le déroulement du processus, ainsi il peut vous sembler qu'il ne se passe rien. L'écriture sur la carte peut prendre plus de cinq minutes. Si votre lecteur de carte dispose d'une LED vous pourrez visualiser l'exécution du processus. 

- Pour voir le processus, vous pouvez exécuter la commande dd avec l'option de status.
   ```
    dd bs=4M if=2018-03-13-raspbian-stretch.img of=/dev/sdX status=progress conv=fsync
   ```
- Si vous disposez d'une ancienne version de `dd`, l'option status n'est pas disponible. À la place vous pouvez utiliser la commande `dcfldd`, qui vous vous indiquera le nombre d'octets écrit. Une autre méthode est d'envoyer un signal USR1 vers `dd`, ce qui provequera l'affichage de l'information status. Recherchez le PID de `dd` en utilisant la commande `pgrep -l dd` ou `ps a | grep dd`. Puis utilisez `kill -USR1 PID` pour envoyer le signal USR1 vers `dd`.

### Verification si la copie de l'image sur la carte SD s'est correctement déroulée

- À la fin de l'exécution de `dd`, vous pouvez vérifier ce qui a été écrit sur la carte SD en exécutant un `dd` inverse vers un autre fichier d'image; puis de tronquer la taille de cette image à la taille exacte de l'image d'origine; et, enfin, en exécutant un `diff` (ou `md5sum`) sur les deux images.

- Si la carte SD est plus grande que la taille originale de l'image, `dd` fera une copie de l'ensemble de la carte. Remplacez l'argument du fichier d'entrée `if=` par le périphérique correct. `diff` devrait indiquer que les fichiers sont identiques.

    ```bash
    dd bs=4M if=/dev/sdX of=from-sd-card.img
    truncate --reference 2018-03-13-raspbian-stretch.img from-sd-card.img
    diff -s from-sd-card.img 2018-03-13-raspbian-stretch.img
    ```

- Exécutez `sync`. Cecie assurera que le cache d'écriture est vidé avant de retirer la carte SD.

- Retirez la carte SD du lecteur de carte.
