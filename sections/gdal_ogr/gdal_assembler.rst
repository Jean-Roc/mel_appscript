# Assembler plusieurs images
===================

Le format VRT
-------------

Il s'agit d'un fichier XML référencant une série de raster et leurs métadonnées, il peut être appelé directement de manière transparente

à partir d'une liste de fichier

.. code-block::  doscon

	gdalbuildvrt -srcnodata "255,255,255" -a_srs "EPSG:2154" -input_file_list C:\data\raster\ortho_2016\merge.txt C:\data\raster\ortho_2016\test\ortho.vrt

tous les fichiers d'un repértoire ayant la même extension

.. code-block::  doscon

	gdalbuildvrt -srcnodata "254,254,254" -a_srs "EPSG:2154" C:\data\raster\ortho_2016\test\test.vrt C:\data\raster\ortho_2016\test\*.tif

gdal merge.py
-------------

principe de la pile

.. code-block::  doscon

	gdal_merge -of Gtiff -co BIGTIFF=YES -co "COMPRESS=DEFLATE" -co "INTERLEAVE=BAND" -co "TILED=YES" -co NUM_THREADS=4 --config GDAL_CACHEMAX 8192 -o ortho_merged.tif --optfile tiff_list.txt
