# GLOSSAIRE-QUIZ


# GENERAL

## 1) Quel est l’environnement à installer pour exécuter un script PHP ? Citer 2 exemples de logiciels permettant ce contexte :
- Pour exécuter un script PHP, il faut un serveur web permettant à la machine d’interpréter le code PHP, exemple :
    - Laragon
    - XAMPP

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
- Structure séquentielles : 
La structure par défaut, le code s'éxècute ligne après ligne, de haut en bas.
$a = 10;
$b = 5;
$resultat = $a + $b,

- Structure conditionnelles (if/else, elseif) : 
Execute un bloc d'instruction uniquement si certaines conditions sont remplies ou non.
if(10 > 5)
{
    $info =  "10 est bien plus grand que 5";
}else
{
    $info = "10 n'est pas plus grand que 5";
}

- Srtucture itératives (boucles) :
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