
## commentaire
* Le template pour la liste des cartes était cassé, tous les éléments de design étaient pré-intégrés, il ne restait plus qu'à les faire fonctionner.

* ReferenceError: C:\Users\steven\Desktop\dev\tuteur\bapteme-freelances\bapteme_javascript\apprenant3\app\views\main\cardDetails.ejs:8 (vue de la carte).
 * Bonne utilisation de la boucle, mais cependant attention, c'est la variable singleCard qui renvoie des infos et non la variable card.
 * La variable du template renvoyé attendu n'a pas le bon nom. En effet, il aurait fallu mettre dans la propriété "card" en renvoyant un tableau comme ceci:
```js
{card : [oneCard]} //bon exemple
{oneCard} // mauvais exemple cela reviendrais a avoir écris {oneCard: oneCard}
```
 * Il n'y a pas besoin d'une boucle pour afficher un seul résultat. Le plus cohérent aurait été de définir la variable "card" avec le retour du data mapper directement.

* Le searchController contient plusieurs erreurs (les résultats envoyés au template ainsi qu'un require manquant sur dataMapper). Le template retourné n'est pas le bon.

* Attention au nom de variable utilisé. "dataMapper.cardElement(element)" dans le searchController aurait dû être "dataMapper.getCardByElement(element)". La fonction est également incomplète.

* Il manque la route et les fonctions pour le deck en sessions.

Beaucoup de corrections à faire pour obtenir le résultat attendu. N'hésitez pas à poser des questions lors de blocages ou de rechercher sur Google. Une recherche efficace vous donnera souvent accès à ce que vous cherchez.