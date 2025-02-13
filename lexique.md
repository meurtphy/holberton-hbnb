📘 Doc Technique HBnB
📝 Introduction
Ce document décrit l’architecture technique du projet HBnB. Il comprend les principaux diagrammes UML et leurs explications pour structurer l’application et faciliter son développement.

🏗️ Architecture
🔹 Vue d’Ensemble
L’application HBnB repose sur une architecture modulaire comprenant :

Une API REST (Flask) pour gérer les interactions utilisateur
Une couche de logique métier pour appliquer les règles et contraintes
Un système de persistance SQLAlchemy pour la gestion des données
🔹 Logique Métier
Les principales entités du projet et leurs opérations :

🧑 User (Gestion des utilisateurs)
create_user(data): Crée un nouvel utilisateur
get_user(user_id): Récupère un utilisateur
update_user(user_id, data): Met à jour un utilisateur
delete_user(user_id): Supprime un utilisateur
🏡 Place (Gestion des lieux)
create_place(data): Ajoute un lieu
get_place(place_id): Récupère un lieu
update_place(place_id, data): Met à jour un lieu
delete_place(place_id): Supprime un lieu
📝 Review (Gestion des avis)
add_review(data): Ajoute un avis
get_review(review_id): Récupère un avis
update_review(review_id, data): Met à jour un avis
delete_review(review_id): Supprime un avis
🏨 Amenity (Services et équipements)
add_amenity(data): Ajoute un service
get_amenity(amenity_id): Récupère un service
update_amenity(amenity_id, data): Met à jour un service
delete_amenity(amenity_id): Supprime un service
🗂️ Persistance des Données
Gestion des données via SQLAlchemy avec :

Relations entre les entités pour assurer l’intégrité
Opérations CRUD :
save(): Sauvegarde un objet
delete(): Supprime un objet
query.all(): Récupère tous les objets
query.filter_by(): Recherche selon un critère
📊 Diagrammes UML
📦 Diagramme de packages : Vue des différentes couches et modules
🛠️ Diagramme de classes : Définition des entités et relations
🔄 Diagrammes de séquence : Flux des interactions API
🎯 Objectifs
✔️ Clarifier l’architecture
✔️ Optimiser la communication entre les couches
✔️ Faciliter la maintenance et l’évolution du projet

📖 Lexique
API REST : Interface permettant la communication entre applications via HTTP
Flask : Framework web Python utilisé pour l’API
SQLAlchemy : ORM pour gérer la base de données en objets Python
Encapsulation : Principe OOP regroupant données et méthodes associées
Persistance des données : Stockage et récupération d’informations en base
Modularité : Séparation des fonctionnalités en composants indépendants
