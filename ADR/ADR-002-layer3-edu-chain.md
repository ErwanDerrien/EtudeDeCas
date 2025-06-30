# ADR-002 - Choix d'Ethereum Layer 3 (EDU Chain)

**Statut** : En attente  
**Date** : 2025-02-20  
**Décideurs** : CTO, Équipe Blockchain  

## Contexte  

Frais de transaction (gas) prohibitifs sur Ethereum Mainnet pour les micro-transactions de tokens, avec besoin d'une solution scalable spécifique à notre écosystème éducatif.  

## Options considérées  

1. **Rester sur Ethereum L1**  
   - _Avantages_ : Sécurité maximale, décentralisation.  
   - _Inconvénients_ : Coût >1$ par transaction, limite l'adoption pour les cas d'usage éducatifs.  

2. **Migrer vers un Layer 2 généraliste (Arbitrum/Polygon)**  
   - _Avantages_ : Frais réduits, compatibilité EVM.  
   - _Inconvénients_ : Non optimisé pour les flux pédagogiques, moindre contrôle.  

3. **Développer EDU Chain (Layer 3 custom sur Arbitrum)**  
   - _Avantages_ :  
     - Frais quasi-nuls pour les étudiants/enseignants  
     - Possibilité d'intégrer des primitives métier (badges, parcours certifiants)  
     - Interopérabilité maintenue avec L2/L1 via bridges  
   - _Inconvénients_ :  
     - Effort initial de développement  
     - Nécessité de gérer des validateurs dédiés  

## Décision  

**Option 3 (EDU Chain)** avec architecture hybride :  

- **L1 Ethereum** : Ancrage de sécurité pour les assets critiques  
- **L2 Arbitrum** : Liquidité et interconnexion avec l'écosystème DeFi  
- **L3 EDU Chain** :  
  - Rollup optimiste custom  
  - Whitelist d'opérations éducatives gasless  
  - Modules spécifiques pour la gouvernance académique  

## Conséquences  

- _Positives_ :  
  - Expérience utilisateur idéale pour les établissements partenaires  
  - Possibilité d'innovations pédagogiques on-chain  

- _Négatives_ :  
  - Surcharge opérationnelle initiale  
  - Courbe d'apprentissage pour les utilisateurs non techniques  

- _Risques_ :  
  - Sécurité du stack L3 encore émergente  
  - Effet réseau à construire sur la chaîne dédiée  