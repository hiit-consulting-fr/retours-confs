# La fin des archis event-based ? Orchestration avec Temporal

## Main info

Lorsqu’il s’agit d’architectures microservices, même en l’absence d’un consensus sur la bonne manière de faire, une réalité persiste : elles sont complexes. Actuellement, la plupart de ces architectures reposent sur un broker de message ou une plateforme de streaming, on parle alors de pattern choreography (event-based). Il est intéressant de noter qu’il existe une alternative moins connue, mais qui peut se montrer tout aussi efficace : le pattern orchestration. C’est précisément dans ce domaine que brille Temporal, une solution open-source sortie tout droit d’Uber.

Son leitmotiv : simplifier votre code, éliminant toute la plomberie superflue.

Rejoignez-moi dans 45 minutes de live coding d’un système de commande en ligne, simple mais puissant, efficace et fault-tolerant, tout ça en plain old java.

## Notes

- Exécution de workflow
- Input
- Activity étape du workflow

- github : https://github.com/HCaupert/temporal-talk
- 500$ free credit: https://pages.temporal.io/event-devoxx-france-free-credits-with-takima.html

## Some notes

Temporal est un framework qui s'occupe de toute la plomberie de votre application. Vous n'avez plus qu'à vous concentrer sur votre Workflow métier.
Remplace Kafka et les appels http, s'occupe de la communication entre services

Utile dans le cas des Event Drive Architecture
