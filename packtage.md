1️⃣ Comprendre l’architecture en trois couches
L'application HBnB suit une architecture en couches, ce qui signifie que le code est organisé en plusieurs niveaux distincts, chacun ayant une responsabilité spécifique.

Présentation (Presentation Layer) : C'est l’interface avec l'utilisateur, via les services et les API.
Logique métier (Business Logic Layer) : Contient les modèles et les règles métier (ex. : gestion des utilisateurs, des lieux, des avis…).
Persistance (Persistence Layer) : Responsable du stockage et de l’accès aux données via une base de données.
La Facade Pattern est utilisée pour simplifier la communication entre ces couches.




2️⃣ Représenter ces couches dans un diagramme de packages UML
Le diagramme de packages sert à visualiser les différentes parties de l’application et leurs relations.
///////////////
image[diagramme.de.packages.UML.1.pdf](https://github.com/user-attachments/files/18780154/diagramme.de.packages.UML.1.pdf)

////////////////////


3️⃣ Détails de chaque couche
Presentation Layer (Couche Présentation)
📌 Contient l’API et les services exposés aux utilisateurs.
🔹 Exemples : Flask API, REST API, GraphQL.

Business Logic Layer (Couche Logique Métier)
📌 Contient les classes métiers qui gèrent les entités et la logique du programme.
🔹 Exemples : User, Place, Review, Amenity.

Persistence Layer (Couche de Persistance)
📌 Gère la communication avec la base de données.
🔹 Exemples : SQLAlchemy, DatabaseAccess.

4️⃣ Explication du modèle Facade
Le modèle de conception Facade est utilisé ici pour simplifier l’accès aux différentes couches :

La Présentation ne communique pas directement avec la Persistance.
Tout passe par la Logique Métier, qui fait office d’interface unique (Facade).
Pourquoi utiliser Facade ? ✅ Encapsulation : Cache la complexité interne.
✅ Simplicité : Fournit une interface unique pour chaque couche.
✅ Maintenance facile : Permet de modifier une couche sans impacter directement les autres.







Explication du modèle Facade
Le modèle de conception Facade est utilisé ici pour simplifier l’accès aux différentes couches :

La Présentation ne communique pas directement avec la Persistance.
Tout passe par la Logique Métier, qui fait office d’interface unique (Facade).
Pourquoi utiliser Facade ? ✅ Encapsulation : Cache la complexité interne.
✅ Simplicité : Fournit une interface unique pour chaque couche.
✅ Maintenance facile : Permet de modifier une couche sans impacter directement les autres.
