# Cartes SD

Le Raspberry Pi peut fonctionner avec toute carte SD compatible, toutefois les quelques recommandations suivantes doivent être observées:

## Taille de carte SD (capacité). 

Pour l'installation d'une image NOOBS ou d'une image de Raspbian, la taille minimum recommandée est 8Go. Pour une image Raspbian Lite nous recommandons un minimum de 4Go. Plusieurs distributions, spécialement LibreELEC et Arch, peuvent fonctionner avec des cartes d'une taille inférieure. Si vous projetez d'utiliser une carte de 4Go ou plus avec NOOBS voyez d'abord [cette page](sdxc_formatting.md).

## Classe de carte SD. 

La classe d'une carte détermine sa vitesse moyenne d'écriture; une cate de classe 4 sera capable d'écrire à une vitesse de 4Mo/s, alors qu'une classe 10 serait capable d'atteindre 10Mo/s. De toute manière, vous devriez noter que vous ne pouvez attendre les même performance du classe 10 et d'une classe 4 pour un usage général, en effet cette vitesse d'écriture atteinte a un impacte sur la vitesse de lecture et sur le temps de recherche.

## Taille physique de carte SD. 

Le modèle orignal des Raspberry Pi Model A et Raspberry Pi Model B rnécessite une carte SD de dimension full-size. Les nouveaux [Raspberry Pi Model A+](https://www.raspberrypi.org/products/raspberry-pi-1-model/), [Raspberry Pi Model B+](https://www.raspberrypi.org/products/raspberry-pi-1-model-b/), [Raspberry Pi 2 Model B](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/), [Raspberry Pi Zero](https://www.raspberrypi.org/products/raspberry-pi-zero/), et [Raspberry Pi 3 Model B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/) nécessite une carte au format micro SD.

## Dysfonctionnement

Nous recommandons d'acheter une carte SD pour Raspberry Pi disponible [ici](https://shop.pimoroni.com/products/noobs-8gb-sd-card), mais aussi chez d'autres revendeurs; c'est une carte de classe 6 au format micro SD d'une capacité de 8Go (avec un adaptateur full-size) qui a les mêmes performances que d'autres cartes SD du marché et qui est une solution valable.

Si vous rencontrez de corruption de vos cartes SD, assurez-vous de respecter ces étapes:

1. Assurez-vous d'utiliser une carte SD de marque. Beaucoup de cartes disponibles sur le marché nsont en réalité plus petites que la capacité annoncée ou ne durent pas très longtemps.
2. Assurez-vous d'utiliser une alimentation de bonne qualité. Vous pouvez contrôler cette alimentation avec un contrôleur de tension, elle doit fournir une tension située entre TP1 et TP2 sur le Raspberry Pi; si celle-ci chutte en dessous de 4.75V quand vous effectuez une tâche complexe alors c'est que vous rencontrerez des problèmes.
3. Assurez-vous de la qualité du cable USB utilisé pour l'alimentation. Si vous utilisez une alimentation de mauvaise qualité la tension TP1->TP2 peut descendre sous les 4.75V. Ceci est généralement le résultat de la résistance de cable; pour économiser de l'argent, les cables USB ont une section la plus petite possible et ainsi provoquer une perte de 1V (ou 1W) selon la longueur.
4. Assurez-vous d'arrêter correctement votre Raspberry Pi avant de débrancher l'alimentation. Exécutez la commande `sudo halt` et attendez que le Pi signale qu'il est prêt à être débranché en faisant clignoter la LED d'activité.
5. Enfin, des corruptions ont été observées dans le cas de l'overclocking le Pi. Ce problème a été réglé précédemment, mais la solution utilisée peut se révéler inefficace. Si après vérification de ces étapes vous rencontrez toujours des problèmes de coruption faites le nous savoir.
