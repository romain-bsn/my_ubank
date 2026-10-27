**UE :** S-INFO-015 Projet d'analyse et de conception logicielle  
**Année académique :** 2026-2027  
**Groupe :** G02
**Responsable de l'extension :** Vandooren Romain (Matricule : 251074)

### Gestion des placements :

*Note :* Le terme « client investisseur » est défini comme un client ayant un profil d'investisseur valide. Cette forme est utilisée par simplicité d'écriture dans les user stories ci-dessous.

##### US1 - Demander l'ouverture d'un compte-titre
En tant que utilisateur connecté,  
je veux ouvrir un compte titre  
afin de réaliser des placements financiers.

**Critères d’acceptation :**

- Le compte-titre du client doit être lié à un de ses comptes courants
- Ce compte-titre peut gérer plusieurs devises en allouant un compartiment pour chaque devise
- Au sein d'un compartiment d'une devise, uniquement les placements utilisant cette devise y seront accessibles

##### US2 - Remplir / modifier le formulaire de profil d'investisseur
En tant que client investisseur  
je souhaite remplir un formulaire  
afin de définir mon profil d'investisseur (conservateur, défensif, neutre, dynamique, agressif)

**Critères d’acceptation :**

- A tout moment le formulaire peut être repassé par le client afin de modifier son profil
- Le formulaire évalue la situation financière, le risque que le client est prêt à prendre et son horizon de placement (en années).
- Le profil bloque tout nouvel achat de produit boursier dont le risque est plus élevé que celui configuré par le profil
- Le formulaire doit être envoyé vers le serveur et être validé par l'institution financière
- Le profil est attribué par l'institution financière

##### US3 - Acheter des produits financiers
En tant que client ayant un profil d'investisseur,  
je veux acheter des produits financiers  
afin d'enrichir mon compte-titre.

**Critères d’acceptation :**

- L'interface doit verrouiller l'achat et la visibilité des produits financiers dont le risque est strictement supérieur au profil du client
- Les potentiels frais d'investissement et autres coûts liés sont inclus dans l'achat

##### US4 - Consulter les placements réalisés du compte-titre
En tant que client investisseur,  
je souhaite visualiser mes placements réalisés triés par type  
afin de suivre l'évolution de mes investissements.

**Critères d’acceptation :**

- Pour chaque placement, l'interface affiche Nom, ISIN, Date achat, Date expiration (si existe), Quantité, Prix d'achat, Valeur actuelle, rendement, poids relatif dans le compte titre et dans le portefeuille global.

##### US5 - Vendre des placements financiers
En tant que client investisseur,  
je souhaite vendre les placements de mon compte titre  
afin d'obtenir de l'argent.

**Critères d’acceptation :**

- L'argent de la vente doit être placé sur un compte courant du client
- Les taxes, frais de ventes et autres coûts liés doivent être inclus dans le processus de vente

##### US6 - Comparer avec un portefeuille de référence
En tant que client investisseur  
je souhaite voir un portefeuille de référence basé sur mon profil d'investisseur  
afin de comparer la performance et la diversification de mon portefeuille actuel.

**Critères d’acceptation :**

- Un compte titre fictif doit être généré pour l'investisseur basé sur son profil de risque.
- L'interface doit dédier une vue pour comparer le portefeuille réel et le portefeuille de référence.

##### US7 - Consulter l'historique des prix et statistiques d'un produit
En tant que client investisseur,  
je souhaite apercevoir l'historique des prix d'un produit à plusieurs échelles de temps (D, W, M, 3M, 6M, YTD, 1Y, 5Y, MAX) sous forme d'un graphique et de statistiques  
afin de pouvoir réaliser un investissement éclairé.

**Critères d’acceptation :**

- Les données du produit boursier proviennent d'une API externe
- Les données doivent être stocké dans le base de donnée
- Les données doivent être mises à jour automatiquement régulièrement.

##### US8 - Exporter les données du compte-titre
En tant que client investisseur,  
je souhaite visualiser sous formes de graphique, exporter l'ensemble des données ou une partie/période spécifique de mon portefeuille boursier  
afin d'analyser mes performances en dehors de l'application.

**Critères d’acceptation :**

- L'interface présente des vues en tableaux de données et en graphiques.
- Le client peut filtrer une période spécifique, une partie spécifique (par type de placement) ou regarder l'ensemble des données.
- L'exportation peut se réaliser dans plusieurs formats différents (PDF, CSV)

##### US9 - Percevoir les dividendes, intérêts et remboursements à terme
En tant que client investisseur,  
je souhaite percevoir automatiquement les dividendes de mes actions, les intérêts de mes obligations et le remboursement de mes placements à terme  
afin de fructifier mon patrimoine financier.

**Critères d’acceptation :**

- Les dividendes et intérêts sont versés automatiquement sur le compte courant lié au compte titre à échéance ou à intervalle régulier selon le type de placement
- Les prélèvement fiscaux liés aux revenus du capital sont automatiquement prélevés à la source si applicable
- Lors de l'expiration d'un bon de caisse ou d'une obligation le montant investi est automatiquement reversé sur le compte courant lié au compte titre

##### US10 - Valider et attribuer le profil d'investisseur
En tant qu'employé d'une institution financière,  
je souhaite analyser les formulaires soumis par mes clients  
afin de leur attribuer un profil d'investisseur

**Critères d’acceptation :**

- L'employé a accès à chaque formulaire soumis par les clients de son institution financière
- L'employé en fonction des réponses du formulaire soumis attribue un profil d'investisseur au client qui a soumis celui-ci
- Une fois le formulaire validé, le formulaire soumis est archivé et le profil d'investisseur est appliqué au client

##### US11 - Consulter les comptes-titres des clients de l'institution
En tant qu'employé d'une institution financière,  
je souhaite visualiser la liste des comptes-titres et leur contenu  
afin de conseiller au mieux mes clients.

**Critères d’acceptation :**

- L'employé a uniquement accès aux comptes-titres des clients de l'institution financière où il travaille
- L'interface de visualisation du compte-titre est identique à celle du client qui le détient
- L'employé peut rechercher les comptes titres à l'aide de multiples critères (nom du titulaire, type de placement, compartiment de devise, etc...)
