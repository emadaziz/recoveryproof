# RecoveryProof V0.2 fonctionnelle

Cette version persiste réellement les organisations, utilisateurs, systèmes, agents, contrôles, tests de restauration et journaux d'audit dans PostgreSQL. Le tableau de bord est calculé par l'API: aucun KPI n'est écrit en dur dans JavaScript.

## Démarrage
```bash
make up
```
Ouvrir `http://localhost:8080`, puis initialiser l'organisation et le compte administrateur. Mot de passe minimum: 12 caractères.

## Parcours de test
1. Ajouter un système dans **Systèmes** et retenir son ID.
2. Créer un agent dans **Agents** et copier immédiatement son jeton.
3. Construire l'image: `make agent-image`.
4. Créer un dossier de test: `mkdir -p /tmp/backups && date > /tmp/backups/test.bak`.
5. Exécuter l'agent avec la commande documentée dans `docs/AGENT.md`.
6. Revenir au tableau de bord. Les KPI sont recalculés depuis PostgreSQL.

## Limites
V0.2 n'est pas encore prête pour Internet: TLS externe, OIDC/MFA, migrations Alembic, sauvegarde automatique, tests d'intrusion et politique RGPD complète restent nécessaires avant production.
