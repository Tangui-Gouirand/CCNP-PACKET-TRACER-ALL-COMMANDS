# CCNP-PACKET-TRACER-COMMANDES-UTILES FR
English version coming soon... ✍️

⚠️C'EST PAS FINI, IL MANQUE : SPANNING TREE, NAT-PAT, ACL, ETHERCHANNEL ET TOUT LES TRUCS EN LIEN AVEC IPV6


Ce document rassemble les commandes les plus utiles pour la préparation du CCNP sur Packet Tracer.

## Table des Matières

1.  [Sécurité et Accès](#sécurité-et-accès)
    * 1.1. [Configuration des Mots de Passe](#configuration-des-mots-de-passe)
        * 1.1.1. [Mot de passe d'activation (mode privilégié)](#mot-de-passe-dactivation-mode-privilégié)
        * 1.1.2. [Mot de passe d'accès à la console](#mot-de-passe-daccès-à-la-console)
        * 1.1.3. [Mot de passe d'accès VTY (SSH/Telnet)](#mot-de-passe-daccès-vty-sshtelnet)
    * 1.2. [AAA](#aaa)
        * 1.2.1. [Configuration AAA de base](#configuration-aaa-de-base)
        * 1.2.2. [Comptes locaux](#comptes-locaux)
        * 1.2.3.  [Configuration RADIUS](#configuration-radius)
        * 1.2.4.  [Configuration TACACS+](#configuration-tacacs)
    * 1.3. [SSH](#ssh)
    * 1.4. [Banner Message](#banner-message)
    * 1.5. [Déconnexion en Cas d'Inactivité](#déconnexion-en-cas-dinactivité)
        * 1.5.1. [Déconnexion pour la console](#déconnexion-pour-la-console)
        * 1.5.2. [Déconnexion pour VTY](#déconnexion-pour-vty)

2.  [Routage Dynamique](#routage-dynamique)
    * 2.1. [OSPF](#ospf)
        * 2.1.1. [Activation d'OSPF](#activation-dospf)
        * 2.1.2. [Configuration du Router-ID](#configuration-du-router-id)
        * 2.1.3. [Configuration des Interfaces OSPF](#configuration-des-interfaces-ospf)
        * 2.1.4. [Annonce des Réseaux](#annonce-des-réseaux)
        * 2.1.5. [Interface Passive](#interface-passive)
        * 2.1.6. [Authentification MD5 sur une Interface](#authentification-md5-sur-une-interface)
        * 2.1.7. [Authentification pour une Area](#authentification-pour-une-area)
        * 2.1.8. [Affichage des Voisins OSPF](#affichage-des-voisins-ospf)
    * 2.2. [EIGRP](#eigrp)
        * 2.2.1. [Activation d'EIGRP](#activation-deigrp)
        * 2.2.2. [Configuration du Router-ID](#configuration-du-router-id-1)
        * 2.2.3. [Définition des Réseaux à Annoncer](#définition-des-réseaux-à-annoncer)
        * 2.2.4. [Désactivation de la Summarization Automatique](#désactivation-de-la-summarization-automatique)
        * 2.2.5. [Configuration de l'Interface Passive](#configuration-de-linterface-passive-1)
        * 2.2.6. [Vérification des Voisins EIGRP](#vérification-des-voisins-eigrp)
        * 2.2.7. [Vérification de la Table de Topologie EIGRP](#vérification-de-la-table-de-topologie-eigrp)
        * 2.2.8. [Vérification de la Table de Routage EIGRP](#vérification-de-la-table-de-routage-eigrp)
    * 2.3. [BGP](#bgp)
        * 2.3.1 [Activation de BGP](#activation-de-bgp)
        * 2.3.2. [Définition des Voisins BGP](#définition-des-voisins-bgp)
        * 2.3.3. [Annonce d'un Réseau à Travers BGP](#annonce-dun-réseau-à-travers-bgp)
        * 2.3.4. [Redistribution de la Route par Défaut BGP](#redistribution-de-la-route-par-défaut-bgp)
    * 2.4. [HSRP](#hsrp)
    * 2.5. [Tunnel GRE](#tunnel-gre)

3.  [VLAN](#vlan)
    * 3.1. [Création de VLANs](#création-de-vlans)
    * 3.2. [Définir interface ip du VLAN](#définir-interface-ip-du-vlan)
    * 3.3. [Configuration des ports VLAN access (1vlan par lien)](#configuration-des-ports-vlan-access-1vlan-par-lien)
    * 3.4. [Configuration des ports VLAN TRUNK](#configuration-des-ports-vlan-trunk)
        * 3.4.1. [Protocole 802.1Q pour étiqueter les trames avec l'ID du VLAN (TRUNK)](#protocole-8021q-pour-étiqueter-les-trames-avec-lid-du-vlan-trunk)
        * 3.4.2. [VLAN natif](#vlan-natif)
        * 3.4.3. [VLAN VOIX](#vlan-voix)
    * 3.5. [Routage Inter-VLAN](#routage-inter-vlan)

4.  [Spanning Tree Protocol (STP)](#spanning-tree-protocol-stp)
    * 4.1. [Configuration du mode STP](#configuration-du-mode-stp)
    * 4.2. [Priorité et racine](#priorité-et-racine)
    * 4.3. [Timers STP](#timers-stp)
    * 4.4. [PortFast / BPDU Guard](#portfast-bpdu-guard)
    * 4.5. [MSTP (Multiple Spanning Tree)](#mstp-multiple-spanning-tree)
    * 4.6. [Vérification STP](#vérification-stp)

5.  [EtherChannel](#etherchannel)
    * 5.1. [LACP EtherChannel](#lacp-etherchannel)
    * 5.2. [PAgP EtherChannel](#pagp-etherchannel)
    * 5.3. [Statique EtherChannel](#statique-etherchannel)
    * 5.4. [Interface Port-Channel](#interface-port-channel)
    * 5.5. [Vérification EtherChannel](#verif-etherchannel)

6.  [NAT/PAT](#natpat)
    * 6.1. [NAT statique](#nat-statique)
    * 6.2. [NAT dynamique](#nat-dynamique)
    * 6.3. [PAT (NAT overload)](#pat-nat-overload)
    * 6.4. [Port forwarding (PAT statique)](#port-forwarding-pat)
    * 6.5. [Définition inside/outside](#inside-outside-nat)
    * 6.6. [Vérification NAT/PAT](#verif-nat-pat)

7.  [Access Control Lists (ACL)](#access-control-lists-acl)
    * 7.1. [ACL standard](#acl-standard)
    * 7.2. [ACL étendue](#acl-etendue)
    * 7.3. [ACL nommée](#acl-nommee)
    * 7.4. [Application interface](#application-acl-interface)
    * 7.5. [Application VTY](#application-acl-vty)
    * 7.6. [Suppression/Séquence](#suppression-sequence-acl)
    * 7.7. [Vérification ACL](#verif-acl)

8.  [IPv6 (Routage et Autoconfiguration)](#ipv6-routage-et-autoconfiguration)
    * 8.1. [Activation IPv6](#activation-ipv6)
    * 8.2. [Adresse interface IPv6](#adresse-interface-ipv6)
    * 8.3. [Routage statique IPv6](#routage-statique-ipv6)
    * 8.4. [OSPFv3](#ospfv3)
    * 8.5. [EIGRPv6](#eigrpv6)
    * 8.6. [BGP IPv6](#bgp-ipv6)
    * 8.7. [SLAAC](#slaac)
    * 8.8. [DHCPv6](#dhcpv6-stateless-stateful)
    * 8.9. [DHCPv6 relay](#dhcpv6-relay)
    * 8.10. [Vérification IPv6](#verif-ipv6)

9.  [Services Réseau](#services-réseau)
    * 9.1. [Protocole NTP](#protocole-ntp-network-time-protocol)
        * 9.1.1. [Serveur NTP](#serveur-ntp)
        * 9.1.2. [Pair NTP](#pair-ntp)
        * 9.1.3. [Serveur principal NTP](#serveur-principal-ntp)
    * 9.2. [Vérification NTP](#verif-ntp)
        * 9.2.1. [Synchronisation NTP](#etat-synchronisation-ntp)
        * 9.2.2. [Associations serveurs](#associations-serveurs-ntp)
        * 9.2.3. [Détails associations](#details-associations-ntp)
        * 9.2.4. [Détails horloge](#details-horloge)
    * 9.3. [SNMP](#snmp)
        * 9.3.1. [Communauté SNMP](#communaute-snmp)
        * 9.3.2. [Hôtes SNMP](#hotes-snmp)
        * 9.3.3. [Utilisateurs SNMPv3](#utilisateurs-snmpv3)
        * 9.3.4. [Vérification SNMP](#verif-snmp)
    * 9.4. [DHCP](#dhcp)
        * 9.4.1. [Pool DHCP](#pool-dhcp)
        * 9.4.2. [Serveur DNS](#serveur-dns-dhcp)
        * 9.4.3. [Exclusions IP](#exclusion-ip-dhcp)
    * 9.5. [SYSLOG](#syslog)
    * 9.6. [Fuseau Horaire](#fuseau-horaire)
    * 9.7. [Désactivation Recherche DNS](#desactiver-recherche-dns)

10. [Maintenance du Réseau](#maintenance-du-réseau)
    * 10.1.  [Effacer la configuration du switch](#effacer-la-configuration-du-switch)

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

### 1.2 AAA

#### 1.2.1 Configuration AAA de base

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

### 1.2.2 Comptes locaux

* **Commande :**

    ```cisco
    Router(config)# username {nom_utilisateur} privilege 15 secret {mot_de_passe}
    ```

    Crée un compte utilisateur local avec privilège 15 (administrateur). Le mot de passe de type secret est chiffré

### 1.2.3 Configuration RADIUS

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

### 1.2.4 Configuration TACACS+

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

### 1.3 SSH

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

### 1.4 Banner Message

* **Définir un message de bannière :**

    ```cisco
    Router(config)# banner {motd|exec|login|incoming} # message #
    ```

    * `MOTD` (Message of the Day) : Affiche un message avant l'invite de connexion.
    * `EXEC` : Affiche un message avant le mode d'exécution privilégié.
    * `Login` : Affiche un message avant l'invite de connexion.
    * `Incoming` : Affiche un message pour les connexions entrantes (par exemple, Telnet, SSH).

### 1.5 Déconnexion en Cas d'Inactivité

#### 1.5.1 Déconnexion pour la console

* **Commande :**

    ```cisco
    Router(config)# line console 0
    Router(config-line)# exec-timeout minutes secondes
    ```

* **Explication :** Remplacez `minutes` et `secondes` par la durée d'inactivité souhaitée.

#### 1.5.2 Déconnexion pour VTY

* **Commande :**

    ```cisco
    Router(config)# line vty 0 4
    Router(config-line)# exec-timeout minutes secondes
    ```

* **Explication :** Remplacez `minutes` et `secondes` par la durée d'inactivité souhaitée.

## Routage Dynamique

### 2.1 OSPF

#### 2.1.1 Activation d'OSPF

* **Commande :**

    ```cisco
    R1(config)# router ospf <process-id>
    ```

    * **Explication** Active le processus OSPF et spécifie l'ID de processus OSPF

#### 2.1.2 Configuration du Router-ID

* **Commande :**

    ```cisco
    R1(config-router)#ospf router-id <id ex:1.1.1.1>
    ```

#### 2.1.3 Configuration des Interfaces OSPF

* **Commandes :**

    ```cisco
    R1(config)# interface <interface>
    R1(config-if)# ip ospf <process-id> area  <num area>
    ```

#### 2.1.4 Annonce des Réseaux

* **Commandes :**

    ```cisco
    R1(config-router)# network 192.168.1.0 0.0.0.255 area <num area>
    R1(config-router)# network 10.0.0.0 0.0.255.255 area <num area>
    ```

#### 2.1.5 Interface Passive

* **Commande :**

    ```cisco
    R1(config-router)# passive-interface GigabitEthernet0/0
    ```

    * **Explication**: Désactive l'envoi de paquets OSPF sur une interface

#### 2.1.6 Authentification MD5 sur une Interface

* **Commandes :**

    ```cisco
    Router(config)# interface FastEthernet0/0
    Router(config-if)# ip ospf message-digest-key 1 md5 MOTDEPASSE
    Router(config-if)# ip ospf authentication message-digest
    ```

#### 2.1.7 Authentification pour une Area

* **Commandes :**

    ```cisco
    Router(config)# router ospf 1
    Router(config-router)# area 0 authentication message-digest
    ```

#### 2.1.8 Affichage des Voisins OSPF

* **Commandes :**

    ```cisco
    R1#show ip ospf neighbors
    ```

    Ou

    ```cisco
    R1#show ip ospf database
    ```

### 2.2 EIGRP

#### 2.2.1 Activation d'EIGRP

* **Commande :**

    ```cisco
    R1(config)#router eigrp <numero_AS>
    ```

#### 2.2.2 Configuration du Router-ID

* **Commande :**

    ```cisco
    R1(config-router)#eigrp router-id <id ex:1.1.1.1>
    ```

#### 2.2.3 Définition des Réseaux à Annoncer

* **Commande :**

    ```cisco
    network <adresse_réseau> [mask-inversé]
    ```

    * **Explication**: L'utilisation du masque générique est optionnelle mais recommandée

#### 2.2.4 Désactivation de la Summarization Automatique

* **Commande :**

    ```cisco
    R1(config-router)#no auto-summary
    ```

#### 2.2.5 Configuration de l'Interface Passive

* **Commande :**

    ```cisco
    R1(config-router)# passive-interface GigabitEthernet0/0
    ```

    * **Explication**: Empêche l'envoi de mises à jour EIGRP sur une interface.

#### 2.2.6 Vérification des Voisins EIGRP

* **Commande :**

    ```cisco
    R1#show ip eigrp neighbors
    ```

#### 2.2.7 Vérification de la Table de Topologie EIGRP

* **Commande :**

    ```cisco
    R1#show ip eigrp topology
    ```

#### 2.2.8 Vérification de la Table de Routage EIGRP

* **Commande :**

    ```cisco
    R1#show ip route eigrp
    ```

### 2.3 BGP

#### 2.3.1 Activation de BGP

* **Commande :**

    ```cisco
    R1(config)#router bgp <numero_AS>
    ```

#### 2.3.2 Définition des Voisins BGP

* **Commande :**

    ```cisco
    R1(config-router)#neighbor <adresse_réseau> remote-as <numero_AS_voisin>
    ```

#### 2.3.3 Annonce d'un Réseau à Travers BGP

* **Commande :**

    ```cisco
    R1(config-router)#network <adresse_réseau> mask <masque_sous-réseau>
    ```

#### 2.3.4 Redistribution de la Route par Défaut BGP

* **Commande :**

    ```cisco
    R1(config-router)#default-information originate
    ```

### 2.4 HSRP

* **Interface <numéro_vlan> ou <serial/gigabit>**

    ```cisco
    Router(config-if)# standby version {1|2}
    Router(config-if)# standby {groupe} ip {adresse_ip_virtuelle}
    Router(config-if)# standby {groupe} priority {priorité}
    ```

    par défaut : 100, mettre 150 pour définir en primaire – ne pas mettre la commande pour secondaire

    ```cisco
    Router(config-if)# standby {groupe} preempt
    ```

    Permet au routeur ayant la priorité la plus élevée de devenir actif

    ```cisco
    Router(config-if)# standby {groupe} name {nom}
    ```

    configuration d'un nom de groupe

* Affiche l'état des groupes HSRP.

    ```cisco
    Router# show standby
    ```

* Affiche l'état résumé des groupes HSRP.

    ```cisco
    Router# show standby brief
    ```

### 2.5 Tunnel GRE

* ```cisco
    Router(config)# interface tunnel {numéro}
    Router(config-if)#ip addresse {adresse_ip} {masque}
    ```

    Crée une interface de tunnel GRE.
    Attribuer une adresse IP à l'interface de tunnel.

* ```cisco
    Router(config-if)# tunnel source {adresse_ip_source}
    ```

    Définir l'adresse IP source du tunnel.

    ```cisco
    Router(config-if)# tunnel destination {adresse_ip_destination}
    ```

    Définir l'adresse IP de destination du tunnel.

    ```cisco
    Router(config-if)# tunnel mode gre ip
    ```

    Indique que le type de tunnel est GRE.

* ```cisco
    Router(config-if)# ip mtu {valeur}
    ```

    Ajustement de la MTU (Maximum Transmission Unit) du tunnel, pour éviter la fragmentation.

* ```cisco
    Router# show interfaces tunnel {numéro}
    ```

    Affiche les informations de l'interface de tunnel.

## VLAN

### 3.1 Création de VLANs

* **Commandes :**

    ```cisco
    S1(config)#vlan <numéro_vlan>
    S1(config-vlan)#name <nom_vlan>
    ```

#### 3.2 Définir interface ip du VLAN

* **Commandes :**

    ```cisco
    S1(config)#interface vlan <numéro_vlan>
    S1(config-if)#ip address 192.168.10.254 255.255.255.0
    S1(config-if)#ip default-gateway 192.168.10.1
    ```

#### 3.3 Configuration des ports VLAN access (1vlan par lien)

* **Commandes :**

    ```cisco
    S1(config-if)#switchport mode access
    S1(config-if)#switchport access vlan <numéro_vlan>
    ```

#### 3.4 Configuration des ports VLAN TRUNK

* **Commande :**
    Configure un port en mode trunk (pour les liaisons inter-switch ou routeur)

    ```cisco
    S1(config-if)#switchport mode trunk
    S1(config-if)#switchport trunk allowed vlan <liste_vlans>
    ```

#### 3.5 Protocole 802.1Q pour étiqueter les trames avec l'ID du VLAN (TRUNK)

* **Commande :**

    ```cisco
    S1(config-if)#switchport trunk encapsulation dot1q
    ```

#### 3.6 VLAN natif

* **Commande :**
    Lorsque des trames qui ne sont pas étiquetées sont transférées sur un port trunk, le switch vas les associés au vlan natif

    ```cisco
    S1(config-if)#switchport trunk native vlan <numéro_vlan>
    ```

#### 3.7 VLAN VOIX

* **Commande :**

    ```cisco
    S1(config-if)#switchport voice vlan <vlan-id>
    ```

* **Résumé des VLANs et de leurs ports associés**

    ```cisco
    S1#show vlan brief
    ```

* **Informations détaillées sur les VLANs**

    ```cisco
    S1#show vlan
    ```

### 3.8 Routage Inter-VLAN

* **Crée une sous-interface**

    ```cisco
    R1(config)#interface G0/1.10
    R1(config-subif)#description Default Gateway for VLAN 10
    R1(config-subif)#encapsulation dot1Q 10
    R1(config-subif)#ip add 192.168.10.1 255.255.255.0
    ```

* **Démo 2**

    ```cisco
    R1(config)#interface G0/1.20
    R1(config-subif)#description Default Gateway for VLAN 20
    R1(config-subif)#encapsulation dot1Q 20
    R1(config-subif)#ip addr 192.168.20.1 255.255.255.0
    ```

## Services Réseau

### 9.1 Protocole NTP (Network Time Protocol)

#### 9.1.1 Définir un serveur NTP

* **Commande :**

    ```cisco
    Router(config)# ntp server adresse_ip_serveur
    ```

#### 9.1.2 Définir un pair NTP (synchronisation mutuelle)

* **Commande :**

    ```cisco
    Router(config)# ntp peer adresse_ip_pair
    ```

#### 9.1.3 Configurer l'appareil comme serveur NTP principal

* **Commande :**

    ```cisco
    Router(config)# ntp master
    ```

### 9.2 Vérification de l'État NTP

#### 9.2.1 Afficher l'état de la synchronisation NTP

* **Commande :**

    ```cisco
    Router# show ntp status
    ```

#### 9.2.2 Afficher les associations avec les serveurs NTP

* **Commande :**

    ```cisco
    Router# show ntp associations
    ```

#### 9.2.3 Afficher les détails des associations NTP

* **Commande :**

    ```cisco
    Router# show ntp associations detail
    ```

#### 9.2.4 Afficher les détails de l'horloge

* **Commande :**

    ```cisco
    Router# show clock detail
    ```

### 9.3  SNMP (Simple Network Management Protocol) - Gestion Réseau

#### 9.3.1 Configuration de la Communauté SNMP

* **Commande :**

    ```cisco
    Router(config)# snmp-server community nom {RO|RW}
    ```

* **Explication :**
    * `RO` (Read-Only) : Lecture seule.
    * `RW` (Read-Write) : Lecture et écriture.

#### 9.3.2 Configuration des Hôtes SNMP

* **Commande :**

    ```cisco
    Router(config)# snmp-server host adresse_ip_NMS community nom [traps|informs]
    ```

### 9.3.3 Configuration des Utilisateurs SNMPv3

* **Commande :**

    ```cisco
    Router(config)# snmp-server user nom group-name auth {md5|sha} mot_de_passe priv {des|aes} mot_de_passe access acl-name
    ```

### 9.3.4 Vérification de la Configuration SNMP

* **Commandes :**

    ```cisco
    Router# show snmp community
    Router# show snmp host
    Router# show snmp traps
    ```

### 9.4 DHCP

#### 9.4.1 Configuration du Pool DHCP

* **Commandes :**

    ```cisco
    Routerconfig)# ip dhcp pool Mon_POOL_DHCP
    Router(dhcp-config)# network 192.168.10.0 255.255.255.0
    Router(dhcp-config)# default-router 192.168.10.1
    Router(dhcp-config)#domain-name MONDOMAINE.FR
    ```

#### 9.4.2 Définition du Serveur DNS pour le DHCP

* **Commande :**

    ```cisco
    Router(dhcp-config)# dns-server 8.8.8.8
    ```

#### 9.4.3 Exclusion d'Adresses IP

* **Commande :**

    ```cisco
    Router(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.10
    ```

### 9.5 SYSLOG

* **Définir l'adresse du serveur Syslog :**

    ```cisco
    Router(config)# logging host adresse_ip_serveur
    ```

* **Définir le niveau de gravité des messages Syslog à envoyer (souvent debugging) :**

    ```cisco
    Router(config)# logging trap niveau_gravité
    ```

### 9.6 Fuseau Horaire

* **Définir le fuseau horaire :**

    ```cisco
    Router(config)# clock timezone nom_fuseau_horaire décalage_utc
    ```

* **Afficher les détails de l'horloge :**

    ```cisco
    Router# show clock detail
    ```

### 9.7 Désactiver la Recherche DNS

* **Désactiver la recherche DNS :**

    ```cisco
    Router(config)# no ip domain-lookup
    ```

## Maintenance du Réseau

### 10.1 Effacer la Configuration du Switch

* **Effacer la configuration du switch :**

    ```cisco
    S1# erase startup-config
    S1# delete vlan.dat
    S1# reload
    ```
