Documentation Technique du Projet HBnB
1. Introduction
Contexte :
HBnB est une application simplifiée de type AirBnB permettant à des utilisateurs de gérer des lieux (places), de laisser des avis (reviews), et de gérer les commodités (amenities). Le projet suit une architecture en couches (Presentation, Business Logic, Persistence), afin de séparer clairement les responsabilités et de faciliter la maintenance et l’évolutivité de l’application.

Objectif du Document :
Ce document fournit une vue d’ensemble de l’architecture et de la conception du système. Il sert de référence pour l’implémentation et inclut :

Un diagramme de packages illustrant l’architecture haute-niveau.
Un diagramme de classes décrivant la logique métier (Business Logic).
Plusieurs diagrammes de séquence montrant comment les différentes couches interagissent pour répondre à des appels API précis.
2. Architecture Haute-Niveau
2.1. Diagramme de Packages
(Si tu as déjà un diagramme de packages, insère-le ici. Sinon, voici un exemple générique en Mermaid.js)

inserez packtage ????????

PresentationLayer --> BusinessLogicLayer : utilise (Facade)
BusinessLogicLayer --> PersistenceLayer : utilise (DAO/Repository)
Explications :

PresentationLayer : Gère l’interaction avec le client (front-end ou application externe). Ici, on y trouve l’API REST, les contrôleurs, etc.
BusinessLogicLayer : Contient les règles métiers, les services et les modèles de domaine (User, Place, Review, Amenity).
PersistenceLayer : Responsable de la persistance des données (accès à la base de données, requêtes CRUD, etc.).
Le Facadé Pattern (ou façade) est utilisé pour exposer un point d’entrée unique depuis la couche Présentation vers la couche Business Logic, simplifiant ainsi l’interaction et masquant la complexité interne.

(Si tu as déjà un diagramme de packages fourni dans tes captures, place-le et adapte les explications en fonction de tes noms de packages.)

3. Détail de la Logique Métier (Business Logic)
3.1. Diagramme de Classes
Voici un exemple de diagramme de classes basé sur les entités clés : User, Place, Review, Amenity. (Ton screenshot en montre un similaire, tu peux l’insérer directement.)

inserer diagramme de classe ?.?????

User 1..–0..n Place (un user peut posséder plusieurs places, une place est associée à un seul user propriétaire).
Place 1..–0..n Review (une place peut avoir plusieurs reviews, une review est associée à une place).
User 1..–0..n Review (un user peut poster plusieurs reviews, une review appartient à un seul user).
Place 0..n–0..n Amenity (relation plusieurs-à-plusieurs : un lieu peut avoir plusieurs commodités, et une commodité peut appartenir à plusieurs lieux).
(Adapte les relations et la cardinalité selon ton besoin exact.)

4. Diagrammes de Séquence (API Interaction Flow)
Selon les consignes, il est recommandé de présenter quatre diagrammes de séquence pour les appels API majeurs :

Inscription d’un utilisateur
Création d’un lieu (Place)
Soumission d’une review
Récupération d’une liste de lieux (Places)
Tu as déjà fourni un diagramme de séquence pour la récupération d’une liste de places (GET /api/places?price=100&city=Paris). Ci-dessous, je l’intègre et je commente.
(Les 3 autres diagrammes peuvent être construits sur le même modèle.)

4.1. Récupération d’une liste de places

inserer les 4????????????

Description du flux :

Client envoie une requête GET sur /api/places?price=100&city=Paris.
API reçoit la requête et appelle la méthode getPlaces(filters) de la couche Service (ici, PlaceService).
PlaceService traite la logique métier, formate les filtres, et appelle fetchPlaces(filters) sur le PlaceRepository (couche Persistance).
PlaceRepository interroge la base de données et retourne la liste des places correspondantes.
PlaceService reçoit cette liste, applique éventuellement une dernière logique (tri, vérification, etc.), et la renvoie à l’API.
API envoie la réponse 200 OK au Client avec la liste des places.
Remarques :

Le diagramme montre clairement la séparation entre API, Service et Repository.
Les flèches à sens unique indiquent les appels de méthodes ou de fonctions.
Les retours (messages en pointillés) indiquent la réponse ou la valeur de retour.
4.2. Exemple : Inscription d’un Utilisateur
(Exemple en pseudo-Mermaid si tu veux un squelette)


Idée de description :

Le Client envoie une requête POST avec les informations d’utilisateur (email, password, etc.).
L’API valide le format et appelle registerUser(userData) sur la couche Service (UserService).
UserService applique les règles métiers (hash du mot de passe, validations, etc.) puis enregistre le nouvel utilisateur en base via UserRepository.
Le UserRepository renvoie l’objet utilisateur créé.
UserService le renvoie à l’API, qui envoie la réponse 201 Created au Client.
4.3. Exemple : Création d’un Lieu (Place)
(Même principe : Client -> API -> PlaceService -> PlaceRepository -> etc.)

4.4. Exemple : Soumission d’une Review
(Même principe : Client -> API -> ReviewService -> ReviewRepository -> etc.)

5. Conclusion
Dans ce document, nous avons présenté :

L’architecture en couches du projet HBnB et la logique d’interaction via un facade pattern.
Le diagramme de classes décrivant les entités principales (User, Place, Review, Amenity) et leurs relations.
Les diagrammes de séquence illustrant comment le client interagit avec l’API et comment les couches s’échangent des informations.
Perspectives :

Ce document servira de référence tout au long du développement.
Il pourra être mis à jour à mesure que l’application évolue (nouvelles fonctionnalités, refactorisations, etc.).
Il est essentiel de maintenir la cohérence entre la documentation et le code pour éviter toute divergence et faciliter la maintenance