# Datacenter-as-Code : les arcanes de notre build system omniscient basé sur Nix.

## Main info

Afin de garantir une consistance globale de notre système, nous visons une infrastructure consciente de chaque modification. Utiliser à bon escient l'effet papillon nous permet de modeler et auditer notre infrastructure dans sa globalité, et piloter nos applications à chaque instant.

Dans ce talk, nous vous expliquerons notre utilisation de Nix pour décrire notre infrastructure: build des applications, des images Docker, des VM, des configurations applicatives, des manifestes Kubernetes, mais aussi des topologies réseau, etc... Tous ces éléments sont décrits sous forme d'un graph complètement déterministe ouvrant un nouveau champ d’utilisation, de manipulation et de réactivité face aux changements, et ce, avant même que la compilation ne soit lancée !

Découvrez tous les bénéfices découlant de cette architecture: performance, sécurité (run et supply chain), capacité à être testé ainsi que ses gains de fiabilité. Ce retour d'expérience illustré de nombreux exemples permettra de comprendre notre stratégie permettant de répondre aux exigences de normes telles que SecNumCloud.

## Notes

- Infra gcp
- Nix sert à construire toute sorte de choses
- Nix est un meta builder (permet de remplacer make, script shell, Dockerfile)
- Nix se base sur un arbre de construction
- Nix est un binaire
- Nixpkgs : package nix utilisés dans NixOs
- NixOs : l'OS qui est construit avec Nix
- Test nix pour vérifier que le build est ok
- Propagation des changements facile
- Découverte de breaking change 

Repo utilisé pendant la démo : [https://github.com/abryko/treeverse-nix-demo-devoxx](https://github.com/abryko/treeverse-nix-demo-devoxx)

## À étudier

- curl 127.1
- Commande glow
