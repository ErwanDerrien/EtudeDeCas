# ADR-001 - Utilisation d'un Proxy Upgradable pour les contrats  
**Statut** : Approuvé  
**Date** : 2025-03-15  
**Décideurs** : Architecte blockchain, Lead Dev  

## Contexte  
Nécessité de corriger des bugs ou d'ajouter des fonctionnalités post-déploiement sans perdre l'état existant (ex: balances des utilisateurs).  

## Options considérées  
1. **Contrats immutables**  
   - *Avantages* : Alignement avec le principe "code is law", sécurité accrue.  
   - *Inconvénients* : Impossible de patcher des vulnérabilités ou d'évoluer.  
2. **Proxy Upgradable (Pattern Transparent Proxy)**  
   - *Avantages* : Logique métier modifiable tout en conservant le stockage.  
   - *Inconvénients* : Complexité accrue, coût en gas initial plus élevé.  

## Décision  
**Option 2** avec implémentation du standard OpenZeppelin `TransparentUpgradeableProxy`.  
- Justification :  
  - Nécessité de maintenir l'évolutivité pour un produit en phase de croissance.  
  - Séparation claire entre le stockage (conservé) et la logique (upgradable).  

## Conséquences  
- *Positives* :  
  - Mises à jour possibles sans migration coûteuse des données.  
- *Négatives* :  
  - Risque d'attaques sur le proxy si mal configuré (ex: contrôle d'accès oublié).  
- *Risques* :  
  - Perte de confiance des utilisateurs si les upgrades sont trop fréquentes.  