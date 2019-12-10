# TFM
Trabajo fin de máster - IA

Para compilar el modelo de detección de objetos solo hay que bajar dlib http://dlib.net/compile.html
construir todo el framewrok con cmake https://cmake.org seleccionando unicamente la carpeta samples(las demas carpetas y codigo c++ se vincularan a la estructura principal automaticamente)
Y despues reemplazar todo el codigo del ejemplo "dnn_mmod_ex.cpp" por el codigo desarrollado para el TFM que esta en este repositorio con el mismo nombre.

El programa creado para el TFM tiene las dos funciones de training y testing.
Se puede asignar el dataset usado y entrenar el modelo desde 0 o usar los archivos mmod_network.dat, mmod_sync, mmod_sync_ pegandolos en la carpeta donde se compilo Dlib(seleccionada anteriormente en Cmake) y asi poder usar la red neuronal ya entrenada para hacer testing o directaemnte para usarla en producción.

Los archivos mmod_sync, mmod_sync_ son los puntos de guardado del entrenamiento, al pegarlos donde se compilo Dlib se detectara que el entrenamiento ya termino y pasara a ejecutar "mmod_network.dat" que es el modelo serializado con lo cual se llevaria directamente a la sección de testing del programa de inventario de la infraestructura electrica.
