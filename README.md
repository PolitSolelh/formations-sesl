# Fiche technique maintient du site formations

## I/ Outils préalables
### FileZilla
FileZilla est un client qui permet de communiquer avec les fichiers d’un serveur pour upload et download des fichiers. Il servira notamment à mettre les nouvelles pages dans le serveur ou à modifier les anciennes s’il y avait besoin. Vous pouvez le télécharger gratuitement ici : https://filezilla-project.org/.
Pour vous connecter au serveur sur FileZilla, appuyer sur le bouton qui ouvre le gestionnaire de sites

Une fois la fenêtre ouverte, remplissez comme suit. Si vous ne connaissez pas le mot de passe, n’hésitez pas à le demander au SF.

Une fois connecté, vous aurez à gauche une fenêtre avec les fichiers locaux (stockés sur votre ordinateur) et à droite une fenêtre avec les fichiers distants (stockés sur le serveur). Avec cet accès SFTP vous ne pourrez modifier que les fichiers du site formations.

### Notepad++
Je recommande l’utilisation d’un logiciel de “code” qui permet la coloration syntaxique pour rendre plus simple la navigation dans le code et plus clair le fonctionnement de celui-ci. Notepad++ fait très bien l’affaire sur windows. Dans l’idée ça ressemble à ça, les couleurs varient selon le logiciel et les paramètres que vous utilisez.


### Github
Un github a été créé qui permet d’héberger le “code vierge” du site au cas où il devait être réinstallé de 0. Vous pouvez le trouver ici https://github.com/PolitSolelh/formations-sesl 

## II/ Comprendre le fonctionnement de base
### CSS
Le CSS est un langage de code utilisé pour le web. Il permet de créer une feuille à part de la page web HTML pour créer des fonctions qui pourront être utilisées dans la page HTML.
 
Ici, @font-face sont des fonctions particulières qui permettent d’appeler des polices de caractères. Par contre “.formations_titre” est une fonction à part entière. Elle débute par un point pour marquer que c’est une fonction, son nom qui doit être écrit sans espace, puis est suivi d’un  { pour ouvrir les propriétés à intégrer à la fonction et } pour fermer les propriétés à intégrer à la fonction, traditionnellement le } fermant est mis après un retour à la ligne. Les propriétés sont ici, par exemple “width”, “height”. Les propriétés sont suivies d’un deux points “:” sans espace puis de l’argument qui est associé à la propriété. Par exemple, pour “width” l’argument est “50%”. Chaque lot propriété-argument est fermé par un point virgule “;” puis un retour à la ligne. La fonction du dessous “.formations_titre h1” permet de marquer que c’est une propriété attribuée à la fonction `<h1>` dans le code html, seulement si cette fonction `<h1>` est à l’intérieur d’un `<div class=”formations_titre”>`, donc comme suit : `<div class=”formations_titre”><h1>Texte</h1></div>`.
Le code peut être commenté. Les commentaires commencent par /* et finissent par */
### HTML
Le HTML est l’autre versant des pages web. C’est là qu’on construit à proprement parler la page en réutilisant les variables créées dans la feuille CSS. Toute page html commence par `<!DOCTYPE html>` puis la balise `<html>`. A l’intérieur de la balise `<head>`, on déclare le titre de la page (ce qui est affiché en haut dans l’onglet), on lie la ou les feuilles CSS dont on a besoin, puis on ferme la balise head pour passer à la balise body où on rentre le code qui sera affiché dans la page. La plupart des balises sont des `<div class=””>`, entre guillemet la variable voulue créée précédemment dans le CSS. class permet d’appeler ces variables.
Le code peut être commenté. Les commentaires commencent par `<!-- et finissent par -->`.
## III/ Rajouter des nouvelles pages
### Architecture du site
Le dossier du site sur le serveur de Solidaires Étudiant-e-s est rangé d’une certaine manière qu’il faut maintenir pour ne pas casser tout le site.
Dans la racine, il y a index.html, stylesheet.css, chaque fichier html (page web) de catégorie ainsi que des dossiers. index.html est la page qui est affichée dans le site /formations/, stylesheet.css est la feuille CSS utilisée dans tout le site. Déplacer ces fichiers dans un dossier par exemple rendrait le site inutilisable ou compliqué à utiliser.
Chaque dossier représente un thème et chaque fichier dans ce dossier est une page web qui contient une formation de ce thème. Là aussi, déplacer les fichiers casseraient les liens.
### Ajouter une nouvelle formation
Un fichier doit être créé dans le thème qui correspond à la formation avec un titre en un nom de fichier court en un seul mot. Il faut ensuite aller dans le fichier de la catégorie dans la racine pour dupliquer la partie marquée à dupliquer et modifier les informations pour correspondre à la nouvelle formation.
Les nouvelles formations doivent être formatées pour être lisibles dans une nouvelle page. Elles doivent être mises à l’intérieur du code après la balise `<div class=”formations_corps”>`. Chaque paragraphe doit être suivi d’une balise `<br />` sans quoi il n’y aura aucun espace dans la formation. S’il y a des images, elles doivent être entrées avec la balise `<img src=”lien_du_fichier” class=”image” alt=”description (courte) de l’image”>`. Les images peuvent être stockées dans l’intranet ou hébergées ailleurs. Pour le stocker dans l’intranet, dans le fichier de thème, dans un dossier image. Votre balise serait donc `<img src=”/titre_du_dossier_du_theme/image/nom_de_limage.extension_du_fichier” class=”image” alt=”description (courte) de l’image”>`.
### Ajouter une nouvelle catégorie
Si une nouvelle catégorie devait être ajoutée, le procédé est identique au fait d’ajouter une nouvelle formation dans la catégorie sauf qu’à la place du fichier de la catégorie, il faut aller dans index.html, c’est à dire qu’il faut dupliquer la partie marquée à dupliquer et modifier les informations pour correspondre à la nouvelle formation.
