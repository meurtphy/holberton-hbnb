📘 Documentation Technique du Projet HBnB

🟡 1. Introduction

📝 Contexte

HBnB est une application simplifiée de type AirBnB, conçue pour permettre aux utilisateurs de gérer :

Des lieux (Places) : création, mise à jour, suppression et consultation.

Des avis (Reviews) : soumission, modification et suppression.

Des commodités (Amenities) : gestion des équipements associés aux lieux.

L'application repose sur une architecture en couches (3-tier) :

Presentation Layer (Interface utilisateur et API)

Business Logic Layer (Règles métiers et services)

Persistence Layer (Stockage et gestion des données)

Cette approche modulaire facilite la maintenance, l'évolutivité et la réutilisation des composants.

🎯 Objectif du Document

Ce document constitue une référence technique pour guider les phases d'implémentation. Il contient :✅ Un diagramme de packages présentant l'architecture globale (haute-niveau).✅ Un diagramme de classes décrivant la couche métier et les relations entre les entités principales.✅ Des diagrammes de séquence illustrant les interactions entre les couches pour différents appels API.

🟠 2. Architecture Haute-Niveau (Diagramme de Packages)

📊 2.1. Diagramme de Packages

![diagramme_packages_1](https://github.com/user-attachments/assets/a5794080-6db7-4d30-b37d-4b65d5dee46e)


Explications des couches principales :

PresentationLayer :Gère l'interaction avec les utilisateurs (front-end, API REST). Cette couche contient :

Les API Controllers (points d'entrée des requêtes)

Les Services exposés via l'API.

BusinessLogicLayer :Responsable de l'application des règles métiers. Elle contient :

Les entités principales (User, Place, Review, Amenity)

Les services métiers (UserService, PlaceService, ReviewService, AmenityService)

PersistenceLayer :Gère la sauvegarde et la récupération des données. Elle contient :

Les DAO (Data Access Objects) pour chaque entité.

La base de données.

🧩 Pattern utilisé :Le Facade Pattern est appliqué pour simplifier les interactions entre la couche Présentation et la couche Business Logic. Cette approche permet de masquer la complexité interne et de centraliser les points d'entrée.

🟢 3. Détail de la Logique Métier (Diagramme de Classes)

📊 3.1. Diagramme de Classes

![diagramme_classes_1](https://github.com/user-attachments/assets/3dc948ec-7ad9-4c08-8218-a79871c66f73)



Principales Entités et Relations :

User

Possède plusieurs Places (1 utilisateur → plusieurs lieux).

Peut laisser plusieurs Reviews (1 utilisateur → plusieurs avis).

Place

Appartient à un seul User (propriétaire).

Possède plusieurs Reviews (1 lieu → plusieurs avis).

Possède plusieurs Amenities (relation plusieurs-à-plusieurs).

Review

Appartient à un User et concerne un Place.

Amenity

Peut être associée à plusieurs Places (relation plusieurs-à-plusieurs).

✅ Pattern clé utilisé : L'association Place - Amenity utilise une relation Many-to-Many via une table de liaison.

🟤 4. Diagrammes de Séquence (API Interaction Flow)

📌 Diagrammes attendus :



📊 4.1. Récupération d'une Liste de Lieux
![DiagrammeFetching a List of Places drawio](https://github.com/user-attachments/assets/803026d1-6902-4c22-91a1-48f069978915)



Description du Flux :

Client : Envoie une requête GET avec des filtres (ex. /api/places?price=100&city=Paris).

API : Reçoit la requête et appelle getPlaces(filters) de PlaceService.

PlaceService : Traite les filtres et appelle fetchPlaces(filters) de PlaceRepository.

PlaceRepository : Interroge la base de données et retourne la liste des lieux.

PlaceService : Traite les résultats (ex. trie, pagine) et renvoie la liste à l'API.

API : Envoie une réponse 200 OK avec la liste des lieux au Client.

Remarques :

✅ Les flèches pleines indiquent des appels de méthode.

✅ Les flèches pointillées indiquent les réponses.

✅ Le Service centralise la logique métier (applique des filtres, formats, etc.).

📊 4.2. Inscription d'un Utilisateur (Exemple en pseudo-Mermaid)

![DiagrammeUser Registration drawio](https://github.com/user-attachments/assets/47c927e7-cb15-491e-bf09-3ccd019d84af)

![DiagrammePlace Creation drawio](https://github.com/user-attachments/assets/4ed27a07-37e2-4f2a-ab10-778a8081d9c4)
![DiagrammeReview Submission drawio](https://github.com/user-attachments/assets/e225dfb1-c2af-4d22-9502-58c310d0119d)

Étapes clés :

Client : Envoie les informations (email, mot de passe) via l'API.

UserService : Valide, hash le mot de passe, enregistre l'utilisateur.

UserRepository : Effectue l'insertion dans la base.

API : Retourne la confirmation (201 Created).

🟣 5. Conclusion

📝 Synthèse : Ce document a exposé l'architecture, les entités principales et le flux des appels API.

🔄 Mises à jour : Ce document évoluera selon l'ajout de nouvelles fonctionnalités.

🛡️ Bonnes pratiques : Maintenir la cohérence avec le code et suivre les principes SOLID.
