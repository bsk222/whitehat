Disponible aux 50 étoiles!

<div align="center">

```
 █     █░ ██░ ██ ██▓▄▄▄█████▓▓█████      ██░ ██  ▄▄▄      ▄▄▄█████▓
▓█░ █ ░█░▓██░ ██▒▓██▒▓  ██▒ ▓▒▓█   ▀    ▓██░ ██▒▒████▄    ▓  ██▒ ▓▒
▒█░ █ ░█ ▒██▀▀██░▒██▒▒ ▓██░ ▒░▒███      ▒██▀▀██░▒██  ▀█▄  ▒ ▓██░ ▒░
░█░ █ ░█ ░▓█ ░██ ░██░░ ▓██▓ ░ ▒▓█  ▄   ░▓█ ░██ ░██▄▄▄▄██ ░ ▓██▓ 
░░██▒██▓ ░▓█▒░██▓░██░  ▒██▒ ░ ░▒████▒  ░▓█▒░██▓ ▓█   ▓██▒  ▒██▒ ░
░ ▓░▒ ▒   ▒ ░░▒░▒░▓    ▒ ░░   ░░ ▒░ ░   ▒ ░░▒░▒ ▒▒   ▓▒█░  ▒ ░░
  ▒ ░ ░   ▒ ░▒░ ░ ▒ ░    ░     ░ ░  ░   ▒ ░▒░ ░  ▒   ▒▒ ░    ░
  ░   ░   ░  ░░ ░ ▒ ░  ░         ░      ░  ░░ ░  ░   ▒      ░
    ░     ░  ░  ░ ░               ░  ░   ░  ░  ░      ░  ░
```

**Pentest & OSINT Multitool — Python 3 — Windows / Linux / macOS**

[![Python](https://img.shields.io/badge/Python-3.8%2B-white?style=flat-square&logo=python&logoColor=white&labelColor=222)](https://python.org)
[![Tools](https://img.shields.io/badge/Tools-27-white?style=flat-square&labelColor=222)](.)
[![Platform](https://img.shields.io/badge/Platform-Win%20%7C%20Linux%20%7C%20Mac-white?style=flat-square&labelColor=222)](.)
[![License](https://img.shields.io/badge/License-MIT-white?style=flat-square&labelColor=222)](LICENSE)
[![Discord](https://img.shields.io/badge/Discord-Join-white?style=flat-square&logo=discord&logoColor=white&labelColor=5865F2)](https://discord.com/invite/S5A8SNMZqe)

</div>

---

## Installation

```bash
git clone https://github.com/bsk222/whitehat
cd whitehat
pip install -r requirements.txt
```

**Lancer :**

```bash
# Linux / macOS
chmod +x start.sh && ./start.sh        # recommandé (auto-sudo)
python3 whitehat.py                    # direct

# Windows
start.bat                              # recommandé (auto-admin)
python whitehat.py                     # direct
```

**Dépendances système** (optionnelles — les outils fonctionnent sans) :

```bash
# Debian / Kali / Ubuntu
sudo apt install whois dnsutils

# Arch
sudo pacman -S whois bind-tools

# macOS
brew install whois bind
```

> Pas besoin de nmap. Tous les scans réseau utilisent des sockets Python natifs.

---

## Structure

```
whitehat/
├── whitehat.py             ← Point d'entrée
├── start.sh                ← Launcher Linux/macOS (auto-sudo)
├── start.bat               ← Launcher Windows (auto-admin)
├── requirements.txt
│
├── core/                   ← Moteur
│   ├── colors.py           ← Palette, gradients, fonctions log
│   ├── banner.py           ← ASCII art, animation, headers
│   └── utils.py            ← HTTP, DNS, sauvegarde logs
│
├── programs/               ← Tous les outils
│   ├── network/
│   │   ├── port_scanner.py
│   │   ├── vuln_scanner.py
│   │   ├── subdomain_finder.py
│   │   ├── dns_lookup.py
│   │   ├── waf_ssl.py
│   │   ├── dir_bruteforce.py
│   │   ├── tech_fingerprint.py
│   │   └── banner_grabber.py
│   ├── osint/
│   │   ├── ip_lookup.py
│   │   ├── whois_lookup.py
│   │   ├── username_osint.py
│   │   ├── email_osint.py
│   │   ├── phone_lookup.py
│   │   ├── github_osint.py
│   │   ├── google_dorks.py
│   │   ├── shodan_dorks.py
│   │   ├── image_exif.py
│   │   └── reverse_ip.py (→ reverse_ip.py inclus dans osint)
│   └── pentest/
│       ├── hash_tools.py
│       ├── password_gen.py
│       ├── zip_cracker.py
│       ├── payload_gen.py
│       ├── jwt_analyzer.py
│       ├── cve_search.py
│       ├── s3_finder.py
│       └── breach_check.py
│
└── data/
    ├── wordlists/
    │   └── common.txt
    └── logs/               ← Résultats sauvegardés ici
```

---

## Outils

### Network (01–08)

| # | Outil | Description |
|---|-------|-------------|
| 01 | **Port Scanner** | TCP multi-threadé, top 50 ports ou plage/full scan, service detection |
| 02 | **Web Vuln Scanner** | Headers, cookies, CSP, CORS, XSS, SQLi, Open Redirect, SSL, fichiers sensibles |
| 03 | **Subdomain Finder** | Brute-force DNS multi-threadé, wordlist intégrée (80+) ou custom |
| 04 | **DNS Lookup** | A, AAAA, MX, NS, TXT, CNAME, SOA via dnspython ou dig |
| 05 | **WAF & SSL Detector** | 13 WAF reconnus, analyse TLS (protocole, cipher, expiration, SANs) |
| 06 | **Dir Bruteforcer** | Chemins cachés, extensions custom, 200/403/redirect colorés |
| 07 | **Tech Fingerprinter** | CMS, frameworks, serveurs, CDN (30+ signatures) |
| 08 | **Banner Grabber** | Récupère les bannières TCP, détecte versions SSH/MySQL/Redis/HTTP |

### OSINT (09–18)

| # | Outil | Description |
|---|-------|-------------|
| 09 | **IP Lookup / GeoIP** | Pays, ville, FAI, ASN, coordonnées, lien Google Maps |
| 10 | **Whois Lookup** | Registrar, dates, nameservers (système ou API hackertarget) |
| 11 | **Username OSINT** | Recherche sur 33 plateformes en parallèle |
| 12 | **Email OSINT** | Gravatar, MX records, dorks Google, liens leak databases |
| 13 | **Phone Lookup** | Indicatif pays, opérateur FR, liens Truecaller/annuaires |
| 14 | **GitHub OSINT** | Profil, repos, **emails extraits des commits**, scan secrets, gists, orgs |
| 15 | **Google Dorking** | 21 dorks auto + constructeur + référence 15 opérateurs |
| 16 | **Shodan Dorking** | 28 dorks prédéfinis + constructeur + référence filtres Censys |
| 17 | **Image EXIF** | Métadonnées complètes, coordonnées GPS → Google Maps |
| 18 | **Reverse IP** | Domaines hébergés sur une IP |

### Pentest (19–27)

| # | Outil | Description |
|---|-------|-------------|
| 19 | **Hash Cracker** | Wordlist attack multi-threadé, MD5/SHA1/SHA256/SHA512 |
| 20 | **Hash & Encoder** | 10 algos hash, Base64, Hex, URL, ROT13, César, Binaire |
| 21 | **Password Generator** | Aléatoire, passphrase, bulk + score entropie |
| 22 | **ZIP Cracker** | Brute-force archive ZIP multi-threadé |
| 23 | **Payload Generator** | XSS, XSS Exfil, XSS WAF Bypass, SQLi, UNION, LFI, CMDi, SSTI, XXE, SSRF, Open Redirect, RCE |
| 24 | **JWT Analyzer** | Décode, vérifie signature, bruteforce secret, attaque alg:none, forge JWT |
| 25 | **CVE / Exploit Search** | NVD par keyword/CVE-ID, score CVSS coloré, PoC GitHub, liens Exploit-DB |
| 26 | **S3 Bucket Finder** | 35 permutations, détecte public/privé/listé, extrait les fichiers exposés |
| 27 | **Breach Checker** | HIBP k-Anonymity (mot de passe), liens HIBP/DeHashed/IntelX |

---

## GitHub OSINT — ce que ça fait

L'outil le plus puissant du lot. En mode recon complet sur un utilisateur :

- Profil complet (nom, bio, localisation, entreprise, twitter, blog)
- Liste tous les repos publics avec langages et étoiles
- **Extrait les emails depuis les commits** (y compris ceux non affichés sur le profil)
- Scanne les gists, organisations, followers, activité récente
- **Scan de secrets dans les repos** : AWS keys, tokens GitHub, JWT, API keys, credentials, URLs de base de données, clés privées, Firebase, Stripe
- Mode recherche de code, utilisateurs, dépôts via l'API GitHub

---

## Interface

```
  [+]  Succès       (vert)
  [-]  Erreur       (rouge)
  [*]  Info         (jaune)
  [!]  Warning      (rose)

  ━━━━►  Flèche d'entrée dégradée blanc → gris
```

Résultats sauvegardés dans `data/logs/` après confirmation.

---

## Commandes menu

| Touche | Action |
|--------|--------|
| `01–27` | Lancer l'outil |
| `G` | guns.lol/newbsk |
| `D` | Discord |
| `I` | Infos système |
| `C` | Clear logs |
| `Q` | Quitter |

---

**Usage légal uniquement. Testez uniquement des systèmes que vous êtes autorisé à tester.**

*by BsK — [discord.com/invite/S5A8SNMZqe](https://discord.com/invite/S5A8SNMZqe)*
