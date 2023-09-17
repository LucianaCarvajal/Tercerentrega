# Objetivo general:
Desarrollar un algoritmo de recomendación por similitud entre productos audiovisuales, utilizando elementos en comunes tales como el género, la trama, el elenco y el director para las películas de diferentes plataformas. 
Para se cuenta con conjuntos de datos de películas disponibles de las siguientes plataformas: Amazon Prime, HBO Max, DisneyPlus y Netflix.
# Objetivo específico: 
Caracterizar el dataset de títulos de películas y programas de televisión disponibles en la plataforma Amazon Prime:
qué columnas tiene y qué información aporta cada una
Determinar si hay valores faltantes y cómo proceder
Explorar y visualizar:
¿Cuántas películas y cuántas series hay en la plataforma?
¿Cuántas hay por año?
¿Cuántas hay para cada tipo de público?
# Glosario: 
El diccionario que se presenta, es acorde a la etapa EDA-INICIAL, por lo que es posible que en etapas posteriores sufra modificaciones, por lo tanto se lo invita al lector a que no deje de consultartlo en el futuro. 
- show_id: Identificador único de cada serie o película. Posterioremente se denominará "id".
- type: Indica si se trata de una serie ("TV Show") o de una película ("Movie"). Posteriormente se denominará "tipo".
- title: Corresponde al nombre de la serie o película. Posteriormente se denominará "titulo"
- director: Hace referencia a la persona encargada de dirigir la película o serie.
- cast: Enlista a los actores que forman parte de la película, El listado incluye los nombres de los actores separados por comas. Posteriormente se denominará "elenco".
- country: Lugar (país) de producción. Posteriormente se denominará "pais".
- date_added: fecha en que se agregó a la plataforma. Posteriormente se denominará "fecha_agregado".
- release_year: Representa el año de producción. Posterioemente de denominará "anio".
- rating: Clasifica a las producciones de acuerdo a la edad mínima o público recomendado.Cabe aclarar que según los medios o los países, el significado puede varias, por lo que a continuación se detalla cada código. Posteriormente de denominará "calificacion". 
                                             7+: No recomendada para menores de 7 años.
                                             13+: No recomendada para menores de 13 años.
                                             16+: No recomendada para menores de 16 años.
                                             18+: No recomendada para menores de 18 años.
                                             ALL: Apropiado para todas las edades.         
                                             R: Restringido y para mayores de 18 años.     
                                             PG-13: Guía paternal estricta, algunos materiales pueden ser inapropiados para niños menores de 13 años.      
                                             PG: Guía paternal sugerida (con supervisión de los padres), algunos materiales pueden no ser adecuados para niños.
                                             NR:(Sin clasificación). Películas que no fueron clasificadas por el comité (las causas varían, aunque por lo general sucede con producciones que no llegaron a salas comerciales en su momento o que se estrenaron previo a la existencia de los sistemas de clasificación).
                                             TV-14: Para mayores de 14 años. Se requiere la compañía de padres. 
                                             TV-PG: Guía paternal extricta.                                              
                                             TV-NR:(Sin clasificación). Películas que no fueron clasificadas por el comité (las causas varían, aunque por lo general sucede con producciones que no llegaron a salas comerciales en su momento o que se estrenaron previo a la existencia de los sistemas de clasificación).
                                             G: Todas las edades, aptas para todo público.
                                             TV-G: Se refiere a programación apta para todas las edades. 
                                             TV-MA: Para programas dirigidos para adultos, por lo que podrían ser inapropiados para menores de 17 años
                                             TV-Y: Programación dirigida a un público muy joven, de edades entre dos a seis años.
                                             TV-Y7: Producciones dirigidas a niños de siete años en adelante. En algunos casos se asigna al final el descriptivo FV (TV-Y7 FV) para aludir a contenido de violencia de fantasía.
                                             UNRATED: Película no clasificada o es una versión sin editar de una película ya calificada. Las versiones sin cortes o extendidas de películas que tienen esta calificación, también contienen avisos que advierten que esa versión de la película contiene imágenes que difieren del original y podrían no ser aptas para menores.
                                             NC-17: No se admiten niños menores de 17 años.
                                             AGES_18_: Para mayores de 18 años.
                                             NOT_RATE: Película no clasificada o es una versión sin editar de una película ya calificada. Las versiones sin cortes o extendidas de películas que tienen esta calificación, también contienen avisos que advierten que esa versión de la película contiene imágenes que difieren del original y podrían no ser aptas para menores.
                                             AGES_16_: Para mayores de 16 años. 
                                             16: Para mayores de 16 años.
                                             ALL_AGES: Esta clasificación es para programación que es apropiada para todas las edades.   
- duration: Tiempo desde el comienzo y el fin de la película o serie. La unidad de medida del tiempo será en minutos para las películas y temporadas para series. Posteriormente se denominará "duracion".
- listed_in: Géneros y denominación de la clasificación según la plataforma en la que aparece listada la serie o película. Posteriormente se denominará "listado_en".
- description: Breve explicación en idioma ingles de la trama de la serie o película. Posteriormente se denominará "descripción".
- plataforma: Indica a que plataforma pertenece la película.

  # Reseña:
  En esta etapa se llevan a cabo tareas iniciales exploratorias. Se decide comenzar con un sólo dataset: correspondiente a la plataforma amazon. Se verifican cantidad de columnas y filas, tipo de estructura de datos de dataframe. Se verifica si hay filas duplicadas, tipos de columnas, primeras y ultimas 10 filas del dataset. Se indaga sobre estadísticas de la columna:release_year.
  Se explora y visualizan los datos faltantes. Posteriormente se estudian las peliculas y los TV show (series) de forma separada para generar gráficos de visualización.
  Se realizan cambios en la columna duration para unificar la unidad de medida.
  En el dataset amazon, se observa que hay columnas con datos que están separados por comas, que requerirán un tratameinto especial.
  Se importan los demás dataset, se crea la columna plataforma y concatenan los mismos. 
  Finalmente, del análisis exploratorio de los datos inicial, se consluye con que los datasets elegidos serán:  Amazon Prime,  DisneyPlus y Netflix. Se excluirá a Hulu, ya que no es una plataforma de uso en Argentina. Por otra parte, se determina que se tomarán como objeto de estudio en este análisis sólo a las películas, excluyéndose a las series. 
  
  
