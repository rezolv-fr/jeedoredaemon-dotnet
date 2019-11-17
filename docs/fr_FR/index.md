Description 
===

Le plugin JeeDore permet de piloter les équipements DeltaDore à travers une box Tydom 1.0. Plusieurs types d'équipements sont prises en compte :
 * Volets roulants
 * Ouverture de porte
 * Porte de garage

Commande
===
En fonction des équipements, certaines commandes ne sont pas disponibles.

Liste des commandes disponible par équipement.

 * Volets roulants
   * position en %
   * stop
   * down
   * up
 * Porte de garage
   * toggle
 * Retour d'état de detecteur d'ouverture de porte
 * Scenario, permet de jouer un scenario configure dans la box DeltaDore

Retour d'état
===
Si un équipement change d'état, alors Jeedom est immédiatement informé du changement par un évenement. Position des volets roulants en temps réel, ouverture de porte d'entrée.
Même si le changement est initié par le JeeDore ou une télécommande, le plugin sera toujours informé de son état.
