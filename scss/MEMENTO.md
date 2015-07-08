# N-Col(s) - V 1.0.0 (master)

Copyright: (c) 2013 - 2015 Steeve Lefebvre - <webstartup.sl at gmail.com>
License: http://www.cecill.info/licences/Licence_CeCILL-C_V1-fr.html

## Liste des mixins 

### Les conteneur 

```scss
// Permet d'ajouter une rangé de contenu de type full width
@include auto_conteneur($mar_t:0, $mar_b:0, $pad_tb:0, $pad_lr:0, $cf:null);

// Permet d'ajouter un bloc de contenu centré: margin: 0 auto;
@include box_conteneur($width:$fmk-box-width, $mar_t:0, $mar_b:0, $pad_tb:0, $pad_lr:0, $cf:null);

// Permet d'ajouter un bloc de colonnes
@include colonne_conteneur($par_nbCol:1, $elm_nbCol:1, $pad:0%, $mar_r:0%, $fin:null, $cf:null);
```

### Les média-queries 

```scss
// Permet d'ajouter des requêtes de médias
@include rmq($media, $type:max, $orientation: null){ /* Votre css */ };
```

### Les mixins utiles

```scss
// Permet d'ajouter un clearFix
@include clearfix($type:min);

// Permet d'ajouter une font a partir de Google Font 
@include typo_fonts($noms...);

// Permet d'ajouter des pavleur en px + rem
@include regle_px_rem($regle, $valeurs);

// Permet d'ajouter une règle css avec ses préfixes vendeurs 
@include regle_css($regle, $valeurs, $prefixes:null);
```

### Le css-3

```scss
// Les noms des mixins parlent d'eux mêmes.

@include text_shadow($valeurs, $couleur:$N-Cols_textShadow);
@include box_shadow($valeurs, $couleur:$N-Cols_boxShadow);
@include border_radius($valeurs);
@include transition($valeurs);
@include transform($valeurs, $type:rotate);
@include opacite($valeurs);
```

