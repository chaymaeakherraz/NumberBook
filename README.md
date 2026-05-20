# 📱 NumberBook — Android Contact Synchronization App

## 📌 Description

NumberBook est une application Android développée en Java permettant :

* de lire les contacts enregistrés dans le téléphone ;
* d’afficher les contacts dans une interface moderne avec RecyclerView ;
* de synchroniser les contacts vers un serveur distant ;
* d’enregistrer les données dans une base MySQL ;
* d’effectuer une recherche distante par nom ou numéro.

Ce projet combine Android, Retrofit, PHP et MySQL dans une architecture client/serveur simple et pédagogique.

---

# 🛠️ Technologies utilisées

## Android

* Java
* RecyclerView
* Retrofit
* Gson
* ContentResolver

## Backend

* PHP
* MySQL
* PDO

## Outils

* Android Studio
* XAMPP
* phpMyAdmin

---

# 📂 Structure du projet

## Backend

```text
numberbook-api/
│
├── config/
│   └── Database.php
│
├── service/
│   └── ContactService.php
│
└── api/
    ├── insertContact.php
    ├── getAllContacts.php
    └── searchContact.php
```

## Android

```text
app/
│
├── java/
│   └── ma.fst.numberbook/
│       ├── MainActivity.java
│       ├── Contact.java
│       ├── ApiResponse.java
│       ├── ContactApi.java
│       ├── RetrofitClient.java
│       └── ContactAdapter.java
│
└── res/
    └── layout/
        └── activity_main.xml
```

---

# ⚙️ Fonctionnalités

* Chargement des contacts du téléphone
* Gestion des permissions Android
* Affichage avec RecyclerView
* Synchronisation vers serveur distant
* Recherche distante des contacts
* Communication REST avec Retrofit
* Stockage MySQL

---

# 🗄️ Base de données

## Création de la base

```sql
CREATE DATABASE IF NOT EXISTS numberbook
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

## Création de la table

```sql
CREATE TABLE contact (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(150) NOT NULL,
    phone VARCHAR(50) NOT NULL,
    source VARCHAR(50) DEFAULT 'mobile',
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

---

# ▶️ Installation du backend

## 1. Copier le dossier backend

Copier le dossier :

```text
numberbook-api
```

dans :

```text
C:\xampp\htdocs\
```

## 2. Démarrer XAMPP

Activer :

* Apache
* MySQL

## 3. Tester l’API

Ouvrir :

```text
http://localhost/numberbook-api/api/getAllContacts.php
```

---

# ▶️ Installation Android

## Permissions

Ajouter dans AndroidManifest.xml :

```xml
<uses-permission android:name="android.permission.READ_CONTACTS"/>
<uses-permission android:name="android.permission.INTERNET"/>
```

## Dépendances Gradle

```gradle
implementation 'com.squareup.retrofit2:retrofit:2.11.0'
implementation 'com.squareup.retrofit2:converter-gson:2.11.0'
implementation 'androidx.recyclerview:recyclerview:1.3.2'
implementation 'com.google.android.material:material:1.11.0'
```

---

# 🌐 Configuration Retrofit

## Emulator Android

```java
private static final String BASE_URL =
"http://10.0.2.2/numberbook-api/api/";
```

## Téléphone réel

```java
private static final String BASE_URL =
"http://IP_PC/numberbook-api/api/";
```

Exemple :

```java
http://192.168.1.10/numberbook-api/api/
```

---

# 📱 Utilisation

## 1. Charger les contacts

Cliquer sur :

```text
Charger les contacts
```

L’application demande l’autorisation d’accéder aux contacts puis affiche les données.

## 2. Synchroniser

Cliquer sur :

```text
Synchroniser vers le serveur
```

Les contacts sont envoyés vers MySQL.

## 3. Rechercher

Saisir un nom ou un numéro puis cliquer sur :

```text
Rechercher
```

Les résultats correspondants sont affichés.

---

# 🧪 Tests réalisés

* Lecture des contacts Android
* Synchronisation vers serveur PHP
* Insertion dans MySQL
* Recherche distante
* Affichage RecyclerView
* Communication Retrofit

---

# 📚 Concepts appris

* ContentResolver
* Permissions Android
* RecyclerView
* Retrofit
* API REST
* JSON
* PHP PDO
* MySQL
* Architecture client/serveur

---

# 🚀 Améliorations possibles

* Suppression des contacts
* Mise à jour des contacts
* Gestion des doublons
* Authentification utilisateur
* Sauvegarde locale Room
* Synchronisation bidirectionnelle



# 📖 Conclusion

Ce projet permet de comprendre comment une application Android peut communiquer avec un backend distant afin de synchroniser et rechercher des contacts. Il combine plusieurs notions importantes du développement mobile moderne : accès aux données système, permissions Android, communication HTTP, API REST et persistance des données dans MySQL.



https://github.com/user-attachments/assets/32729387-bd38-4e3b-bdb3-a5ffef6f0fbf

<img width="1779" height="336" alt="image" src="https://github.com/user-attachments/assets/22c522d1-fc5e-44fd-b52e-b23bc68309a3" />

