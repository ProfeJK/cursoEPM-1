# cursoEPM-1 - Modificación "datosmaestro_epm_corr.py"

Integrantes:
- Luis Humberto Berrio
- Juan Sebastian Franco
- Cristian Camilo Hernandez Suarez

Modificaciones, actualizaciones y mejoras:

Del ejercicio de predicción en "datosmaestro_epm_corr.py" de la variable ENSA, en el siguiente código se realizaron algunas mejoras y modificaciones que permitieran completar y mejorar la predicción:

- Se hizo un análisis exploratorio de datos sencillo, con algunas graficas de tendencia e histogramas para análisis el tipo de distribución de los datos.

- Se agrego un análisis por componentes principales (PCA) que, si bien en este ejercicio no se tiene un numero alto de variables, se requería identificar el comportamiento del resto de variables y como se correlacionaban y afectaban a la variable a predecir, para de esta manera decidir en quedarnos solo con las que mayor relevancia aportaban (0.80 PCA).

- Se agrego al código un optimizador por hiperparametros usando Hyperband para la LSTM con el fin de llegar a tener algunas mejoras a los resultados de predicción.

- Inicialmente se tenían errores de predicción, y era porque no se estaban tomando los datos escalados para el modelo, sino los datos en forma numérico total, esto generaba problemas en la predicción del modelo, lo que se hace entonces es usar los datos escalados y e hace un ajuste para indexar la fecha y visualizar de forma ordenada los datos escalados. Luego de escalares se aplica "scaler.inverse_transform" para volver a los datos normales luego de haber conformado el dataframe con la predicción realizada de los datos futuros.

- Finalmente, realizan algunas modificaciones gráficas, para la representación de los datos originales y la predicción.