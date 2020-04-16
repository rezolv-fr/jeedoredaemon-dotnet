# Présentation de JeeDore

Le plugin **JeeDore** permet de piloter les équipements [DeltaDore]("https://www.deltadore.fr/") via une box Tydom.
Ainsi, les équipements compatibles avec Tydom peuvent être pilotés par Jeedom.

# Installation

## Activation du plugin

Le plugin **JeeDore** doit être installé via le market Jeedom.

![JeeDore Market](./assets/images/jeedore_icon.png "JeeDore Market")

Dès que le plugin est installé, il suffit d'activer le plugin.

![JeeDore Plugin Activation](./assets/images/pluginstateinactive.png "JeeDore Plugin Inactive")

Après l'activation du plugin :

![JeeDore Plugin Activation](./assets/images/pluginstateactive.png "JeeDore Plugin Active")

## Installation des dépendances

Le plugin est composé d'un démon développé en .Net Core qui requiert le runtime .Net pour les architectures x86, arm et arm64. Jeedom installera les dépendances dans les 5 min. Elles seront également réinstallées lors d’une mise à jour du plugin si besoin.

![JeeDore Plugin Dependency](./assets/images/plugindependency.png "JeeDore Plugin Dependency")

## Statut du démon

Le démon peut être dans deux états, démarré ou arreté.

Démon arrêté : 

![JeeDore Daemon Stopped](./assets/images/daemonstatusstopped.png "JeeDore Daemon Stopped")

Démon demarré : 

![JeeDore Daemon Started](./assets/images/daemonstatusstarted.png "JeeDore Daemon Started")

Pour démarrer le démon, il suffit de clicker sur le bouton **(Re)Démarrer** de Jeedom.

## Configuration

Pour que **JeeDore** puisse piloter une box Tydom, il faut rensigner l'adresse MAC et le mot de passe.
Une adresse MAC est un nombre au format hexadécimal se situant sur la Tydom. Elle est composé de 12 caractères.

L'adresse MAC se situe sur votre Tydom :

![DeltaDore MacAddress](./assets/images/macaddress.png "DeltaDore MacAddress")

![JeeDore Configuration](./assets/images/configuration.png "JeeDore MacAddress")


Il est possible de choisir le type de connection :
* Local, l'adresse IP de votre Tydom doit être saisi. Vous pouvez la retrouver dans l'application Tydom de Delta Dore dans le menu _A propos_.
* Remote, l'identification et l'envoi de toutes les commandes passent par les serveurs Delta Dore

> Le type _Local_ est **fortement** conseillé pour avoir une connection fiable.

**JeeDore** dispose de deux thèmes : Sombre et Clair. Cela change les icônes de noir sur blanc en blanc sur noir.

Il suffit de clicker sur le bouton _Sauvgarder_ pour appliquer les modifications.

# Compatiblité

## Plateforme

**JeeDore** est compatible sur les plateformes Jeedom suivantes :
* Docker (testé sur Synology)
* Raspberry Pi 2, 3, 4
* Jeedom Smart
* Freebox Delta

> Si une plateformne n'est pas mentionnée, cela signifie qu'aucun retour utilisateur a été fait.

Pour que **JeeDore** puisse piloter des équipements de la marque Delta Dore, il utilise une box Tydom.
Les boxes Delta Dore compatibles sont :
* [Tydom 1.0](https://www.deltadore.fr/domotique/pilotage-maison-connectee/box-domotique/tydom-1-0-ref-6700103)
* [Tydom 2.0](https://www.deltadore.fr/domotique/pilotage-maison-connectee/box-domotique/tydom-2-0-ref-6414118)

Les boxes Delta Dore incompatibles sont :
* Tydom 2000

## Type d'équipement et commande

### Tydom
![JeeDore Market](./assets/images/tydom1.png "JeeDore Market")

* productName : nom du produit
* mac : adresse MAC
* config : ?
* bddEmpty : base de données vide
* bddStatus : non documenté
* apiMode : non documenté        | 1                   |
* mainVersionSW : version logiciel Tydom
* mainId : non documenté
* mainReference : plan logiciel Tydom
* keyVersionSW : version logiciel clé
* keyVersionHW : version matériel Tydom
* keyVersionStack : version logiciel stack
* keyReference : plan logiciel clé
* bootReference : plan logiciel boot
* bootVersion : version logiciel boot
* tydomDat : version Tydom.dat
* momJson : version Mom.Json
* gatewayDat : version Gateway.Json
* momApiJson : version Mom_Api.Json
* scenarioJson : version Scenario.Json
* configJson : version Config.Json
* updateAvailable : version disponible
* longitude : longitude
* latitude : latitude
* timezone : fuseau horaire (en minutes)
* summerOffset : heure d'été/hiver
* bddJson : version Bdd.Json
* collectJson : version Collect.Json
* groupsJson : version Groups.Json
* urlMediation : url utilisé pour la connection sur les serveurs DeltaDore

### Scénario
![JeeDore Market](./assets/images/scenario.png "JeeDore Market")

  * play : executer un scénario défini sur la box Tydom

### Ouvrants
![JeeDore Market](./assets/images/shutter_60.png "JeeDore Market")

* up : monte le volet
* down : descends le volet
* stop : arrête le mouvement du volet
* setPosition : défini l'ouverture du volet en pourcentage
  > Cette commande n'est pas compatible avec tous les modèles de volet. Pour palier, il suffit de faire un scénario sur Jeedom, de _up_ le volet, faire une pause de 2s et de faire un _stop_
* getPosition : pourcentage d'ouverture du volet

#### Modèles validés

*Pack pour volets roulants*
> Pack Tyxia : 540, 630

*Récepteurs pour portail ou porte de garage*
> Tyxia : 4620, 6410

*Récepteurs*
> Tyxia : 5630, 4630, 4730, 4731

*Moteurs*
> Pack Rollia : 10, 30
> RL : 5010 BO, 5010 BOT, 5020 BO, 5020 BOT, 5030 BO, 5030 BOT 

*Stores* :
> Stores Well’Com

Liste des équipements non confirmé, il est probable que seul l'info de la batterie de la télécommande soit retourné :
> Tyxia : 1612, 1600, 1400, 2310, 4000

Liste des équipements à valider :
> Tyxia 5612


### Lumière
![JeeDore Market](./assets/images/light_30.png "JeeDore Market")

  * setLevelCmdOn : allumer
  * setLevelCmdOff : éteindre
  * setLevelCmdToggle : inverse la position de la lumière
  * setLevel : défini l'intensité de la lumière en pourcentage
  * setRecFav1 : défini une valeur en favori pour le créneau 1
  * setRecFav2 : défini une valeur en favori pour le créneau 2
  * setLevelCmdFavorit1 : défini l'intensité de la lumière défini dans le créneau 1
  * setLevelCmdFavorit2 : défini l'intensité de la lumière défini dans le créneau 2
  * setModeAsso : mets l'équipement en mode association
  * levelCmd : retour d'état pour connaître l'intensité en pourcentage

#### Modèles validés

*Récépteur simple allumage*
> Tyxia : 4610, 46XX, 4910

*Récépteur variation d'allumage*
> Tyxia : 4801, 4811, 4840, 4840

*Intérrupteurs / Récepteurs*
> Tyxia 6610, 5610

### Porte d'entrée
![JeeDore Market](./assets/images/door_unlocked.png "JeeDore Market")

* openstate : retour d'état pour savoir si une porte est ouverte

### Chauffage/climatisation
![JeeDore Market](./assets/images/thermostat.png "JeeDore Market")
  * setHvacMode : défini le mode 
  * setSetpoint :  défini la température à atteindre
  * setModeAsso : mets l'équipement en mode association

#### Modèles validés

*Chaudière et pompes à chaleur*
* Thermostats programmables
> Tybox 800, 801, 810, 811, 812, 813, 820, 821, 137, 237, 337, 437, Pack promo Tybox 137, Pack promo radio 811+1

* Thermostats programmables RT 2012
> Tybox 1010 P, 1010 WT, 2000 WT, 2010 P, 2010 WT, 2020 P, 2020 WT

* Thermostats d’ambiance
> Tybox : Pack 4100, Pack 4110, Pack 4150, Pack 4210, Pack 4250, 5100, 5101, 5150, 

*Chauffage électrique*
* Gestionnaire d’énergie 
> Calybox 1020 P, 1020 WT, 2020 P, 2020 WT, 210, 220, 220 WT, 230, 230 WT, 320, 320 WT, 330, 420, 430

* Gestionnaire d’énergie RT 2012
> Calybox 1020 P, 1020 WT, 2020 P, 2020 WT

* Récepteur pour plancher rayonnant électrique
> RF 4890

* Indicateur de consommation
> Tywatt : 1000, 1000 P, 2000, 2000 P, 5200

* Fil pilote connecté
> Pack RF6600 FP 


### Alarme
#### Modèles validés
*Alarme Tyxal*
> Kit 20Kit, 30Kit, 5Kit, 50Kit, 51Kit, 70Kit, 71CSTX, 50CSX, 20CSX, 40CTX, CTX 60, Pack appartement, Pack maison, Pack maison animaux 

*Alarme Evology*
> Pack Evology 2 zones, 4 zones 

*Alarme Deltal*
> Pack : 2.00, 2.10, 2.15, 2.50, 3.00, 4.00, 4.00 A, 4.01, 4.50 GSM, 4.50, 4.50 A, 7.00

*Alarme Tyxal+*
> Pack Tyxal+, CS 8000 Tyxal+


> Tous les équipements DeltaDore ne sont pas encore tous compatibles. La prise en charge de nouveaux équipements est en cours.


### Caméra

Liste des équipements pas encore traités :
> Toutes les caméras

Liste des équipements non compatible :
* Tycam 1000 car non compatible Tydom 1.0


# Utilisation

## Synchronisation des équipements

Pour que Jeedom puisse connaître les équipements associés via l'application Tydom de Delta Dore, il faut se rendre sue la page du plugin

![JeeDore Menu](./assets/images/menujeedore.png "JeeDore Menu")

et de clicker sur le bouton __Synchroniser équipement__.

Une fois la synchronisation réalisée, tous vos équipements pris en compte s'afficheront.

![JeeDore Synchronization](./assets/images/jeedoreequipment.png "JeeDore Synchronization")

Lors d'un click sur un équipement, il est possible de tester les commandes disponibles sur cet équipement et de les tester.

Dans un scénario, il est possible d'appeler les commandes.

# Changelog

[Changelog]("https://www.deltadore.fr/")

Eli.
