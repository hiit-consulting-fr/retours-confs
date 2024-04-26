# L'Architecture Hexagonale par la pratique, le live coding qui rendra vos applications plus pérennes

## Main info
45' by Julien Topcu (Shodo)

see the conference here:

TL;DR: 
Qu'est ce que l'archi hexagonale, quelques consepts et une belle démo

## Notes

Dans la majorité des applis on retrouve une archi en couche: controller/service/persistence. Ce genre d'archi introduiut beaucoup de couiplage donc de la fragilité.

On retrouve également du code métier (celui qui apporte la valeur à l'appli) dans plusieurs couches.

L'archi hexagonale est un pattern permettant d'isoler et de centraliser le code métier dans un "Domaine"
Et après globalement, pour éviter les dépendances, on créer des interfaces

### Resources

 - autre vidéo sur le sujet : https://youtu.be/r2XMwAUqZBA?si=ezqP9Lshm93krVf5
 - repo de la démo : https://gitlab.com/beyondxscratch/hexagonal-architecture-java-springboot
