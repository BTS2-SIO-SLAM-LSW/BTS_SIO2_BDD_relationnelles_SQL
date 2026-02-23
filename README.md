# TP SQL — BTS SIO SLAM (phpMyAdmin)



## Connexion à PhpMyAdmin
Dans l’écran de login :

- Server : db
- Username : root
- Password : la valeur de MYSQL_ROOT_PASSWORD dans ton .env (ex: rootpwd)



Base utilisée : `cours_sql_tp`





---

# THÈME 1 — LDD (Langage de Définition de Données)

## Résumé du cours
Le LDD permet de modifier la structure d’une base :
- `CREATE DATABASE`, `DROP DATABASE`
- `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`, `RENAME`
- Contraintes : `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `CHECK`, `NOT NULL`
- Index : `CREATE INDEX`, `DROP INDEX`

## Exercices LDD (10)
1. Créer une base `tp_structures` puis l’utiliser.
2. Créer une table `Departement` (id PK AI, nom NOT NULL, budget DECIMAL CHECK > 0).
3. Créer une table `Employe` (id PK AI, nom NOT NULL, prenom, salaire, id_departement FK).
4. Modifier `Employe` : `salaire` NOT NULL avec DEFAULT 2000.00.
5. Ajouter `email` UNIQUE dans `Employe`.
6. Créer un index sur `Employe(nom)`.
7. Renommer `Departement` en `Service`.
8. Modifier le type de `budget` en `DECIMAL(12,2)`.
9. Supprimer la contrainte UNIQUE sur `email` (supprimer l’index UNIQUE correspondant).
10. Supprimer les tables puis la base `tp_structures`.

---

# THÈME 2 — LMD (Langage de Manipulation de Données)

## Résumé du cours
Le LMD permet d’agir sur les données :
- `INSERT`, `UPDATE`, `DELETE`, `SELECT`
Attention : `UPDATE`/`DELETE` sans `WHERE` impactent toute la table.

## Exercices LMD (10) — base `cours_sql_tp`
1. Insérer un client : `Dupuis Léa, Lyon, 2001`.
2. Insérer un produit : `Webcam HD`, 350.00.
3. Enregistrer un achat : Léa achète 2 webcams (date du jour).
4. Augmenter de 10% le prix du produit `SSD 1To`.
5. Supprimer tous les achats avant le `2025-03-01`.
6. Afficher les clients nés après 1971 (nom, prénom, anneeN).
7. Afficher les produits entre 3000 et 7000 triés par prix décroissant.
8. Afficher le nombre de clients habitant à `El Jadida`.
9. Afficher le produit le plus cher.
10. Afficher les produits jamais vendus.

---

# THÈME 3 — LCD (Langage de Contrôle de Données)

## Résumé du cours
Le LCD gère les droits :
- `CREATE USER`, `DROP USER`
- `GRANT`, `REVOKE`
Principe du moindre privilège.

## Exercices LCD (10)
1. Créer l’utilisateur `lecteur` (mdp : `lecteur_pwd`).
2. Créer l’utilisateur `gestion` (mdp : `gestion_pwd`).
3. Donner `SELECT` sur la base `cours_sql_tp` à `lecteur`.
4. Retirer `SELECT` sur la table `Pay` pour `lecteur`.
5. Donner à `gestion` : `SELECT, INSERT, UPDATE, DELETE` sur `Client`, `Produit`, `Achat`.
6. Retirer à `gestion` le droit `DELETE` sur `Client` uniquement.
7. Créer `dba_tp` (mdp : `dba_pwd`) et donner `ALL PRIVILEGES` sur `cours_sql_tp`.
8. Tester : `lecteur` ne doit pas pouvoir lire `Pay`.
9. Révoquer tous les droits de `gestion` sur `Achat`.
10. Supprimer `lecteur`, `gestion`, `dba_tp`.
