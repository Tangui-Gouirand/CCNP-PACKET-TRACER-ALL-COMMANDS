# CCNP-PACKET-TRACER-COMMANDES-UTILES FR
English version coming soon... ✍️

Ce document rassemble les commandes les plus utiles pour la préparation du CCNP Encor sur Packet Tracer.

> **Note importante :** Ce guide se concentre *uniquement* sur les commandes et les technologies supportées par **Packet Tracer**. Les sujets avancés de l'examen ENCOR (Wireless, SD-WAN, automatisation, etc.) ne sont pas inclus.

## Table des Matières

0.  [Configuration Initiale et Vérifications](#0-configuration-initiale-et-vérifications)
    * 0.1. [Configuration de Base](#01-configuration-de-base)
    * 0.2. [Commandes de Vérification Fondamentales](#02-commandes-de-vérification-fondamentales)
    * 0.3. [Test de Connectivité](#03-test-de-connectivité)

1.  [Sécurité et Accès](#1-sécurité-et-accès)
    * 1.1. [Configuration des Mots de Passe](#11-configuration-des-mots-de-passe)
        * 1.1.1. [Mot de passe d'activation (mode privilégié)](#111-mot-de-passe-dactivation-mode-privilégié)
        * 1.1.2. [Mot de passe d'accès à la console](#112-mot-de-passe-daccès-à-la-console)
        * 1.1.3. [Mot de passe d'accès VTY (SSH/Telnet)](#113-mot-de-passe-daccès-vty-sshtelnet)
    * 1.2. [AAA](#12-aaa)
        * 1.2.1. [Configuration AAA de base](#121-configuration-aaa-de-base)
        * 1.2.2. [Comptes locaux](#122-comptes-locaux)
        * 1.2.3. [Configuration RADIUS](#123-configuration-radius)
        * 1.2.4. [Configuration TACACS+](#124-configuration-tacacs)
    * 1.3. [SSH](#13-ssh)
    * 1.4. [Banner Message](#14-banner-message)
    * 1.5. [Déconnexion en Cas d'Inactivité](#15-déconnexion-en-cas-dinactivité)
        * 1.5.1. [Déconnexion pour la console](#151-déconnexion-pour-la-console)
        * 1.5.2. [Déconnexion pour VTY](#152-déconnexion-pour-vty)
    * 1.6. [Port Security](#16-port-security)
        * 1.6.1. [Configuration Port Security](#161-configuration-port-security)
        * 1.6.2. [Vérification Port Security](#162-vérification-port-security)

2.  [Routage Statique et Dynamique](#2-routage-statique-et-dynamique)
    * 2.1. [Routage Statique (IPv4)](#21-routage-statique-ipv4)
    * 2.2. [OSPF](#22-ospf)
        * 2.2.1. [Activation d'OSPF](#221-activation-dospf)
        * 2.2.2. [Configuration du Router-ID](#222-configuration-du-router-id)
        * 2.2.3. [Configuration des Interfaces OSPF](#223-configuration-des-interfaces-ospf)
        * 2.2.4. [Annonce des Réseaux](#224-annonce-des-réseaux)
        * 2.2.5. [Interface Passive](#225-interface-passive)
        * 2.2.6. [Authentification MD5 sur une Interface](#226-authentification-md5-sur-une-interface)
        * 2.2.7. [Authentification pour une Area](#227-authentification-pour-une-area)
        * 2.2.8. [Vérification OSPF](#228-vérification-ospf)
    * 2.3. [EIGRP](#23-eigrp)
        * 2.3.1. [Activation d'EIGRP](#231-activation-deigrp)
        * 2.3.2. [Configuration du Router-ID](#232-configuration-du-router-id)
        * 2.3.3. [Définition des Réseaux à Annoncer](#233-définition-des-réseaux-à-annoncer)
        * 2.3.4. [Désactivation de la Summarization Automatique](#234-désactivation-de-la-summarization-automatique)
        * 2.3.5. [Configuration de l'Interface Passive](#235-configuration-de-linterface-passive)
        * 2.3.6. [Vérification EIGRP](#236-vérification-eigrp)
    * 2.4. [BGP](#24-bgp)
        * 2.4.1 [Activation de BGP](#241-activation-de-bgp)
        * 2.4.2. [Définition des Voisins BGP](#242-définition-des-voisins-bgp)
        * 2.4.3. [Annonce d'un Réseau à Travers BGP](#243-annonce-dun-réseau-à-travers-bgp)
        * 2.4.4. [Redistribution de la Route par Défaut BGP](#244-redistribution-de-la-route-par-défaut-bgp)
    * 2.5. [Redistribution](#25-redistribution)
        * 2.5.1. [EIGRP vers OSPF](#251-eigrp-vers-ospf)
        * 2.5.2. [OSPF vers EIGRP](#252-ospf-vers-eigrp)
    * 2.6. [HSRP](#26-hsrp)
    * 2.7. [Tunnel GRE](#27-tunnel-gre)

3.  [VLAN et Commutation L2](#3-vlan-et-commutation-l2)
    * 3.1. [Création de VLANs](#31-création-de-vlans)
    * 3.2. [Définir interface ip du VLAN (SVI)](#32-définir-interface-ip-du-vlan-svi)
    * 3.3. [Configuration des ports VLAN access](#33-configuration-des-ports-vlan-access)
    * 3.4. [Configuration des ports VLAN TRUNK](#34-configuration-des-ports-vlan-trunk)
        * 3.4.1. [Protocole 802.1Q (Encapsulation)](#341-protocole-8021q-encapsulation)
        * 3.4.2. [VLAN natif](#342-vlan-natif)
        * 3.4.3. [VLAN VOIX](#343-vlan-voix)
    * 3.5. [Routage Inter-VLAN](#35-routage-inter-vlan)
    * 3.6. [Vérification VLAN](#36-vérification-vlan)
    * 3.7. [DTP (Dynamic Trunking Protocol)](#37-dtp-dynamic-trunking-protocol)
    * 3.8. [VTP (VLAN Trunking Protocol)](#38-vtp-vlan-trunking-protocol)
        * 3.8.1. [Configuration VTP](#381-configuration-vtp)
        * 3.8.2. [Vérification VTP](#382-vérification-vtp)

4.  [Spanning Tree Protocol (STP)](#4-spanning-tree-protocol-stp)
    * 4.1. [Configuration du mode STP](#41-configuration-du-mode-stp)
    * 4.2. [Priorité et racine](#42-priorité-et-racine)
    * 4.3. [Timers STP](#43-timers-stp)
    * 4.4. [PortFast / BPDU Guard](#44-portfast--bpdu-guard)
    * 4.5. [MSTP (Multiple Spanning Tree)](#45-mstp-multiple-spanning-tree)
    * 4.6. [Vérification STP](#46-vérification-stp)

5.  [EtherChannel](#5-etherchannel)
    * 5.1. [LACP EtherChannel](#51-lacp-etherchannel)
    * 5.2. [PAgP EtherChannel](#52-pagp-etherchannel)
    * 5.3. [Statique EtherChannel](#53-statique-etherchannel)
    * 5.4. [Interface Port-Channel](#54-interface-port-channel)
    * 5.5. [Vérification EtherChannel](#55-vérification-etherchannel)

6.  [NAT/PAT](#6-natpat)
    * 6.1. [NAT statique](#61-nat-statique)
    * 6.2. [NAT dynamique](#62-nat-dynamique)
    * 6.3. [PAT (NAT overload)](#63-pat-nat-overload)
    * 6.4. [Port forwarding (PAT statique)](#64-port-forwarding-pat-statique)
    * 6.5. [Définition inside/outside](#65-définition-insideoutside)
    * 6.6. [Vérification NAT/PAT](#66-vérification-natpat)

7.  [Access Control Lists (ACL)](#7-access-control-lists-acl)
    * 7.1. [ACL standard](#71-acl-standard)
    * 7.2. [ACL étendue](#72-acl-étendue)
    * 7.3. [ACL nommée](#73-acl-nommée)
    * 7.4. [Application interface](#74-application-interface)
    * 7.5. [Application VTY](#75-application-vty)
    * 7.6. [Suppression/Séquence](#76-suppressionséquence)
    * 7.7. [Vérification ACL](#77-vérification-acl)

8.  [IPv6 (Routage et Autoconfiguration)](#8-ipv6-routage-et-autoconfiguration)
    * 8.1. [Activation IPv6](#81-activation-ipv6)
    * 8.2. [Adresse interface IPv6](#82-adresse-interface-ipv6)
    * 8.3. [Routage statique IPv6](#83-routage-statique-ipv6)
    * 8.4. [OSPFv3](#84-ospfv3)
    * 8.5. [EIGRPv6](#85-eigrpv6)
    * 8.6. [BGP IPv6](#86-bgp-ipv6)
    * 8.7. [SLAAC](#87-slaac)
    * 8.8. [DHCPv6 (Stateless et Stateful)](#88-dhcpv6-stateless-et-stateful)
    * 8.9. [DHCPv6 relay](#89-dhcpv6-relay)
    * 8.10. [Vérification IPv6](#810-vérification-ipv6)

9.  [Services Réseau](#9-services-réseau)
    * 9.1. [Protocole NTP](#91-protocole-ntp)
        * 9.1.1. [Serveur NTP](#911-serveur-ntp)
        * 9.1.2. [Pair NTP](#912-pair-ntp)
        * 9.1.3. [Serveur principal NTP](#913-serveur-principal-ntp)
    * 9.2. [Vérification NTP](#92-vérification-ntp)
        * 9.2.1. [Synchronisation NTP](#921-synchronisation-ntp)
        * 9.2.2. [Associations serveurs](#922-associations-serveurs)
        * 9.2.3. [Détails associations](#923-détails-associations)
        * 9.2.4. [Détails horloge](#924-détails-horloge)
    * 9.3. [SNMP](#93-snmp)
        * 9.3.1. [Communauté SNMP](#931-communauté-snmp)
        * 9.3.2. [Hôtes SNMP](#932-hôtes-snmp)
        * 9.3.3. [Utilisateurs SNMPv3](#933-utilisateurs-snmpv3)
        * 9.3.4. [Vérification SNMP](#934-vérification-snmp)
    * 9.4. [DHCP (IPv4)](#94-dhcp-ipv4)
        * 9.4.1. [Pool DHCP](#941-pool-dhcp)
        * 9.4.2. [Serveur DNS](#942-serveur-dns)
        * 9.4.3. [Exclusions IP](#943-exclusions-ip)
    * 9.5. [DHCP Relay (IPv4)](#95-dhcp-relay-ipv4)
    * 9.6. [CDP / LLDP](#96-cdp--lldp)
        * 9.6.1. [Configuration](#961-configuration)
        * 9.6.2. [Vérification](#962-vérification)
    * 9.7. [SYSLOG](#97-syslog)
    * 9.8. [Fuseau Horaire](#98-fuseau-horaire)
    * 9.9. [Désactivation Recherche DNS](#99-désactivation-recherche-dns)

10. [Maintenance du Réseau](#10-maintenance-du-réseau)
    * 10.1. [Effacer la configuration du switch](#101-effacer-la-configuration-du-switch)

---

## 0. Configuration Initiale et Vérifications

### 0.1 Configuration de Base

* **Définir le nom de l'équipement :**
    ```ini
    Router(config)# hostname R1
    ```
* **Enregistrer la configuration en cours dans la configuration de démarrage :**
    ```ini
    R1# copy running-config startup-config
    ```
    * **Raccourci :** `wr`

### 0.2 Commandes de Vérification Fondamentales

* **Afficher la configuration en cours :**
    ```ini
    R1# show running-config
    ```
* **Afficher la configuration de démarrage :**
    ```ini
    R1# show startup-config
    ```
* **Afficher un résumé de l'état des interfaces IP :**
    ```ini
    R1# show ip interface brief
    ```
* **Afficher les détails d'une interface (état, erreurs, duplex, etc.) :**
    ```ini
    R1# show interfaces GigabitEthernet0/0
    ```
* **Afficher la table de routage IP :**
    ```ini
    R1# show ip route
    ```
* **Afficher les informations système (version IOS, uptime, etc.) :**
    ```ini
    R1# show version
    ```

### 0.3 Test de Connectivité

* **Envoyer des requêtes ICMP (ping) :**
    ```ini
    R1# ping 192.168.1.1
    ```
* **Tracer le chemin vers une destination :**
    ```ini
    R1# traceroute 8.8.8.8
    ```

---

## 1. Sécurité et Accès

### 1.1 Configuration des Mots de Passe

#### 1.1.1 Mot de passe d'activation (mode privilégié)

* **Commande :**
    ```ini
    Router(config)# enable secret cisco
    ```
* **Explication :** `enable secret` crypte le mot de passe, offrant une meilleure sécurité que `enable password`.

#### 1.1.2 Mot de passe d'accès à la console

* **Commandes :**
    ```ini
    Router(config)# line console 0
    Router(config-line)# login
    Router(config-line)# password cisco
    ```
* **Explication :**
    * `line console 0` configure la ligne de console.
    * `login` demande un mot de passe pour accéder à la console.

#### 1.1.3 Mot de passe d'accès VTY (SSH/Telnet)

* **Commandes :**
    ```ini
    Router(config)# line vty 0 4
    Router(config-line)# login
    Router(config-line)# password cisco
    ```
* **Explication :** `line vty 0 4` configure les lignes virtuelles pour les connexions Telnet et SSH (0 à 4 = 5 sessions simultanées).

### 1.2 AAA

#### 1.2.1 Configuration AAA de base

* **Commandes :**
    ```ini
    Router(config)# aaa new-model
    ```
    Définit la méthode d'authentification par défaut pour les connexions :
    ```ini
    Router(config)# aaa authentication login default group {tacacs+|radius|local}
    ```
    Définit la méthode d'autorisation par défaut pour les commandes EXEC :
    ```ini
    Router(config)# aaa authorization exec default group {tacacs+|radius|local}
    ```
    Active la comptabilité pour les commandes EXEC :
    ```ini
    Router(config)# aaa accounting exec default start-stop group {tacacs+|radius}
    ```

#### 1.2.2 Comptes locaux

* **Commande :**
    ```ini
    Router(config)# username {nom_utilisateur} privilege 15 secret {mot_de_passe}
    ```
    Crée un compte utilisateur local avec privilège 15 (administrateur). Le mot de passe de type `secret` est chiffré.

#### 1.2.3 Configuration RADIUS

* **Commandes :**
    Définit un serveur radius :
    ```ini
    Router(config)# radius server {nom}
    ```
    Definit l'adresse et le port du serveur radius :
    ```ini
    Router(config-radius-server)# address ipv4 {adresse_serveur} auth-port {port} acct-port {port}
    ```
    Définit la clé secrète partagée avec le serveur RADIUS :
    ```ini
    Router(config-radius-server)# key {clé}
    ```
    Configure radius puis local en méthode de secours :
    ```ini
    Router(config)# aaa authentication login default group radius local
    Router(config)# aaa authorization exec default group radius local
    ```

#### 1.2.4 Configuration TACACS+

* **Commandes :**
    Définit un serveur TACACS :
    ```ini
    Router(config)# tacacs server {nom}
    ```
    Définit l'adresse et le port du serveur tacacs :
    ```ini
    Router(config-tacacs-server)# address ipv4 {adresse_serveur} port {port}
    ```
    Définit la clé secrète partagée avec le serveur TACACS+ :
    ```ini
    Router(config-tacacs-server)# key {clé}
    ```
    Configure tacacs+ puis local en méthode de secours :
    ```ini
    Router(config)# aaa authentication login default group tacacs+ local
    Router(config)# aaa authorization exec default group tacacs+ local
    ```

### 1.3 SSH

* **Générer une clé RSA (nécessaire pour SSH) :**
    * Un nom de domaine doit être configuré au préalable : `ip domain-name nom_de_domaine`
    ```ini
    Router(config)# crypto key generate rsa
    ```
    * Pour la taille de la clé, il est recommandé d'utiliser 2048 bits.

* **Définir la version de SSH :**
    ```ini
    Router(config)# ip ssh version {1|2}
    ```
    * La version 2 est recommandée.

* **Configurer les lignes VTY pour accepter uniquement les connexions SSH :**
    ```ini
    Router(config)# line vty 0 15
    Router(config-line)# transport input ssh
    Router(config-line)# login local
    ```
    * `line vty 0 15` configure les lignes virtuelles 0 à 15 (16 sessions simultanées).
    * `transport input ssh` limite le trafic entrant sur ces lignes à SSH.
    * `login local` utilise la base de données locale du routeur pour l'authentification des utilisateurs.

* **Définir le nombre de tentatives d'authentification SSH :**
    ```ini
    Router(config)# ip ssh authentication-retries nombre
    ```

### 1.4 Banner Message

* **Définir un message de bannière :**
    ```ini
    Router(config)# banner {motd|exec|login|incoming} # message #
    ```
    * `MOTD` (Message of the Day) : Affiche un message avant l'invite de connexion.
    * `EXEC` : Affiche un message avant le mode d'exécution privilégié.
    * `Login` : Affiche un message avant l'invite de connexion.
    * `Incoming` : Affiche un message pour les connexions entrantes (par exemple, Telnet, SSH).

### 1.5 Déconnexion en Cas d'Inactivité

#### 1.5.1 Déconnexion pour la console

* **Commande :**
    ```ini
    Router(config)# line console 0
    Router(config-line)# exec-timeout minutes secondes
    ```
* **Explication :** Remplacez `minutes` et `secondes` par la durée d'inactivité souhaitée.

#### 1.5.2 Déconnexion pour VTY

* **Commande :**
    ```ini
    Router(config)# line vty 0 4
    Router(config-line)# exec-timeout minutes secondes
    ```
* **Explication :** Remplacez `minutes` et `secondes` par la durée d'inactivité souhaitée.

### 1.6 Port Security

#### 1.6.1 Configuration Port Security

* **Commandes :**
    ```ini
    Switch(config)# interface <type/num>
    Switch(config-if)# switchport mode access
    Switch(config-if)# switchport port-security
    Switch(config-if)# switchport port-security maximum <nombre>
    Switch(config-if)# switchport port-security violation {shutdown | restrict | protect}
    Switch(config-if)# switchport port-security mac-address sticky
    ```
* **Explications :**
    * `port-security` : Active la sécurité du port.
    * `maximum` : Définit le nombre maximum d'adresses MAC autorisées.
    * `violation` : Définit l'action en cas de violation (shutdown est le plus courant).
    * `mac-address sticky` : Apprend dynamiquement les adresses MAC et les ajoute à la running-config.

#### 1.6.2 Vérification Port Security

* **Commande :**
    ```ini
    Switch# show port-security interface <type/num>
    ```

---

## 2. Routage Statique et Dynamique

### 2.1 Routage Statique (IPv4)

* **Route vers un réseau :**
    ```ini
    Router(config)# ip route <réseau_destination> <masque> <ip_next-hop | interface_sortie>
    ```
* **Route par défaut :**
    ```ini
    Router(config)# ip route 0.0.0.0 0.0.0.0 <ip_next-hop | interface_sortie>
    ```

### 2.2 OSPF

#### 2.2.1 Activation d'OSPF

* **Commande :**
    ```ini
    R1(config)# router ospf <process-id>
    ```
    * **Explication** Active le processus OSPF et spécifie l'ID de processus OSPF

#### 2.2.2 Configuration du Router-ID

* **Commande :**
    ```ini
    R1(config-router)# ospf router-id <id ex:1.1.1.1>
    ```
    * **Note :** Sur Packet Tracer, `router-id <id>` est parfois la commande correcte.

#### 2.2.3 Configuration des Interfaces OSPF

* **Commandes :**
    ```ini
    R1(config)# interface <interface>
    R1(config-if)# ip ospf <process-id> area <num area>
    ```

#### 2.2.4 Annonce des Réseaux

* **Commandes :**
    ```ini
    R1(config-router)# network 192.168.1.0 0.0.0.255 area <num area>
    R1(config-router)# network 10.0.0.0 0.0.255.255 area <num area>
    ```

#### 2.2.5 Interface Passive

* **Commande :**
    ```ini
    R1(config-router)# passive-interface GigabitEthernet0/0
    ```
    * **Explication**: Désactive l'envoi de paquets OSPF sur une interface

#### 2.2.6 Authentification MD5 sur une Interface

* **Commandes :**
    ```ini
    Router(config)# interface FastEthernet0/0
    Router(config-if)# ip ospf message-digest-key 1 md5 MOTDEPASSE
    Router(config-if)# ip ospf authentication message-digest
    ```

#### 2.2.7 Authentification pour une Area

* **Commandes :**
    ```ini
    Router(config)# router ospf 1
    Router(config-router)# area 0 authentication message-digest
    ```

#### 2.2.8 Vérification OSPF

* **Affichage des Voisins OSPF :**
    ```ini
    R1# show ip ospf neighbor
    ```
* **Affichage de la base de données OSPF :**
    ```ini
    R1# show ip ospf database
    ```
* **Affichage des interfaces OSPF :**
    ```ini
    R1# show ip ospf interface brief
    ```

### 2.3 EIGRP

#### 2.3.1 Activation d'EIGRP

* **Commande :**
    ```ini
    R1(config)# router eigrp <numero_AS>
    ```

#### 2.3.2 Configuration du Router-ID

* **Commande :**
    ```ini
    R1(config-router)# eigrp router-id <id ex:1.1.1.1>
    ```

#### 2.3.3 Définition des Réseaux à Annoncer

* **Commande :**
    ```ini
    R1(config-router)# network <adresse_réseau> [mask-inversé]
    ```
    * **Explication**: L'utilisation du masque générique est optionnelle mais recommandée

#### 2.3.4 Désactivation de la Summarization Automatique

* **Commande :**
    ```ini
    R1(config-router)# no auto-summary
    ```

#### 2.3.5 Configuration de l'Interface Passive

* **Commande :**
    ```ini
    R1(config-router)# passive-interface GigabitEthernet0/0
    ```
    * **Explication**: Empêche l'envoi de mises à jour EIGRP sur une interface.

#### 2.3.6 Vérification EIGRP

* **Vérification des Voisins EIGRP :**
    ```ini
    R1# show ip eigrp neighbors
    ```
* **Vérification de la Table de Topologie EIGRP :**
    ```ini
    R1# show ip eigrp topology
    ```
* **Vérification de la Table de Routage EIGRP :**
    ```ini
    R1# show ip route eigrp
    ```

### 2.4 BGP

#### 2.4.1 Activation de BGP

* **Commande :**
    ```ini
    R1(config)# router bgp <numero_AS>
    ```

#### 2.4.2 Définition des Voisins BGP

* **Commande :**
    ```ini
    R1(config-router)# neighbor <adresse_réseau> remote-as <numero_AS_voisin>
    ```

#### 2.4.3 Annonce d'un Réseau à Travers BGP

* **Commande :**
    ```ini
    R1(config-router)# network <adresse_réseau> mask <masque_sous-réseau>
    ```

#### 2.4.4 Redistribution de la Route par Défaut BGP

* **Commande :**
    ```ini
    R1(config-router)# default-information originate
    ```

### 2.5 Redistribution

#### 2.5.1 EIGRP vers OSPF

* **Commande :**
    ```ini
    R1(config)# router ospf 1
    R1(config-router)# redistribute eigrp <numero_AS> subnets
    ```
* **Explication :** `subnets` est crucial pour inclure tous les sous-réseaux.

#### 2.5.2 OSPF vers EIGRP

* **Commande :**
    ```ini
    R1(config)# router eigrp <numero_AS>
    R1(config-router)# redistribute ospf <process-id> metric <bw> <delay> <reliability> <load> <mtu>
    ```
* **Explication :** EIGRP nécessite la définition de métriques par défaut lors de la redistribution.
* **Exemple de métriques :** `metric 10000 10 255 1 1500`

### 2.6 HSRP

* **Configuration Interface :**
    * S'applique sur une interface (physique ou SVI `interface Vlan <num>`)
    ```ini
    Router(config-if)# standby version {1|2}
    Router(config-if)# standby {groupe} ip {adresse_ip_virtuelle}
    Router(config-if)# standby {groupe} priority {priorité}
    ```
    * par défaut : 100, mettre 150 pour définir en primaire
    ```ini
    Router(config-if)# standby {groupe} preempt
    ```
    * Permet au routeur ayant la priorité la plus élevée de redevenir actif
    ```ini
    Router(config-if)# standby {groupe} name {nom}
    ```

* **Vérification :**
    Affiche l'état des groupes HSRP :
    ```ini
    Router# show standby
    ```
    Affiche l'état résumé des groupes HSRP :
    ```ini
    Router# show standby brief
    ```

### 2.7 Tunnel GRE

* **Commandes de configuration :**
    ```ini
    Router(config)# interface tunnel {numéro}
    Router(config-if)# ip address {adresse_ip} {masque}
    Router(config-if)# tunnel source {adresse_ip_source | interface_source}
    Router(config-if)# tunnel destination {adresse_ip_destination}
    Router(config-if)# tunnel mode gre ip
    Router(config-if)# ip mtu 1400
    ```
* **Explications :**
    * `interface tunnel` : Crée une interface de tunnel GRE.
    * `tunnel source` : Définit l'adresse IP ou l'interface source du tunnel.
    * `tunnel destination` : Définit l'adresse IP de destination du tunnel.
    * `tunnel mode gre ip` : Indique que le type de tunnel est GRE.
    * `ip mtu 1400` : Ajuste la MTU (Maximum Transmission Unit) du tunnel pour éviter la fragmentation.

* **Vérification :**
    ```ini
    Router# show interfaces tunnel {numéro}
    ```

---

## 3. VLAN et Commutation L2

### 3.1 Création de VLANs

* **Commandes :**
    ```ini
    S1(config)# vlan <numéro_vlan>
    S1(config-vlan)# name <nom_vlan>
    ```

### 3.2 Définir interface ip du VLAN (SVI)

* **Commandes :**
    ```ini
    S1(config)# interface vlan <numéro_vlan>
    S1(config-if)# ip address 192.168.10.254 255.255.255.0
    S1(config-if)# no shutdown
    S1(config)# ip default-gateway 192.168.10.1
    ```
* **Explication :** L'interface VLAN (SVI) permet l'administration (L2) ou le routage (L3). `ip default-gateway` est pour l'accès management si le switch est L2.

### 3.3 Configuration des ports VLAN access

* **Commandes :**
    ```ini
    S1(config)# interface <type/num>
    S1(config-if)# switchport mode access
    S1(config-if)# switchport access vlan <numéro_vlan>
    ```

### 3.4 Configuration des ports VLAN TRUNK

* **Commandes :**
    Configure un port en mode trunk (pour les liaisons inter-switch ou routeur)
    ```ini
    S1(config)# interface <type/num>
    S1(config-if)# switchport mode trunk
    S1(config-if)# switchport trunk allowed vlan <liste_vlans>
    ```

#### 3.4.1 Protocole 802.1Q (Encapsulation)

* **Commande :**
    ```ini
    S1(config-if)# switchport trunk encapsulation dot1q
    ```
* **Explication :** Sur les switches modernes, c'est souvent le seul protocole supporté et activé par défaut.

#### 3.4.2 VLAN natif

* **Commande :**
    ```ini
    S1(config-if)# switchport trunk native vlan <numéro_vlan>
    ```
* **Explication :** Les trames non étiquetées sur un trunk seront associées à ce VLAN. Doit être identique des deux côtés.

#### 3.4.3 VLAN VOIX

* **Commande :**
    ```ini
    S1(config-if)# switchport voice vlan <vlan-id>
    ```
* **Explication :** Permet à un port "access" de transporter un VLAN de données (pour le PC) et un VLAN voix (pour le téléphone IP).

### 3.5 Routage Inter-VLAN

* **Configuration "Router on a Stick" :**
    Crée une sous-interface pour VLAN 10
    ```ini
    R1(config)# interface G0/1.10
    R1(config-subif)# description Default Gateway for VLAN 10
    R1(config-subif)# encapsulation dot1Q 10
    R1(config-subif)# ip address 192.168.10.1 255.255.255.0
    ```
    Crée une sous-interface pour VLAN 20
    ```ini
    R1(config)# interface G0/1.20
    R1(config-subif)# description Default Gateway for VLAN 20
    R1(config-subif)# encapsulation dot1Q 20
    R1(config-subif)# ip address 192.168.20.1 255.255.255.0
    ```

### 3.6 Vérification VLAN

* **Résumé des VLANs et de leurs ports associés**
    ```ini
    S1# show vlan brief
    ```
* **Informations détaillées sur les VLANs**
    ```ini
    S1# show vlan
    ```

### 3.7 DTP (Dynamic Trunking Protocol)

* **Configuration :**
    ```ini
    S1(config-if)# switchport mode dynamic {auto | desirable}
    ```
* **Désactivation (Bonne pratique) :**
    ```ini
    S1(config-if)# switchport nonegotiate
    ```
* **Explications :**
    * `dynamic desirable` : Tente activement de former un trunk.
    * `dynamic auto` : Devient un trunk si le voisin est en mode `trunk` ou `desirable`.
    * `nonegotiate` : Désactive DTP (doit être utilisé avec `switchport mode trunk` ou `access`).

### 3.8 VTP (VLAN Trunking Protocol)

#### 3.8.1 Configuration VTP

* **Commandes :**
    ```ini
    S1(config)# vtp mode {server | client | transparent}
    S1(config)# vtp domain <nom-domaine>
    S1(config)# vtp password <mot-de-passe>
    ```
* **Explications :**
    * `server` : Peut créer/modifier/supprimer des VLANs et les propage.
    * `client` : Reçoit les mises à jour VTP mais ne peut pas modifier les VLANs localement.
    * `transparent` : Ne participe pas à VTP (mais relaie les annonces VTP).

#### 3.8.2 Vérification VTP

* **Commande :**
    ```ini
    S1# show vtp status
    ```

---

## 4. Spanning Tree Protocol (STP)

### 4.1 Configuration du mode STP

* **Commande :**
    ```ini
    Switch(config)# spanning-tree mode {pvst|rapid-pvst|mst}
    ```
    * `pvst` : Per VLAN Spanning Tree.
    * `rapid-pvst` : Rapid PVST (802.1w).
    * `mst` : Multiple Spanning Tree (802.1s).

### 4.2 Priorité et racine

* **Commandes :**
    ```ini
    Switch(config)# spanning-tree vlan <vlan-id> priority <0-61440>
    Switch(config)# spanning-tree vlan <vlan-id> root {primary|secondary}
    ```
    * La priorité doit être un multiple de 4096 (par défaut : 32768).

### 4.3 Timers STP

* **Commandes :**
    ```ini
    Switch(config)# spanning-tree vlan <vlan-id> hello-time <1-10>
    Switch(config)# spanning-tree vlan <vlan-id> forward-time <4-30>
    Switch(config)# spanning-tree vlan <vlan-id> max-age <6-40>
    ```
    * hello-time : Intervalle d’envoi des BPDU (défaut 2s).
    * forward-time : Délai état listening/learning (défaut 15s).
    * max-age : Délai pour juger un BPDU obsolète (défaut 20s).

### 4.4 PortFast / BPDU Guard

* **Commandes :**
    ```ini
    Switch(config-if)# spanning-tree portfast
    Switch(config-if)# spanning-tree bpduguard enable
    ```
    * PortFast : active l’état forwarding immédiat (sur ports access).
    * BPDU Guard : désactive le port si BPDU reçu (sécurité).

### 4.5 MSTP (Multiple Spanning Tree)

* **Commandes :**
    ```ini
    Switch(config)# spanning-tree mst configuration
    Switch(config-mst)# name <nom_region>
    Switch(config-mst)# revision <numero>
    Switch(config-mst)# instance <num> vlan <liste_vlans>
    Switch(config-mst)# show pending
    Switch(config-mst)# exit
    Switch(config)# spanning-tree mst <instance> priority <0-61440>
    ```
    * Permet d’associer des VLANs à différentes instances MST.

### 4.6 Vérification STP

* **Commandes :**
    ```ini
    Switch# show spanning-tree
    Switch# show spanning-tree vlan <vlan-id>
    Switch# show spanning-tree mst
    Switch# show spanning-tree summary
    Switch# show spanning-tree detail
    Switch# show spanning-tree root
    Switch# show spanning-tree mst configuration
    ```
    * Vérifie toute la topologie STP, état des ponts racines, config MST répliquée sur tous les switches.

---

## 5. EtherChannel

### 5.1 LACP EtherChannel

* **Commandes :**
    ```ini
    Switch(config)# interface range <interface_list>
    Switch(config-if-range)# channel-group <num> mode active
    ```
    ou
    ```ini
    Switch(config-if-range)# channel-group <num> mode passive
    ```
    * `active` : le switch initie activement la négociation LACP.
    * `passive` : le switch attend que l’autre device lance la négociation.

### 5.2 PAgP EtherChannel

* **Commandes :**
    ```ini
    Switch(config)# interface range <interface_list>
    Switch(config-if-range)# channel-group <num> mode desirable
    ```
    ou
    ```ini
    Switch(config-if-range)# channel-group <num> mode auto
    ```
    * `desirable` : le switch initie activement la négociation PAgP.
    * `auto` : le switch attend que l’autre device lance la négociation.

### 5.3 Statique EtherChannel

* **Commande :**
    ```ini
    Switch(config)# interface range <interface_list>
    Switch(config-if-range)# channel-group <num> mode on
    ```
    * Pas de protocole de négociation, force le port à être membre.

### 5.4 Interface Port-Channel

* **Commandes :**
    ```ini
    Switch(config)# interface port-channel <num>
    Switch(config-if)# switchport mode {access|trunk}
    Switch(config-if)# switchport trunk allowed vlan <liste_vlans>
    ```
    * Configuration logique pour le bundle des interfaces physiques.

### 5.5 Vérification EtherChannel

* **Commandes :**
    ```ini
    Switch# show etherchannel summary
    Switch# show etherchannel <num> detail
    Switch# show lacp neighbor
    Switch# show pagp neighbor
    ```
    * Affiche résumé des groupes, interfaces membres et état de la négociation.

---

## 6. NAT/PAT

### 6.1 NAT statique

* **Commande :**
    ```ini
    Router(config)# ip nat inside source static <ip_privée> <ip_publique>
    ```

### 6.2 NAT dynamique

* **Commandes :**
    ```ini
    Router(config)# ip nat pool <nom_pool> <ip_debut> <ip_fin> netmask <masque>
    Router(config)# access-list <num> permit <réseau> <wildcard>
    Router(config)# ip nat inside source list <num_acl> pool <nom_pool>
    ```

### 6.3 PAT (NAT overload)

* **Commande :**
    ```ini
    Router(config)# ip nat inside source list <num_acl> interface <interface_ext> overload
    ```
* Traduction d'adresses avec surcharge de ports (multiplexage IP+ports).

### 6.4 Port forwarding (PAT statique)

* **Commande :**
    ```ini
    Router(config)# ip nat inside source static {tcp|udp} <ip_locale> <port_local> <ip_publique> <port_public>
    ```

### 6.5 Définition inside/outside

* **Commandes :**
    ```ini
    Router(config)# interface <interface_interne>
    Router(config-if)# ip nat inside
    Router(config)# interface <interface_externe>
    Router(config-if)# ip nat outside
    ```

### 6.6 Vérification NAT/PAT

* **Commandes :**
    ```ini
    Router# show ip nat translations
    Router# show ip nat statistics
    Router# clear ip nat translation *
    Router# debug ip nat
    ```

---

## 7. Access Control Lists (ACL)

### 7.1 ACL standard

* **Commande :**
    ```ini
    Router(config)# access-list <num (1-99|1300-1999)> {permit|deny} <source> <wildcard>
    ```
    * Contrôle basique sur l'adresse source.
    * Utilisé pour filtrer le trafic simple.

### 7.2 ACL étendue

* **Commande :**
    ```ini
    Router(config)# access-list <num (100-199|2000-2699)> {permit|deny} <protocole> <source> <wildcard_source> <destination> <wildcard_destination> [eq <port>]
    ```
    * Filtrage basé sur protocole, source, destination, ports.
    * Permet un contrôle plus fin du trafic.

### 7.3 ACL nommée

* **Commandes :**
    ```ini
    Router(config)# ip access-list extended <nom_acl>
    Router(config-ext-nacl)# {permit|deny} <protocole> <source> <wildcard_source> <destination> <wildcard_destination> [eq <port>]
    Router(config-ext-nacl)# exit
    ```
    * ACL avec un nom pour facilité gestion et modification.
    * Les règles peuvent être réordonnées et modifiées facilement.

### 7.4 Application interface

* **Commande :**
    ```ini
    Router(config)# interface <interface>
    Router(config-if)# ip access-group <num_ou_nom_acl> {in|out}
    ```
    * Applique l'ACL au trafic entrant (`in`) ou sortant (`out`) sur l'interface.

### 7.5 Application VTY

* **Commande :**
    ```ini
    Router(config)# line vty 0 15
    Router(config-line)# access-class <num_ou_nom_acl> in
    ```
    * Restreint l'accès aux lignes VTY pour SSH/Telnet selon l'ACL.

### 7.6 Suppression/Séquence

* **Commande :**
    ```ini
    Router(config)# ip access-list extended <nom_acl>
    Router(config-ext-nacl)# no <num_sequence>
    ```
    * Supprime une entrée spécifique dans une ACL nommée.

### 7.7 Vérification ACL

* **Commandes :**
    ```ini
    Router# show access-lists
    Router# show ip access-lists
    Router# show ip access-lists <nom_ou_num_acl>
    Router# show ip interface <interface>
    ```
    * Affiche les ACL configurées et leur application sur les interfaces.

---

## 8. IPv6 (Routage et Autoconfiguration)

### 8.1 Activation IPv6

* **Commande :**
    ```ini
    Router(config)# ipv6 unicast-routing
    ```
    Active le routage IPv6 global sur le routeur.

### 8.2 Adresse interface IPv6

* **Commandes :**
    ```ini
    Router(config-if)# ipv6 address <adresse_ipv6>/<prefixe>
    Router(config-if)# ipv6 enable
    ```
    * `ipv6 address` configure une adresse IPv6 globale.
    * `ipv6 enable` active IPv6 sur l'interface (attribue adresse lien-local automatiquement).

### 8.3 Routage statique IPv6

* **Commande :**
    ```ini
    Router(config)# ipv6 route <destination>/<prefix> <interface|next-hop>
    ```
    * Route statique vers un réseau IPv6.
    * Exemple de route par défaut (any) : `ipv6 route ::/0 <next-hop>`

### 8.4 OSPFv3

* **Commandes :**
    ```ini
    Router(config)# ipv6 router ospf <process-id>
    Router(config-router)# router-id <id_routeur>
    Router(config-if)# ipv6 ospf <process-id> area <area-id>
    ```
    * Configuration du protocole OSPFv3 pour le routage IPv6.
    * Supporte router-id comme OSPFv2.

### 8.5 EIGRPv6

* **Commandes :**
    ```ini
    Router(config)# ipv6 router eigrp <as_number>
    Router(config-router)# eigrp router-id <id_routeur>
    Router(config-router)# no shutdown
    Router(config-if)# ipv6 eigrp <as_number>
    ```
    * Active EIGRP pour IPv6 avec un AS donné.
    * Active le protocole sur l’interface.

### 8.6 BGP IPv6

* **Commandes :**
    ```ini
    Router(config)# router bgp <as_number>
    Router(config-router)# neighbor <ipv6_address> remote-as <as_neighbor>
    Router(config-router)# address-family ipv6 unicast
    Router(config-router-af)# neighbor <ipv6_address> activate
    Router(config-router-af)# network <ipv6_network>/<prefix>
    Router(config-router-af)# exit-address-family
    ```
    * Configuration BGP pour IPv6 (MP-BGP).

### 8.7 SLAAC

* **Commande :**
    ```ini
    Router(config-if)# ipv6 address autoconfig
    ```
    * Permet à un client d’auto-configurer son adresse IPv6 à partir des annonces routeur (RA).

### 8.8 DHCPv6 (Stateless et Stateful)

* **Commandes :**
    ```ini
    Router(config)# ipv6 dhcp pool <nom_pool>
    Router(dhcp-config)# address prefix <ipv6_prefix>/<prefix_len>
    Router(dhcp-config)# dns-server <ipv6_dns>
    Router(dhcp-config)# domain-name <nom_domaine>
    Router(config-if)# ipv6 dhcp server <nom_pool>
    Router(config-if)# ipv6 nd other-config-flag       # pour DHCPv6 stateless
    Router(config-if)# ipv6 nd managed-config-flag     # pour DHCPv6 stateful
    ```

### 8.9 DHCPv6 Relay

* **Commande :**
    ```ini
    Router(config-if)# ipv6 dhcp relay destination <adresse_ipv6_serveur>
    ```

### 8.10 Vérification IPv6

* **Commandes :**
    ```ini
    Router# show ipv6 interface
    Router# show ipv6 neighbors
    Router# show ipv6 dhcp binding
    Router# show ipv6 route
    Router# show ipv6 protocols
    ```

---

## 9. Services Réseau

### 9.1 Protocole NTP

#### 9.1.1 Serveur NTP

* **Commande :**
    ```ini
    Router(config)# ntp server adresse_ip_serveur
    ```

#### 9.1.2 Pair NTP

* **Commande :**
    ```ini
    Router(config)# ntp peer adresse_ip_pair
    ```

#### 9.1.3 Serveur principal NTP

* **Commande :**
    ```ini
    Router(config)# ntp master
    ```

### 9.2 Vérification NTP

#### 9.2.1 Synchronisation NTP

* **Commande :**
    ```ini
    Router# show ntp status
    ```

#### 9.2.2 Associations serveurs

* **Commande :**
    ```ini
    Router# show ntp associations
    ```

#### 9.2.3 Détails associations

* **Commande :**
    ```ini
    Router# show ntp associations detail
    ```

#### 9.2.4 Détails horloge

* **Commande :**
    ```ini
    Router# show clock detail
    ```

### 9.3 SNMP

#### 9.3.1 Communauté SNMP

* **Commande :**
    ```ini
    Router(config)# snmp-server community nom {RO|RW}
    ```
* **Explication :**
    * `RO` (Read-Only) : Lecture seule.
    * `RW` (Read-Write) : Lecture et écriture.

#### 9.3.2 Hôtes SNMP

* **Commande :**
    ```ini
    Router(config)# snmp-server host adresse_ip_NMS community nom [traps|informs]
    ```

#### 9.3.3 Utilisateurs SNMPv3

* **Commande :**
    ```ini
    Router(config)# snmp-server user nom group-name auth {md5|sha} mot_de_passe priv {des|aes} mot_de_passe
    ```

#### 9.3.4 Vérification SNMP

* **Commandes :**
    ```ini
    Router# show snmp community
    Router# show snmp host
    Router# show snmp traps
    ```

### 9.4 DHCP (IPv4)

#### 9.4.1 Pool DHCP

* **Commandes :**
    ```ini
    Router(config)# ip dhcp pool Mon_POOL_DHCP
    Router(dhcp-config)# network 192.168.10.0 255.255.255.0
    Router(dhcp-config)# default-router 192.168.10.1
    Router(dhcp-config)# domain-name MONDOMAINE.FR
    ```

#### 9.4.2 Serveur DNS

* **Commande :**
    ```ini
    Router(dhcp-config)# dns-server 8.8.8.8
    ```

#### 9.4.3 Exclusions IP

* **Commande :**
    ```ini
    Router(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.10
    ```

### 9.5 DHCP Relay (IPv4)

* **Commande :**
    ```ini
    Router(config)# interface <interface_SVI_ou_routeur>
    Router(config-if)# ip helper-address <adresse_ip_serveur_dhcp>
    ```
* **Explication :** Se configure sur l'interface qui reçoit les broadcasts DHCP des clients.

### 9.6 CDP / LLDP

#### 9.6.1 Configuration

* **Activation/Désactivation globale :**
    ```ini
    Router(config)# cdp run
    Router(config)# no cdp run
    Router(config)# lldp run
    Router(config)# no lldp run
    ```
* **Activation/Désactivation par interface :**
    ```ini
    Router(config-if)# cdp enable
    Router(config-if)# no cdp enable
    ```

#### 9.6.2 Vérification

* **Commandes :**
    ```ini
    Router# show cdp neighbors
    Router# show cdp neighbors detail
    Router# show lldp neighbors
    ```

### 9.7 SYSLOG

* **Définir l'adresse du serveur Syslog :**
    ```ini
    Router(config)# logging host adresse_ip_serveur
    ```
* **Définir le niveau de gravité des messages Syslog à envoyer (souvent debugging) :**
    ```ini
    Router(config)# logging trap debugging
    ```

### 9.8 Fuseau Horaire

* **Définir le fuseau horaire :**
    ```ini
    Router(config)# clock timezone nom_fuseau_horaire décalage_utc
    ```
* **Afficher les détails de l'horloge :**
    ```ini
    Router# show clock detail
    ```

### 9.9 Désactivation Recherche DNS

* **Désactiver la recherche DNS :**
    ```ini
    Router(config)# no ip domain-lookup
    ```

---

## 10. Maintenance du Réseau

### 10.1 Effacer la configuration du switch

* **Effacer la configuration du switch :**
    ```ini
    S1# erase startup-config
    S1# delete vlan.dat
    S1# reload
    ```
