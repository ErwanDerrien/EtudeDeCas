# ADR-002 - Choix d'Ethereum Layer 2 (Arbitrum)

**Statut** : Approuvé  
**Date** : 2025-02-20  
**Décideurs** : CTO, Équipe Blockchain

## Contexte

Frais de transaction (gas) prohibitifs sur Ethereum Mainnet pour les micro-transactions de tokens.

## Options considérées

1. **Rester sur Ethereum L1**
   - _Avantages_ : Sécurité maximale, décentralisation.
   - _Inconvénients_ : Coût >1$ par transaction, limite l'adoption.
2. **Migrer vers Polygon**
   - _Avantages_ : Frais très bas, compatibilité EVM.
   - _Inconvénients_ : Sécurité moins éprouvée qu'Arbitrum (Validium).
3. **Utiliser Arbitrum One**
   - _Avantages_ : Sécurité héritée d'Ethereum (Rollup), frais 10x moins chers.
   - _Inconvénients_ : Latence de 7 jours pour les retraits vers L1.

## Décision

**Option 3 (Arbitrum)** avec déploiement multi-chaîne :

- L1 pour le contrat ERC20 (sécurité).
- L2 (Arbitrum) pour le `RewardContract` (frais réduits).

## Conséquences

- _Positives_ :
  - Expérience utilisateur améliorée (coût négligeable).
- _Négatives_ :
  - Complexité accrue (gestion des bridges L1↔L2).
- _Risques_ :
  - Dépendance à la stabilité du réseau Arbitrum.
