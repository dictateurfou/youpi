* Sur le MCD ci-présent, on ne sait pas quelle est la référence. Ce qui serait bien, c'est de souligner le champ qui sert de liaison (regardez l'exemple de fin).

* "LIKE" étant un mot clé de base de données, je recommanderais de mettre "LIKED".

* Dans le "LIKE" entouré, je vois "many-to-many" avec "1,1". 
Cette cardinalité indique un "one-to-one". 
 * Il aurait fallu mettre "0,n" :
 * Le "0" pour dire que le minimum est 0 (l'utilisateur peut avoir liké 0 mug).
 * Le "n" pour dire que c'est un nombre qui peut varier, cela peut être 1 comme 10, 100...


* La liaison entre "order" et "product" aurait dû être faite comme avec le "LIKE". En effet, les informations entre les tables peuvent devenir une table avec des relations lors de la mise en pratique.

 * ci dessous voici un exemple

 * ![This is a alt text.](https://cdn.discordapp.com/attachments/760716097925283853/1082069842640769025/dfdf.drawio.png "This is a sample image.")
 
* explication
 * * "create order" ici deviendra une table en base de données. On lui rajoute donc les informations complémentaires. Elle sera liée avec l'ID de l'utilisateur et l'ID du produit. Pas besoin de le spécifier dans "create order" étant donné que les tables sont liées.
    * "user" -> "create order" cardinalité "0,n" : en effet, un utilisateur peut avoir plusieurs "order".
    * "create order" -> "product" cardinalité "1,n" : un "order" peut contenir un ou plusieurs produits.

### bonus:
    On pourrait modifier "create order" pour "add to basket" qui serait plus parlant .
Voici un exemple (les argument ne sont pas a prendre en compte cela sert juste d'exemple) :

* ![This is a alt text.](https://cdn.discordapp.com/attachments/760716097925283853/1082083192049246388/dfdf.drawio_2.png "This is a sample image.")
