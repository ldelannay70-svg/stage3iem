sur mon ordinateur mac, j'ouvre un terminal et je tape la commande

```
psql postgres
```

```
create database lohanngames;
\c lohanngames
```

pour lister les bases

```
\l
```

\dt : Liste toutes les tables du schéma public (tables créées par l'utilisateur).

\dt+ : Liste les tables avec des détails supplémentaires (taille, description, etc.).

\dt *.* : Liste toutes les tables de tous les schémas (y compris les tables système).

ton entreprise de jeux videos elle a une db lohanngames

elle a une liste de Commandes dans l'application SAP qui gère la comptabilité
elle contient une ligne par commande
un commande contient le prixdevente, date, nom, prenom du client

elle a une liste de Ventes dans l'application CaisseEnregistreuse
elle contient une ligne par vente
une vente contient le prixunitaire_ttc, qty, date, nom, prenom du client

CREATE DATABASE lohanngames;

comment créer les deux tables Commandes et Ventes ? dans le language SQL ? 

CREATE TABLE temps (
    ville           varchar(80),
    t_b asse         int,           -- température basse
    t_haute         int,           -- température haute
    prcp            real,          -- précipitation
    date            date
);


    CREATE TABLE ventes ( 
        id bigint GENERATED ALWAYS AS IDENTITY,
        prixunitaire_ttc        int,
        quantité                int,
        date                    date,
        nom                     varchar(80),
        prenom                  varchar(80)
);

CREATE TABLE commandes ( 
    prixdevente             int,
    date                    date,
    nom                     varchar(80),
    prenom                  varchar(80)
);

https://docs.postgresql.fr/11/tutorial-sql.html

comment insérer une Vente dans la table Ventes

comment insérer une Commande dans la table Commandes

https://docs.postgresql.fr/11/tutorial-populate.html

INSERT INTO ventes VALUES (DEFAULT, 10, 1, '1994-11-27', 'Dupond', 'Toto');

comment lister 10 Vente

SELECT * FROM ventes;

https://docs.postgresql.fr/11/tutorial-select.html

comment lister 10 Commande

comment mettre à jour une Vente

UPDATE ventes SET date='2026-11-27';

UPDATE ventes SET date='2026-11-27' WHERE prixunitaire_ttc=10;
UPDATE ventes SET date='2026-10-27' WHERE id=1;

comment avoir un attribut qui est un identifiant pour une ligne? https://docs.postgresql.fr/17/ddl-identity-columns.html

CREATE TABLE people (
    id bigint GENERATED ALWAYS AS IDENTITY,
    ...,
);

DELETE from ventes;

ALTER TABLE ventes ADD COLUMN id bigint GENERATED ALWAYS AS IDENTITY PRIMARY KEY;

DROP TABLE ventes;