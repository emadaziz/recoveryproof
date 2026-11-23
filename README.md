# RecoveryProof MVP 0.1

Socle SaaS de preuve de reprise: dashboard, API, connecteurs a jetons, plugins et mises a jour. Les sauvegardes restent chez le client.

## Demarrage
1. Installer Docker Engine et Docker Compose v2.
2. Lancer `make up`. Les secrets sont generes localement dans `secrets/`, ignores par Git et montes comme Docker secrets.
3. Ouvrir http://localhost:8080
4. API: http://localhost:8080/api/health

## Regles de secrets
- Aucun mot de passe, jeton ou cle API dans Git, une URL, le frontend ou une image.
- Les jetons d'integration sont aleatoires (256 bits), affiches une seule fois et stockes uniquement sous empreinte HMAC.
- Pour la production, remplacer les fichiers secrets par Docker Swarm secrets, HashiCorp Vault, Azure Key Vault ou Scaleway Secret Manager.
- Ne jamais journaliser les en-tetes Authorization.

## Limites
Ceci est un MVP executable, pas une certification RGPD/NIS2. Une mise en production exige DPIA/registre si applicable, contrats de sous-traitance, politique de retention, tests d'intrusion, supervision, sauvegardes restaurees et validation juridique.
