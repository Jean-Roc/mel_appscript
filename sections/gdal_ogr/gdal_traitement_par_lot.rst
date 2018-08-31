Traitements par lot
===================

Windows DOS CMD
--------------------

Directement depuis une invite de commmande

.. code-block::  doscon

	cd \monchemin\mondossier
for %i in (*.tif) do gdal_translate -of "ENVI" %i %i.bil

Avec un fichier .bat executable

.. code-block::  doscon

	for %%i in (*.tif) do gdal_translate -of "ENVI" %%i %%i.bil
