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
Dans cette exemple, chaque couleur est une valeur, et pour utiliser chaque élément du tableau, il faut appeler sa "clé" correspondante. A noter qu'un tableau numérique commence toujours par la clé "[0]". Ainsi, pour appeler la couleur "vert" il faudra écrire : echo $couleur[1];

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
C'est la méthode ".push" en indiquant le nom de le variable contenant le tableau suivi de la valeur qu'on veut lui ajouter : 
    ex : let monTableau = [1, 2, 3];
         monTableau.push(4);
A noter que la méthode push ne marche que pour les tableau numériques.

## 14) Qu’est-ce qu’un « media query » ? 
- Un media query est une technique utilisé en CSS pour rendre une page web responsive, en appliquant un style différent selon le type de périphérique, pour adapter l'affichage de la page selon la taille de l'écran ou la résolution, ou encore pour appliqué un style différent lors de l'impression d'une page.

## 15) Qu’est-ce qu’un pseudo élément en CSS ? 
- C'est un mot clé ajouté à un selecteur CSS qui permet d'ajouter du style sans avoir besoin de créer un nouveau noeud DOM. Cela permet d'avoir une structure html plus courte et "propre".
    ex : p::before {
        content: "Note: "; // "Note" seras ajouté avant chaque paragraphe.
    }
## 16) Qu’est-ce que Bootstrap ? Donner d’autres exemples équivalent 
- Bootstrap est un framework de développement front-end, ce sont des feuilles de styles pré-établis qui permettent d'appliquer du CSS ou même du JS sans avoir besoin de les créer manuelement. Il s'ajoutent via les attributs "class" des balises HTML.

Il existent bien d'autres framework front-end, tels que : Foundation, Bulma, Semantic UI etc ...
Chacun ayant ses forces et faiblesses, ils se distinguent en termes de taille et performances ou option de personnalisation.

## 17) Quand un formulaire HTML est créé, quelles sont les 2 méthodes qui peuvent lui être associées ? Donner la différence entre ces 2 méthodes
- Quand un formulaire est crée deux méthodes peuvent lui être associés, "GET" et "POST".

    GET : Les données sont envoyées via l'URL du navigateur, ce qui a pour conséquances de : 
        - Securité : Les rend moins sécurisées pour les informations sensible telles que les mots de passe ou information de carte de crédit.
        - Taille : La quantité de données est limitée en raison de restrictions sur la longueur max d'une URL.

    POST : Les données sont envoyées dans le corps de la requête HTTP, ce qui signifie qu'elles ne sont pas directement visible par l'utilisateur, donc plus sécurisé et permettent également d'envoyer une quantité beaucoup plus grande de données.


# UX / UI 

## 1) Quelle est la différence entre UX Design et UI Design ? 
- UX Designer (User Experience Design) se concentre sur les attentes, les besoins et le comportement des utilisateurs, il conçoit ensuite les fonctionnalités et interactions pour rendre l'experience utilisateur aussi intuitive et fluide que possible.

- UI Designer (User Interface design) se concentre sur l'aspect visuel et l'esthétisme de l'application, il va agir sur la disposition général, les couleurs, polices, icônes etc ...

## 2) Qu’est-ce qu’un wireframe ?  
- Un wireframe est utilisé lors de la conception d'une interface. C'est une ébauche, un croquis, en version simplifée du résultat final attendu. Il permet de définir la structure et les fonctionnalitées essentiels du projet.

## 3) Qu’est-ce qu’un prototype ?  
- Un prototype est une version interactive de l'application. Il peut-être plus moins fidèle en terme de représentation, mais il à l'avantage de supporter les interactions et fonctionnalités demandées.

## 4) Qu’est-ce que la hiérarchie visuelle en UI Design ? 
- La hiérarchie visuelle sert à distinguer les élèments important sur lesquelles on veut attirer l'attention de l'utilisateur. Pour se faire, on agit sur la disposition des éléments, les couleurs / contrastes, les polices, leur tailles etc ...

## 5) Qu’est-ce que l’accessibilité en UX Design ?  
- Cela fait référence au fait de rendre l'application accessible à tous, notamment aux personnes en situation de déficiences ou de handicaps. Par exemple en permettant la navigation au clavier, la possibilité de modifier la taille du texte ainsi que les couleurs du site ou le contraste.

## 6) Qu’est-ce qu’une grille de mise en page ?
- Une grille de mise en page est un outil qui sert de cadre organisé en colonnes et rangées et va servir à stucturer, placer et aligner les élèments de notre page.

## 7) Qu’est-ce que la notion d’affordance en UX Design ? 
- L'affordance est le fait de donner des indices visuels à une fonctionnalité avec laquelle l'utilisateur peut agir, comme un lien qui est souligné et d'une autre couleur, ou un bouton cliquable auquel on ajoute un fond et une ombre portée pour une impression de relief.

## 8) Qu’est-ce qu’un « mobile first design » ?
- Cela veut dire que la conception du site ou de l'application est d'abord réalisé pour s'adapter aux tailles d'écran des mobiles. Mettant l'accent sur le fait de développer de manière "responsive".


# Programmation orientée objet (POO)

## 1) Donner une définition de la programmation orientée objet  
- La POO est une méthode de programmation utilisant des objets et permet des les manipuler à l'aide de fonctions qu'on appelle méthode dans ce cas précis. L'avantage est que l'on peut "instancier" un nombre indéfini d'objet à une classe, ce qui permet d'éviter la répétitions de code et de le rendre plus modulaire en rajoutant des méthodes par la suite. La fonction d'héritage permet aussi de rendre le code réutilisable en pouvant étendre les propriétés et méthodes d'une classe existante à une nouvelle tout en donnant la possibilité d'en rajouter par la suite.

## 2) Qu’est-ce qu’une classe ? Comment la déclare-t-on ? 
- Une classe sert de modèle auxquelle on renseigne les attributs et les méthodes avec lesquelles on va les manipuler pour chaque nouvel objet qu'on va y instancier.

- On déclare une classe en lui attribuant tout d'abord un nom, on lui ajoutes ensuite les "attributs" dont on a besoin, c'est à ce moment que l'on va indiquer "l'encapsulation" (public ou privé), (une bonne pratique est de renseigner le type pour chaque attribut), ensuite on met en place le constructeur, qui va servir comme un "plan" à suivre pour chaque nouvel objet qu'on va lui instancier. Puis on va écrire les méthodes qui vont constituer les "comportements" à suivre de nos objets.

## 3) Qu’est-ce qu’un objet ? 
- Un objet est une entité qui représente une des instances que va contenir une classe. C'est lui qui contient les attributs et méthodes avec lesquelles on va travailler.

## 4) Définir la notion de propriété / attribut / méthode 
- Propriété et attribut : Sont similaires, ce sont des variables que vont contenir les objets, "marque" et "modèle" pourraient être les attributs d'une classe "Voiture". C'est au moment ou l'on va instancier un nouvel objet (en suivant le modèle donné par le constructeur) qu'on va associer une valeur à chaque attribut.

- Méthode : C'est l'écriture du comportement que l'on souhaite avec les données (attributs) que l'on manipule.

Ils définissent les données et opérations que l'on peut effectuer avec chaque objet.

## 5) Qu’est-ce que la visibilité d’une propriété ou d’une méthode ? Citer les différents types de visibilité 
- La visibilité définie dans quelle partie la méthode ou la propriété est accessible dans le code, ce qui renforce la sécurité et l'encapsulation. Il y'a tois différent niveaux de visibilité : 
    • Public : Accessible à n'importe quelle partie du code, tout autre class peut intéragir avec cette méthode ou propriété.
    • Protected : Accessible seulement à l'intérieur de la class ou elle est définie ainsi que par les class qui en héritent.
    • Private : Accessible uniquement à l'intérieur de la class ou elle est définie.

## 6) Quelle est la méthode spécifique utilisée pour créer un nouvel objet à partir d’une classe ? 
- C'est grâce à la méthode "__construct" qu'on peut instancier un nouvel objet à une classe. Lorsqu'on instancie un nouvel objet, on associe en faite des valeurs aux attributs que l'on à précedemment déclaré dans le constructeur. (Une bonne pratique est de déclarer le type de chaque attribut dans le constructeur et lors des déclarations de celles-ci dans la classe)

## 7) Qu’est-ce que l’encapsulation ? 
- L'encapsulation est le fait de regrouper les méthodes et les attributs en une seule entitée (class). Elle permet de cacher (via la visibilité) les valeurs des attributs et le fonctionnement interne des méthodes pour les utilisateurs de cette classe.

## 8) Que signifie « étendre une classe » ? Quelle est le concept clé mis en œuvre ? Donner un exemple 
- C'est le fait d'utiliser le concept d'héritage. Cela permet de reprendre les méthodes et attributs d'une classe existante, tout en ayant la possibilité d'en rajouter d'avantages. 
    Ex : 
// Classe de base
class Vehicule {
    protected $marque;

    public function __construct($marque) {
        $this->marque = $marque;
    }

    public function demarrer() {
        echo "Le véhicule démarre<br>";
    }
}

// Classe héritière
class Voiture extends Vehicule {
    private $nombreDePortes;

    public function __construct($marque, $nombreDePortes) {
        parent::__construct($marque); // Appel au constructeur de la classe parente
        $this->nombreDePortes = $nombreDePortes;
    }

    public function demarrer() {
        parent::demarrer(); // Appel de la méthode demarrer de la classe parente
        echo "La voiture démarre avec " . $this->nombreDePortes . " portes<br>";
    }
}

## 9) Définir l’opérateur de résolution de portée 
- L’opérateur de résolution de portée est "::". Il sert à : 
    • Accèder a des membres statiques d'une classe (ses méthodes et propriétés statiques).
    • Dans le cas d'une classé héritée, sert à accèder à la version originale de la classe parente.
    • Accèder à des constantes de classes.

L'opérateur permet simplement d'intéragir directement avec des éléments associés à la classe elle-même, plutôt qu'à une de ses instances.

## 10) Définir une méthode / propriété statique 
- Une propriété statique est une variable partagée par toutes les instances d'une classe. Elle est utilisé pour conserver une donnée qui doit être partagé entre toutes les instances de cette classe.

- Une méthode statique peut être appelée sans instance de cette classe, elle sont appelées sur le classe elle-même.

## 11) Définir le polymorphisme en POO 
- C'est le fait d'attibuer un nouveau comportement à une méthode héritée de la classe parente. Améliorant ainsi la flexibilité du code.

## 12) Définir une méthode / classe abstraite ? 
- Une classe abstraite est une classe qui ne peut pas être instancié dirtement. Elle peut contenir à la fois des méthodes abstraites et des méthodes avec une implémentation complète.

- Une méthode abstraite est une méthode dans laquelle on ne définie aucun comportement, elle est obligatoirement associée à une classe abstraite. Elle est "vide" et les classes héritière de celle-ci doivent OBLIGATOIREMENT fournir une implémentation pour les méthodes abstraites, à moins qu'elles mêmes soient également abstraites.

## 13) Définir le chaînage de méthodes 
- Le chaînage de méthode permet d'appeler plusieurs fonctions, les unes à la suite des autres dans une seule et même instructions, chaque fonctions modifie une donnée et renvoie (à l'aide de return) le résultat, permettant à la fonctions suivante de travailler dessus.

## 14) Qu’est-ce que la méthode __toString() ? Existe-t-il d’autres méthodes « magiques » 
- La méthode "__toString()" permet de traîter un objet comme une chaïne de caractère, lui indiquant ce qu'il doit afficher. On peut ensuite directement appeler un objet avec un "echo".

- 
## 15) Qu’est-ce qu’un « autoload » ? 
- Autoload est un mécanisme qui permet de charger automatiquement les classes présentes dans les différent script, sans avoir besoin de les importer manuellement avec "require" ou "include"
    Ex : spl_autoload_register(function ($class_name) 
        {
            include $class_name . '.php';
        });

    Inclut tout les scripts dont le nom est identique à celui de la classe.
## 16) Comment appelle-t-on en français les « getters » et les « setters » ?
- En français, les termes « getters » et « setters » sont souvent traduits par « accesseurs » et « mutateurs ».
    • Accesseurs (Getters) : Ce sont des méthodes utilisées pour obtenir la valeur d'une propriété privée ou protégée d'un objet.
    • Mutateurs (Setters) : Ce sont des méthodes utilisées pour modifier la valeur d'une propriété privée ou protégée d'un objet.

## 17) Qu’est-ce que la sérialisation en PHP ?  
- La sérialisation permet de convertir un objet sous forme de chaîne de caractères à l'aide de "serialize", pouvant ainsi être sauvegardé et envoyé. Ensuite en utilisant "unserialize" nous pouvons reconstituer l'objet et accèder a ses getters / setters.


# Architecture  

## 1) Qu’est-ce que l’architecture client / serveur ? Grâce à quel type de requête peut-on interroger le serveur. Définir l’acronyme de ce type de requête. Si on ajoute un « S » à cet acronyme, expliquer la différence 
- C'est une mode de communication entre le client et le serveur, qui se fait sous forme de requête http. La requête se compose de la méthode, GET (récupère des données), POST (envoi de données), PUT (maj de données), DELETE (suppression de données); de l'URL (l'adresse de la page / ressource que le client veut obtenir); Version du protocole; Headers (Navigateur client, OS, cookies, langues user etc...) utiles pour renvoyer des données compatibles; Corps de la requête pour les méthodes POST ou PUT.

    ex : 
        POST /submit-form HTTP/1.1                              # Méthode POST, chemin de la ressource, version HTTP
        Host: www.example.com                                   # Nom du domaine du serveur à qui la requête est adressée
        Content-Type: application/x-www-form-urlencoded         # Type de contenu du corps de la requête, ici des données de formulaire encodées en URL
        Content-Length: 27                                      # Longueur du corps de la requête en octets
        User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)   # Information sur le navigateur et le système d'exploitation du client
        Cookie: sessionToken=abcde; userID=12345                # Cookies envoyés qui peuvent inclure des identifiants de session ou d'autres données pertinentes
        Connection: keep-alive                                  # Indique que la connexion doit rester ouverte pour des requêtes futures

        username=johndoe&password=123456                        # Corps de la requête contenant les données envoyées au serveur, ici les informations de connexion


## 2) Donner la définition d’un design pattern. Citer au moins 3 exemples de design pattern 
- C'est un modèle de conception qui sert à organiser le code, afin de séparer les responsabilités. Affichage, logique, connexions ...
    
    • MVC (Modèle-vue-Contrôleur): Sépare les données (modèle), l'interface utilisateur (vue) et la logique de contrôle (contrôleur) en trois composants distincts.
    • MVVM (Modèle-Vue-VueModèle) : Populaire dans le développement de logiciels avec des frameworks qui supportent le binding de données bidirectionnel
    • FLUX : Utilise un flux unidirectionnel pour gérer les données. Il se compose de quatre parties principales : Dispatchers, Stores, Views, et Actions. Les actions captent les interactions de l'utilisateur, les dispatchers envoient ces actions aux stores qui gèrent l'état de l'application, et cet état est ensuite reflété dans les vues.

## 3) Qu’est-ce que l’architecture MVC ? 
- Model-View-Controller, c'est une architecture qui pour but de séparer le code, afin de mieux l'organiser, et ce, en trois composants :

        - Model : 
            * Responsable de l'écriture / lecture dans la base de donées.
            * Informe la Vue et le Controller des modifications de l'état des données.

        - View :
            * Responsable de l'affichage des données à l'utilisateur.
            * Ne contient pas de logique métier.
        
        - Controller : 
            * Agit comme intermédiaire entre le Model et la View
            * Gère les requêtes HTTP et les intéractions utilisateur.
            * Effectue des actions spécifiques (CRUD, authentification, etc ...).
                

## 4) Quel est le rôle de chaque couche du design pattern MVC : Model, View, Controller ? 
        - Model : 
            * Responsable de l'écriture / lecture dans la base de donées.
            * Informe la Vue et le Controller des modifications de l'état des données.

        - View :
            * Responsable de l'affichage des données à l'utilisateur.
            * Ne contient pas de logique métier.
        
        - Controller : 
            * Agit comme intermédiaire entre le Model et la View
            * Gère les requêtes HTTP et les intéractions utilisateur.
            * Effectue des actions spécifiques (CRUD, authentification, etc ...).

## 5) Quels sont les avantages de l’architecture MVC ? 
- Le design pattern MVC est beaucoup utilisé dans les applications web en raison de ses nombreux avantages :

        • Sépare les responsabilités : Rend le code plus organisé et structuré, et isole les fonctionnalités, permettant de ne pas affecter le model ou le contrôleur lors de changement dans la vue.

        • Facilite la maintenance : L'ajout de nouvelles fonctionnalités devient plus simple grâce au fait qu'elles soient isolées, et les bugs plus facile à identifier.

        • Développement parallèle : Les Dévs front-end et back-end peuvent travailler indépendamment les uns des autres, réduisant les dépendances et accélèrant le développement.
        

## 6) Existe-t-il des variantes à l’architecture MVC ? 
- MVC a introduit l'idée de séparer les responsabilités en trois couches principales et à en effet, inspiré d'autres variantes, notamment pour répondre aux besoins de développement qui ont évolué : 

        • MVP (Model-View-Presenter): Cette architecture est une évolution de MVC, principalement utilisée dans les applications où la logique de présentation est complexe. Ici, le présentateur remplace le Contrôleur et est plus lié à la vue, il intéragit directement avec la Vue.

        • MVVM (Model-View-ViewModel) : Populaire dans les environnement ou le data-binding (liaison de données) est utilisé. Le ViewModel sert d'intermédiaire entre la Vue et le Modèle, mais contrairement au Contrôleur, il contient une logique de présentation plus poussée.

        • HMVC (Hierarchical MVC) : Une variante de MVC qui structure l'application en sous-MVC. Chaque section de l'application peut avoir son propre MVC, permettant une organisation plus modulaire pour les applications les plus complexex.

## 7) Qu’est-ce qu’une API ? Définir l’architecture REST
- Une API (Application Programming Interface) est un mécanisme qui permet à deux logiciels de communiquer entre eux, permettant à une application d'utiliser les fonctionnalités d'une autre sans connaître son fonctionnement interne.

- REST (Representational State Transfer) est une architecture d'API utilisé pour la communication entre un client (application) et un serveur via le protocole HTTP.

# Modélisation / Base de données

## 1) Qu’est-ce que la modélisation de données ? Définir la méthode Merise
- La modélisation de données est un processus qui permet de structurer et organiser les données pour faciliter leur compréhension et leur utilisation, sous forme de schéma notamment.

- La méthode MERISE guide la création de schémas visuels et conceptuels pour modéliser une base de données, partant d'une représentation abstraite MCD (Modèle Conceptuel des Données) vers une conception logique MLD (Modèle Logique des Données).

## 2) Quelles sont les 3 étapes principales de la méthode Merise ?
        - a. Analyse, conception et réalisation
        - b. Planification, exécution et contrôle
        - c. Création, modification et suppression

## 3) Qu’est-ce qu’un modèle conceptuel de données (MCD) en Merise ?
- Un MCD est une représentation graphique qui reprend les données nécessaires au fonctionnement, sans se soucier de l'aspect technique. L'objectif est de structuter les données et d'y établir les relations entre elles.

## 4) Qu’est-ce qu’un modèle logique de données (MLD) en Merise ?
- Un MLD est une étape intermédiaire entre le MCD et la création de la base de données. Il offre un aspect plus technique et structuré que le MCD.

## 5) Donner la définition des mots suivants :
        - a. Entité
            • Une Entité représente un objet à part entière que l'on veut modéliser.

        - b. Relation
            • Une relation est un lien qui existe entre deux ou plusieurts entités, qui permet de modéliser comment elles intéragissent entre elles, et d'y établir leur cardinalités.

        - c. Cardinalité
            • La cardinalité définit le nombre minimum et maximum de fois ou deux entités peuvent intéragir entre elles. Elle s'éxprime de manière quantitative.

        - d. Clé primaire / clé étrangère
            • Une clé primaire est un attribut qui permet d'identifier de manière unique les enregistrements d'une base de données.
            • Une clé étrangère est un attribut qui reprend la clé primaire d'une autre table et permet d'établir une relations entre elles.

## 6) Que devient une relation de type « Many To Many » dans le modèle logique de données ?
- Une relation Many-to-Many ne peux pas être modéliser directement, on passe par une table intérmédiaire pour gérer la relation Many-to-Many, qui contient des clés étrangères qui relient les deux entités d'origine.

## 7) Qu’est-ce qu’une base de données ?
- Une base de données est un ensemble structuré et organisé de données qui sont stockées, de manière à pouvoir être facilement consultées et modifiées par divers logiciels.

## 8) Définir les notions suivantes :
        - a. SQL
            • (Structured Query Language) est un language standardisé utilisé pour intéragir avec les bases de données, afin d'effectuer des opérations CRUD (Create, Read, Update, Delete) aux moyens de requêtes.

        - b. MySQL
            • MySQL est un SGBD (Système de Gestion de Base de Données) qui utilise le langage SQL. C'est l'un des SGBD les plus populaires.

        - c. SGBD (donner 2 exemples de SGBD)
            • (Système de Gestion de Base de Données), il y'a donc MySQL, PostgreSQL, un autre SGBD open-source.

## 9) Dans une base de données, les données sont stockées dans des ???  Celles-ci sont constituées de lignes appelées ??? et de colonnes appelées ???
- Dans une base de données, les données sont stockées dans **TABLES**. Celles-ci sont constituées de lignes appelées **ENREGISTREMENTS** et de colonnes appelées **ATTRIBUTS**.

## 10) Quelle est la différence entre une base de données relationnelle et non relationnelle ?
- Les différences résident en termes de langage de requêtes, structure des données, et scalabilité (Capacité d'un système à gérer une augmentation du volume du travail).

    - Une base de données relationnelle utilise : 
        • Le langage SQL (Structured Query Language) pour les opérations CRUD.
        • Les données sont stockées dans des tables, organisées en lignes et colonnes.
        • Scalabilité verticale, pour gérer plus de données, on boost les performances du serveur (plus de CPU, RAM etc ...)

    - Une base de données non-relationnelle utilise : 
        • N'utilise pas SQL. Chaque SGBD NoSQL à son propre langage pour manipuler les données.
        • Les données peuvent être stockées sous différentes formes, dcuments (JSON), clé-valeur, colonnes ou graphes. 
        • Scalabilité horizontale, on ajoute plusieurs serveurs gérer plus de données.

## 11) Qu’est-ce qu’une jointure dans une base de données ? En existe-t-il plusieurs ? Si oui lesquelles ?

## 12) A quoi sert une vue dans une base de données ?

## 13) Qu’est-ce que l’intégrité référentielle dans une base de données ?

## 14) Quelles sont les fonctions d’agrégation en SQL ?

## 15) Qu’est ce qu’un CRUD dans le contexte d’une base de données ?

## 16) Quelles sont les clauses qui permettent de :
       - a. Insérer un nouvel enregistrement dans une table
       - b. Modifier un enregistrement dans une table
       - c. Supprimer un enregistrement dans une table
       - d. Supprimer la base de données
       - e. Filtrer les résultats d’une requête SQL
       - f. Trier les résultats d’une requête SELECT
       - g. Regrouper les résultats d'une requête SELECT en fonction d'une colonne spécifique
       - h. Concaténer 2 chaînes de caractères

## 17) Comment se connecter à une base de données en PHP ? Quelle est la classe native utilisée ?


# Symfony

## 1) Qu’est-ce que Symfony ?

## 2) Sur quel langage de programmation et design pattern repose Symfony ?

## 3) Quelle est la dernière version en date de Symfony ?

## 4) Qu’est-ce qu’un bundle ?

## 5) Quel est le moteur de template utilisé par défaut dans Symfony ?

## 6) Qu’est-ce qu’un ORM ? Quel est son utilité et comment s’appelle-t-il au sein de Symfony ?

## 7) Qu’est-ce que l’injection de dépendances ? Quel est l’outil utilisé dans ce contexte et quel fichier contient l’intégralité des dépendances du projet ?

## 8) Que permet le bundle Maker au sein de Symfony ?

## 9) Quel est le langage de requêtage exploité au sein d’un projet Symfony ?

## 10) Quel est le composant qui garantit l’authentification et l’autorisation des utilisateurs ?


# Sécurité

## 1) Qu’est-ce que l’injection SQL ? Comment s’en prémunir ?

## 2) Qu’est-ce que la faille XSS ? Comment s’en prémunir ?

## 3) Qu’est-ce que la faille CSRF ? Comment s’en prémunir ?

## 4) Définir l’attaque par force brute et l’attaque par dictionnaire

## 5) Existe-t-il d’autres failles de sécurité ? Citer celles-ci et expliquer simplement leur comportement

## 6) A quoi servent l’authentification et l’autorisation dans un contexte d’application web ?

## 7) Définir la notion de hachage d’un mot de passe et citer des algorithmes de hachage

## 8) Qu’est-ce qu’une politique de mots de passe forts ?

## 9) Qu’est-ce que l’hameçonnage ?

## 10) Définir la « validation des entrées »


# RGPD

## 1) Qu’est-ce que le RGPD ?

## 2) Quel est son objectif principal ?

## 3) Quelle est la date d’entrée en vigueur du RGPD ?

## 4) Quelles sont les sanctions possibles en cas de non-respect du RGPD ?

## 5) En France, quel est l’autorité administrative qui s’occupe de faire appliquer le RGPD ?

## 6) Quel est le consentement valide selon le RPGD ?

## 7) Qu’est-ce qu’une politique de confidentialité ?

## 8) Quelle est la durée de conservation maximale des données personnelles selon le RGPD ?

## 9) Quels sont les droits des utilisateurs selon le RGPD ?

## 10) Qu’est-ce que le principe de minimisation des données selon le RGPD ?


# SEO

## 1) Qu’est-ce que le SEO ?

## 2) Quel est l’objectif principal du SEO ?

## 3) Existe-t-il plusieurs types de référencement ? Lesquels ?

## 4) Qu’est-ce que la densité de mots-clés en SEO ?

## 5) Qu’est-ce qu’une balise « alt » ?

## 6) Qu’est-ce que la balise « meta description » ?

## 7) Qu’est-ce que le « nofollow » en SEO ?

## 8) Quelle est l'importance du contenu de qualité pour le référencement d'un site web ?

## 9) Pourquoi est-il important d'utiliser des balises de titre (h1, h2, h3, etc.) de manière structurée ?

## 10) Quelle est la recommandation pour les URL d'un site web bien référencé ?

## 11) Qu'est-ce que le maillage interne et pourquoi est-il important pour le référencement ?

## 12) Qu'est-ce que l'optimisation des images pour le référencement ?

## 13) Qu'est-ce qu'un plan de site (sitemap) et pourquoi est-il important pour le référencement ?


# Gestion de projets / DevOps

## 1) Qu’est-ce que la gestion de projet ?

## 2) Qu’est-ce qu’une méthode Agile de gestion de projet ?

## 3) Expliquer la méthode MoSCoW en quelques lignes et citer ses avantages

## 4) A quoi sert la méthodologie MVP ? Citer les caractéristiques clés

## 5) Qu’est-ce que la planification itérative ?

## 6) Citer 3 méthodes Agiles dans le cadre d’un projet informatique

## 7) Qu’est-ce qu’une réunion de revue de projet ?

## 8) Qu’est-ce qu’un livrable dans un projet ?

## 9) Quels sont les 3 piliers SCRUM ? Définir chacun d’entre eux

## 10) Qu’est-ce que le DevOps et quel est son objectif principal ?

## 11) Qu’est-ce que l’intégration continue ?

## 12) Qu’est-ce que Docker ? Et en quoi est-il utile dans le cadre du DevOps ?

## 13) Qu’est-ce qu’un test unitaire ?

## 14) Quelle est l'unité de code testée lors d'un test unitaire ?

## 15) Quelles sont les caractéristiques d'un bon test unitaire ?

## 16) Qu'est-ce qu'une assertion dans un test unitaire ?


# English

## 1) What does JavaScript enable you to do on a website ?
        - a. Add interactive behavior and dynamic content
        - b. Define the layout and design of web pages
        - c. Handle server-side operations

## 2) Which programming language is primarily used for server-side web development ?
        - a. PHP
        - b. JavaScript
        - c. HTML

## 3) What is the purpose of a web browser ?
        - a. To render and display web pages
        - b. To execute serve-side code
        - c. To manage databases

## 4) What is the difference between GET and POST methods in HTTP ?
        - a. GET retrieves data from a server, while POST submits data to a server
        - b. GET submits data to a server, while POST retrieves data from a server
        - c. GET and POST methods are interchangeable

## 5) What is the purpose of version control systems (e.g., Git) in web development ?
        - a. To track changes and manage collaborative development
        - b. To optimize website loading speed
        - c. To handle server-side scripting

## 6) What is the purpose of a framework in web development ?
        - a. To provide a structured environment for building web applications
        - b. To handle network protocols and data transfer
        - c. To create visual designs and layouts for websites

## 7) What does NoSQL stand for ?
        - a. Not Only SQL
        - b. Non-Structured Query Language
        - c. New Object-Oriented Language

## 8) Which of the following is a characteristic of NoSQL databases ?
        - a. Strict schema enforcement
        - b. Support for complex transactions
        - c. Scalability and flexible data models

