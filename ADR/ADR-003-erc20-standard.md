# ADR-003 - Implémentation du Standard ERC-20 au lieu d'ERC-777

**Statut** : En attente  
**Date** : 2025-01-10  
**Décideurs** : Équipe Sécurité, Smart Contract Devs

## Contexte

Besoin d'un token fongible pour récompenser les joueurs, avec compatibilité maximale.

## Options considérées

1. **ERC-20**
   - _Avantages_ : Standard le plus adopté, supporté par tous les wallets.
   - _Inconvénients_ : Fonctionnalités limitées (ex: pas de hooks).
2. **ERC-777**
   - _Avantages_ : Plus flexible (hooks pour des callbacks).
   - _Inconvénients_ : Risques de reentrancy, support limité.

## Décision

**Option 1 (ERC-20)** avec extension via `ERC20Snapshot` pour les besoins futurs.

- Justification :
  - Priorité à la sécurité et à l'interopérabilité.
  - Les hooks de l'ERC-777 introduisent des vecteurs d'attaque complexes.

## Conséquences

- _Positives_ :
  - Intégration facile avec les exchanges et wallets.
- _Négatives_ :
  - Nécessité de développer des mécanismes custom pour certaines features.
- _Risques_ :
  - Aucun identifié (standard bien éprouvé).
