**UE :** S-INFO-015 Projet d'analyse et de conception logicielle  
**Année académique :** 2026-2027  
**Groupe :** G02 
**Membres du groupe :**
- Berkani Zinediné (Matricule : )
- Fontaine Alexis (Matricule : )
- Quarta Hugo (Matricule : 250711)
- Vandooren Romain (Matricule : )

---

### Général :

#### 1. Feature : Internationalisation et gestion des langues

##### US1 - Support multilingue :
En tant que visiteur non-enregistré, je veux pouvoir choisir la langue dans la page d’accueil afin de suivre les instructions d’enregistrement dans cette langue.

**Critères d’acceptation :**

- La page d’accueil fournit un sélecteur de langue permettant de changer la langue d’affichage.
- Toute information affichée utilise la langue sélectionnée.

##### US2 - Choix de la langue préférée lors de la création d’un compte :
En tant que visiteur non-enregistré, je veux indiquer et mémoriser ma langue préférée afin d'utiliser l’application dans cette langue pour toutes mes connections futures.

**Critères d’acceptation :**

- Le formulaire de création de compte propose un champ de choix de langue.
- Ce champ obligatoire est pré-rempli avec une valeur par défaut qui peut être modifiée.
- La langue choisie après validation du formulaire est enregistrée dans le profil utilisateur.

##### US3 - Application automatique de la langue préférée à chaque connexion :
En tant que titulaire, je veux que l’application utilise automatiquement ma langue préférée afin de ne pas devoir la reconfigurer à chaque session.

**Critères d’acceptation :**

- Après authentification, l’application utilise la langue enregistrée dans le profil utilisateur.
- Ce comportement s’applique pendant toute la session.

##### US4 - Modification a posteriori de la langue préférée :
En tant que titulaire, je veux pouvoir changer ma langue préférée afin de utiliser l’application dans cette langue lors de la session actuelle ainsi que toutes les sessions futures.

**Critères d’acceptation :**

- Une option dans le profil utilisateur permet de changer sa langue préférée.
- Le changement se répercute immédiatement sur l’interface sans nécessiter une déconnexion et reconnexion.
- La nouvelle préférence persiste lors des connexions suivantes.

---

### Application titulaire pour gérer ses "portefeuilles financiers" :

#### 1. Feature : Authentification et Accès

##### US5 - Inscription d'un nouveau titulaire
En tant que titulaire non-enregistré,
je veux créer un compte utilisateur en renseignant mon nom complet, mon numéro de registre national, ma langue préférée et un mot de passe sécurisé
afin de pouvoir m'authentifier et gérer mes portefeuilles financiers.

**Critères d’acceptation :**

- Tous les champs du formulaire sont obligatoires : nom complet, numéro de registre national, langue préférée, mot de passe et confirmation du mot de passe.
- Le numéro de registre national doit être valide.
- Le mot de passe doit comporter au minimum 8 caractères, dont au moins une majuscule, un chiffre et un caractère spécial.
- L'inscription est rejetée si un compte existe déjà avec le même numéro de registre national ou le même nom complet.
- Le champ de langue préférée est pré-rempli avec la langue par défaut et peut être modifié.
- Si tous les champs sont valides et que les mots de passe sont identiques, le compte est créé et l'utilisateur peut se connecter (ou est connecté automatiquement).

##### US6 - Connexion à l'espace titulaire
En tant que titulaire,
je veux me connecter à l'application avec mon nom complet, mon numéro de registre national et mon mot de passe
afin d'accéder à mes portefeuilles financiers.

**Critères d’acceptation :**

- Le formulaire de connexion nécessite le nom complet, le numéro de registre national et le mot de passe.
- Si les trois informations correspondent exactement à un compte enregistré, l'utilisateur est connecté et redirigé vers son tableau de bord.
- Si au moins une information est incorrecte ou absente, l'accès est refusé avec un message d'erreur.
- Un utilisateur ne peut avoir qu'une seule session active à la fois : la création d'une nouvelle session entraîne la fermeture de la précédente.
- L'application permet à plusieurs utilisateurs différents d'être connectés simultanément.

##### US7 - Réinitialisation d'un mot de passe oublié
En tant que titulaire ayant oublié son mot de passe,  
je veux réinitialiser mon mot de passe depuis la page de connexion en fournissant mes identifiants
afin de recouvrer l'accès à mon espace personnel.

**Critères d’acceptation :**

- Une option "Mot de passe oublié" est présente sur la page de connexion.
- La réinitialisation du mot de passe nécessite le numéro de registre national et le nom complet associés au compte.
- Si les informations fournies correspondent à un utilisateur enregistré, le formulaire permet de saisir un nouveau mot de passe et sa confirmation.
- Le nouveau mot de passe doit respecter les mêmes règles de sécurité (minimum 8 caractères, majuscule, chiffre et caractère spécial).
- Le nouveau mot de passe et la confirmation du nouveau mot de passe doivent être identiques pour valider la réinitialisation.
- Si les données d'identification ne correspondent à aucun compte, la réinitialisation échoue avec un message d'erreur.
- Une fois réinitialisé, l'ancien mot de passe est invalidé et l'utilisateur peut se connecter avec son nouveau mot de passe.

##### US8 - Modification du mot de passe depuis le profil
En tant que titulaire,  
je veux pouvoir modifier mon mot de passe actuel dans mes paramètres de compte  
afin de renforcer la sécurité de mon compte.

**Critères d’acceptation :**

- L'utilisateur doit saisir son mot de passe actuel, le nouveau mot de passe et la confirmation du nouveau mot de passe.
- L'ancien mot de passe saisi doit être vérifié avant sa mise à jour.
- Le nouveau mot de passe doit respecter les mêmes règles de sécurité et doit être différent du mot de passe actuel.
- La mise à jour est immédiatement enregistrée.

##### US9 - Déconnexion de l'application
En tant que titulaire connecté,  
je veux pouvoir me déconnecter à tout moment de mon application
afin de terminer ma session.

**Critères d’acceptation :**

- Une option de déconnexion est accessible à tout instant.
- La déconnexion termine la session et redirige vers la page de connexion.


#### 2. Feature : Gestion des Portefeuilles Financiers

##### US10 - Demande de création et liaison d'un portefeuille financier
En tant que titulaire, 
je veux soumettre une demande de création d'un portefeuille lié à une institution financière
afin d'accéder aux produits financiers dont je suis titulaire.

**Critères d’acceptation :**

- L'utilisateur peut sélectionner une institution financière parmi la liste des banques enregistrées dans le système.
- Une fois soumise, la demande apparaît avec le statut "En attente de validation par l'institution".
- Si la demande est approuvée par l'institution financière :
  - Le portefeuille est automatiquement créé et devient accessible à l'utilisateur.
  - Le portefeuille inclut au minimum le compte courant du titulaire.
  - L'utilisateur a accès à tous les produits pour lesquels il est titulaire ou co-titulaire auprès de cette banque.
- Si la demande est refusée par l'institution financière :
  - L'utilisateur est informé par une notification du rejet de sa demande.
  - Aucun portefeuille n'est créé pour cette institution.

##### US11 - Gestion de l'affichage des produits
En tant que titulaire,
je veux désactiver ou réactiver certains produits financiers de mon portefeuille 
afin de ne visualiser que les produits que je souhaite gérer.

**Critères d'acceptation :**

- Seuls les produits activés par le client sont visibles dans son portefeuille.
- Le client possède une option pour désactiver des produits de son portefeuille.
- Le client a la possibilité de réactiver ses produits désactivés via une liste des produits masqués.

##### US12 - Demande d'ouverture ou de clôture d'un produit financier
En tant que titulaire,  
je veux introduire une demande d'ouverture ou de clôture d'un produit financier auprès de mon institution financière
afin de faire gérer la création et la suppression de mes produits financiers directement depuis l'application.

**Critères d’acceptation :**

- L'utilisateur peut soumettre une demande d'ouverture en choisissant le type de compte souhaité parmi les produits proposés par la banque du portefeuille.
- L'utilisateur peut soumettre une demande de clôture pour un compte existant dont il est titulaire.
- Une confirmation est demandée avant toute validation d'une demande de clôture.
- Une fois envoyée, la demande apparaît sous le statut "En attente de traitement par l'institution financière".
- Si la demande est approuvée par l'institution, le nouveau produit apparaît dans le portefeuille (ou le produit clôturé passe dans le statut archivé).
- Si la demande est refusée par l'institution, le client reçoit une notification expliquant le rejet.


##### US13 - Notifications de mise à jour du portefeuille et consultation des archives
En tant que titulaire,  
je veux être averti dès l'ouverture de mon portefeuille de tout ajout ou suppression de produit effectué par ma banque
afin de suivre l'état de mes comptes.

**Critères d’acceptation :**

- À l'ouverture d'un portefeuille, si la banque a ajouté un ou plusieurs produits, une notification informe le titulaire et les produits sont automatiquement disponibles.
- À l'ouverture d'un portefeuille, si la banque a supprimé un ou plusieurs produits, une notification est affichée au titulaire.


##### US14 - Consultation des archives
En tant que titulaire,
je veux accéder aux produits financiers archivés
afin de consulter l'historique des transactions de mes produits financiers supprimés.

**Critères d’acceptation :**

- Tout produit financier clôturé passe automatiquement dans le statut "archivé".
- Un produit archivé ne permet plus d'effectuer de nouvelles transactions financières.
- L'utilisateur dispose d'une visualisation de l'historique complet des transactions de ses produits archivés.


##### US15 - Bascule entre portefeuilles et vue d'ensemble
En tant que titulaire client de plusieurs institutions financières,  
je veux pouvoir afficher la liste de tous mes portefeuilles et basculer facilement d'un portefeuille à un autre 
afin de gérer individuellement chacun de mes portefeuilles et avoir une vision d'ensemble de ceux-ci.

**Critères d’acceptation :**

- La page d'accueil de l'application affiche à l'utilisateur connecté la liste de ses portefeuilles financiers.
- L'utilisateur peut cliquer sur un des portefeuilles de la liste afin de le consulter individuellement.
- Une option "Vue d'ensemble" affiche l'ensemble des produits de tous les portefeuilles du client sur une même interface.


#### 3. Feature : Virements Bancaires

##### US16 - Demande d'activation de la fonctionnalité de virement
En tant que titulaire,  
je veux soumettre une demande d'accès à la fonctionnalité de virement auprès de mon institution financière 
afin d'obtenir l'autorisation de transférer de l'argent depuis mes comptes liés à l'institution.

**Critères d’acceptation :**

- L'utilisateur peut soumettre une demande d'autorisation de virement pour son portefeuille.
- Une fois soumise, la demande passe dans le statut "En attente d'approbation par l'institution financière".
- Tant que la demande n'est pas approuvée, l'accès aux virements reste verrouillé sur ce portefeuille.
- Si l'institution approuve la demande :
  - La permission est activée pour le titulaire.
  - La fonctionnalité de virements devient accessible.
  - L'utilisateur est informé de l'activation par une notification.
- Si l'institution refuse la demande :
  - L'utilisateur est notifié du rejet et la fonctionnalité reste verrouillée.

##### US17 - Émission d'un virement SEPA en euros
En tant que titulaire bénéficiant de l'autorisation de virement,  
je veux effectuer un virement en euros vers un autre compte bancaire au sein de la zone SEPA 
afin de transférer de l'argent vers mes propres comptes ou un autre destinataire.

**Critères d’acceptation :**

- L'utilisateur sélectionne l'un de ses comptes comme compte source (émetteur).
- Le formulaire nécessite la saisie du compte destinataire (IBAN valide), du montant (en euros avec au maximum 2 décimales) et du nom complet du destinataire.
- L'utilisateur peut aussi ajouter :
  - Une communication libre ou structurée.
  - Une date pour planifier l'exécution du virement à une date future.
- Si le nom saisi ne correspond pas exactement au nom du titulaire réel associé à l'IBAN destinataire, un avertissement est affiché à l'utilisateur avant la validation.
- Si le destinataire ne se trouve pas dans la zone SEPA, l'opération est annulée avec un message d'erreur.
- Si le solde du compte source n'est pas suffisant pour couvrir le montant du virement, celui-ci est annulé avec un message d'erreur.
- L'opération nécessite une validation de sécurité obligatoire (saisie du mot de passe ou code de confirmation) avant l'exécution.
- En cas de confirmation valide, le montant est débité du compte source, crédité sur le compte cible (ou programmé si date future) et une confirmation est affichée.


#### 4. Feature : Historique, Visualisation et Exportation

##### US18 - Consultation et filtrage de l'historique des transactions
En tant que titulaire,  
je veux consulter l'historique des transactions pour un produit spécifique ou pour un ensemble de produits sur une période définie 
afin de vérifier mes opérations passées et visualiser l'évolution de mes produits financiers.

**Critères d’acceptation :**

- L'utilisateur peut sélectionner un ou plusieurs comptes spécifiques au sein d'un portefeuille ou choisir l'ensemble de ses portefeuilles.
- L'utilisateur peut définir la période de consultation des transactions.
- La visualisation peut se faire sous forme de listes, de tableaux ou de graphes.
- Chaque transaction affiche la date, le type d'opération, le montant (avec exactement 2 décimales), la devise et les informations du tiers (IBAN/nom).
- Si aucune transaction n'existe sur la période sélectionnée, un message informatif est affiché.

##### US19 - Exportation des données historiques
En tant que titulaire,
je veux exporter les données de transactions visualisées aux formats CSV et JSON,  
afin de conserver une copie externe de mes relevés et pouvoir les exploiter dans d'autres outils d'analyse.

**Critères d’acceptation :**

- L'interface propose des options de téléchargement aux formats CSV et JSON.
- Le fichier exporté contient l'ensemble des transactions correspondant aux filtres actifs à l'écran (période et produits sélectionnés).
- Le format des données exportées respecte la syntaxe standard (colonnes valides pour le CSV, structure d'objets valide pour le JSON).

---

### Application Institution Financière :

#### 1. Feature : Authentification et Sécurité de l'Institution

##### US20 - Connexion de l'institution financière
En tant qu'employé d'une institution financière,  
je veux me connecter à l'application avec l'identifiant unique de mon institution et son mot de passe  
afin d'accéder à l'espace de gestion des clients et produits financiers de ma banque.

**Critères d’acceptation :**

- Le formulaire nécessite la saisie de l'identifiant de l'institution (code SWIFT/BIC ou login institutionnel) et du mot de passe.
- L'application utilise un accès unique pour l'ensemble des employés d'une même institution financière.
- Si les identifiants correspondent, l'utilisateur est connecté et accède à l'espace de son institution.
- Si l'identifiant ou le mot de passe est invalide, l'accès est refusé avec un message d'erreur.

##### US21 - Modification du mot de passe de l'institution
En tant qu'employé connecté d'une institution financière,  
je veux pouvoir modifier le mot de passe du compte de l'institution depuis l'application  
afin de renforcer la sécurité d'accès à ce compte.

**Critères d’acceptation :**

- Une option de changement de mot de passe est accessible depuis les paramètres de l'application.
- La procédure nécessite la saisie de l'ancien mot de passe, du nouveau mot de passe et de la confirmation du nouveau mot de passe.
- L'ancien mot de passe doit être validé avant sa modification.
- Le nouveau mot de passe doit respecter les mêmes règles de sécurité et être différent de l'actuel.
- Une fois modifié, le nouveau mot de passe est immédiatement actif pour toutes les prochaines connexions de l'institution.

##### US22 - Déconnexion de l'espace institutionnel
En tant qu'employé connecté d'une institution financière,  
je veux pouvoir me déconnecter à tout moment de l'application,  
afin de fermer la session administrative.

**Critères d’acceptation :**

- Une option de déconnexion est accessible à tout instant.
- La déconnexion met immédiatement fin à la session en cours et redirige vers la page de connexion.

#### 2. Feature : Gestion des Clients et des Produits Financiers

##### US23 - Enregistrement d'un nouveau client auprès de l'institution
En tant qu'employé connecté d'une institution financière,  
je veux enregistrer un client en renseignant son identité,  
afin de lui permettre de souscrire à nos produits financiers.

**Critères d'acceptation :**

- L'enregistrement nécessite la saisie du nom complet et du numéro de registre national.
- L'opération est refusée si le client est déjà enregistré auprès de notre institution financière.
- Une fois enregistré, le client apparaît immédiatement dans la liste des clients de l'institution.
- L'employé n'a accès qu'à la liste des clients enregistrés auprès de sa propre institution.

##### US24 - Suppression d'un client de l'institution
En tant qu'employé connecté d'une institution financière,  
je veux supprimer un client de notre institution,  
afin de mettre fin à son contrat avec notre institution.

**Critères d'acceptation :**

- L'employé peut sélectionner un client lié à son institution et demander sa suppression.
- Le client supprimé n'apparaît plus dans la liste des clients de l'institution.

##### US25 - Ouverture d'un produit financier pour un client
En tant qu'employé connecté d'une institution financière,  
je veux ouvrir un nouveau produit financier pour l'un de nos clients,  
afin de lui fournir un nouveau compte répondant à ses besoins bancaires.

**Critères d'acceptation :**

- L'employé sélectionne un client existant de l'institution et choisit un type de compte à ouvrir (compte courant, compte jeune, compte épargne, compte à terme,...).
- Le système génère automatiquement un identifiant unique (code IBAN conforme) associé au code BIC/SWIFT de l'institution.
- Le produit créé apparaît dans la liste des produits financiers gérés par l'institution.
- L'employé n'a accès à la gestion qu'aux produits fournis par sa propre institution.

##### US26 - Clôture d'un produit financier
En tant qu'employé connecté d'une institution financière,  
je veux clôturer un produit financier détenu par un client auprès de notre institution,  
afin de résilier ce contrat bancaire.

**Critères d'acceptation :**

- L'employé peut clôturer un produit actif de son institution pour un de ses clients à condition que celui-ci ait un solde nul.
- Si le solde du produit financier n'est pas nul, l'opération est annulée et un message d'erreur est affiché.
- Dès la suppression, le produit passe dans le statut "archivé".
- L'historique des opérations passées du produit archivé reste conservé.

#### 3. Feature : Traitement des demandes clients

##### US27 - Traitement des demandes d'ouverture et de clôture de produits financiers
En tant qu'employé connecté d'une institution financière,
je veux consulter, approuver ou refuser les demandes d'ouverture et de clôture de comptes formulées par nos clients
afin de gérer l'ensemble de leurs produits financiers liés à notre institution.

**Critères d'acceptation :**

- L'employé peut consulter l'ensemble des demandes d'ouverture et de clôture de produits en attente pour les clients de son institution.
- Pour une demande d'ouverture :
  - Si la demande est approuvée, le produit est créé avec un code IBAN conforme, est lié au client passe dans l'état actif et une notification de succès est envoyée au client.
  - Si la demande est refusée, le client reçoit une notification expliquant le refus et la demande est clôturée.
- Pour une demande de clôture :
  - Si la demande est approuvée, le produit est supprimé, passe dans l'état archivé et une notification de succès est envoyée au client.
  - Si la demande est refusée, le client reçoit une notification expliquant le refus et la demande est clôturée.

##### US28 - Traitement des demandes de liaison de portefeuille
En tant qu'employé connecté d'une institution financière,
je veux consulter, approuver ou refuser les demandes de liaisons de portefeuille émises par nos clients
afin de contrôler l'accès de nos clients à nos produits.

**Critères d'acceptation :**

- L'employé peut consulter les demandes de liaisons de portefeuille en attente des clients de son institution.
- Si la demande est approuvée, tous les produits du client liés à l'institution lui sont rendus visibles.
- Si la demande est refusée, le client reçoit une notification expliquant le refus et la demande est clôturée.

##### US29 - Traitement des demandes d'activation des virements
En tant qu'employé connecté d'une institution financière,
je veux consulter, approuver ou refuser les demandes d'autorisation de virement émises par nos clients
afin de contrôler l'accès de nos clients à cette fonctionnalité.

**Critères d'acceptation :**

- L'employé peut consulter les demandes d'autorisation de virement en attente des clients de son institution.
- Si la demande est approuvée, la permission de virement est débloquée pour le client et celui-ci en est notifié.
- Si la demande est refusée, la fonctionnalité de virement reste verrouillée pour ce client et celui-ci est averti du refus par une notification.

#### 4. Feature : Visualisation, filtrage, export et import

##### US30 - Consultation et filtrage des clients et des produits
En tant qu'employé connecté d'une institution financière,  
je veux lister et filtrer l'ensemble des clients et produits financiers de mon institution,  
afin d'accéder rapidement aux informations de nos comptes.

**Critères d'acceptation :**

- L'employé peut consulter l'entièreté des clients liés à son institution et des produits financiers associés.
- L'interface fournit des outils de recherche et de filtrage permettant de combiner :
  - La recherche par nom complet ou nom partiel du client.
  - Le filtrage par type de produit financier (compte courant, épargne, terme,...).
  - La recherche par code unique ou code partiel du produit (IBAN).
  - Le filtrage par date ou période de création du produit financier.
- Les données affichées se mettent à jour dynamiquement selon les filtres appliqués.
- L'employé ne peut consulter aucun produit lié à une autre institution.

##### US31 - Exportation des données clients et produits de l'institution
En tant qu'employé connecté d'une institution financière,  
je veux exporter la liste filtrée des clients et des produits de notre institution aux formats CSV et JSON,  
afin de conserver nos données en dehors de l'application.

**Critères d'acceptation :**

- L'interface propose des options de téléchargement aux formats standard CSV et JSON.
- Le fichier exporté contient exactement les données correspondant aux filtres sélectionnés.

##### US32 - Importation de données et peuplement de la base de données
En tant qu'employé connecté d'une institution financière,  
je veux importer un fichier de données (CSV ou JSON) dans l'application,  
afin d'initialiser ou de mettre à jour la base de données de notre institution sans devoir le faire à la main.

**Critères d'acceptation :**

- L'employé peut charger un fichier de données au format CSV ou JSON.
- Si le fichier contient des données liées à une autre institution financière, l'importation est rejetée avec un message d'erreur.
- Si le fichier est valide, les données sont enregistrées et la liste des clients/produits est immédiatement mise à jour dans l'application.

