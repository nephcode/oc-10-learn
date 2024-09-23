![Cover](https://kpkfzczpavanzocxzyta.supabase.co/storage/v1/object/public/oc-react/readme-header-oc-react-10.png)

<!-- ∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴∵ ƸӜƷ ∴ -->

# USER STORIES LEARN@HOME

**[Gherkin]** les priorités d'urgence, les difficultés techniques, et les allocations front-end/back-end, ainsi que la nécessité de validation par le client. Les tâches sont aussi associées aux phases du kanban et incluent des tags pour faciliter la gestion.

## User Story 1: Connexion utilisateur (Front-end)
**Priorité**: Haute.  
**Difficulté technique**: Moyenne.  
**Validation par le client**: Oui. 

### Feature Page de connexion
 En tant qu'élève ou bénévole,   
 Je veux me connecter à mon compte,    
 Afin d'accéder aux fonctionnalités du site.

|Scenario |  Connexion réussie|
|---  		|---					|
|Given 	| un utilisateur valide avec ses identifiants|
|When		| l'utilisateur entre son email et mot de passe corrects|
|Then 		| il est redirigé vers la page Tableau de bord|

|  Scenario| Mot de passe oublié|
|---  		|---					|
|Given| un utilisateur qui a oublié son mot de passe
|    When |il clique sur le lien "Mot de passe oublié"
|    Then |il reçoit un email pour réinitialiser son mot de passe.
    
|Scenario | Connexion SSO |
|---  		|---					|
|    Given |un utilisateur choisi|
|    When |il valide son identité SSO|
|    Then| il reçoit un email pour réinitialiser son mot de passe.|
    
    
**Phase Kanban:** backlog  
**Tags:** `connexion` `sécurité` `front-end`  
**Validation par le client:** Oui 

### Critères d'acception

- La page doit comporter deux champs : un pour saisir un identifiant et un
autre pour saisir un mot de passe.
- La page doit afficher une erreur si lʼon clique sur le bouton de connexion sans remplir les champs.
- La page doit afficher une erreur si au moins un des deux champs nʼest pas rempli.
- La page doit afficher une erreur si le compte email saisi nʼexiste pas dans la base de données.
- La page doit afficher une erreur si le compte email saisi existe bien dans la base de données mais que le mt de passe saisi est erroné.
- La page doit inclure un bouton pour se connecter et qui redirige vers le tableau de bord si les identifiants saisis sont valides.
- La page doit contenir un lien pour récupérarer son mot de passe oublié.
- La page doit contenir un lien vers une page de création de compte pour les nouveaux utilisateurs.

## User Story 2: Interface de chat (Front-end/Back-end)
**Priorité** Moyenne.  
**Difficulté technique** Élevée.  
**Validation par le client** Oui.  

### Feature Interface de chat
En tant qu'élève ou bénévole,   
Je veux discuter avec mon tuteur ou élève,   
Afin d'échanger des informations en temps réel.

|  Scenario| Envoyer un message
|---  		|---					|
|Given |un utilisateur connecté
|    When |il tape un message dans l'interface de chat et clique sur envoyer|
|    Then |le message apparaît dans la conversation et est horodaté|

|  Scenario| Indicateur de lecture|
|---  		|---					|
|Given |un message envoyé|
|When| le destinataire a lu le message|
|Then |un indicateur "lu" apparaît à côté du message|
    
**Phase Kanban:** analyze.  
**Tags:** `chat` `messagerie` `temps réel`.  
**Validation par le client:** Oui

### Critères d'acceptation
- L'interface doit permettre l'envoi et la réception de messages
instantanément.
- Chaque message doit afficher la photo de profil de l'expéditeur.
Un indicateur de lecture doit montrer si le message a été lu.
- L'horodatage doit être visible pour chaque message.
- Les utilisateurs doivent pouvoir ajouter ou supprimer des contacts.
- Les utilisateurs doivent pouvoir accéder facilement à l'historique complet des conversations avec chaque contact.

## User Story 3: Gestion des tâches (Back-end)
**Priorité:** Basse.  
**Difficulté technique:** Moyenne.  
**Validation par le client:** Oui

### Feature Gestion des tâches (Bénévole)
En tant que bénévole,   
Je veux créer des tâches pour l'élève que je suis,   
Afin de l'aider à mieux organiser son travail.   

|Scenario| Ajouter une tâche
|---  		|---					|
|Given |un bénévole connecté|
|    When| il crée une nouvelle tâche pour l'élève|
|    Then| la tâche apparaît dans la liste de tâches de l'élève|

|  Scenario| Modifier une tâche|
|---  		|---					|
|Given| un bénévole connecté|
|When |il modifie une tâche pour l'élève|
|    Then |la tâche est mise à jour de la liste de l'élève|

|  Scenario| Supprimer une tâche|
|---  		|---					|
|Given| un bénévole connecté|
|When |il supprime une tâche pour l'élève|
|    Then |la tâche disparaît de la liste de l'élève|


### Feature Gestion des tâches (élève)
|  Scenario| gérer une tâche|
|---  		|---					|
|Given| un élève connecté|
|When |il crée une tâche |
|Then |la tâche apparait sa la liste |
|**And** |il modifie une tâche |
|Then |la tâche se met à jour de la liste |
|**And** |il supprime une tâche |
|Then |la tâche disparaît de sa liste|

**Phase Kanban:** develop  
**Tags:** `gestion des tâches` `backend`, `élève`  
**Validation par le client:** Oui 

### Critères d'acceptation
- Les élèves peuvent créer des tâches uniquement pour eux-mêmes.
- Les tuteurs bénévoles peuvent créer des tâches pour eux-mêmes et pour les élèves qu'ils suivent.
- Les tâches doivent inclure un titre, une description, une date d'échéance, et une option pour marquer la tâche comme complétée.
- Les utilisateurs (élèves et tuteurs) doivent pouvoir afficher la liste des tâches.
- Les utilisateurs (élèves et tuteurs) doivent pouvoir supprimer une tâche.
 
## User Story 4: Calendrier (Front-end)
**Priorité:** Haute.  
**Difficulté technique:** Moyenne.  
**Validation par le client:** Oui.  

###Feature: Calendrier des rendez-vous
En tant qu'élève ou bénévole,   
Je veux voir mes rendez-vous hebdomadaires,   
Afin de m'organiser pour mes sessions d'apprentissage.  

|Scenario| Affichage des événements|
|---  		|---					|
|Given| un utilisateur connecté,
|When |il ouvre la page calendrier,
|Then |il voit la liste de ses rendez-vous planifiés pour la semaine.
    
**Phase Kanban:** backlog.  
**Tags:** `calendrier` `rendez-vous` `front-end`.  
**Validation par le client:** Oui

### Critères d'acceptation
- Le calendrier doit afficher tous les événements et rendez-vous de
l'utilisateur.
- Les utilisateurs doivent pouvoir ajouter et supprimer des événements dans leur propre calendrier.
- Un évènement doit être visible dans le calendrier sʼil a été ajouté.
- Un événement doit être masqué dans le calendriersʼil a été supprimé.
 
## User Story 5: Dashboard (Front-end/Back-end)
**Priorité:** Haute.  
**Difficulté technique:** Élevée.  
**Validation par le client:** Oui.  


### Feature: Tableau de bord
En tant qu'élève ou bénévole,    
Je veux avoir un récapitulatif des tâches et des événements,   
Afin de gérer efficacement mes activités.

|Scenario| Affichage des tâches|
|---  		|---					|
|Given |un utilisateur connecté
|When |il ouvre le tableau de bord
|Then| il voit la liste de ses tâches à faire provenant de la page gestion des tâches.

|Scenario| Affichage des événements à venir|
|---  		|---					|
|Given | un utilisateur connecté
|When| il consulte le tableau de bord
|Then| il voit un récapitulatif des prochains événements tirés du calendrier.
    
**Phase Kanban:** develop.  
**Tags:** `tableau de bord` `récapitulatif` `front-end` `back-end`  
**Validation par le client:** Oui

### Critères d'acceptation
- Le tableau de bord doit afficher un liste des tâches à faire(to-do list).
- Il doit lister les événements à venir tirés du calendrier.
- Il doit montrer un compteur de messages non lus.
- Chaque élément sur le tableau de bord doit être cliquable et rediriger vers la page correspondante (gestion des tâches, calendrier, chat).
- Si l'utilisateur est un tuteur bénévole, le tableau de bord doit inclure une section distincte ou un filtre pour afficher les tâches de ses élèves.

![Cover](https://kpkfzczpavanzocxzyta.supabase.co/storage/v1/object/public/oc-react/readme-footer-oc-react-10.png)