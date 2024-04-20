# Le cauchemar des attaquants : une infrastructure sans secret

## Main info

La gestion des secrets a toujours été un sujet complexe : comment et où les stocker, comment les partager,qui les utilise, ont-ils été volés ? Sérieusement, quand avez-vous changé le mot de passe de votre base de données pour la dernière fois ? Selon les chiffres de Verizon, 49% des attaques informatiques impliquent le vol et l'utilisation de secrets, parfois des mois après leur exfiltration.

Est-il possible de construire un écosystème sans secret long-terme, en coupant ainsi l’herbe sous le pied des hackers ? Les avancées technologiques récentes (SSO, OIDC, Cloud IAM, Workload Identity, Vault credential brokering, Just-in-Time access) rendent ce rêve non seulement réalisable, mais en prime, elles simplifient la vie des développeurs.

A la lumière de plus d’une dizaine de missions dans des écosystèmes différents, Thibault se propose de vous montrer par des exemples concrets le chemin vers l’infrastructure “Zero-Creds” :

Comment supprimer les secrets utilisés par les développeurs ? (applicatifs, base de données, clés SSH…)

Quels mécanismes et outils permettent la rotation automatique des secrets utilisés par les machines ?

A la fin du talk, vous connaitrez toutes les bonnes pratiques et outils pour supprimer tout secret long-terme de votre écosystème.

## Notes

- Rotation à 15min
- Mise en place de sso
- Oauth2proxy
- Boundary/vault
- Sops encryption de mot de passe