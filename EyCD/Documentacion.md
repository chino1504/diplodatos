  # Documentación
  Este documento presenta un resumen de las operaciones y criterios utilizados para obtener el conjunto de datos final como producto del desarrollo de los trabajos prácticos entregables correspondientes a la materia Exploración y Curación de Datos.
  
  ## Criterios de exclusión de registros
  Dentro del proceso de limpieza de nuestra base de datos decidimos eliminar los siguientes valores al considerarlos outliers.
  *  Rooms mayor a 5
  *  Car mayor a 4
  *  Y Price menor que 300.000 y mayor a 2.290.050
  
  ## Características seleccionadas
  Durante el proceso de selección de características algunas no las hemos considerado ya que no aportan información relevante como es el caso de Regionname o Propertycount.
  Para el caso del dataset de airbnb solo hemos seleccionado la característica 'price' a la cual realizamos dos transformación.
  Nuestro dataset final queda entonces conformado por las siguientes características
  ### Características categóricas
  1. Type: tipo de propiedad.
  2. Suburb: barrio donde esta ubicada la vivienda.

  ### Características numéricas
  1. Rooms: número de habitaciones
  2. Car: cantidad de cocheras
  3. Price: precio de la propiedad
  4. Postcode: código postal
  5. Landsize: superficie del terreno
  6. BuildingArea: superficie construida
  7. YearBuilt: año de edificación
  8. Lattitude: 
  9. Longtitude: 
  10. airbnb_price_mean: precio diario promedio de 
     publicaciones de AirBnB para el mismo código postal.
  11. airbnb_price_max: precio diario máximo publicado en AirBnB para un determinado código postal.
  12. airbnb_record_count: cantidad de ocurrencias para ese codigo postal.

  Las características categóricas han sido codificadas utilizando DictVectorizer, el cual las combina con las característcas numéricas existentes.

  ### Transformaciones:
  1. Se normalizaron todas las variables,mediante el método StandardScaler.
  2. Se imputaron de los valores faltantes de “YearBuilt” y “BuildingArea” utilizando el método de vecinos cercanos (KNN), con n=5 vecinos. Este modelo utiliza el resto de variables para determinar los vecinos cercanos y luego calcula el valor promedio de la variable estudiada para imputar el valor faltante.

  ### Datos aumentados
  1. Se aplicó el método PCA, para reducir la
dimensionalidad del data frame procesado, previamente normalizado para evitar que alguna de las variables sea predominante.
  2. Se agregan las 3 primeras columnas obtenidas luego de aplicar PCA.