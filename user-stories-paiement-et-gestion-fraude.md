# Paiement et Gestion de fraude:

## US1 - Création d'une demande de paiement par QR code:
En tant que titulaire, je veux pouvoir créér une demande de QR code afin de facilité la réception d'un paiements

### Critères d'acceptation :

- l'application doit permettre a l'utilisateur de générer un QR code.
- Le QR code doit contenir: 
    - le montant à payer;
    - le numéro du compte béneficiaire (IBAN);
    - un message décrivant le paiement;
    - la date et l'heure de création.
- L'utilisateur doit pouvoir téléchargé le QR code sous forme d'image
- Le QR code doit etre valide pendant une durée maximal d'une heure
- Le QR code devient automatiquement invalide:
    - après son expiration ;
    - après sa première utilisation.
- Une fois le QR code validé par un payeur : 
    - celui-ci choisit le compte source à débiter;
    - le montant est transféré automatiquement vers le compte bénéficiare encodé dans le QR code.
- Apres  une transaction réussie:
    - le solde du compte source doit etre debité;
    - le solde du compte destinataire doit crédité.

## US2 - Paiement avec ou sans contact : 
En tant titulaire, je veux pouvoir effectuer des paiements avec ou sans contact afin de réaliser des achats de manière rapide et sécurisée.

### critères d'acceptation :
- L'utilisateur peut sélectionner un paiement parmi ceux disponibles dans l'application.
- L'utilisateur peut choisir entre :
    - un paiement avec contact;
    - un paiement sans contact.
- Pour un paiement avec contact :
    - la confirmation par PIN est obligatoire.
- Pour un paiement sans contact:
    - Aucun PIN n'est demandé tant que aucun suspicion de fraud n'est détecté.
- L'utilisateur doit pouvoir sélectionner le compte source à débiter
- Le paiement doit etre refusé si le solde est insuffisant.
- Le montant du paiement et le destinataire sont automatiquement récupérer depuis le paiement sélectionné
- Apres une transaction reussit:
    - Le montant doit etre débité du solde du compte source;
    - Le montant doit doit crédité au solde du compte destinataire;
    - Les soldes sont immédiatemment mis à jour.
- L'institution financière doit pouvoir configurer :
    - Une limite par transaction;
    - Une limite journalière;
    - Une limite hebdomadaire;
    - Une limite mensuelle.
- Le paiement est refusé lorsque l'une des limites configurées est dépassée 

## US3 - Detection de fraude :
En tant que titulaire, je veux mes transactions soit automatiquement analysé afin que toute activité suspecté sur mon compte soit détecter.

### Critères d'acceptation :
- L'application doit enregistrer les métadonnées suivantes pour chaque transaction :
    - montant;
    - date;
    - heure;
    - mode de paiement;
    - lieu de paiement;
    - pays de paiement;
    - destinataire;
- L'application doit conserver l'historique des transaction afin d'améliorer la détection de fraudes.
- Le système doit etre capable d'identifier  notamment :
    - plusieurs paiement successifs dans un court intervalle de temps;
    - des paiements effectuees dans plusieurs pays différents dans un délai anormalement court;
    - des montants inhabituels;
    - des paiements vers des destinataires présents sur une liste noire.
- Lorsqu'un suspicion est détectée, l'utilisateur doit recevoir une notification.
- Chaque suspicion doit etre enregistrée dans un historique dédié.
- Le système doit tenir compte des suspicions précedentes pour ajuster son niveau d'alerte.
## US4 - Gestion de fraude : 
En tant que titulaire, je veux que l'application réagissent automatiquement lorsqu'un fraude est suspectée afin de protéger mon compte.

### Critères d'acceptation :

- Le système doit attribuer un niveau de risque:
    - faible;
    - moyen;
    - fort.
- En cas de faible suspicion:
    - toute nouvelle transaction doit exiger une authentification (code PIN ou mots de passe).
- En cas de moyen suspicion:
    - la transaction est bloquée;
    - une notification est envoyée au client;
    - le client peut confirmer ou refuser l'opération.
- En cas de fort:
    - le compte est temporairement bloqué;
    - le client est contacté via un canal sécurisé.
- Si le client signal une fausse alerte
    - toute les restrictions appliquées sont supprimées
- Toute desicion prise doivent etre enregistrées dans l'historique des fraudes.

## US5 - Consultation de l'historique des transactions :

En tant que titulaire, je veut consulter mon historique de transaction afin de consulté mes opération et détecté toute activité suspecte.

### Critères d'acceptation:

- Toutes les transaction passé doivent figurée dans l'historique des transaction
- L'application doit enregistrer pour chaque transaction:
    - date et l'heure;
    - montant;
    - le compte source;
    - le compte destinataire;
    - lieu de la transaction;
    - le mode de paiement;
    - statut du paiement;
- L'utilisateur doit pouvoir consulter cette historique a tout moments.
- Chaque transaction doit afficher l'un des statuts suivant:
    - Reussie;
    - Refusée;
    - Bloquée;
- Toute les informations nécessaire a la détection de fraude doivent figuré et etre conservé dans l'historique;
- Les transaction peuvent etre triées par date.
- L'utilisateur peut consulter l'historique des transactions suspectes ainsi que leur niveau de risque.

## US6 - Consultation et gestion de l'historique des alertes de fraude:
En tant que titulaire, je veux pouvoir consulter les alertes de fraudes détectées sur mon compte afin de comprendres les actions prise par le systemes et déclarer les faux positifs.

### Critères d'acceptations:

- Toute les transaction détécté comme suspecte de fraude doivent figurée dans l'historique.
- Pour chaque alerte, les informations suivant doivent etre disponibles:
    - date et heure;
    - transaction concernée;
    - niveau de risque (faible,moyen et fort);
    - action appliqué par le système.
- L'utilisateur doit pouvoir consulter l'historique des alertes de fraude.
- L'utilisateur doit pouvoir indique qu'une alerte est un faux possitif.
- Le système doit conserver les désicions de l'utilisateur afin d'améliorer les futurs controles.
- L'etat de chaque alerte doit etre affiché:
    - en attente;
    - confirmée comme fraude;
    - faux possitif.




    



