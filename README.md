# GLOSSAIRE-QUIZ


# GENERAL

## 1) Quel est l’environnement à installer pour exécuter un script PHP ? Citer 2 exemples de logiciels permettant ce contexte :
- Pour exécuter un script PHP, il faut un serveur web permettant à la machine d’interpréter le code PHP, exemple :
    • Laragon
    • XAMPP

## 2) Qu’est-ce qu’un algorithme ?
- Un algorithme est une suite d'étapes à suivre permettant d'obtenir un résultat à partir de données fournies en entrée.

## 3) Qu’est-ce qu’une variable ? Par quel symbole est préfixée une variable en PHP ?
- Une variable est comme une "boîte" qu'ont créé afin d'y stocker une information. Pour déclarer une variable il faut précéder le nom qu'on lui donne du symbole "$". On peut y stocker des chaînes de caractères (strings), des nombres entiers (integers), des nombres à virgules (float) etc. À noter qu'il y a une convention nommée camelCase à respecter pour nommer les variables.
Exemple :
`$maVariable = "ma variable, respectant le camelCase"; // Contient une chaîne de caractères (strings)`

## 4) Qu’est-ce que la portée d’une variable ?
- La portée d’une variable fait référence à la partie du code où elle pourra être « appelée ». Une variable déclarée à l’intérieure d’une méthode ou d’une fonction pourras être appelée uniquement à l’intérieure de celle-ci (locale), alors qu’une variable créée en dehors pourra être appelée n’importe où dans le script (globale).

## 5) Qu’est-ce qu’une constante ? Quelle est la différence avec une variable ?
- Une constante est similaire à une variable, à la différence que la valeur attribuée à celle-ci ne pourra pas être modifiée par la suite. Elle a une valeur fixe, et on la déclare de cette façon :
`define("NOM_CONSTANTE", "valeur");`

## 6) Qu’est-ce qu’une superglobale, combien en existent-ils et donner un exemple d’utilisation :
- Une superglobale est une variable déjà intégrée dans le langage et qui a l’avantage d’être disponible dans tout le script, sans nécessiter de la déclarer.
Exemple : il y a `$_GET`, qui contient les données transmises par l'URL.

## 7) Quels sont les différents types (primitifs) que l’on peut associer à une variable en PHP ? Les citer et en donner des exemples (ne pas oublier le type d’une variable sans valeur)
- Une variable peut contenir : Des chaînes de caractères (string), des nombres entier (int), des nombres à virgules (float), des booléens (bool), des tableaux (array).

## 8) Existe-t-il plusieurs types de tableaux en PHP, si oui lesquels ?
- Oui, il y'a les tableaux numériques :
    Exemple : $couleurs = ["rouge", "vert", "beu"];
Dans cette exemple, chaque couleur est une valeur, et pour utiliser chaque élément du tableau, il faut appeler sa "clé" correspondante. A noter qu'un tableau numérique commence toujours par la clé    "[0]". Ainsi, pour appeler la couleur "vert" il faudra écrire : echo $couleur[1];

- Et il y'a les tableaux associatif : 
Exemple : $age = ["Quentin" => "26", "Mickael" => "38", "Stephane" => "41"];
    Dans cette exemple, "Quentin" devient la clé, et "26" la valeur qu'on lui à attribué. Ainsi : echo $age["Quentin"]; // Affiche "26"

## 9) Quelles sont les différentes structures de contrôles qu’il existe en algorithmie ? Donner un exemple pour chacune d’entre elles
• Structure séquentielles : 
La structure par défaut, le code s'éxècute ligne après ligne, de haut en bas.
$a = 10;
$b = 5;
$resultat = $a + $b,

• Structure conditionnelles (if/else, elseif) : 
Execute un bloc d'instruction uniquement si certaines conditions sont remplies ou non.
if(10 > 5)
{
    $info =  "10 est bien plus grand que 5";
}else
{
    $info = "10 n'est pas plus grand que 5";
}

• Srtucture itératives (boucles) :
Répète un bloc d'instruction tant qu'une condition est remplie, il y'a les boucles :
    - for, utiles quand on connaît à l'avance le nombre de fois que la boucle doit s'éxécuter.
    - while, le nombre d'itérations n'est pas connu à l'avance.
    - do ... while, pour que la boucle s'execute au moins une fois avant de vérifier la condition.

  Exemple avec une boucle while : 
$i = 1;
while ($i <= 5) {
    echo "Le numéro est: $i <br>";
    $i++;
}

## 10) Quelle est la fonction PHP permettant de demander la longueur d’une chaîne de caractères ?
- En php on utilise la fonction "strlen" pour calculer la longueur d'une chaîne de caractères.
"str" fait en faite référence au type "string" qui est donc le type de données "texte", et "len" pour "length" qui se traduit par longueur en français. 
    Exemple : 
        $maChaine = "Bonjour le monde !";
        $longueur = strlen($maChaine);
        echo $longueur; // Affichera la longueur de la chaîne, dans ce cas : 18
            (A noter que les espaces sont également compté comme caractères)

## 11) Qu’est-ce qu’une session ? Quelle fonction permet de démarrer une session en PHP ? Donner un exemple d’utilisation en PHP
- $_SESSION est une super globale, elle permet de stocker des informations sur le serveur et d'y avoir accès sur toutes les fichiers de l'application.
Pour démarrer une session, on utilise "session_start();", la fonction doit être appelée avant tout code HTML
    Exemple : 
        // Démarre la session
        session_start();

        // Stocke des données dans la session
        $_SESSION["nom_utilisateur"] = "JeanDupont";
        $_SESSION["email"] = "jean.dupont@example.com";

        // Accéde aux données stockées dans une autre page
        echo "Nom d'utilisateur : " . $_SESSION["nom_utilisateur"];
        echo "Email : " . $_SESSION["email"];


## 12) Qu’est-ce qu’un cookie ? Donner un exemple d’utilisation en PHP
- Un cookie est un fichier texte qu'un site web laisse sur l'ordinateur ou le mobile d'un utilisateur. Cela sert au site à sauvegarder certaines informations à son propos pour pouvoir le reconnaître et afficher ses préférences.
    Exemple : 
        // Création d'un cookie nommé "utilisateur" avec la valeur "Jean"
        setcookie("utilisateur", "Jean", time() + (86400 * 30), "/");

        // Accès à la valeur du cookie
        if(isset($_COOKIE["utilisateur"])) 
        {
            echo "Bonjour, " . $_COOKIE["utilisateur"];
        } else {
            echo "Bonjour, visiteur!";
        }

## 13) Quelle est la différence entre les instructions « require » et « include » en PHP
Ce sont des instructions qui permettent d'inserer le contenu d'un fichier dans un autre fichier.
La différence réside dans le fait que si PHP ne trouve pas le contenu ou ne peux pas le lire, avec include il continuera d'exéctuer le script, contrairement à require qui arrêtera l'exécution du script et genérera une erreur.

## 14) Comment effectuer une redirection en PHP ?
- On utilise la fonction "header()" en indiquant une nouvelle URL vers laquelle naviguer.


## 15) Définir la partie « front-end » et « back-end » d’une application
- Front-end : 
    C'est la partie "client". Tout ce qui est visible par l'utilisateur et ce avec quoi il lui est possible d'intéragir. Il à été définit par le W3C d'utiliser le HTML, CSS et JavaScript comme language de référance pour le développement de cette partie.

- Back-end : 
    La partie "Serveur". C'est la partie que ne voit pas l'utilisateur et avec laquelle il n'intéargit pas directement. Elle s'occupe de traiter et executer les opérations demandées, gérer les bases de données, etc... On utilise des languages qui y sont appropriés, tel que : PHP, Ruby, Java, C# ...

## 16) Définir le contrôle de version ? Qu’est-ce que Git ?
- Le contrôle de version est un système qui sauvegarde en ligne l'avancé des fichiers sur lesquels on travail. Il permet de garder une trace de chaque modification effectué et aux développeurs de travailler sur le même projet.

-Git est l'un de ces systèmes de contrôle de version, il est gratuit et on open source.

## 17) Qu’est-ce qu’un CMS ? Citer au moins 2 exemples
- Système de Gestion de Contenu, est une application logicielle qui met a dispostions des sites web prêt à l'emploi.
Cela permet d'introduire du texte ou des images sans avoir besoin de rédiger la moindre ligne de code, et de se concentrer sur le contenu plutôt que sur les aspects techniques de sa consctruction.
On peut y choisir un modèle de design, ajouter des pages, personnaliser certains éléments, installer des fonctionnalités comme un formulaire de contact, galerie photo, ou une boutique en ligne.


# FRONT-END

## 1) Définir HTML
- Hypertext Markup Language, est le language de balisage standard qui est utilisé pour créer et structurer tout le contenu d'une page web. A l'aide de balises, on peut y définir des élèments tels que des paragraphes, des titres, des liens, des images et des listes.

## 2) Définir CSS
- Cascading style sheets, est un language de feuille de style qui va permettre de procéder à la mise en page de notre contenu HTML. C'est la qu'on va y agencer les couleurs, la police, les effets spéciaux, ou encore la disposition de nos éléments HTML.
Le CSS est primordiale pour rendre les pages web plus attrayantes pour les utilisateurs.

## 3) Définir Javascript
- Contrairement à HTML et CSS, JavaScript est un language de programmation, utilisé en front-end. Il sert à dynamiser les pages web, en manipulant le "DOM" (Document Object Model) il permet de répondre aux actions de l'utilisateur, comme des clics de souris.

## 4) Définir JSON. Dans quel contexte ce format est-il utilisé ?
- JSON (JavaScript Object Notation) est un format léger d'échange de données. Il est uniquement utilisé pour stocker des données sour forme de clé/valeurs.
Comme des variables dans un language de programmation en quelques sorte.

## 5) Peut-on interpréter du Javascript côté serveur ? Si oui, comment ?
- Oui, avec Node.js qui fournit l'environnement et les outils nécessaires pour exécuter du JavaScript côté serveur.

## 6) Qu’est-ce qu’un sélecteur CSS ?
- Un selecteur est un moyen d'identifier un ou plusieurs éléments HTML. Il en existe plusieurs, chacun ayant ses spécificité.
On peut noter les plus courants:

    • Selecteur de type : Cible tout les éléments ayant la même balise HTML, ex '<p>'

    • Selecteur de classe : Cible tout les éléments qui ont une classe spécifique, pour l'appeler, on utilise le nom de la classe précédé d'un point.
        ex : '.maClasse', pour tous les éléments ayant 'class="maClasse"'.

    •Selecteur d'identifiant : Cible un élément unique qui a un identifiant spécifique. Il est précédé d'un dièse (#). 
        ex : '#monId' cible l'élément ayant 'id="monId"'.

## 7) Quelle balise HTML permet de créer un lien hypertexte ?
- La balise '<a>', accompagné de l'attribut 'href', qui va indiquer le chemin du lien vers lequel on va être redirigé. Cela peut être une autre page, un fichier, un emplacement sur la même page, ou à une adresse email.
A noter que l'attribut "title" permet d'ajouter une déscription au lien sous forme d'infobulle au survole avec le curseur.

## 8) Qu’est-ce qu’une requête AJAX ? 

## 9) Quel sélecteur CSS permet de sélectionner tous les éléments d’une classe spécifique ? D’un identifiant spécifique ?
- Je pense y avoir déja répondu précedement:

    • Selecteur de classe : Cible tout les éléments qui ont une classe spécifique, pour l'appeler, on utilise le nom de la classe précédé d'un point.
        ex : '.maClasse', pour tous les éléments ayant 'class="maClasse"'.

## 10) Définir le responsive design
- C'est le fait de pouvoir pouvoir afficher convenablement le contenu d'une page web sur toutes les tailles d'écrans, (moniteurs, tablettes, portables).
Pour rendre une page responsive voici les outils dont j'ai connaissance : 

    • Le header avec la balise "Meta viewport" : Elle indique au navigateur comment contrôler l'affichage (viewport) de la page pour s'adapter à la taille de   l'écran.

    • Les unités relatives : (em, rem, %, vh, vw) pour agir sur les dimensions, ils ont l'avantages de s'adapter à plusieurs facteurs :
        • Taille de l'écran
        • Résolution  
        • Paramètres de zoom de l'utilisateur
        • Taille de base du texte

    • Les media queries : Elles permettent d'appliquer des styles CSS conditionnels en fonction des caractéristiques de l'appareil, comme la largeur ou la hauteur.

## 11) Qu’est-ce que le templating ?
- Le templating consiste a dissocier la partie front-end de la logique back-end. Les templates contiennent la structure html tandis que les opérations back-end sont codés dans d'autres fichiers. Ils communiquent ensemble à l'aide de superglobales ou encore la fonction "include"

## 12) Qu’est-ce qu’une fonction anonyme en Javascript ? 
- C'est une fonction qui n'a pas de nom. C'est utile quand on à besoin d'elle qu'une seule fois ou pour une opération spécifique. Comme exécuter une action quand l'utilisateur clique sur un bouton. Elles ont la particularité de pouvoir être créée et utilisé en même temps.

## 13) Quelle méthode JavaScript est utilisée pour ajouter un élément à la fin d'un tableau ? 
C'est la méthode ".push" en indiquant le nom de le variabel contenant le tableau suivi de la valeur qu'on veut lui ajouter : 
    ex : let monTableau = [1, 2, 3];
         monTableau.push(4);
A noter que la méthode push ne marche que pour les tableau numériques.

## 14) Qu’est-ce qu’un « media query » ? 
- Un media querry est une technique utilisé en CSS pour rendre une page web responsive, en appliquant un style différent selon le type de périphérique, pour adapter l'affichage de la page selon la taille de l'écran ou la résolution, ou encore pour appliqué un style différent lors de l'impression d'une page.
## 15) Qu’est-ce qu’un pseudo élément en CSS ? 

## 16) Qu’est-ce que Bootstrap ? Donner d’autres exemples équivalent 

## 17) Quand un formulaire HTML est créé, quelles sont les 2 méthodes qui peuvent lui être associées ? Donner la différence entre ces 2 méthodes
