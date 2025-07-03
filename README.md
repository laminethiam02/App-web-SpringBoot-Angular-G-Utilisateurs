# Application Web (CRUD) de gestion des utilisateurs avec Spring Boot + Angular + PostgreSQ


Voici un fichier `README.md` bien structuré pour ton projet **Application Web (CRUD) de gestion des utilisateurs avec Spring Boot + Angular + PostgreSQL** :

````markdown
# Application Web (CRUD) avec Spring Boot + Angular + PostgreSQL

## Description

Ce projet est une application web de type CRUD (Create, Read, Update, Delete) utilisant :

- **Spring Boot** pour le backend (API REST)
- **Angular** pour le frontend
- **PostgreSQL** pour la base de données

---

## 🛠️ Prérequis

- Java 17+
- Node.js & npm
- Angular CLI (`npm install -g @angular/cli`)
- PostgreSQL
- IDE (IntelliJ, VS Code, etc.)

---

## 🧑‍💻 Étapes de configuration

### 1. Création de la base de données PostgreSQL

#### Vérification du service PostgreSQL

- Lancer `services.msc` et s’assurer que le service **PostgreSQL** est démarré.
- Se connecter avec `psql` :

```bash
psql -U postgres
````

Mot de passe : `passer`

#### Création de la base de données et des tables

```sql
CREATE DATABASE demo;
\l
\c demo;

CREATE TABLE USERS (
    USER_ID BIGSERIAL PRIMARY KEY NOT NULL,
    USER_FIRSTNAME VARCHAR(32),
    USER_LASTNAME VARCHAR(32)
);

INSERT INTO USERS (USER_FIRSTNAME, USER_LASTNAME)
VALUES ('Hamza', 'Mouddene');

SELECT * FROM USERS;
```

---

### 2. Configuration de l'application Spring Boot

#### Fichier `application.properties`

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/demo
spring.datasource.username=postgres
spring.datasource.password=passer
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
```

#### Dépendance Lombok (si problème de version)

```xml
<!-- pom.xml -->
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.18.32</version>
    <scope>provided</scope>
</dependency>
```

---

### 3. Exécution du backend

Avant de lancer l'application, s'assurer que le port `8080` est libre :

```bash
netstat -ano | findstr :8080
```

Si un processus utilise le port `8080` (par exemple PID 6628), le tuer avec :

```bash
taskkill /PID 6628 /F
```

Puis lancer l'application Spring Boot (`DemoApplication.java`) :

```bash
mvn spring-boot:run
```

Accès à l'API backend :

[http://localhost:8080/](http://localhost:8080/)

---

### 4. Exécution du frontend Angular

Dans le dossier du frontend :

```bash
npm install
ng serve
```

Accès à l’interface utilisateur :

[http://localhost:4200/](http://localhost:4200/)

---

## 📂 Structure du projet

```
CRUD-main/
├── demo/ (Spring Boot)
│   └── src/main/java/com/example/demo/
├── frontend/ (Angular)
│   └── src/app/
└── README.md
```

---

## 🧑‍🏫 Auteur

**Lamine THIAM** – Élève ingénieur en informatique, réseaux et télécommunications

---

## 📝 Licence

Ce projet est libre et ouvert. N'hésitez pas à l'utiliser et à le modifier selon vos besoins.

```


```
