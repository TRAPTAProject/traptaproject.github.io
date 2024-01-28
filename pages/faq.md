# FAQ


## Application Android
Problème courrant de l'application Android :

### **Symptôme** : TRAPTA app v1.32 affiche de la somme des volées de 3 flèches sur 2 chiffres.

  **Explication** : La version 1.32 de l'application Android Trapta a un bug d'affichage avec les écrans à faible résolution.

  **Solution** : mettre à jour avec la version **app v1.33** téléchargeable sur [GitHub](https://github.com/TRAPTAProject/trapta-app/releases) ou sur [Google Play](https://play.google.com/store/apps/details?id=com.trapta.app)


### **Symptôme** : Un smartphone ne parvient pas à reconnaître le Wifi du routeur TRAPTA.

  **Explication** : Le téléphone tente d'utiliser la connexion de data au lieu du wifi comme réseau principal.

  **Solution** : désactiver l’option **Données mobiles** des smartphones qui enregistrent les scores en cible.


## Trapta-Score

### **Symptôme** :  Trapta-score  ne liste pas les marques en direct.

  **Explication** : La version hitorique de trapta-score et trapta-score-Simple ne gère pas le HTTPS.

  **Solution** : Passer à une nouvelle version de trapta-score (a partir de 2024) ou corriger à la main les fichiers sources de trapta-score 
  
  Remplacer (**http**)
  ```<script src="http://code.jquery.com/jquery-1.11.0.min.js"></script>```
  par (**https**)
  ```<script src="https://code.jquery.com/jquery-1.11.0.min.js"></script>```
  dans le fichier index.php.

### **Symptôme** : Hébergement web incompatible.

  **Explication** : La version de PHP ou l'utilisation de HTTPS peut entrainer une incompatibilité avec certain hébergeurs

  **Solution** : 
    * Les tests ont été menés avec succès sur tout hébergement OVH mutualisé payant fonctionnant avec PHP 7.4 avec TLS
    * Sportsregions: Il n’est pas possible d’intégrer Trapta sur un site Sportsregions
    * free.fr gratuit :  en erreur :

        ```
        Call to undefined function: json_decode() in /mnt/111/sda/5/0/moncompte.free.fr/updatepositions.php

        La fonction json_decode est compatible à partir de PHP 5.2, 7, 8

        https://www.php.net/manual/en/function.json-decode.php
        ```



## Trapta Cloud

### **Symptôme** : TRAPTA Cloud ne se connecte pas.

  **Explication** : Mauvaise configuration ou ordre de lancement de TRAPTA Cloud

  **Solution** : Il faut d'abord lancer TRAPTA (server) sur l'ordinateur du greffe, puis TRAPTA Cloud en indiquant l'url du site web avec http:// et non https://.

  Le site web affiche le départ avec les positions des archers ou les scores d'un départ, avec les départs précédents et les calculs de score d'équipe selon les options choisies dans l'application TRAPTA .


## Trapta Serveurs

### **Symptôme** : TRAPTA Server (ou trapta Transfert) ne parvient pas à lire la liste des archers de Result’Arc

  **Explication** : Mauvaise configuration ou ordre de lancement de TRAPTA Cloud

  **Solution** : installer **Result’Arc 8.0** dans un répertoire sans les sauvegardes des concours au format 7.0 et antérieur; anticiper cette installation séparée dès le début des inscriptions du concours.

  >  **Recommandation**: installer chaque nouvelle version de ResultArc dans un nouveau répertoire; par exemple pour la version ResultArc 9:
``c:\resultarc9``
  Saisir les compétiteurs avec ``c:\resultarc9\ffta.exe`` puis, avant chaque départ, lister les archers pour le transfert vers TRAPTA serveur dans ``c:\resultarc9``

### **Symptôme** : TRAPTA Server (ou trapta Transfert) ne se lance pas car msvcp140.dll est manquant

  **Explication** : les fichiers DLL redistribuables de Visual Studio ne sont pas installés

  **Solution** : télécharger et exécutez la mise à jour Microsoft 32 bits: https://aka.ms/vs/17/release/vc_redist.x86.exe
  
les infomations sur les dll manquants sont disponibles sur:
https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170

## Matériel

### **Symptôme** : La connexion WIFI entre greffe et smartphone est mauvaise.

  **Explication** : Le signal peut être perturbé, ou le routeur wifi peut être surchargé par un trop gros nombre d'appareil.

  **Solution** : 
  * La couverture WIFI dans un gymnase comportant une quinzaine de cibles peut très bien fonctionner bien avec un routeur de faible puissance comme le robuste Linksys WRT54GL une box Internet (freebox...).
  * Sur un terrain extérieur pour l'organisation de concours à plus de 30 à 40 cibles sur les distances dépassant 100m, une configuration Wifi supportant un grand nombre de connexions à longue distance est requise.
    La configuration recommandée comprend
    * Un switch avec branchement POE (alimentation par câble Ethernet)
    * Une antenne wifi de type Ubiquity
    * Eventuellement, un long câble Ethernet (50m) pour relier le switch entre l'ordinateur du greffe sous les tribunes d'un stade à l'antenne wifi placée à l'extérieur en hauteur sur les gradins

    Exemple de configuration https://cd31arc.fr/tir/trapta/#Materiel
