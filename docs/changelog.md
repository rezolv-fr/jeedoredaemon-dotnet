* 1.0 Version initial stable
  * prise en compte des volets roulants
  * prise en compte des portes d'entrées
  * prise en compte des lumières
  * connection local
  * widgets
  * 
* 1.1
  * fix : suppression du message d'erreur pingbeat lorsque la Tydom n'a pas été synchro
  * fix : si on supprime un équipement alors que sur un autre onglet on affiche le dashboard, alors JeeDore affiche un smiley rouge
  * add : envoi des plusieurs ids par la central pour faire les modifications en même temps
  * add : ajout d'un modèle compatible
* 1.1.1
  * Ajout de l'architecture i686
* 1.1.2
  * Ajout de la commande pour faire varier la lumière si l'équipement le permet
* 1.2 
  * Ajout du widget lumière avec réglage de la luminisité
* 1.3
  * Ajout des widgets chauffage : central, electrique et chuadière
* 1.3.1
  * fix sur une conversion implicite
  * widget lumière : ignorer le slider si non dispo
* 1.3.2
  * fix sur la sonde
* 1.3.3
  * fix shutter immage
* 1.4
  * add : application de la valeur de tous les chauffage pour les appliquer sur la centrale pour les commandes hvacMode et authorization
  * add : ajout de la commande auto
* 1.4.1
  * fix : liste des commandes de la centrale a sommer
* 1.5
  * add : ajout des équipements de type others
* 1.6
  * add : équipement de type alarm
  * fix : gestion des commandes optionnelles sur le chauffage
* 1.6.1
  * add : classemnent des équipements par catégoriesort eqLogic by category, 
  * add : ajout des valeurs pour les commandes des unités, min, max et step
  * fix : type de subtype
* 1.6.2
  * add : ajout des equipements fenêtre coulissantes4
* 1.6.3
  * add : ajout de 27 commandes
* 1.6.4
  * add : type d'équipement window
  * add : type d'équipement conso
  * fix : a chaque synchronisation d'équipement, les propriétés suivantes dans Jeedom ne sont pas changées : name, enable, visible, category, tags, order
  * fix : changement de logs lorsqu'un equipement n'est pas trouvé pour la création d'une commande
  * add : ajout des commandes : config, lightPower, lightPowerStep, supervisionMode
  * add : ajout du type équipement not-managed, équipement gérer par une Lifedomus
