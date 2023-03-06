# info téhorique
La méthode fetch en JavaScript est utilisée pour effectuer des requêtes HTTP asynchrones (c'est-à-dire sans bloquer l'exécution du reste du code) vers des URLs afin de récupérer le contenu de la réponse. Cela peut être du HTML comme dans le cas ci-dessous, mais aussi du JSON, du XML, etc. Cela sert généralement à récupérer des données côté serveur sans avoir besoin de reconstruire la page entièrement.

Dans le cadre de cette application, le serveur génère toute la page HTML. Donc, si on venait à rajouter un bouton "rafraîchir" sur la page principale, il serait intéressant de faire appel à une route qui enverrait les cartes sous forme de JSON. Le serveur n'aurait donc pas besoin de régénérer la page et le client pourrait changer les données affichées grâce au retour du fetch avec un peu de JavaScript.

#### ordre de fonctionnement
Fetch envoie une réponse avec l'objet Response sous forme de promesse (async). Une fois l'objet réponse traité, il renvoie une promesse avec les informations récupérées. 
Il sera donc bien souvent utilisé de cette manière avec 2 .then de suite :
```js
fetch('https://api.example.com/data')
  .then(response => response.json()) // recois l'objet réponse
  .then(data => console.log(data)) //recois l'objet réponse encoder en json grace a response.json()
  .catch(error => console.error(error));// en cas d'érreur
```

Voici un exemple de code concret récupérant le bout de code HTML de la page d'accueil  :
```js
fetch('http://localhost:1234')
  .then(response => response.text())// traite la réponse sous forme de text dans notre cas nous donne un document html
  .then((data) => {
    console.log(data) //affiche le retour html dans la console
    //peut être isérer dans le document ou autre
  })
  .catch(error => console.error(error)); // en cas d'érreur
```

Exemple plus poussé en évitant les gros blocs de callbacks partout si beaucoup d'appels à fetch dans le code :
```js
function fetchHtml(url){ // return dans une promise pour utiliser le await
    return new Promise((resolve,reject) =>{
        fetch('http://localhost:1234')
        .then(response => response.text()) // traite la réponse sous forme de text dans notre cas nous donne un document html
        .then((data) => resolve(data)) // resoud la promesse en renvoyant la data
        .catch(error => reject(error)); // en cas d'érreur
    })
}

async function start(){
    try{
        const rslt = await fetchHtml("http://localhost:1234") // on évite les await hors function async c'est pour sa que j'ai fais une fonction start
        console.log(rslt)
    }catch(error){
        console.log(error)
    }
}
start();
```