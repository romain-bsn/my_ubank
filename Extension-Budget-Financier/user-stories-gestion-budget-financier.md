**UE :** S-INFO-015 Projet d'analyse et de conception logicielle  
**Année académique :** 2026-2027  
**Groupe :** G02
**Responsable de l'extension :** Quarta Hugo (Matricule : 250711)

### Gestion du budget financier :

#### 1. Feature : Virements bancaires récurrents

##### US1 - Création et planification d'un virement récurrent
En tant que titulaire bénéficiant de l'autorisation de virement sur mon portefeuille,  
je veux programmer un virement bancaire récurrent en définissant sa fréquence, son montant et ses comptes associés 
afin d'automatiser mes transferts d'argent réguliers.

**Critères d’acceptation :**

- L'utilisateur sélectionne un compte source et un compte bénéficiaire (compte interne au portefeuille ou IBAN SEPA externe valide).
- La fonctionnalité est accessible uniquement si la permission de virement a été accordée par l'institution financière.
- L'utilisateur doit définir la période du virement : hebdomadaire, mensuelle ou trimestrielle.
- L'utilisateur peut renseigner une date de début obligatoire et une date de fin optionnelle.
- L'utilisateur peut associer une communication libre ou structurée et une catégorie budgétaire spécifique au virement.
- Le virement programmé est visible dans la liste des virements récurrents avec le statut "Actif".
- À chaque échéance, le montant est débité du compte source et crédité sur le compte bénéficiaire (et la transaction est enregistrée dans l'historique).
- Si, à l'échéance, le solde est insuffisant, le virement récurrent échoue, aucune transaction n'est effectuée et une notification d'échec est envoyée au titulaire.

##### US2 - Virements récurrents conditionnels :
En tant que titulaire bénéficiant de l'autorisation de virement sur mon portefeuille,  
je veux ajouter des conditions à mes virements récurrents
afin d'empêcher mon compte courant d'être à découvert ou d'épargner prudement de l'argent.

**Critères d’acceptation :**

- Lors de la création ou modification d'un virement récurrent, l'utilisateur peut activer une des conditions suivantes :
    - Condition d'épargne prudente : Le virement du compte courant vers le compte d'épargne ne s'exécute que si le solde restant sur le compte courant après exécution reste supérieur (ou égale) à un seuil défini par l'utilisateur.
    - Condition de compte à découvert : Un virement automatique est déclenché depuis un compte d'épargne vers le compte courant dès que le solde de celui-ci descend sous un seuil critique défini afin de le réapprovisionner.
- Si la condition n'est pas remplie à l'échéance, le virement est ignoré pour cette échéance sans être annulé pour les échéances futures et une notification d'information est envoyée à l'utilisateur.
- L'utilisateur peut ajouter, modifier ou retirer une condition à n'importe quel instant sans devoir recréer le virement récurrent.

##### US3 - Pause et réactivation des virements récurrents :
En tant que titulaire bénéficiant de l'autorisation de virement sur mon portefeuille,
je veux pouvoir suspendre, réactiver et supprimer un virement récurrent programmé,  
afin de contrôler l'ensemble de mes transferts automatiques actifs facilement.

**Critères d’acceptation :**

- L'interface affiche la liste de tous les virements automatiques (actifs et suspendus).
- L'utilisateur peut cliquer sur "Mettre en pause" : le statut du virement devient immédiatement "En pause" et aucune transaction n'est effectuée lors des échéances tant qu'il est dans cet état.
- L'utilisateur peut réactiver un virement suspendu à tout moment : les exécutions reprennent alors à partir de la prochaine échéance.
- L'utilisateur peut supprimer définitivement un virement récurrent (une demande de confirmation est affichée avant la suppression).
- La suppression d'un virement récurrent n'efface pas l'historique des transactions passées de celui-ci.

#### 2. Feature : Classification des transactions

##### US4 - Personnalisation et gestion des catégories budgétaires
En tant que titulaire connecté,  
je veux gérer mes catégories budgétaires en modifiant les catégories existantes ou en créant de nouvelles catégories  
afin d'adapter le système de gestion de budget à mes habitudes de consommation personnelles.

**Critères d’acceptation :**

- L'application fournit par défaut des catégories prédéfinies : *Santé, Travail, Loisirs, Sport, Énergie, Transport, Études, Autres*.
- Chaque catégorie possède un nom unique, une icône et un code couleur.
- L'utilisateur peut ajouter une nouvelle catégorie personnalisée en définissant son nom, son icône et sa couleur.
- L'utilisateur peut modifier le nom, la couleur ou l'icône d'une catégorie existante (les modifications se répercutent dynamiquement sur toutes les transactions et graphiques associés).
- L'utilisateur peut supprimer une catégorie personnalisée (les transactions qui y étaient associées basculent dans la catégories "Autres" ou dans une catégorie choisie par l'utilisateur lors de la suppression).
- La catégorie système "Autres" ne peut être ni renommée ni supprimée.

##### US5 - Classification manuelle des transactions :
En tant que titulaire connecté,  
je veux affecter ou modifier manuellement la catégorie associée à une transaction financière passée ou récente
afin de modifier ou préciser la répartition de mes dépenses et revenus.

**Critères d’acceptation :**

- Dans l'historique des transactions d'un compte ou d'un portefeuille, chaque ligne affiche la catégorie actuellement associée avec son icône colorée.
- L'utilisateur peut cliquer sur la catégorie d'une transaction afin de lui attribuer une autre catégorie.
- La mise à jour modifie dynamiquement les visualisations budgétaires.
- Par défaut, toute les transactions qui ne correspondent à aucune règle automatique est rattachée à la catégorie "Autres".

##### US6 - Définition de règles de classification automatique
En tant que titulaire d'un portefeuille,  
je veux configurer des règles d'assignation automatique de catégories
afin de catégoriser automatiquement mes dépenses et revenus.

**Critères d’acceptation :**

- L'utilisateur peut créer une règle de classification automatique liée à son portefeuille en précisant :
  - L'attribut de la transaction à analyser (ex : IBAN émetteur/destinataire, communication ou montant).
  - L'opérateur de comparaison (*égal à*, *supérieur à*, *inférieur à*, *contient*,...).
  - La valeur cible (nombre à 11 chiffres, chaîne de caractères ou montant en fonction du type d'attribut comparé).
  - La catégorie cible à assigner automatiquement.
- L'utilisateur peut organiser les règles de classification automatiques définies par ordre de priorité.
- Lorsqu'une nouvelle transaction est effectuée, les règles sont évaluées dans l'ordre de priorité défini par l'utilisateur et dès qu'une règle est valide, la catégorie correspondante est immédiatement assignée à la transaction.
- L'utilisateur peut appliquer une nouvelle règle créée à l'historique complet de ses transactions.

##### US7 - Consultation et filtrage de l'historique des transactions étendus aux catégories (Extension de l'US18 de base)
En tant que titulaire connecté,  
je veux visualiser la répartition de mes dépenses et de mes revenus par catégorie sous forme de graphiques, de listes et de tableaux,  
afin d'identifier les catégories de dépenses et de revenus les plus importantes de mon budget.

**Critères d’acceptation :**

- L'interface d'analyse comporte un diagramme circulaire et un graphique à barres illustrant la répartition en pourcentage et en montant par catégorie.
- L'utilisateur peut filtrer la visualisation par période, par catégorie budgétaire et par comptes spécifiques au sein d'un ou plusieurs portefeuilles.
- L'utilisateur peut exporter les données visualisées filtrées par catégorie aux formats CSV et JSON (extension de l'US19 de base).

#### 3. Feature : Statistiques budgétaires et analyse de tendances

##### US8 - Consultation des statistiques budgétaires
En tant que titulaire connecté,  
je veux consulter des statistiques détaillées sur mes dépenses et revenus
afin d'évaluer la distribution et la variabilité de mes dépenses sur une période choisie.

**Critères d’acceptation :**

- L'interface dédiée aux statistiques affiche pour la période sélectionnée :
  - Le montant minimum et maximum.
  - La moyenne et l'écart-type.
  - La médiane, les quartiles et l'écart interquartile.
- L'utilisateur peut choisir de calculer ces statistiques sur l'ensemble des transactions ou de sélectionner/exclure certaines catégories.
- L'utilisateur peut choisir la période sur laquelle les statistiques sont calculées.
- Si aucune transaction n'existe pour les filtres appliqués, un message informatif est affiché.

##### US9 - Visualisation des tendances temporelles et de la saisonnalité
En tant que titulaire connecté,  
je veux analyser l'évolution temporelle de mon budget via des courbes comparatives et des indicateurs de saisonnalité,  
afin de visualiser les variations de mes dépenses et revenus d'une période à l'autre.

**Critères d’acceptation :**

- L'application fournit un graphique linéaire comparant les dépenses d'une période par rapport à la période précédente.
- L'interface affiche le taux de variation (en pourcentage et en euro) entre les deux périodes comparées.
- L'utilisateur peut sélectionner et modifier l'ensemble des catégories à prendre en compte lors de la visualisation.
- L'application fournit une vue mettant en évidence les dépenses/revenus majoritaires en fonction de la saison.

#### 4. Feature : Détection d'anomalies et alertes

##### US10 - Détection d'anomalies de dépenses par rapport à l'historique et au foyer moyen
En tant que titulaire connecté,  
je veux être notifié automatiquement dès qu'une dépense inhabituelle ou anormale est détectée sur mon compte 
afin d'éviter les dépenses déraisonnables et d'améliorer la gestion de mon budget financier.

**Critères d’acceptation :**

- Le système analyse en continu les transactions effectuée et détecte :
    - Les anomalie par rapport à l'historique personnel : Le système détecte les dépenses d'une catégorie qui dépassent significativement la moyenne habituelle du titulaire.
    - Les anomalie par rapport au foyer moyen : Le système compare les dépenses d'une catégorie du titualire par rapport à celles du foyer moyen.
- Dès qu'une anomalie est détectée, une alerte est envoyée au titulaire en précisant la transaction concernée ainsi que le montant et l'écart constaté.
- L'utilisateur a la possibilité de marquer une alerte comme "Légitime" (pour ne plus être alerté sur cet événement) ou de régler les seuils de détection des anomalies pour une cette catégorie.


#### 5. Feature : Prédiction et projection budgétaire

##### US11 - Projection du solde d'un portefeuille 
En tant que titulaire connecté,  
je veux visualiser une prédiction de l'évolution du solde de mes comptes pour un certain portefeuille à une date ultérieure  
afin d'anticiper mon budget future et anticiper d'éventuelles difficultés financières.

**Critères d’acceptation :**

- L'utilisateur peut sélectionner une date cible de prédiction future.
- L'application prédis le solde future du solde sur base :
  - des virements récurrents actifs sur la période.
  - de la projection des dépenses et revenus sur la période estimée à partir des statistiques historiques et des tendances.
- L'utilisateur peut sélectionner un ensemble de catégories à exclure ou à prendre en compte lors de la projection.
