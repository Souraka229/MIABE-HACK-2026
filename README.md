# DiasporaConnect

## Description

DiasporaConnect est une plateforme innovante de transfert de fonds internationaux, construite sur la blockchain Polygon, permettant a la diaspora africaine d'envoyer de l'argent vers le Benin avec des frais reduits a 0.8% et une reception en Mobile Money (MTN MoMo, Moov Money) en moins de 30 minutes.

## Probleme resolu

Les transferts d'argent vers l'Afrique sont domines par des services comme Western Union ou MoneyGram qui facturent entre 7% et 15% de frais, avec des delais de 1 a 5 jours. Pour un envoi de 200 USD, ces frais representent entre 14 et 30 USD de perte. DiasporaConnect reduit ces frais a seulement 0.8% (soit 1,60 USD pour 200 USD), faisant economiser jusqu'a 20 650 XOF par transfert aux familles beneficiaires.

## Solution

DiasporaConnect propose deux portails complementaires :

### Portail Diaspora (Expediteur)
- Formulaire d'envoi avec calcul automatique des frais et conversion en temps reel
- Authentification passwordless par OTP (SMS)
- Transfert securise via smart contract sur Polygon
- Confirmation instantanee avec ID de transaction et suivi

### Portail Benin (Destinataire)
- Recherche de transfert par numero de telephone ou ID de transaction
- Retrait en Mobile Money (MTN MoMo / Moov Money)
- Paiement de factures (SBEE, SONEB, MTN, Canal+)
- Paiement marchand par QR Code

### Points forts
- **Frais quasi nuls** : 0.8% contre 7-15% chez les concurrents
- **Rapidite** : Moins de 30 minutes de bout en bout
- **Securite** : Chiffrement AES-256 + blockchain Polygon
- **Simplicite** : Pas de compte bancaire requis, reception via Mobile Money

## Tech Stack

### Frontend
- HTML5 / CSS3 / JavaScript Vanilla
- Lucide Icons
- Design responsive (mobile-first)
- API integration avec fallback mock pour demo hors-ligne

### Backend
- Node.js + Express.js
- Prisma ORM (SQLite en dev, PostgreSQL en production)
- JSON Web Tokens (JWT) pour l'authentification
- Twilio pour les SMS OTP

### Blockchain
- Solidity (Smart Contracts)
- Polygon Amoy Testnet
- Hardhat (dev, test, deploy)
- ethers.js pour les interactions blockchain
- MockUSDC (stablecoin de test)
- DiasporaTransfer.sol (verrouillage et liberation des fonds)

## Comment lancer en local

### Prerequis
- Node.js v22+
- npm ou yarn

### 1. Cloner le depot

```bash
git clone -b stj_branch https://github.com/Souraka229/disporaconnect-mbh2026.git
cd disporaconnect-mbh2026
```

### 2. Lancer le backend

```bash
cd backend
npm install
npx prisma db push
npx prisma generate
npm start
```

Le serveur sera accessible sur http://localhost:3000

### 3. Lancer le frontend

Ouvrez `index.html` dans votre navigateur ou utilisez un serveur statique :

```bash
# Depuis la racine du projet
npx serve .
```

### 4. Blockchain locale (optionnel)

```bash
cd contracts
npm install
npx hardhat node
npx hardhat run scripts/deploy.js --network localhost
```

## Variables d'environnement

Creez un fichier `.env` dans le dossier `backend/` :

```env
DATABASE_URL="file:./dev.db"
ENCRYPTION_KEY="votre_cle_hex_64_caracteres"
JWT_SECRET="votre_secret_jwt"
RELAYER_PRIVATE_KEY="cle_privee_wallet_relayer"
AMOY_RPC_URL="https://rpc-amoy.polygon.technology"
USE_REAL_TWILIO="false"
TWILIO_ACCOUNT_SID=""
TWILIO_AUTH_TOKEN=""
TWILIO_PHONE_NUMBER=""
```

## Equipe

Projet developpe dans le cadre du **MIABE Hackathon 2026** - Benin.

## Lien prototype

- **Prototype interactif** : https://diaspora-connect-ayaxntwu.devinapps.com/
- **Code source** : https://github.com/Souraka229/disporaconnect-mbh2026.git

## MIABE Hackathon 2026

DiasporaConnect contribue aux Objectifs de Developpement Durable :
- **ODD 1** - Fin de la pauvrete : Reduire les frais de transfert pour maximiser l'impact de chaque envoi
- **ODD 8** - Travail decent : Faciliter les investissements de la diaspora pour creer des emplois locaux
- **ODD 10** - Inegalites reduites : L'ODD 10 fixe un plafond de 3% de frais d'ici 2030, DiasporaConnect propose 0.8%
# MIABE-HACK-2026
