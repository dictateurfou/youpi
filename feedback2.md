
## commentaire
* Il y a un oubli, la fonction pour supprimer une carte du deck n'est pas présente. La méthode dataMapper.getElements devrait prendre en compte l'élément en question et pour ceux n'ayant aucun élément faire presque la même chose qu'actuellement mais en cherchant les éléments null. Se référer à la correction :
```javascript
const query = "SELECT * FROM card WHERE element IS NULL";
```

* La colonne "élément" dans votre deck est constituée uniquement d'un "$" pour afficher un prix, une information qui n'existe pas et aurait dû être remplacée par l'élément.

## point important
dataMaper.js contient une faille de sécurité SQL. Penser à utiliser les paramètres de cette manière :
```javascript
const cardResults = await client.query("SELECT * FROM card WHERE id = $1, [id]);
```

## optionel
* Il aurait été préférable de mettre la session secret key dans le .env.
* Penser à vider les console.log() utilisés pour le développement.

Bon travail dans l'essemble je t'encourage a continuer sur cette voix la.
