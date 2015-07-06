# N-Cols
Mini framework scss basé sur un système Multi-grille allant de 1 à n colonnes.

## A propos
À mi-chemin entre une librairie et un framework, N-Col(s) est surtout un cadre de travail SCSS simple constitué d’une structure de fichiers et de dossiers de code simplifiant la gestion du design ainsi que la construction d’architectures adaptatives complexes en css.

N-Col(s) a pour but d'offrir aux web-designer un cadre de travail structuré ou la création de code métier est prioritère sur l'adaptation.

Malgré cela, N-Col(s) ne fournit, pour le moment, pas tout ce dont vous avez besoin pour la réalisation complète d’un site, il dispose d'une base typographique minimaliste, un système Multi-grilles, des médias-queries, des mixins css-3 et quelques autres mixins dédiées au design (Fonts, Patterns, liens…) permettant de gagner pas mal de temps tout en simplifiant la gestion des modifications.

## Code Example

Pour structurer le contenu N-Col(s) dispose de trois mixins, les valeurs que vous pouvez voir sont celle définies par défaut. 
Ces mixins seront utilisées sur tous les blocs servant à la mise en forme de la structure du site.

```scss
.exemple{
    // Permet de créer des rangées de contenus
    @include auto-conteneur($mar_t:15px, $mar_b:33px, $pad_tb:25px, $pad_lr:25px, $cf:null); 
}
.exemple{
    // Permet de créer des blocs de contenus a largueur fixe et centrés
    @include box-conteneur($width:1200px, $mar_t:50px, $mar_b:0, $pad_tb:0, $pad_lr:0, $cf:null);
}
.exemple{
    // Permet de fractionner un bloc en colonnes
    @include colonne-conteneur($par_nbCol:1, $elm_nbCol:1, $pad:0%, $mar_r:0%, $fin:null, $cf:null);
}
```

## Installation
Il nécessite d’avoir préalablement installé pré-processeur SASS: au cas où, [voici le Guide d’installation de Sass] (http://sass-lang.com/install).

Partant du principe que tout est bon, ouvrez votre serveur local et décompressez l'archive d'N-col(s), il contient tous ce qu’il fait pour bien commencer les tests.

L code est en place, il vous faut lancer Sass, ouvrez le dossier: sass/config/ et double-cliquez sur le fichier .bat, un invite de commande s’ouvre et affiche: --- Sass is watching for changes. Press Ctrl-C to stop ---

La machine est en route, y-a plus qu’a…

## Premier tests
Pour commencer, nous allons partir d’un modèle html simple, celui ci-dessous, il est a coller dans index.html situé a la racine de notre site de tests.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
        <title>Titre du site</title>
        
        <link rel="stylesheet" href="style.css">
        <!--[if lt IE 9]>
            <link rel="stylesheet" href="css/ie.css" type="text/css" media="screen"/>
            <script src="//html5shiv.googlecode.com/svn/trunk/html5.js"></script>
        <![endif]-->
    </head>
    <body>
        <!-- HEADER -->
        <header>
            <div id="header">
                <h1>Mon header</h1>
            </div>
        </header>
        <!-- MAIN -->
        <main>
            <div id="main">
                <!-- ARTICLE -->
                <article>
                    <h1>Mon article</h1>
                </article>
                <!-- ASIDE -->
                <aside>
                    <h3>Mon aside</h3>
                </aside>
            </div>
        </main>
        <!-- FOOTER -->
        <footer>
            <div id="footer">
                <h4>Mon footer</h4>
            </div>
        </footer>
    </body>
</html>
```

Ajoutez le code suivant dans votre fichier _theme.scss

```scss
// GENERALE
body{
    background-image: url("libs/images/fond.png");
}
// HEADER
header{
    @include auto-conteneur();
    background-color: white;
    #header{
        @include box-conteneur(1025px);
    }
}
// MAIN
main{
    @include auto-conteneur();
    #main{
        @include box-conteneur(1025px, $cf:cf);
        // ARTICLE
        article{
            @include colonne-conteneur(10, 7);
        }
        // ASIDE
        aside{
            @include colonne-conteneur(10, 3);
        }
    }
}
// FOOTER
footer{
    @include auto-conteneur();
    background-color: white;
    #footer{
        @include box-conteneur(1025px);
    }
}
```

Au finale, le css compilé sera celui ci-dessous

```css
body { background-image: url("libs/images/fond.png"); }

header { margin: 0 0 0 0; padding: 0 0; background-color: white; }
header #header { width: 1025px; position: relative; left: 50%; margin: 0 auto 0 -512.5px; padding: 0 0; }

main { margin: 0 0 0 0; padding: 0 0; }
main #main { width: 1025px; position: relative; left: 50%; margin: 0 auto 0 -512.5px; padding: 0 0; *zoom: 1; overflow: hidden; }
main #main:before, main #main:after { content: ''; display: table; }
main #main:after { clear: both; }
main #main article { width: 70%; padding: 0%; margin: 0 0% 0 0; float: left; }
main #main aside { width: 30%; padding: 0%; margin: 0 0% 0 0; float: left; }

footer { margin: 0 0 0 0; padding: 0 0; background-color: white; }
footer #footer { width: 1025px; position: relative; left: 50%; margin: 0 auto 0 -512.5px; padding: 0 0; }
```

## Crédits

 -[SASS](http://sass-lang.com/)
 -[Eric Meyer](http://meyerweb.com/eric/tools/css/reset/)
 -[Google Fonts](https://www.google.com/fonts/)
 -[Font Awesome] (http://fortawesome.github.io/)
 -[Twemoji Awesome](http://ellekasai.github.io/twemoji-awesome/)

## License

CONTRAT DE LICENCE DE LOGICIEL LIBRE CeCILL-C : Voir LICENSE.md