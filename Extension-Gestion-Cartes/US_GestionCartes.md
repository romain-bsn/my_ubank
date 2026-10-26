# Extention : gestion de cartes

## US1 Demander une carte 
En tant que titulaire,
je veux pouvoir demander une nouvelle carte à une institution,  
afin d'y ascocier un compte.

**Critères d'acceptation :**
- L'utilisateur doit-être conncecté.
- Chaque carte a un numéro unique, une date d'expiration, un code de sécurité et un code PIN.
- La carte reçue est inactive.

## US2 Lier un compte à une carte
En tant que titulaire possédant une carte active,
je veux pouvoir y ascocier un compte,
afin de faire des achats avec la carte.

**Critères d'acceptation :**
- Une carte n'est liée qu'a un seul compte.
- Un compte peut être lié à plusieurs cartes.
- L'utilisateur doit être titulaire ou co-titulaire du compte.
- Il doit être possible de dissocier une carte d'un compte.

## US3 Visualisation de la carte 
En tant que titulaire possédant une carte,
je veux pouvoir voir les informations la concernant (date, numéro, code de sécurité/verification) ainsi que le nombre de crédit restant pour les cartes de crédits,  
afin de savoir l'argent que je peux encore dépenser.

**Critères d'acceptation :**
- La visualisation n'est possible que si l'utilisateur est connecté.
- Précise si la carte est active ou non.

## US4 Se connecter avec une carte 
En tant que titulaire possédant une carte active,
je veux pouvoir me connecter à l'application avec mon numéro de carte et un code PIN,  
afin de faciliter la connection.

**Critères d'acceptation :**
- Il s'agit d'une fonctionnalité que l'utilsateur peut activer/désactiver pour chacune de ses cartes.
- Il doit y avoir une limite maximale d'échecs pour entrer le code PIN. Si la limite est dépassée, une notification est envoyée et cette carte ne peut plus servir pour se connecter à l'application temps que l'utilisateur ne réactive pas cette fonctionnalité.

## US5 Visualisation de l'historique de la carte
En tant que titulaire possédant une carte,
je veux pouvoir visualiser et exporter l'historique d'une carte de la même façon que je visualise l'historique d'un compte,
afin de stocker les données en local.

**Critères d'acceptation :**
- La visualisation doit être la même que celle utilisée pour les comptes.
- Une carte est considéré comme un produit financier pour la visualisation.

## US6 Expiration d'une carte 
En tant que titulaire possédant une carte active,
je veux automatiquement recevoir une nouvelle carte lorsque l'une d'entre elle expire,
afin de continuer mes achats.

**Critères d'acceptation :**
- Une carte inactive qui expire, ne déclenche pas la procédure.
- Une fois la date d'expiration dépassée, l'utilisation de la carte est impossible.
- Avant l'expiration de la carte, l'utilisateur est averti et reçoit une nouvelle carte non active.
- Lors de l'activation de la nouvelle carte, l'ancienne est automatiquement désactivée.

## US7 Bloquer une carte
En tant que titulaire possédant une carte,
je veux pouvoir bloquer une carte et au besoin en demander une nouvelle,
afin de me préserver en cas de perte ou de vol.

**Critères d'acceptation :**
- Il est possible de bloquer une carte qui n'est pas encore active.
- La demande doit être envoyée à la banque qui bloquera la carte.
- L'utilisateur reçoit à la demande, une nouvelle carte qu'il devra activer.
- Une carte bloquée est inactive et ne peut pas être réactivée.

## US8 Modifier une carte
En tant que titulaire possédant une carte active,
je veux pouvoir modifier le seuil de crédit accordé, autoriser ou non l'utilisation à l'étranger et autoriser ou non les transactions qui donneront lieues à un solde négatif,
afin d'utiliser ma carte dans les meilleures conditions.

**Critères d'acceptation :**
- Modifier le seuil de crédit doit être validé par la banque.
- Les modifications peuvent être temporaire avec une date de fin prédéfinie.

## US9 Utiliser la carte 
En tant que titulaire possédant une carte active,
je veux pouvoir utiliser ma carte pour effectuer des achats,  
afin de le faire de façon simplifié.

**Critères d'acceptation :**
- Doit tenir compte des frais d'utilisation et d'une taxe à l'étranger.

## US10 Activer une carte
En tant que titulaire possédant une carte,
je veux pouvoir activer une carte,
afin d'accéder à toutes les fonctionalités possibles avec la carte.

**Critères d'acceptation :**
- Activer une carte se fait directement dans l'application avec le code PIN.

## US11 Modifier le code PIN d'une carte
En tant que titulaire possédant une carte,
Je veux pouvoir modifier le code PIN de ma carte,
afin de mémoriser plus facilement le code.

**Critères d'acceptations :**
- Cette opération requiert l'ancien code PIN.
- Si la carte est inactive cela activera explicitement la carte avec une confirmation du titulaire.

## US12 Validation du bloquage d'une carte
En tant qu'employé d'une institution financiaire,
je veux pouvoir valider la demande de bloquage d'une carte d'un titulaire,
afin de rendre cette carte définitivement inactive.

**Critères d'acceptation :**
- Le titulaire de la carte bloquée reçoit une notifiaction lors de la validation du bloquaga.
- Démarre la procédure de création d'une nouvelle carte si le client la demandée.

## US13 Validation d'une demande de carte
En tant qu'employé d'une institution financiaire,
je veux pouvoir valider la demande de création d'une nouvelle carte d'un client,
afin que le client reçoive une carte.

**Critères d'acceptation :**
- Une carte créée est inactive.

## US13 Validation d'une demande de modification de paramètres d'une carte
En tant qu'employé d'une institution financiaire,
je veux pouvoir valider la demander de modification de paramètres de carte d'un client,
afin que le client ait les paramètres de son choix.

**Critères d'acceptation :**
- Si la demande est temporaire, aucune vérifiaction n'est requise lors de la date d'expiration du paramètre qui revient à sa valeur précédente.

## US14 Visualiser les cartes en circulation
En tant qu'employé d'une institution financiaire,
je veux pouvoir visualiser les cartes émisent par cette institution financiaire,
afin de savoir combien de cartes sont en circulation.

**Critères d'acceptation :**
- Seul les cartes émisent par cette institution sont visible.
- Les infomations ne contiennent pas des information sensible telque le code PIN.