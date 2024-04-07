#  Pokédex Project 

## Prérequis :

- M'envoyer un lien Github vers le projet à robin.lebhar@gmail.com avant le 28 MAI minuit (2024) : (en objet inscrire PROG_WEB:Nom Prénom/Nom Prenom)

- Créer une app react + vite, javascript uniquement.

- L'app doit tourner sur le port 3000

- Le fake server doit tourner sur le port 3001

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

- Laisser un petit commentaire en anglais pour rapidement expliquer ce que fait un composant

Ex:
```jsx
/* 
Display this app logo and redirect to the home page when clicked on.
*/
const Header = () => {
return <> ...</>
}
```

- Bien séparer la partie "api"

- Ecrire des fonctions pures

- Découper la logique au sein des composants en sous fonctions pour avoir un return lisible et facilement modifiable
- Sans over découper non plus

- Utiliser les fichiers de config pour stocker les enpoints

- Pas de warning / erreur dans la console.

- Gérer les erreurs de nos api

- Bien nommer ses composants et ses fichiers en respectant les standards vue en cours

- Bien nommer ses variables ,fonctions, fichiers et dossier comme vue en TP

- Mes if ,else, switch, boucles etc ont des accolades ouvrante et fermantes (je pense au prochain dev qui veut ajouter une ligne de code)

- Le github ne contient que le code source, pas les nodes modules

- Le .README explique comment installer et lancer l'application.

- Bonus : responsive
- Bonus on peut filtrer les pokemon en tappant leurs nom OU en tappant leurs type ex: "poison"
- Bonus : Ecrire des commits propres en conventional commit

