=== N-Col(s) - V 1.0.0 (master) === 

Copyright: (c) 2013 - 2015 Steeve Lefebvre - <webstartup.sl at gmail.com>
License: http://www.cecill.info/licences/Licence_CeCILL-C_V1-fr.html


=== Liste des mixins ===  

--------------------------------------------------------------------------------
* Les conteneur 
---> @include auto_conteneur($mar_t:0, $mar_b:0, $pad_tb:0, $pad_lr:0, $cf:null);
---> @include box_conteneur($width:$fmk-box-width, $mar_t:0, $mar_b:0, $pad_tb:0, $pad_lr:0, $cf:null);
---> @include colonne_conteneur($par_nbCol:1, $elm_nbCol:1, $pad:0%, $mar_r:0%, $fin:null, $cf:null);


--------------------------------------------------------------------------------
* Les média-queries 
---> @include rmq($media, $type:max, $orientation: null){ /* Votre css */ };


--------------------------------------------------------------------------------
* Les mixins utiles
---> @include clearfix($type:min);
---> @include typo_fonts($noms...);
---> @include regle_px_rem($regle, $valeurs);
---> @include regle_css($regle, $valeurs, $prefixes:null);


--------------------------------------------------------------------------------
* Le css-3
---> @include border_radius($valeurs);
---> @include text_shadow($valeurs);
---> @include box_shadow($valeurs);
---> @include transition($valeurs);
---> @include transform($valeurs, $type:rotate);
---> @include opacite($valeurs);

