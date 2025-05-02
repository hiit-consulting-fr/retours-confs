# Pattern Hive

## Informations principales

2025/04/29 11h30

Julien Topcu & Thomas Pierrain

https://mixitconf.org/2025/le-pattern-hive-une-strategie-de-modularisation-pour-votre-monolithe-modulaire-ou-vos-microservice

## Notes

### Evolution

- Monolith : code spaghetti

- Archi hexagonale : Le domain reste du code spaghetti

- Microservice : Distributing computing failed

- DDD : Bounded context = un microservice = une responsabilité métier

- Monolith modulaire

### Raison d'un échec

Le découpage en bounded context peut être faux ou évoluer.

Les scopes peuvent être flou.

Le microservice est une stratégie de déploiement pas de design.

### Solutions

Architecture plus flexible et indépendant de stratégie de déploiement

### Pattern Hive (8 ans de test et utilisé en production)

Possibilité de redesigner

System distribué plus couteux

Le monolith modulaire permet de faire des erreurs et d'itérer sur le design

Isolation entre les modules avec l'encapsulation et le pattern port/adapter (architecture hexagonale)

API (primaire) /SPI (secondaire)

Dans le pattern Hive les ports & adaptateurs sont utilisés pour réduire le couplage entre les modules pas pour isolé des technos (cas de l'architecture hexagonale)

Utilisation d'un inproc pour la communication entre le port et l'adapter (pas d'utilisation du réseau)

### Comment gérer les BDs ?

Idem que microservice => séparer les datastores entre les domaines (module)

### Séparation

#### Raisons

- Technique
- Organisation

#### Comment

Découpage au niveau des SPI, enlever l'inproc adapter (ACL) et le remplacer par un client HTTP et rajouter une API Rest sur le SPI

=> Pattern fractale

#### Patterns

CF Conformist : Importation des modèles dans un autre module

ACL : Anti Corruption Layer

Shared Kernel : Librairie partagée de model sans logique métier

### Avertissements

#### Problème

Trop bavard entre les modules => problème réseau lors de la séparation

#### Solution

Regrouper les appels 

Read model pour éviter le piège du RPC (https://www.qlerify.com/event-storming-concepts/read-model)

Attention suite de tests à découper et utilisation de stub

Eviler de travailler à plusieurs équipes sur un même module

Trop gros => charge cognitive importante

### Conclusion

Lien entre les designs de strategies et de deployment

Pouvoir faire des erreurs et tester rapidement le découpage

### Autre vidéo 

Mot clés : Model Mitosis