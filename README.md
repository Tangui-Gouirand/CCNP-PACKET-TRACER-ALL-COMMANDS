# CCNP-PACKET-TRACER-COMMANDES-UTILES FR

## Table des Matières

1.  [Sécurité et Accès](#sécurité-et-accès)
    * [Configuration des Mots de Passe](#configuration-des-mots-de-passe)
    * [Déconnexion en Cas d'Inactivité](#déconnexion-en-cas-dinactivité)
2.  [Protocole NTP (Network Time Protocol)](#protocole-ntp-network-time-protocol)
    * [Configuration du Serveur NTP](#configuration-du-serveur-ntp)
    * [Vérification de l'État NTP](#vérification-de-létat-ntp)
3.  [SNMP (Simple Network Management Protocol) - Gestion Réseau](#snmp-simple-network-management-protocol---gestion-réseau)
    * [Configuration de la Communauté SNMP](#configuration-de-la-communauté-snmp)
    * [Configuration des Hôtes SNMP](#configuration-des-hôtes-snmp)
    * [Configuration des Utilisateurs SNMPv3](#configuration-des-utilisateurs-snmpv3)
    * [Vérification de la Configuration SNMP](#vérification-de-la-configuration-snmp)
4.  [SYSLOG](#syslog)
5.  [SSH](#ssh)
6.  [Banner Message](#banner-message)

## Sécurité et Accès

### Configuration des Mots de Passe

* **Mot de passe d'activation (mode privilégié) :**

    ```cisco
    Router(config)# enable secret cisco
    ```

    * `enable secret` crypte le mot de passe, offrant une meilleure sécurité que `enable password`.

* **Mot de passe d'accès à la console :**

    ```cisco
    Router(config)# line console 0
    Router(config-line)# login
    Router(config-line)# password cisco
    ```

    * `line console 0` configure la ligne de console.
    * `login` demande un mot de passe pour accéder à la console.

* **Mot de passe d'accès VTY (SSH/Telnet) :**

    ```cisco
    Router(config)# line vty 0 4
    Router(config-line)# login
    Router(config-line)# password cisco
    ```

    * `line vty 0 4` configure les lignes virtuelles pour les connexions Telnet et SSH (0 à 4 = 5 sessions simultanées).

### Déconnexion en Cas d'Inactivité

* **Déconnexion pour la console :**

    ```cisco
    Router(config)# line console 0
    Router(config-line)# exec-timeout minutes secondes
    ```

    * Remplacez `minutes` et `secondes` par la durée d'inactivité souhaitée.

* **Déconnexion pour VTY :**

    ```cisco
    Router(config)# line vty 0 4
    Router(config-line)# exec-timeout minutes secondes
    ```

## Protocole NTP (Network Time Protocol)

### Configuration du Serveur NTP

* **Définir un serveur NTP :**

    ```cisco
    Router(config)# ntp server adresse_ip_serveur
    ```

* **Définir un pair NTP (synchronisation mutuelle) :**

    ```cisco
    Router(config)# ntp peer adresse_ip_pair
    ```

* **Configurer l'appareil comme serveur NTP principal :**

    ```cisco
    Router(config)# ntp master
    ```

### Vérification de l'État NTP

* **Afficher l'état de la synchronisation NTP :**

    ```cisco
    Router# show ntp status
    ```

* **Afficher les associations avec les serveurs NTP :**

    ```cisco
    Router# show ntp associations
    ```

* **Afficher les détails des associations NTP :**

    ```cisco
    Router# show ntp associations detail
    ```

* **Afficher les détails de l'horloge :**

    ```cisco
    Router# show clock detail
    ```

## SNMP (Simple Network Management Protocol) - Gestion Réseau

### Configuration de la Communauté SNMP

* **Définir une communauté SNMP :**

    ```cisco
    Router(config)# snmp-server community nom {RO|RW}
    ```

    * `RO` (Read-Only) : Lecture seule.
    * `RW` (Read-Write) : Lecture et écriture.

### Configuration des Hôtes SNMP

* **Définir le serveur NMS destinataire des traps :**

    ```cisco
    Router(config)# snmp-server host adresse_ip_NMS community nom [traps|informs]
    ```

* **Activer l'envoi des traps SNMP :**

    ```cisco
    Router(config)# snmp-server enable traps
    ```

### Configuration des Utilisateurs SNMPv3

* **Configurer un utilisateur SNMPv3 :**

    ```cisco
    Router(config)# snmp-server user nom group-name auth {md5|sha} mot_de_passe priv {des|aes} mot_de_passe access acl-name
    ```

### Vérification de la Configuration SNMP

* **Afficher les communautés SNMP :**

    ```cisco
    Router# show snmp community
    ```

* **Afficher les hôtes SNMP :**

    ```cisco
    Router# show snmp host
    ```

* **Afficher les traps SNMP activés :**

    ```cisco
    Router# show snmp traps
    ```

## SYSLOG

* **Définir l'adresse du serveur Syslog :**

    ```cisco
    Router(config)# logging host adresse_ip_serveur
    ```

* **Définir le niveau de gravité des messages Syslog à envoyer (souvent debugging) :**

    ```cisco
    Router(config)# logging trap niveau_gravité
    ```

## SSH

* **Générer une clé RSA (nécessaire pour SSH) :**

    ```cisco
    Router(config)# crypto key generate rsa
    ```

    * Pour la taille de la clé, il est recommandé d'utiliser 2048 bits. Un nom de domaine doit être configuré au préalable : `ip domain-name nom_de_domaine`

* **Définir la version de SSH :**

    ```cisco
    Router(config)# ip ssh version {1|2}
    ```

    * La version 2 est recommandée.

* **Configurer les lignes VTY pour accepter uniquement les connexions SSH :**

    ```cisco
    Router(config)# line vty 0 15
    Router(config-line)# transport input ssh
    Router(config-line)# login local
    ```

    * `line vty 0 15` configure les lignes virtuelles 0 à 15 (16 sessions simultanées).
    * `transport input ssh` limite le trafic entrant sur ces lignes à SSH.
    * `login local` utilise la base de données locale du routeur pour l'authentification des utilisateurs.

* **Définir le nombre de tentatives d'authentification SSH :**

    ```cisco
    Router(config)# ip ssh authentication-retries nombre
    ```

## Banner Message

* **Définir un message de bannière :**

    ```cisco
    Router(config)# banner {motd|exec|login|incoming} # message #
    ```

    * `MOTD` (Message of the Day) : Affiche un message avant l'invite de connexion.
    * `EXEC` : Affiche un message avant le mode d'exécution privilégié.
    * `Login` : Affiche un message avant l'invite de connexion.
    * `Incoming` : Affiche un message pour les connexions entrantes (par exemple, Telnet, SSH).
