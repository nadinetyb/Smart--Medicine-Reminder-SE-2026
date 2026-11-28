# Medication Tracker App

Voici le **Use Case Diagram** de l'application :

```mermaid
flowchart LR
    %% Les Acteurs
    User((Utilisateur))
    NotifSys((Système de Notification))

    %% Le Système
    subgraph App [Système : Medication Tracker]
        UC1([S'inscrire / Créer un compte])
        UC2([Se connecter])
        UC3([Ajouter des médicaments])
        UC4([Configurer les horaires et doses])
        UC5([Consulter la liste quotidienne])
        UC6([Suivre le stock de médicaments])
        UC7([Recevoir des rappels intelligents])
        UC8([Recevoir des alertes de stock faible])
    end

    %% Relations Utilisateur
    User --> UC1
    User --> UC2
    User --> UC3
    User --> UC4
    User --> UC5
    User --> UC6
    User --> UC7
    User --> UC8

    %% Relations Système (Notifications automatiques)
    NotifSys --> UC7
    NotifSys --> UC8

    %% Dépendances (Include)
    UC3 -.->|<<include>>| UC2
    UC4 -.->|<<include>>| UC2
    UC5 -.->|<<include>>| UC2
    UC6 -.->|<<include>>| UC2 
