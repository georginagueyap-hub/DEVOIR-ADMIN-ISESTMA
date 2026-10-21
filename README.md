# DEVOIR-ADMIN-ISESTMA

**Projet d'administration du réseau de campus de l'ISESTMA**
Authentification des services d'annuaire et administration des SE réseaux

![Statut](https://img.shields.io/badge/phase-2%20conception-blue)
![Filière](https://img.shields.io/badge/BTS%20N2-R%C3%A9seaux%20et%20S%C3%A9curit%C3%A9-1F3A8A)
![Année](https://img.shields.io/badge/ann%C3%A9e-2026--2027-C99A2E)

---

## Présentation

Ce dépôt regroupe les livrables du projet d'administration du réseau de campus de l'**ISESTMA** (Institut Supérieur d'Études Scientifiques, Technologiques et Managériales), réalisé dans le cadre du module *Authentification des Services d'Annuaire et Administration des SE Réseaux* (BTS Niveau 2 Réseaux et Sécurité, année académique 2026-2027).

Le campus comprend deux bâtiments reliés par une liaison radio (NanoStation A et B), avec un accès Internet fourni par CAMTEL. Le projet vise à centraliser les identités dans un annuaire, sécuriser l'accès filaire et Wi-Fi, segmenter le réseau et mettre en place une journalisation centralisée.

## Équipe

| Rôle | Nom |
|---|---|
| Équipe / chef d'équipe | Gueyap Pokam Georgina |
| Encadreur | Daniel MOUNE |

## Avancement du projet

| Phase | Contenu | Statut |
|---|---|---|
| Phase 1 | Étude de l'existant | Terminée |
| Phase 2 | Conception de l'architecture cible (annuaire, authentification, sécurité) | En cours — dossier remis pour validation |
| Phase 3 | Déploiement de l'annuaire LDAP | À venir |
| Phase 4 | Pare-feu et listes de contrôle d'accès | À venir |
| Phase 5 | Intégration AD / Linux et démonstration finale | À venir |

## Contenu du dépôt

| Fichier | Description |
|---|---|
| `Dossier_Conception_Phase2_ISESTMA.pdf` | Dossier de conception de la phase 2 : architecture cible, annuaire LDAP, authentification 802.1X, VLAN, politique de sécurité, plan de tests |
| `CARTOGRAPHIE Cisco.pkt` | Cartographie du réseau (fichier Cisco Packet Tracer) |
| `document 2.docx`, `Document 3.docx`, `Document 4.docx`, `Document 5.docx` | Documents de travail du projet |

> Pour ouvrir le fichier `.pkt`, utiliser Cisco Packet Tracer.

## Architecture cible (résumé)

- **Annuaire** : OpenLDAP principal (bâtiment A) avec réplica (bâtiment B), échanges chiffrés par TLS.
- **Authentification** : RADIUS avec 802.1X pour le Wi-Fi (EAP-TTLS/PAP), double facteur recommandé pour les comptes à privilèges.
- **Segmentation** : cinq VLAN (administration, serveurs, personnel et enseignants, étudiants, invités) avec une politique « tout refuser par défaut ».
- **Traçabilité** : journaux centralisés (syslog) et heure commune (NTP).
- **Continuité** : annuaire dans chaque bâtiment, sauvegardes quotidiennes, lien de secours étudié pour la liaison radio.

Le détail complet figure dans le dossier de conception (PDF).

## Feuille de route

| Séance | Jalon |
|---|---|
| 1 | Vision produit |
| 4 | Architecture d'annuaire (dossier de conception) |
| 8 | LDAP opérationnel |
| 12 | Pare-feu et ACL en place |
| 16 | Intégration AD / Linux |
| 20 | Démonstration finale |

## Bonnes pratiques pour ce dépôt

Le dépôt est **public** : ne jamais y déposer de mots de passe, de clés privées, de certificats ni d'adresses sensibles. Utiliser des valeurs d'exemple dans les fichiers de configuration.

## Références

- RFC 4510 — LDAP : Technical Specification Road Map
- RFC 2865 — RADIUS
- IEEE 802.1X — Port-Based Network Access Control
- ANSSI, NIST SP 800-53, CIS Benchmarks

---

*ISESTMA — BTS Niveau 2 Réseaux et Sécurité — 2026-2027*
