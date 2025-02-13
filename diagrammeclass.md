# 📌 HBnB - Business Logic Layer

## 📝 Description
Ce projet représente la couche **Business Logic** de l'application **HBnB**, avec un diagramme UML détaillé illustrant les principales entités et leurs interactions.

## 📊 Diagramme de Classes UML
Le diagramme de classes ci-dessous modélise les entités principales de HBnB :
- **User** (Utilisateur)
- **Place** (Lieu)
- **Review** (Avis)
- **Amenity** (Équipement)

Chaque entité possède ses propres **attributs**, **méthodes**, et des **relations** bien définies avec les autres entités.

## 🏗️ **Structure des Classes**

### **1️⃣ BaseModel (Classe Parent)**
Toutes les classes héritent de `BaseModel`, qui fournit les attributs communs :
- `id` (UUID) : Identifiant unique
- `created_at` : Date de création
- `updated_at` : Date de mise à jour

### **2️⃣ User (Utilisateur)**
Représente un utilisateur de l'application.

| Attribut  | Type | Description |
|-----------|------|-------------|
| `firstName` | String | Prénom de l'utilisateur |
| `lastName` | String | Nom de famille |
| `email` | String | Adresse email |
| `password` | String | Mot de passe |
| `isAdmin` | Boolean | Indique si l'utilisateur est admin |

🔹 **Méthodes** :
- `register()` : Inscription d'un utilisateur
- `updateProfile()` : Mise à jour du profil
- `deleteAccount()` : Suppression du compte

### **3️⃣ Place (Lieu)**
Représente un lieu mis en location par un utilisateur.

| Attribut  | Type | Description |
|-----------|------|-------------|
| `title` | String | Nom du lieu |
| `description` | String | Description du lieu |
| `price` | Float | Prix par nuit |
| `latitude` | Float | Latitude géographique |
| `longitude` | Float | Longitude géographique |
| `owner` | User | Propriétaire du lieu |

🔹 **Méthodes** :
- `create()` : Création d'un lieu
- `update()` : Mise à jour des informations
- `delete()` : Suppression du lieu

### **4️⃣ Review (Avis)**
Représente un avis donné par un utilisateur sur un lieu.

| Attribut  | Type | Description |
|-----------|------|-------------|
| `user` | User | Auteur de l'avis |
| `place` | Place | Lieu concerné |
| `rating` | Int | Note (1-5) |
| `comment` | String | Commentaire |

🔹 **Méthodes** :
- `addReview()` : Ajout d'un avis
- `updateReview()` : Modification de l'avis
- `deleteReview()` : Suppression de l'avis

### **5️⃣ Amenity (Équipement)**
Liste des équipements disponibles dans un lieu.

| Attribut  | Type | Description |
|-----------|------|-------------|
| `name` | String | Nom de l'équipement |
| `description` | String | Détails |

🔹 **Méthodes** :
- `create()` : Ajout d'un équipement
- `update()` : Modification de l'équipement
- `delete()` : Suppression

---

## 🔗 **Relations entre les Entités**
- **User** ➝ Possède plusieurs **Place** (`1 - 0..*`)
- **User** ➝ Rédige plusieurs **Review** (`1 - 0..*`)
- **Place** ➝ Reçoit plusieurs **Review** (`1 - 0..*`)
- **Place** ➝ A plusieurs **Amenity** (`1 - 0..*`)

![diagramme_classes_1](https://github.com/user-attachments/assets/a4e8701b-20bd-4b8e-9f98-6bcad84d874d)



---
