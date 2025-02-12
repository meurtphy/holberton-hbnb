diagramme de paquetage qui représente l’architecture en trois couches de l’application HBnB Evolution, en intégrant le patron de conception Façade pour gérer les interactions entre ces couche


🚀 Étapes à suivre :
1️⃣ Comprendre l’architecture en trois couches
L’application suit une architecture multi-couches pour bien séparer les responsabilités :

Couche Présentation (Presentation Layer) :
Contient les API et Services qui permettent aux utilisateurs d'interagir avec l'application.
Exemples : UserService, PlaceService, ReviewService
Couche Métier (Business Logic Layer) :
Gère la logique métier et les modèles des entités (User, Place, Review, Amenity).
C’est ici que les règles de validation et de gestion des objets sont appliquées.
Couche de Persistance (Persistence Layer) :
Responsable de la gestion des données (base de données, requêtes).
Utilise des DAO (Data Access Objects) ou Repositories pour interagir avec la base.


2️⃣ les composants clés
Vous devez représenter les trois couches et leurs composants principaux :

✅ Couche Présentation (Presentation Layer) :
UserService
PlaceService
ReviewService
AmenityService
API Controller
✅ Couche Métier (Business Logic Layer) :
User
Place
Review
Amenity
Facade (interface entre la Présentation et la Persistance)
✅ Couche de Persistance (Persistence Layer) :
UserDAO
PlaceDAO
ReviewDAO
AmenityDAO
Database