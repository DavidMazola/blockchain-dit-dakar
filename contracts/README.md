# Contrats Solidity — SimpleTransfer

Ce dossier contient les deux versions du smart contract développé dans le **Chapitre 3** du cours.  
Ils sont conservés ensemble pour retracer la progression pédagogique, de la version initiale jusqu'à la version finale déployée sur Sepolia.

---

## SimpleTransfer_v0.sol — Version initiale

**Rôle dans le cours :** point de départ du Chapitre 3. C'est cette version qui est commentée et lue en classe lors de la découverte de Solidity.

**Ce qu'elle contient :**
- Structure de base d'un contrat Solidity (`pragma`, `contract`, variables d'état)
- Fonction `sendTransfer()` — envoi d'ETH avec `.transfer()` (syntaxe historique)
- Événement `TransferSent` — émis à chaque transfert
- Fonction `owner()` — retourne l'adresse du déployeur
- Fonction `withdraw()` — retrait des fonds par le propriétaire uniquement (`onlyOwner`)

**Limitation identifiée en séance :**  
L'usage de `.transfer()` génère un avertissement de dépréciation dans les versions récentes de Solidity. C'est ce constat, observé directement dans Remix IDE, qui a motivé le passage à la v1.

---

## SimpleTransfer_v1.sol — Version finale (déployée sur Sepolia)

**Rôle dans le cours :** version aboutie, compilée, déployée et utilisée comme référence pour tout le Chapitre 4 (dApps).

**Ce qui change par rapport à v0 :**

| Point | v0 | v1 |
|-------|----|----|
| Envoi d'ETH | `.transfer()` (déprécié) | `.call{value: ...}()` (recommandé) |
| Historique des transferts | Absent | `getTransfer(index)` — consultation par index |
| Compteur de transferts | Absent | `totalTransfers()` |
| Montant total reçu | Absent | `totalAmountReceived()` |
| Gestion des erreurs | Basique | `require()` avec messages explicites |

**Fonctions exposées :**

| Fonction | Type | Description |
|----------|------|-------------|
| `owner()` | view | Retourne l'adresse du déployeur |
| `totalTransfers()` | view | Nombre total de transferts effectués |
| `totalAmountReceived()` | view | Montant total reçu (en wei) |
| `getTransfer(index)` | view | Détails d'un transfert par son index |
| `sendTransfer()` | payable | Envoie des ETH au contrat |
| `withdraw()` | onlyOwner | Retire les fonds vers l'adresse owner |

**Adresse déployée sur Sepolia :**
```
0xdd60611951b607bd4c68e306992022d5e8f75bcf
```
Consultable sur [sepolia.etherscan.io](https://sepolia.etherscan.io/address/0xdd60611951b607bd4c68e306992022d5e8f75bcf)

---

## Comment utiliser ces contrats dans Remix IDE

1. Ouvrir [remix.ethereum.org](https://remix.ethereum.org)
2. Créer un nouveau fichier → coller le contenu du `.sol` voulu
3. Onglet **Solidity Compiler** → compiler (version `0.8.x`)
4. Onglet **Deploy & Run** → sélectionner **Injected Provider — MetaMask**
5. Vérifier que MetaMask est sur le réseau **Sepolia**
6. Cliquer **Deploy** → confirmer dans MetaMask
7. Récupérer l'adresse dans la section **Deployed Contracts**

> Pour interagir avec le contrat déjà déployé par l'intervenant (sans redéployer), utiliser l'option **At Address** dans Remix en collant l'adresse ci-dessus.

---

## Leçon à retenir

La progression v0 → v1 illustre un principe fondamental du développement de smart contracts : **un contrat déployé est immuable**. On ne peut pas le modifier après déploiement. Toute amélioration nécessite un nouveau déploiement, à une nouvelle adresse. C'est pourquoi la v0 et la v1 ont des adresses différentes sur la blockchain.

---

*Blockchain & Finance — DIT Dakar | Master 2 Finance, Semestre 3*
