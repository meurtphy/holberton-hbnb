# holberton-hbnb
Qu’est-ce que UML et pourquoi l’utiliser pour un hôtel ?
UML permet de modéliser un système logiciel sous forme de diagrammes pour mieux comprendre comment les différentes entités interagissent entre elles.

Dans un système de gestion d’hôtel, nous avons plusieurs entités importantes :

Hôtel : représente un établissement avec un lieu et des commodités.
Client : une personne qui réserve des chambres et laisse des avis.
Lieu : l’adresse et la localisation de l’hôtel.
Commodités : services proposés par l’hôtel (WiFi, piscine, restaurant...).
Avis : commentaires et notes laissés par les clients.
Pourquoi utiliser UML ?
Mieux organiser son code avant de commencer.
Éviter les erreurs de conception et les refontes inutiles.
Faciliter la communication entre développeurs.


Diagramme UML pour un Système d’Hôtel
Voici une modélisation UML des classes principales :


+----------------------+
|        Hotel        |
+----------------------+
| - name: str         |
| - location: Lieu    |
| - commodites: list  |
| - clients: list     |
+----------------------+
| + ajouter_client()  |
| + ajouter_avis()    |
| + afficher_details()|
+----------------------+
        |
        | "est situé à"
        v
+----------------------+
|        Lieu         |
+----------------------+
| - adresse: str      |
| - ville: str        |
| - pays: str         |
+----------------------+
| + afficher_lieu()   |
+----------------------+

       "contient plusieurs"
+----------------------+
|     Commodite       |
+----------------------+
| - type: str         |
+----------------------+
| + afficher_info()   |
+----------------------+

       "est laissé par"
+----------------------+
|        Avis         |
+----------------------+
| - client: Client    |
| - note: int         |
| - commentaire: str  |
+----------------------+
| + afficher_avis()   |
+----------------------+

       "fait une réservation"
+----------------------+
|       Client        |
+----------------------+
| - nom: str         |
| - email: str       |
| - reservations: list|
+----------------------+
| + reserver()       |
| + laisser_avis()   |
+----------------------+


Explication des Classes et Relations
1. Classe Hotel 🏨
Attributs :
name : Nom de l'hôtel.
location : Instance de la classe Lieu représentant l’adresse.
commodites : Liste des services proposés.
clients : Liste des clients ayant réservé.
Méthodes :
ajouter_client() : Ajoute un client.
ajouter_avis() : Associe un avis à l’hôtel.
afficher_details() : Affiche les informations de l’hôtel.
2. Classe Lieu 📍
Attributs :
adresse, ville, pays : Informations sur la localisation.
Méthodes :
afficher_lieu() : Affiche l'adresse complète.
3. Classe Commodite 🏊‍♂️
Attributs :
type : Type de commodité (WiFi, piscine, spa...).
Méthodes :
afficher_info() : Affiche les détails de la commodité.
4. Classe Avis ⭐
Attributs :
client : Instance de Client ayant laissé l’avis.
note : Note attribuée (1-5).
commentaire : Texte du commentaire.
Méthodes :
afficher_avis() : Affiche l’avis.
5. Classe Client 👤
Attributs :
nom, email : Informations du client.
reservations : Liste des réservations faites.
Méthodes :
reserver() : Effectue une réservation.
laisser_avis() : Permet de laisser un avis sur un hôtel.
Relations UML Utilisées
Relation UML	Explication	Exemple dans notre système
Association (→)	Relation entre deux classes.	Un Client est associé à un Avis qu’il écrit.
**Généralisation (`--	>`)**	Relation d'héritage.
Agrégation (o–)	Une partie peut exister indépendamment du tout.	Un hôtel a des commodités, mais une commodité peut exister seule.
Composition (*–)	Une partie dépend entièrement du tout.	Un Lieu est spécifique à un Hotel et ne peut exister sans lui.
