---
layout: default
title: Freebox OS (Freebox_OS)
lang: fr_FR
pluginId: Freebox_OS
---

# Stable

## xx/08/2020

> Il est nécessaire de refaire l'appairage de la Freebox avec le nouveau menu

- Amélioration des messages d'erreurs (en cas d'erreur, un message est indiqué dans le centre des messages)
- Suppression des widgets ne servants plus
- Correction des bugs sur la commande rafraîchir sur certains équipements
- **Appairage**
  - Mise en place d'une modale pour faciliter l'appairage
    > Le menu se trouve maintenant dans l'interface du plugin
  - Modification des réglages par défauts, (masquages des paramètres non nécessaires)
  - Ajout d'une fonction pour contrôler les droits, si NOK il n'est pas possible de continuer (Droits obligatoires en gras)
  - Pour la Freebox Delta : Il est possible de lier les pièces de la Freebox avec les objects de Jeedom
  - Possibilité de lancer des divers équipements en fin d'authentification
- **Téléphone**
  - Suppression de l'ensemble des commandes obsolètes
    > Les commandes seront supprimées lors de la mise à jour du plugin
  - Suppression des widgets
  - Résolution du retour à la ligne sur l'affichage des listes d'appels
- **Appareils connectés**
  - Résolution de la non-suppression des appareils non présents dans la Freebox
  - Ajout cron Jour pour rechercher les nouveaux appareils.
- **Disque Dur**
  - Suppression widget, utilisation widget core par défaut
- **Wifi**
  - Suppression de commande Activer/Désactiver du Wifi
    > il faut utiliser les commandes ON et OFF pour gérer le wifi
- **Caméra**
  - Amélioration des réglages de la Caméra
    > il faut supprimer l'équipement pour avoir les nouveaux réglages
  - Suppression du message d'installation de la caméra, si celle-ci est détecté
- **Tiles**
  - Correction d’un problème sur la recherche
- **Equipements standards**
  - Correction d’un problème sur la recherche
- **Freebox débits**
  - Ajout info de l’IPV4 et IPV6
    > Il faut refaire une recherche des équipements standards pour avoir cette info

## 06/08/2020

> Suite à la mise à jour de la Freebox en 4.2.3

- Correction IP Freebox

## 29/07/2020

> Il est nécessaire d'avoir la Freebox en version 4.2 pour que le plugin fonctionne

- Réécriture de la partie création des équipements standards
- **Contrôle Parental**
  - Possibilité de bloquer ou de débloquer pendant un temps sélectionné
    > Pour pourvoir bénéficier de ces nouveautés, il faudra supprimer les équipements "Contrôle parental" et refaire une recherche
- **Ensemble des Tiles**
  - Correction des commandes des volets de type slider
- **Téléchargement**
  - Correction du nombre de download, la valeur était toujours vide
- **Disque**
  - Amélioration du nom lors de la création de l'équipement
  - Correction du non retour de la capacité du disque
- **Ensemble des équipements**
  - Affectation des Temps de rafraichissement (cron) différents suivant le type d'équipement.
    > Cela s'appliquera uniquement pour les nouveaux équipements

## 24/07/2020

> Attention cette version nécessite d'avoir au minimum la version 4.2 sur la Freebox
> Il faudra aussi mettre à jour les droits dans la console de la Freebox
> Attention : La commande Activer/Désactiver du Wifi sera supprimée lors des prochaines mises à jour, il faudra utiliser les commandes ON et OFF pour gérer le wifi

- Nettoyage Création des commandes
- Ajout icône pour les batteries
- Migration de l'ensemble des API vers V8
- Réécriture de la partie update et refresh
- Création class Template et refresh et update
- Nettoyage des API
- Création de la class Freebox_OS.inc
- Correction Bug création commande Disques
- **Renommage des équipements**
  - _ADSL_ devient _Freebox Débits_
  - _AirPlay_ devient _Air Média_
  - _Réseau_ devient _Appareils connectés_
- **Alarme**
  - Correction Bug widget Alarme Freebox
  - Ajout du nom et de l'icône pour les modes
  - Création des commandes spécifiques pour l'intégrer dans Homebridge
    > - Il est fortement conseillé de supprimer cet équipement pour avoir les nouvelles commandes
- **Télécommande Alarme**
  - Remontée du dernier état
- **Système**
  - Remontée des nouveaux états
    > Il est conseillé de supprimer l'équipement et de faire une recherche des équipements standards
- **4G**
  - Ajout commande pour activer/désactiver la 4G sur la box
    > Les commandes sont ajoutées uniquement si la carte est détectée
- **Wifi**
  - Ajout Planning => Etat + Activation + Désactiver
  - Ajout type de générique pour le Wifi (afin de le commander via Homebridge)
- **Contrôle Parental**
  - Ajout du contrôle parental => Etat
  - Ajout des commandes débloquer / bloquer (30min/1h/2h)
- **Caméra**
  - Mise à jour des infos fabricant et modèle suite à l'intégration dans le plugin Caméra
- **Appareils connectés**
  - Widget prise en charge des nouvelles images des appareils
  - Résolution bugs sur la gestion des ports qui étaient vide
- **Ensemble des Tiles**
  - Corrections bugs sur les sliders de type éclairage
    > Il faut absolument supprimer les commandes pour avoir ce problème résolu

## 05/07/2020

- Résolution bug transparence équipement réseau + disques
- Résolution bug Etat HomeAdapters
- Compatibilité avec la V3 pour certains icônes
- Alignement icônes des commandes de l'alarme en fonction du plugin Alarme
- **Caméra**
  - Ajout de log lors de la création
  - Modification du réglage de la caméra lors de la création de l'équipement dans le **_Plugin Caméra_** cela permettra une meilleure intégration dans Homebridge.
    > Attention, le réglage n'est pas changé dans l'équipement existant.
    >
    > - Soit il faut supprimer l'équipement et relancer un scan des Tiles
    > - Soit modifier les réglages suivants :
    >   - **URL du Flux** : rtsp://#username#:#password#@#ip#/img/live
    >   - **Nombre d'images par seconde de la vidéo** _(onglet capture)_ : 15

## 02/07/2020

- **Wifi**
  - Déplacement des commandes vers un équipement spécifique Wifi
    > Attention cet équipement est désactivé par défaut
  - Ajout icône pour les commandes ON et OFF
  - Ajout widget pour l'état et l'action on/OFF du wifi (uniquement pour la V4)
  - Passage de l'API de V3 à V5
- **Téléphone**
  - Amélioration du widget
  - Ajout icônes pour les différentes commandes (en couleur pour la V4)
- **Téléchargement**
  - Ajout icônes pour les différentes commandes (en couleur pour la V4)
  - Affectation des widgets Core sur les différentes commandes
- **Systèmes**
  - Ajout icônes pour les températures et le ventilateur
  - Ajout icônes pour les boutons updates et reboot (en couleur pour la V4)
  - Corrections du sous-type des équipements
  - Mise à jour des min et maxi de certaines commandes
- **Airplay**
  - Ajout icône stop et play (Uniquement pour les nouvelles installations, en couleur pour la V4)
- **Tiles**
  - Bug luminosité 0 à 255 + affichage du min/max sur les commandes numériques
  - Ajout BP type Switch/Toggle
  - Liaison des actions et des commandes pour les types store et éclairages
  - Déplacement de la fonction rechercher Homeadapter dans la recherche des Tiles (Nécessaire uniquement pour les Freebox DELTA)
  - Regroupement des fonctions Tiles et Homeadapter
  - Amélioration widget pour l'alarme
  - Ajout info du type d'action et d'équipement
    > il est nécessaire de cliquer sur "Scan Tiles" pour avoir ces infos
- **Corrections et améliorations**
  - Correction Bug : **Roue crantée en boucle sur activation plugin**
  - Désactivation de la création des équipements à la première installation
  - Ajout commande pour rechercher les équipements systèmes de la Freebox
  - Ajout analyse réseau après la recherche des équipements systèmes
  - Ajout dans la liste des commandes : l'icône, mini-maxi
  - Désactivation de la création des équipements à la première installation
    > il faudra cliquer sur "Scan équipements standards"

## 11/06/2020

- Bug : Correction Affichage Batterie : Masqué par défaut
- Bug : Template par défaut pour le sabotage et l'ouverture
- Bug : Invertion de la valeur par défaut sur le couvercle + attribution template
- Bug : Détecteur de présence correction des templates et l'inversion des signaux
- Autorisation de supprimer les commandes

## 09/06/2020

- Modification remontée alarme batterie lors de la création de la commande

## 07/06 et 08/06/2020

- Équipement de type "Tiles"

  - Attribution de la catégorie des Tiles (sécurité, lumière)
  - Correction Bug bouton ON/OFF \* Ajout Info dans log en mode Debug
  - Remplacement ' dans le nom de l'équipement ou de la commande par un espace
  - Remplacement "É" dans le nom des commandes par "E"
    - Masquage du bouton ajouter commande
    - Ajout des types de générique sur certaines commandes
    - Modification de la visibilité par défaut de certaines commandes (Batterie, Code Pin => non visible)
    - Correction non-apparition commande rechercher dans l'équipement "home Adapter" après une première recherche \* Renommage des commandes (ajout État dans le cas où la commande et l'info portent le même nom)
      > Pour avoir l'ensemble des nouveautés sur les équipements, il est nécessaire de les supprimer et de cliquer ensuite sur "rechercher les Tiles"

- Ajout commande "refresh" => commande masquée par défaut dans les listes des commandes
- Clean code

## 27/05/2020

- Ajout info lors de la recherche des Tiles
- Amélioration affichage des commandes
- Migration commande API Wifi de V3 à V5
- Séparation des équipements Home et Tiles dans la liste des équipements
- Nettoyage des cron à la suppression du plugin

## 03/04/2020

- Séparation du plugin et sa documentation

## 19/12/2019

- BugFix Syntax Error

## 11/12/2019

- BugFix déconnexion en cas de réponse fausse
- Suppression des équipements réseau en cas de réponse invalide

## 10/12/2019

- Restructuration de la class API
- Création d'un cron de rafraichissement du token pour n'avoir qu'une seule session
- Mise a jour du widget Réseau

## 27/11/2019

- Ajout des widgets pour la partie mobile

# Beta
