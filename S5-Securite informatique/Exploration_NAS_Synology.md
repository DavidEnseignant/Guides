# Atelier d'exploration - NAS (Network Area Storage)

## À quoi ça sert ?

Un NAS (Network Attached Storage) est un dispositif de stockage connecté à un réseau permettant de centraliser les données et les fichiers. Il permet à plusieurs utilisateurs et appareils d'accéder aux mêmes fichiers à partir d'un emplacement commun. Il peut servir à sauvegarder automatiquement les données, partager des documents et conserver des fichiers multimédias. Certains NAS offrent également des fonctionnalités supplémentaires comme l'hébergement de serveurs, la synchronisation de fichiers et l'accès à distance. En résumé, il constitue un espace de stockage centralisé, accessible et partageable sur un réseau. (IA)

## Configuration de l'environnement de base (TP-LINK ER605 + DS120j)

### Routeur (TP-LINK ER605)

- Brancher le routeur. Au besoin, utiliser la barre d'alimentation. Connectez-le ensuite au réseau du cégep dans le port WAN.
- Réinitialiser le routeur à sa configuration d'usine en utilisant la procédure suivante :
    - Attendre que le routeur soit complètement démarré. La lumière "SYS" clignote lentement lorsque c'est le cas.
    - Utiliser le trombone pour maintenir enfoncé le bouton "reset" pendant quelques secondes, la lumière "SYS" devrait se mettre à clignoter rapidement par la suite.
    - Par défaut, votre routeur devrait prendre l'adresse 192.168.0.1. Connectez-vous à cette adresse pour poursuivre la configuration.
    - Vous devrez définir des identifiants lors de votre première connexion à l'appareil.
- Configuration du routeur :
    - Par défaut le routeur se comporte comme un routeur et contient un serveur DHCP.
    - À l'exception de l'activité 4, qui requiert un réseau interne pour tester le VPN, il est plus pratique de configurer le routeur pour qu'il fonctionne comme un commutateur (switch).
    - Désactiver le serveur DHCP du routeur et le redémarrer.
    - Déplacer votre connexion vers le réseau du cégep du port WAN vers un des ports LAN. Vous obtiendrez maintenant vos adresses IP du DHCP du cégep.


### NAS (DS120j)

- Réinitialiser le NAS à sa configuration d'usine avec la procédure suivante :
    - Démarrer le NAS et attendre que la lumière "STATUS" ne clignote plus, cela indique que la séquence de démarrage est terminée.
    - Utiliser un petit objet pointu (Ex. Trombone) pour appuyer sur le bouton de réinitialisation derrière l'appareil.
        - Maintenir le bouton +/- 4 secondes jusqu'à un premier "beep". Relâcher le bouton. Appuyez de nouveau et maintenir +/- 4 secondes jusqu'à ce que trois "beep" se fassent entendre. Relâcher le bouton.
    - Attendre 3-4 minutes. Puis utiliser : [Trouver mon appareil Synology](https://finds.synology.com/)
        - Comparer les adresses MAC des appareils listés avec celui de votre NAS afin de trouver votre appareil dans la liste. Connectez-vous et faites la réinstallation de la dernière version de DSM.
- Configurer l'adresse IP de votre NAS afin de lui donner une adresse statique. Voir liste fournie par l'enseignant.

## Activité 1 - Sauvegardes

- Dans le centre de paquets, trouver "Hyper Backup" et "Hyper Backup Vault". Recherche de la documentation afin de comprendre le rôle de chacun.
- Faire l'installation et la configuration des deux paquets.
- Configurer une sauvegarde sur le NAS d'une autre équipe.
- Permettre à une autre équipe de sauvegarder sur votre NAS

> [!NOTE]
> Vous risquez de devoir explorer la gestion des utilisateurs et des partages pour réaliser cette activité.

## Activité 2 - Partages de fichier et synchronisation

Bien qu'il soit possible de simplement créer un dossier partagé et d'en faire un lecteur réseau sur un poste client, il pourrait être intéressant d'avoir accès à des fonctionnalités plus avancées.

- Dans le centre de paquets, trouver "Synology Drive Server". Recherche de la documentation afin de comprendre son fonctionnement.
- Faire l'installation et la configuration du paquet.
- Tester le fonctionnement à l'aide d'une des applications cliente "Synology Drive Client".

## Activité 3 - Surveillance physique

- Dans le centre de paquets, trouver "Surveillance Station". Recherche de la documentation afin de comprendre son fonctionnement.
- Faire l'installation et la configuration du paquet.
- Faire la configuration de la caméra IP fournie avec la trousse. Vous aurez besoin de l'injecteur PoE pour l'alimenter.

## Activité 4 - VPN (Avancée)

Faire la configuration d'un accès VPN basé OpenVPN. Voici quelques indices pour y arriver.

- Vous devez changer la configuration de votre routeur et le remettre en mode "routeur" afin de produire un réseau interne dans le 192.168.0.0/24.
- Donnez à votre NAS une adresse IP fixe dans cette plage et assurez-vous qu'il est connecté à votre routeur.
- Faire la configuration du paquet "VPN Server" et tester la connexion à l'aide d'un client VPN au choix supportant OpenVPN.

> [!NOTE]
> Vous devez configurer le "Port Forwarding" ou "Port Triggering" du port approprié dans votre routeur vers votre NAS afin que les connexions VPN soient puissent être traitées par celui-ci.

## Activité 5 - Exploration libre

- Explorer. Il y a des paquets en lien avec l'administration de systèmes, le multimédia, versionnement Git... même un wiki.
- Installer et tester !