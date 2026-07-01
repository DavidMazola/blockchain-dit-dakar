# Blockchain & Finance — DIT Dakar

> Ressources pédagogiques du cours **Blockchain & Finance : enjeux et applications**  
> Master 2 Finance — Semestre 3 | Dakar Institute of Technology (DIT)  
> Intervenant : **David Mazola Makasi**

---

## À propos de ce repository

Ce repository contient l'ensemble du code développé, commenté et déployé dans le cadre du cours de Blockchain. Il a été conçu pour que chaque étudiant puisse :

- relire le code après la séance, à son rythme ;
- l'utiliser comme base de départ pour ses propres projets ;
- l'adapter, le modifier et l'explorer librement.

Tout le code est **pré-écrit, commenté ligne par ligne**, et ne nécessite aucune installation en dehors de MetaMask.

---

## Contenu du repository

```
blockchain-dit-dakar/
│
├── contracts/
│   └── SimpleTransfer.sol        # Smart contract Solidity (Chapitre 3)
│
├── dapp_v1.html                  # dApp — lecture seule (Chapitre 4 — Séance 6)
├── dapp_v2.html                  # dApp — complète avec envoi ETH (Chapitre 4 — Séance 7)
│
└── README.md                     # Ce fichier
```

### SimpleTransfer.sol
Le smart contract de référence du cours, écrit en Solidity. Il permet d'envoyer des ETH, de stocker l'historique des transferts, et d'émettre des events. Déployé sur le réseau **Ethereum Sepolia Testnet**.

### dapp_v1.html
La première version de la dApp (Séance 6). Elle permet de :
- connecter MetaMask à la page web ;
- lire les données du contrat (`owner`, `totalTransfers`, `totalAmountReceived`) ;
- afficher l'historique des transactions via les events `TransferSent`.

### dapp_v2.html
La version complète de la dApp (Séance 7). Elle ajoute, en plus de dapp_v1 :
- l'envoi d'ETH directement depuis la page web via la fonction `sendTransfer` ;
- des tests end-to-end complets.

---

## Prérequis

Aucune installation de logiciel n'est nécessaire pour les fichiers HTML, sauf :

| Outil | Rôle | Lien |
|-------|------|------|
| **MetaMask** | Extension navigateur — signe les transactions | [metamask.io](https://metamask.io) |
| Réseau **Sepolia Testnet** | Réseau Ethereum de test (gratuit) | Configurable dans MetaMask |
| **SepoliaETH** | Fonds de test (gratuits) | [sepoliafaucet.com](https://sepoliafaucet.com) |

> ethers.js est chargé automatiquement via CDN dans les fichiers HTML — aucune installation npm requise.

---

## Comment utiliser les fichiers HTML

### Méthode simple (recommandée pour les étudiants)

1. Cliquer sur le fichier voulu (`dapp_v1.html` ou `dapp_v2.html`)
2. Cliquer sur le bouton **Raw** (en haut à droite du fichier)
3. Faire `Ctrl+A` → `Ctrl+C` pour tout sélectionner et copier
4. Créer un nouveau fichier texte sur votre ordinateur
5. Coller le contenu → enregistrer avec l'extension `.html` (ex. `dapp_v1.html`)
6. Double-cliquer sur le fichier → il s'ouvre directement dans votre navigateur

### Via GitHub Pages (live demo)

Les fichiers sont également accessibles en ligne, sans aucun téléchargement :

- **dapp_v1.html** → [davidmazola.github.io/blockchain-dit-dakar/dapp_v1.html](https://davidmazola.github.io/blockchain-dit-dakar/dapp_v1.html)
- **dapp_v2.html** → [davidmazola.github.io/blockchain-dit-dakar/dapp_v2.html](https://davidmazola.github.io/blockchain-dit-dakar/dapp_v2.html)

> Veillez à avoir MetaMask installé et configuré sur Sepolia avant d'ouvrir ces liens.

---

## Comment utiliser SimpleTransfer.sol

1. Ouvrir [remix.ethereum.org](https://remix.ethereum.org) dans votre navigateur
2. Créer un nouveau fichier → coller le contenu de `SimpleTransfer.sol`
3. Compiler avec le compilateur Solidity (version 0.8.x)
4. Dans l'onglet Deploy : sélectionner **Injected Provider — MetaMask**, réseau **Sepolia**
5. Cliquer **Deploy** → confirmer dans MetaMask
6. Récupérer l'adresse du contrat déployé dans la section **Deployed Contracts**

> L'adresse du contrat de référence du cours (déployé par l'intervenant) :  
> `0xdd60611951b607bd4c68e306992022d5e8f75bcf`  
> Consultable sur [sepolia.etherscan.io](https://sepolia.etherscan.io/address/0xdd60611951b607bd4c68e306992022d5e8f75bcf)

---

## Pour aller plus loin

Si vous souhaitez modifier le projet ou l'utiliser comme base :

```bash
# Cloner le repository sur votre machine
git clone https://github.com/davidmazola/blockchain-dit-dakar.git

# Ouvrir le dossier
cd blockchain-dit-dakar
```

Vous pouvez ensuite modifier les fichiers avec n'importe quel éditeur de texte (VS Code recommandé) et ouvrir le HTML directement dans votre navigateur.

---

## Structure du cours

| Chapitre | Titre | Statut |
|----------|-------|--------|
| Ch. 1 | Introduction à la blockchain | ✅ Fait |
| Ch. 2 | Fonctionnement de la blockchain | ✅ Fait |
| Ch. 3 | Développement de smart contracts (Solidity) | ✅ Fait |
| Ch. 4 | Développement de dApps (ethers.js, MetaMask) | 🔄 En cours |
| Ch. 5 | Cas d'utilisation (finance, logistique, santé) | 🔜 À venir |
| Ch. 6 | Enjeux éthiques et réglementaires | 🔜 À venir |

---

## Licence et utilisation

Ce code est partagé librement à des fins **pédagogiques**. Vous êtes libre de l'utiliser, le modifier et l'adapter pour vos projets personnels. Une mention de la source est appréciée.

---

*DIT Dakar — Master 2 Finance, Semestre 3 — 2025/2026*
