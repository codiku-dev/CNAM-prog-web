#  Pokédex Project 

## Prérequis :

- M'envoyer un lien Github vers le projet à robin.lebhar@gmail.com avant le 28 MAI minuit (2024) : (en objet inscrire PROG_WEB:Nom Prénom/Nom Prenom)

- Créer une app react + vite, javascript uniquement.

- L'app doit tourner sur le port 3000

- Utiliser React router

## Spécifications :

### Général

- L'application contient un home page (route "/") ,une page détail ("/pokemon/:id") et une page 404

### Page d'accueil

- La home page affiche la liste des 151 pokémons sous forme de card

- Une card pokemon affiche une image du pokemon, le nom du pokemon , des badges de couleur pour afficher les types d'un pokemon

- Les badges de type sont de la couleur associée au type (voir constante PKMN_TYPES)

- La home page contient un Header avec un logo qui redirige vers la Home page

- La home page contient une input qui permet de filter les pokémon par leurs noms (se déclenche à chaque lettre tappé , pas de bouton)

- Si aucun pokemon n'est trouvé, afficher "Aucun résultat pour la recherche "'Ma recherche'"

### Page de détail

#### Détail d'un pokémon

- La page de détail permet d'accéder à la fiche détaillée d'un pokémon.

- Au clic sur une card dans le home page je suis redirigé vers la page de détail d'un pokemon

- La page de détail d'un pokémon charge les info du pokémon et les affiches (image, nom, stats et badges de type)

- J'affiche au choix les stats sous forme de progress bar, ou sinon au format texte  => value/maxValue (taux de remplissage en pourcentage)
 Ex : 20/200 - (10%)

#### Reviews

- La page de détail contient un icone qui permet de liker le pokémon et d'augmenter son nombre de like de 1
  
- La page de détail affiche l'ensemble des review de ce pokémon

- Un review affiche le contenu et l'auteur

- Il est possible d'ajouter une review via une input ( max 100 caractères). La review est  soumise en tappant sur la touche ENTER.

- Par défaut une review soumise en soumise avec l'auteur "Me"


##  Marquer des points

- Réfléchir à l'architecture et découper en composants et module.css

- Ce qui est constant devrait aller dans constant.js, routes, constantes.

- Tout est nommé en anglais

- J'ai laissé un petit commentaire en anglais pour rapidement expliquer ce que fais ce composant

Ex:
/_
Display this app logo and redirect to the home page when clicked on.
_/
const Header = () => {
return <> ...</>
}

- Bien séparer la partie "api"

- Ecrire des fonctions pures

- Découper la logique au sein des composants en sous fonctions pour avoir un return lisible et facilement modifiable
- Sans over découper non plus

- Utiliser les fichiers d'env pour stocker les enpoints

- Pas de warning / erreur dans la console.

- Gérer les erreurs de nos api

- Afficher un message lors des chargements

- Bien nommer ses composants et ses fichiers en respectant les standards vue en cours

- Bien nommer ses variables ,fonctions, fichiers et dossier comme vue en TP

- Mes if ,else, switch, boucles etc ont des accolades ouvrante et fermantes (je pense au prochain dev qui veut ajouter une ligne de code)

- Un accès au lien direct d'une page devrait fonctionner et devrait requeter uniquement le contenu nécéssaire

- Le github ne contient que le code source, pas les nodes modules

- Le .README explique comment installer et lancer l'application.

- Bonus : responsive
- Bonus on peut filtrer les pokemon en tappant leurs nom OU en tappant leurs type ex: "poison"
- Bonus : Ecrire des commit propres en conventional commit

# Documentation

## Images

To fetch an image by the pokemon id :

raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/<id du pokemon>.svg

Ex : raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg

## Api

### Set up the fake backend

You need a fake server running.

Find db.json , add it at the root of the project.

Install json-server by running

npm i json-server --save-dev

At the project's root run the fake server on the port 3001 :

npx json-server db.json --port 3001

### Api

Fetch all the pokemons (METHOD GET) : http://localhost:3001/pokemons

Fetch a single pokemon (METHOD GET): http://localhost:3001/pokemons/<pokemon id>

Update a pokemon (METHOD PATCH) :
http://localhost:3001/pokemons/<pokemon id>

Example of body :

"{
like: 12
}"

(Becarefull body as to be JSON.Stringify with the method fetch)


Fetch  a all the pokemon reviews (METHOD GET) : http://localhost:3001/reviews/?pokemonId=<pokemonID>

Add a review (METHOD POST) : http://localhost:3001/reviews/

Example of body :

"{
pokemonId: 12
author: "robin",
content: "This is a review"
}"

(Becarefull body as to be JSON.Stringify with the method fetch)

### Utilities

#### Types and colors mapping

```js
export const PKMN_TYPES = Object.freeze([
{ name: "normal", color: "#A8A77A" },
{ name: "fighting", color: "#C22E28" },
{ name: "flying", color: "#A98FF3" },
{ name: "poison", color: "#A33EA1" },
{ name: "ground", color: "#E2BF65" },
{ name: "rock", color: "#B6A136" },
{ name: "bug", color: "#A6B91A" },
{ name: "ghost", color: "#735797" },
{ name: "steel", color: "#B7B7CE" },
{ name: "fire", color: "#EE8130" },
{ name: "water", color: "#6390F0" },
{ name: "grass", color: "#7AC74C" },
{ name: "electric", color: "#F7D02C" },
{ name: "psychic", color: "#F95587" },
{ name: "ice", color: "#96D9D6" },
{ name: "dragon", color: "#6F35FC" },
{ name: "dark", color: "#705746" },
{ name: "fairy", color: "#D685AD" },
{ name: "unknown", color: "#68A090" },
{ name: "shadow", color: "#705898" },
]);
```

#### Max and min stats

```js
// (minimum being 0)

export const MAX_STAT = {
attack: 130,
defense: 180,
specialAttack: 135,
specialDefense: 120,
speed: 120,
hp: 105,
};

```
