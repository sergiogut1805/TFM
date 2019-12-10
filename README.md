# TFM
Trabajo fin de máster - IA

Para compilar el modelo de detección de objetos solo hay que bajar dlib http://dlib.net/compile.html
construir todo el framewrok con cmake https://cmake.org seleccionando unicamente la carpeta samples(las demas carpetas y codigo c++ se vincularan a la estructura principal automaticamente)
Y despues reemplazar todo el codigo del ejemplo "dnn_mmod_ex.cpp" por el codigo desarrollado para el TFM que esta en este repositorio con el mismo nombre.

El programa creado para el TFM tiene las dos funciones de training y testing.
Se puede asignar el dataset usado y entrenar el modelo desde 0 o usar los archivos mmod_network.dat, mmod_sync, mmod_sync_ pegandolos en la carpeta donde se compilo Dlib(seleccionada anteriormente en Cmake) y asi poder usar la red neuronal ya entrenada para hacer testing o directaemnte para usarla en producción.

Los archivos mmod_sync, mmod_sync_ son los puntos de guardado del entrenamiento, al pegarlos donde se compilo Dlib se detectara que el entrenamiento ya termino y pasara a ejecutar "mmod_network.dat" que es el modelo serializado con lo cual se llevaria directamente a la sección de testing del programa de inventario de la infraestructura electrica.

Training data:
1100 fotografias de infraestructura electrica etiquetadas.
https://www.mediafire.com/file/7juc3v01imbwbvg/TrainingData.zip/file

¿Como usar el programa?
Despues de hacer los pasos mencionados anteriormente se debe bajar la data de entrenamiento del link, descomprimir el archivo zip y pasarle al programa el xml(datos etiquetados) como parametro.

En linux:
./dnn_mmod_ex <ruta del archivo descomprimido>
ejemplo:
./dnn_mmod_ex D:\CNN Traineds\ApoyosTFM
  
En windows(con Visual estudio 2015 o superior)
click derecho en dnn_mmod_ex.cpp ->Porpiedades->despuración y en "argumentos de comandos" poner la ruta entre comillas "D:\CNN Traineds\ApoyosTFM"


