:blue_book: Doc Technique HBnB
:memo: Introduction
Ce document sert de guide technique pour l’implémentation du projet HBnB. Il compile les principaux diagrammes UML et leurs explications afin de structurer l’architecture de l’application et de faciliter son développement.
:building_construction: Architecture
:one: Vue d’Ensemble
L’application HBnB repose sur une architecture modulaire comprenant :
Une API REST (Flask) pour gérer les interactions utilisateur
Une couche de logique métier pour appliquer les règles et contraintes
Un système de persistance basé sur SQLAlchemy
:two: Logique Métier
La gestion des principales entités du projet :
User : Gestion des utilisateurs
create_user(data): Crée un nouvel utilisateur
get_user(user_id): Récupère les informations d’un utilisateur
update_user(user_id, data): Met à jour les informations d’un utilisateur
delete_user(user_id): Supprime un utilisateur
Place : Référencement des lieux
create_place(data): Ajoute un nouveau lieu
get_place(place_id): Récupère les détails d’un lieu
update_place(place_id, data): Met à jour un lieu
delete_place(place_id): Supprime un lieu
Review : Avis et notes
add_review(data): Ajoute un avis
get_review(review_id): Récupère un avis
update_review(review_id, data): Met à jour un avis
delete_review(review_id): Supprime un avis
Amenity : Services et équipements
add_amenity(data): Ajoute un service
get_amenity(amenity_id): Récupère un service
update_amenity(amenity_id, data): Met à jour un service
delete_amenity(amenity_id): Supprime un service
:three: Persistance des Données
Communication avec la base de données via SQLAlchemy
Gestion des relations entre les entités
Fonctions clés :
save(): Sauvegarde un objet en base de données
delete(): Supprime un objet
query.all(): Récupère tous les objets d’un type donné
query.filter_by(): Recherche un objet selon un critère
:bar_chart: Diagrammes UML
Diagramme de packages : Vue d’ensemble des différentes couches et modules
Diagramme de classes : Définition des entités et de leurs relations
Diagrammes de séquence : Visualisation des flux d’interactions API
:dart: Objectif
Fournir une vue claire et détaillée de l’architecture
Optimiser la communication entre les différentes couches
Faciliter la maintenance et l’évolution du projet grâce à une conception robuste
:white_check_mark: Encapsulation :white_check_mark: Simplicité :white_check_mark: Maintenance
:book: Lexique
API REST : Interface permettant la communication entre différentes applications via des requêtes HTTP.
Flask : Framework web léger en Python utilisé pour construire l’API du projet.
SQLAlchemy : ORM (Object Relational Mapper) permettant d’interagir avec la base de données en utilisant des objets Python.
Diagramme de packages : Représentation des différentes couches logicielles et leur organisation.
Diagramme de classes : Schéma illustrant les entités du projet et leurs relations.
Diagramme de séquence : Illustration des échanges entre les différents composants du système.
ORM : Technique de programmation permettant de manipuler une base de données via des objets plutôt qu’avec du SQL brut.
Encapsulation : Principe de programmation orientée objet qui consiste à regrouper les données et les méthodes qui les manipulent dans une seule unité.
Persistance des données : Stockage et récupération des informations dans une base de données pour assurer leur conservation.
Modularité : Conception logicielle favorisant la séparation des fonctionnalités en modules indépendants.