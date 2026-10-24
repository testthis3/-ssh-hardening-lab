# SSH Hardening Lab

## Description

Laboratoire de sécurisation d'un serveur SSH sous Ubuntu, en 3 phases : analyse initiale, durcissement, vérification finale depuis Kali.

**Environnement :** Ubuntu Server · Kali Linux · OpenSSH · Nmap · Hydra · UFW

## Phase 1 — Analyse de la sécurité initiale

- **Étape 1 :** Installation et activation d'OpenSSH 
- **Étape 2 :** Scan du serveur depuis Kali avec Nmap 
- **Étape 3 :** Démonstration du risque de mot de passe faible avec Hydra 

## Phase 2 — Durcissement du serveur Ubuntu

Configuration appliquée dans `/etc/ssh/sshd_config` :

```
Port 2222
PermitRootLogin no
PasswordAuthentication no
MaxAuthTries 3
LoginGraceTime 30
X11Forwarding no
AllowTcpForwarding no
```

## Phase 3 — Vérification finale depuis Kali

- **Étape 7 :** `nmap -sV -p 22,2222 192.168.122.49` → port 22 and port 2222 are inaccessible.
- **Étape 8 :** Connexion par mot de passe refusée (`PasswordAuthentication no`).
- **Étape 9 :** Connexion directe de `root` refusée (`PermitRootLogin no`).
