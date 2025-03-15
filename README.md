Gestion des Concours Internes

#Contexte

La gestion des concours internes au sein des institutions est essentielle pour assurer une évaluation équitable et transparente des participants. Toutefois, la gestion manuelle ou avec des systèmes obsolètes peut entraîner des erreurs dans le suivi des participants et des résultats.

#Problématique

Les institutions ont besoin d'un système efficace pour gérer les concours internes, car les méthodes actuelles sont souvent inefficaces, ce qui peut entraîner :

Des erreurs dans l'enregistrement des participants,

Des retards dans la publication des résultats,

Une mauvaise expérience pour les participants.

#Objectif

L'objectif de ce projet est de développer une application qui facilite la gestion des concours internes. L'application doit :
Permettre la création et la gestion des concours,
Offrir un suivi précis des participants et de leurs résultats,
Fournir des outils d'analyse des résultats.

#Fonctionnalités Principales

Création de Concours : Ajout et gestion des concours internes.
Enregistrement des Participants : Suivi des inscriptions des participants.
Filtrage des Résultats : Filtrage des résultats par concours.
Recherche de Participants : Recherche rapide de participants par nom ou email.
Visualisation des Données : Bar chart pour analyser le taux de réussite par concours.

#Requêtes SQL pour la Base de Données

Tables

CREATE TABLE ConcoursInterne (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(50) NOT NULL,
    date DATE NOT NULL,
    lieu VARCHAR(50) NOT NULL
);


CREATE TABLE Participant (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(50) NOT NULL,
    prenom VARCHAR(50) NOT NULL,
    email VARCHAR(50) NOT NULL
);


CREATE TABLE ResultatConcours (
    concours_id INT NOT NULL,
    participant_id INT NOT NULL,
    note DECIMAL(5,2) NOT NULL,
    FOREIGN KEY (concours_id) REFERENCES ConcoursInterne(id) ON DELETE CASCADE,
    FOREIGN KEY (participant_id) REFERENCES Participant(id) ON DELETE CASCADE
);

#Architecture

L'application est basée sur une architecture client-serveur :
Client : Une application Java développée avec NetBeans.
Serveur : Une base de données MySQL pour stocker et récupérer les données.
Interface Utilisateur : Développée avec SWING pour une expérience utilisateur intuitive et conviviale.

#Technologies Utilisées

NetBeans (Java) : Pour le développement de l’application.
MySQL : Pour la gestion de la base de données.
SWING : Pour l'interface graphique et rendre l’application facile à utiliser.
