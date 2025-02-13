🎯 Objectif
Visualiser le flux d'interaction entre les couches :

🖥️ Présentation (Services/API)
⚙️ Business Logic (Modèles)
🗂️ Persistence (Base de données)
🛠️ Les 4 appels API à modéliser :
Inscription d'un utilisateur
Création d'un lieu (Place)
Soumission d'un avis (Review)
Récupération d'une liste de lieux
🔍 1️⃣ Inscription d'un utilisateur (User Registration)
📑 Description :
Un nouvel utilisateur remplit un formulaire d'inscription et crée un compte.

🔹 Participants :

Client (utilisateur)
API (endpoint d'inscription)
UserService (gestion de la logique métier)
UserRepository (gestion de la persistance en base)
🔹 Flux :

Le Client envoie une requête d'inscription.
L'API valide les données et transmet au UserService.
Le UserService applique les règles métier (email unique, mdp sécurisé).
Le UserService demande au UserRepository d'insérer les données.
Le UserRepository sauvegarde les données et confirme.
L'API retourne la réponse au Client.



🏡 2️⃣ Création d'un lieu (Place Creation)
📑 Description :
Un utilisateur connecté crée une nouvelle annonce.

🔹 Participants :

Client (utilisateur)
API (endpoint de création de lieu)
PlaceService (logique métier)
PlaceRepository (persistance des données)
🔹 Flux :

Le Client envoie une demande de création avec les détails du lieu.
L'API transmet au PlaceService.
Le PlaceService vérifie la validité des données.
Le PlaceRepository insère les données.
La réponse est renvoyée au Client.


✍️ 3️⃣ Soumission d'un avis (Review Submission)
📑 Description :
Un utilisateur connecté laisse un avis sur un lieu.

🔹 Participants :

Client (utilisateur)
API (endpoint d'ajout d'avis)
ReviewService (logique métier)
ReviewRepository (persistance des avis)
🔹 Flux :

Le Client soumet un avis.
L'API valide et transmet au ReviewService.
Le ReviewService vérifie la cohérence des données.
Le ReviewRepository enregistre l'avis.
La réponse est renvoyée au Client.

🔍 4️⃣ Récupération d'une liste de lieux (Fetching Places)
📑 Description :
Un utilisateur souhaite afficher les lieux correspondant à certains critères.

🔹 Participants :

Client (utilisateur)
API (endpoint de recherche de lieux)
PlaceService (logique métier)
PlaceRepository (accès aux données)
🔹 Flux :

Le Client envoie une requête avec les filtres (prix, localisation).
L'API transmet au PlaceService.
Le PlaceService interroge le PlaceRepository.
Le PlaceRepository retourne la liste.
L'API envoie la réponse au Client.


🧠 Points Clés
✅ Séparation des responsabilités : Chaque couche a son rôle précis (API, logique, persistance).
✅ Flux logique : Chaque diagramme suit un schéma cohérent d'interactions.
✅ Simplicité : Les interactions sont faciles à comprendre et lisibles via Mermaid.js.

Si tu as besoin d'un README.md pour expliquer ces diagrammes, dis-le-moi ! 😊
