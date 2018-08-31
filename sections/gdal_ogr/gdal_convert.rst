Outils SIG
##########

GDAL
*****

Convertir un raster
===================

Couleur (avec perte)
--------------------

Le meilleur taux mais pas de transparence
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

La compression est à perte (JPEG) et l'espace colorimétrique est YCBCR, ce couple permet d'avoir le taux de compression le plus élevé mais ne permet pas d'utiliser une bande alpha pour la transparence.

.. code-block::  doscon

	gdal_translate -a_srs "EPSG:2154" -of Gtiff -co "TILED=YES" -co "COMPRESS=JPEG" -co "JPEG_QUALITY=75" -b 1 -b 2 -b 3 -co "PHOTOMETRIC=YCBCR" -co "INTERLEAVE=PIXEL" -co "SPARSE_OK=TRUE" "C:\fichier_source.tif" "C:\fichier_produit.tif"


Un bon taux avec transparence
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

L'ajout d'un masque est indispensable avec la compressopn JPEG

.. code-block::  doscon

	gdal_translate -a_srs "EPSG:2154" -of Gtiff -co "TILED=YES" -co "COMPRESS=JPEG" -co "JPEG_QUALITY=75" -co "PHOTOMETRIC=RGB" -co "INTERLEAVE=BAND" -co "SPARSE_OK=TRUE" -mask 4 "C:\fichier_source.tif" "C:\fichier_produit.tif"


Couleur (sans perte)
--------------------

JPEG2000
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

pour la photo source no georef

gdal_translate -co CODEC=JP2 -co YCC=YES -co REVERSIBLE=YES -co QUALITY=100

pour du geof*ref

gdal_translate -co CODEC=JP2 -co GMLJP2=YES -co GeoJP2=YES -co YCC=YES -co REVERSIBLE=YES -co QUALITY=100

Niveaux de gris
^^^^^^^^^^^^^^^^^^^

Monochrome
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
