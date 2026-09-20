# BourseClix
Suivi du portefeuille boursier des investisseurs à la BRVM.

## Accès

- Site : https://ytl1-ops.github.io/BourseClix/
- Connexion / inscription : https://ytl1-ops.github.io/BourseClix/connexion.html
- Application : https://ytl1-ops.github.io/BourseClix/app.html (connexion requise)

## Fonctionnement

- Authentification et données : Supabase (comptes, rôles vérifiés côté serveur, portefeuille synchronisé par utilisateur).
- Essai gratuit de 5 jours à l'inscription, puis abonnement.
- Hébergement : GitHub Pages (branche `main`, racine).

## Suivi des opérations et performances

- **Journal d'opérations datées** : achats, ventes, dividendes, ajustements, dépôts/retraits (table `bc_transactions`), avec suivi de chaque création, modification ou suppression (`bc_transactions_audit`).
- **Base de suivi** : à la création du compte, historique de 3 mois précédant l'ouverture. Les positions initiales sont valorisées au cours de clôture de la date de référence, ou à la date d'acquisition indiquée.
- **Cours réels** : historique des clôtures BRVM synchronisé chaque jour de bourse (Edge Function `bc-sync-prices`, table `bc_prices`) et actualisé à chaque consultation.
- **Performances** : +/- value depuis acquisition/référence, plus-values réalisées, dividendes, rendement pondéré dans le temps comparé à l'indice BRVM Composite.
