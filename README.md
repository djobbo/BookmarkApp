# Bookmark App

## Fonctionnement

-   `yarn` pour installer les dépendances.
-   `yarn typecheck` pour vérifier les types.
-   `yarn test` pour lancer les tests.
-   `yarn start` pour démarrer l'application.

## Structure

> App Bootstrappée avec `create-react-app`

### Components

-   AddBookmarkForm - Formulaire pour ajouter des Bookmarks
-   BookmarkItem - Component pour afficher un Bookmark
-   Loader - Utilisé pendant la requète envoyée à noembed.com

### Custom Hooks

> Abstraction de certaines fonctionnalités pour une meilleure lecture du code.

-   useBookmarks - Fonctionnalités de stockage, addition et suppression des
    bookmarks
-   useFetchBookmark - Utilisé pour récupérer les données de l'embed via
    noembed.com

### Assets Externes

-   Icônes SVG (`Corbeille` et `Plus`): https://coolicons.cool/
-   Loader CSS: https://loading.io/css
-   Placeholder IMG (si un bookmark n'a pas de thumbnail):
    https://via.placeholder.com/160x120

### Styling

CSS Modules supportés par `create-react-app`

### Tests

Utilisation de `jest` et `@testing-library/react` inclus avec `create-react-app`

## Remarques

-   La réponse de l'API noembed n'a pas l'air de contenir de field contenant la
    date d'upload des images Flickr.
-   J'ai ajouté une variable `loading` quand un call à l'API est fait qui
    désactive le bouton de création de bookmark, pour eviter un "spam" de l'API.
    Ce serait une feature à disctuter.
-   Quand un url est déja enregistré dans les bookmarks il n'est simplement pas
    pris en compte (à discuter s'il serait plus judicieux de mettre à jour les
    données du bookmark déja présent avec les nouvelles données).

### Pour aller plus loin

-   Ajout d'un feedback visuel quand une erreur survient (mauvais Bookmark URL,
    problème de connection à l'API etc...)
-   Ajout d'une meilleure validation des données envoyées par l'API (Utilisation
    d'un array d'erreurs par exemple) et de tests pour chaque field retournés.
-   Ajout de tests pour le formatage des dates.

## Énoncé

Vous devrez réaliser une application de gestion de bookmarks.

Celle-ci devra supporter deux types de liens :

-   vidéo Vimeo (ex: https://vimeo.com/565486457)
-   photo Flickr (ex: https://www.flickr.com/photos/feuilllu/45771361701/)
    L’utilisateur aura une vue principale contenant un formulaire d'ajout et une
    liste des bookmarks.

Le formulaire d'ajout comporte un champ de saisie pour l'url du lien et un
bouton de soumission. Lors de la soumission du lien, un appel à l'API
https://noembed.com/ sera effectué pour obtenir les informations de la vidéo ou
de la photo.

### Les informations suivantes seront affichées pour un lien Vimeo :

-   Aperçu vidéo (si disponible)
-   URL
-   Titre de la vidéo
-   Auteur
-   Date d'ajout dans l'application (il y a une heure, il y a 2 minutes...)
-   Date de publication sur Vimeo (le 3 novembre 2020)
-   Durée (hh:mm:ss)

### Les informations suivantes seront affichées pour un lien Flickr :

-   Aperçu photo
-   URL
-   Titre de la photo
-   Auteur
-   Date d'ajout dans l'application (il y a une heure, il y a 2 minutes...)
-   Date de publication sur Flickr (le 3 novembre 2020)
-   Largeur x Hauteur

Un bouton de suppression sera également présent pour chaque lien.

L'application doit être réalisée avec React et les Hooks
(https://fr.reactjs.org/docs/hooks-reference.html). L'utilisation de Typescript
est également un pré-requis.

Seul React est autorisé comme librairie tierce (donc pas de redux, axios,
moment...).

Nous testerons l'application sur la dernière version de Chrome ou Firefox.

Pour bootstrap l'application, voici quelques outils :

Vite : https://vitejs.dev/guide/#scaffolding-your-first-vite-project Parcel :
https://parceljs.org/getting-started/webapp/ create-react-app :
https://create-react-app.dev/docs/adding-typescript/ Il n’est pas demandé de
s’attarder sur l’aspect graphique de l’application ou sur la persistance des
bookmarks.
