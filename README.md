# CCNP-PACKET-TRACER-COMMANDES-UTILES FR

Ce document rassemble les commandes les plus utiles pour la préparation du CCNP sur Packet Tracer. Il est organisé par thèmes pour une consultation facile.

## Table des Matières

1.  [Sécurité et Accès](#sécurité-et-accès)
    * 1.1. [Configuration des Mots de Passe](#configuration-des-mots-de-passe)
        * 1.1.1. [Mot de passe d'activation (mode privilégié)](#mot-de-passe-dactivation-mode-privilégié)
        * 1.1.2. [Mot de passe d'accès à la console](#mot-de-passe-daccès-à-la-console)
        * 1.1.3. [Mot de passe d'accès VTY (SSH/Telnet)](#mot-de-passe-daccès-vty-sshtelnet)
    * 1.2. [Déconnexion en Cas d'Inactivité](#déconnexion-en-cas-dinactivité)
        * 1.2.1. [Déconnexion pour la console](#déconnexion-pour-la-console)
        * 1.2.2. [Déconnexion pour VTY](#déconnexion-pour-vty)
2.  [Protocole NTP (Network Time Protocol)](#protocole-ntp-network-time-protocol)
    * 2.1. [Configuration du Serveur NTP](#configuration-du-serveur-ntp)
        * 2.1.1. [Définir un serveur NTP](#définir-un-serveur-ntp)
        * 2.1.2. [Définir un pair NTP (synchronisation mutuelle)](#définir-un-pair-ntp-synchronisation-mutuelle)
        * 2.1.3. [Configurer l'appareil comme serveur NTP principal](#configurer-lappareil-comme-serveur-ntp-principal)
    * 2.2. [Vérification de l'État NTP](#vérification-de-létat-ntp)
        * 2.2.1. [Afficher l'état de la synchronisation NTP](#afficher-létat-de-la-synchronisation-ntp)
        * 2.2.2. [Afficher les associations avec les serveurs NTP](#afficher-les-associations-avec-les-serveurs-ntp)
        * 2.2.3. [Afficher les détails des associations NTP](#afficher-les-détails-des-associations-ntp)
        * 2.2.4. [Afficher les détails de l'horloge](#afficher-les-détails-de-lhorloge)
3.  [SNMP (Simple Network Management Protocol) - Gestion Réseau](#snmp-simple-network-management-protocol---gestion-réseau)
    * 3.1. [Configuration de la Communauté SNMP](#configuration-de-la-communauté-snmp)
    * 3.2. [Configuration des Hôtes SNMP](#configuration-des-hôtes-snmp)
    * 3.3. [Configuration des Utilisateurs SNMPv3](#configuration-des-utilisateurs-snmpv3)
    * 3.4. [Vérification de la Configuration SNMP](#vérification-de-la-configuration-snmp)
4.  [SYSLOG](#syslog)
5.  [SSH](#ssh)
6.  [Banner Message](#banner-message)
7.  [Fuseau Horaire](#fuseau-horaire)
8.  [Désactiver la Recherche DNS](#désactiver-la-recherche-dns)
9.  [Effacer la Configuration du Switch](#effacer-la-configuration-du-switch)
10. [AAA](#aaa)
    * 10.1. [Configuration AAA de base](#configuration-aaa-de-base)
    * 10.2. [Comptes locaux](#comptes-locaux)
    * 10.3. [Configuration RADIUS](#configuration-radius)
    * 10.4. [Configuration TACACS+](#configuration-tacacs)

## Sécurité et Accès

### 1.1 Configuration des Mots de Passe

#### 1.1.1 Mot de passe d'activation (mode privilégié)

* **Commande :**

    ```cisco
    Router(config)# enable secret cisco
    ```

* **Explication :** `enable secret` crypte le mot de passe, offrant une meilleure sécurité que `enable password`.

#### 1.1.2 Mot de passe d'accès à la console

* **Commandes :**

    ```cisco
    Router(config)# line console 0
    Router(config-line)# login
    Router(config-line)# password cisco
    ```

* **Explication :**
    * `line console 0` configure la ligne de console.
    * `login` demande un mot de passe pour accéder à la console.

#### 1.1.3 Mot de passe d'accès VTY (SSH/Telnet)

* **Commandes :**

    ```cisco
    Router(config)# line vty 0 4
    Router(config-line)# login
    Router(config-line)# password cisco
    ```

* **Explication :** `line vty 0 4` configure les lignes virtuelles pour les connexions Telnet et SSH (0 à 4 = 5 sessions simultanées).

### 1.2 Déconnexion en Cas d'Inactivité

#### 1.2.1 Déconnexion pour la console

* **Commande :**

    ```cisco
    Router(config)# line console 0
    Router(config-line)# exec-timeout minutes secondes
    ```

* **Explication :** Remplacez `minutes` et `secondes` par la durée d'inactivité souhaitée.

#### 1.2.2 Déconnexion pour VTY

* **Commande :**

    ```cisco
    Router(config)# line vty 0 4
    Router(config-line)# exec-timeout minutes secondes
    ```

* **Explication :** Remplacez `minutes` et `secondes` par la durée d'inactivité souhaitée.

## Protocole NTP (Network Time Protocol)

### 2.1 Configuration du Serveur NTP

#### 2.1.1 Définir un serveur NTP

* **Commande :**

    ```cisco
    Router(config)# ntp server adresse_ip_serveur
    ```

#### 2.1.2 Définir un pair NTP (synchronisation mutuelle)

* **Commande :**

    ```cisco
    Router(config)# ntp peer adresse_ip_pair
    ```

#### 2.1.3 Configurer l'appareil comme serveur NTP principal

* **Commande :**

    ```cisco
    Router(config)# ntp master
    ```

### 2.2 Vérification de l'État NTP

#### 2.2.1 Afficher l'état de la synchronisation NTP

* **Commande :**

    ```cisco
    Router# show ntp status
    ```

#### 2.2.2 Afficher les associations avec les serveurs NTP

* **Commande :**

    ```cisco
    Router# show ntp associations
    ```

#### 2.2.3 Afficher les détails des associations NTP

* **Commande :**

    ```cisco
    Router# show ntp associations detail
    ```

#### 2.2.4 Afficher les détails de l'horloge

* **Commande :**

    ```cisco
    Router# show clock detail
    ```

## SNMP (Simple Network Management Protocol) - Gestion Réseau

### 3.1 Configuration de la Communauté SNMP

* **Commande :**

    ```cisco
    Router(config)# snmp-server community nom {RO|RW}
    ```

* **Explication :**
    * `RO` (Read-Only) : Lecture seule.
    * `RW` (Read-Write) : Lecture et écriture.

### 3.2 Configuration des Hôtes SNMP

* **Commande :**

    ```cisco
    Router(config)# snmp-server host adresse_ip_NMS community nom [traps|informs]
    ```

### 3.3 Configuration des Utilisateurs SNMPv3

* **Commande :**

    ```cisco
    Router(config)# snmp-server user nom group-name auth {md5|sha} mot_de_passe priv {des|aes} mot_de_passe access acl-name
    ```

### 3.4 Vérification de la Configuration SNMP

* **Commandes :**

    ```cisco
    Router# show snmp community
    Router# show snmp host
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

## Fuseau Horaire

* **Définir le fuseau horaire :**

    ```cisco
    Router(config)# clock timezone nom_fuseau_horaire décalage_utc
    ```

* **Afficher les détails de l'horloge :**

    ```cisco
    Router# show clock detail
    ```

## Désactiver la Recherche DNS

* **Désactiver la recherche DNS :**

    ```cisco
    Router(config)# no ip domain-lookup
    ```

## Effacer la Configuration du Switch

* **Effacer la configuration du switch :**

    ```cisco
    S1# erase startup-config
    S1# delete vlan.dat
    S1# reload
    ```

## AAA

### 10.1 Configuration AAA de base

* **Commandes :**

    ```cisco
    Router(config)# aaa new-model
    Router(config)# aaa authentication login default group {tacacs+|radius|local}
    ```

    Définit la méthode d'authentification par défaut pour les connexions de connexion

    ```cisco
    Router(config)# aaa authorization exec default group {tacacs+|radius|local}
    ```

    Définit la méthode d'autorisation par défaut pour les commandes EXEC.

    ```cisco
    Router(config)# aaa accounting exec default start-stop group {tacacs+|radius}
    ```

    Active la comptabilité pour les commandes EXEC.

### 10.2 Comptes locaux

* **Commande :**

    ```cisco
    Router(config)# username {nom_utilisateur} privilege 15 secret {mot_de_passe}
    ```

    Crée un compte utilisateur local avec privilège 15 (administrateur). Le mot de passe de type secret est chiffré

### 10.3 Configuration RADIUS

* **Commandes :**

    ```cisco
    Router(config)# radius server {nom}
    ```

    Définit un serveur radius

    ```cisco
    Router(config-radius-server)# address ipv4 {adresse_serveur} auth-port {port} acct-port {port}
    ```

    Definit l'adresse et le port du serveur radius.

    ```cisco
    Router(config-radius-server)# key {clé}
    ```

    Définit la clé secrète partagée avec le serveur RADIUS.

    ```cisco
    Router(config)# aaa authentication login default group radius local
    ```

    configure radius puis local en méthode de secours.

    ```cisco
    Router(config)# aaa authorization exec default group radius local
    ```

    configure radius puis local en méthode de secours.

### 10.4 Configuration TACACS+

* **Commandes :**

    ```cisco
    Router(config)# tacacs server {nom}
    ```

    Définit un serveur TACAS

    ```cisco
    Router(config-tacacs-server)# address ipv4 {adresse_serveur} port {port}
    ```

    Définit l'adresse et le port du serveur tacacs.

    ```cisco
    Router(config-tacacs-server)# key {clé}
    ```

    Définit la clé secrète partagée avec le serveur TACACS+.

    ```cisco
    Router(config)# aaa authentication login default group tacacs+ local
    ```

    configure tacacs+ puis local en méthode de secours.

    ```cisco
    Router(config)# aaa authorization exec default group tacacs+ local1
    ```

    configure tacacs+ puis local en méthode de secours.
