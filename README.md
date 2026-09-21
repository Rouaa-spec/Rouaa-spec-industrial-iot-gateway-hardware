# Passerelle IoT Industrielle (Industrial IoT Gateway) — Conception Matérielle 

Ce dépôt rassemble les fichiers de conception électronique d'une **passerelle IoT industrielle (IIoT Gateway)** conçue sous **Altium Designer**. Cette carte est dimensionnée pour être intégrée au sein d’une armoire électrique sur rail DIN et sert d'alternative connectée aux automates programmables (PLC) traditionnels pour les applications de télémétrie.

---

## 📐 Rôle de la Carte et Concept de Passerelle IoT

Le rôle principal de cette carte est d'agir comme un **pont de communication intelligent** entre le monde physique et les serveurs distants. 

En milieu industriel, les machines et capteurs de terrain utilisent des liaisons locales non connectées à Internet. Cette carte collecte ces données locales, les centralise, les traite, puis les propulse vers le réseau ou le Cloud. 

C'est l'intégration native du **module Ethernet** et du **module GPRS** qui lui confère son statut de **Passerelle IoT** :
*   **Module Ethernet W5500 (Filaire) :** Il assure la fonction principale de transfert de données IoT. Il offre une connexion haut débit, stable et prioritaire pour envoyer les rapports vers les serveurs de l'entreprise ou les plateformes Cloud.
*   **Module GPRS (Cellulaire) :** Il garantit l'autonomie et la résilience de la fonction IoT. Il permet de déployer la passerelle sur des sites isolés dépourvus de réseau filaire, ou de servir de connexion de secours pour maintenir la remontée des données en cas de coupure de la ligne Ethernet principale.

---

## ⚡ Fonctionnalités et Rôle des Protocoles et Bus Embarqués

Chaque interface de la carte a été minutieusement sélectionnée pour répondre à un besoin d'interconnexion spécifique :

### 1. Protocoles et Liaisons de Terrain (Acquisition)
*   **Interface RS485 :** Liaison série différentielle à deux fils, hautement immunisée contre les parasites électromagnétiques des armoires électriques. Elle permet de communiquer avec les équipements du réseau local (centrales de mesure d'énergie, variateurs de vitesse) généralement via le protocole **Modbus RTU**.
*   **Interface RS232 :** Liaison série point à point dédiée à l'interfaçage avec des périphériques de proximité.
*   **Bus I2C (Extension) :** Bus de communication local permettant à la passerelle de dialoguer à courte distance avec d'autres cartes électroniques d'extensions esclaves (des cartes d'entrées/sorties déportées et des cartes relais) fixées dans la même armoire.

### 2. Stockage Local (Sécurité des données)
*   **Lecteur de Carte SD :** Indispensable à la fiabilité du système IoT, il assure le *data logging* (stockage local des données). En cas de perte temporaire de la connexion réseau (Ethernet et GPRS), les données y sont sauvegardées pour être transmises ultérieurement dès le rétablissement du signal (*stratégie Store and Forward*).

---

## 📸 Aperçu 3D 

<p align="center">
<img width="500" alt="3D View" src="https://github.com/user-attachments/assets/bdecdfc0-2aac-4b60-9f50-10bc90a95607" />
  <br />
  <sub><b>Vue 3D</b></sub>
</p>

