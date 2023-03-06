## commentaire

* Il manque le paramètre dans la requête SQL de dataMapper.getCard.

* Changer la route pour utiliser l'ID en tant que paramètre dans la méthode getCard.
```js
router.get('/card/:id', mainController.cardPage); // pour rajouter le paramètre id pour l'utiliser dans la fonction cardPage ici c'est référencer grace a :id donc le params auras comme nom params.id
```

Il manque encore du travail pour que je puisse évaluer correctement cet exercice. Je vous encourage à continuer dans cette voie afin de le terminer.