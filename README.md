Modelado matemático para la predicción de temperatura del aire a corto plazo en el sector del Parque Bicentenario, Quito
Proyecto universitario — Métodos Numéricos  
Escuela Politécnica Nacional (EPN) · Facultad de Ingeniería de Sistemas  
Área de estudio: sector del Parque Bicentenario, parroquia La Concepción, norte de Quito, Ecuador  
Horizontes de predicción: 1, 3 y 5 horas  
Estado: proyecto en desarrollo
---
Contenido
Descripción
¿Por qué es un buen tema de investigación?
Objetivos
Área de estudio y delimitación geográfica
Fuentes de datos
Variables meteorológicas
Metodología propuesta
Fundamento matemático
Evaluación del modelo y representatividad
Tecnologías y ejecución
Resultados
Limitaciones
Equipo
Referencias
📌 Descripción
Este proyecto busca desarrollar una función matemática para estimar la temperatura del aire a 1, 3 y 5 horas en el entorno de referencia del Parque Bicentenario, ubicado en la parroquia La Concepción, al norte de Quito.
El estudio utiliza una serie meteorológica horaria del período 2018–2026 asociada a la estación histórica Quito / Mariscal Sucre de Meteostat. Según la preparación de datos del equipo, los registros faltantes se complementan con información de ERA5 y ECMWF IFS, consultada mediante Open-Meteo. El intervalo exacto de fechas, la cantidad de registros y la proporción de datos completados deberán documentarse al finalizar la depuración.
La técnica matemática central será el ajuste por mínimos cuadrados, con el que se buscará relacionar las variables meteorológicas disponibles con la temperatura futura. El propósito es evaluar la capacidad de predicción a corto plazo en la ubicación de referencia, no generar un pronóstico válido para toda la ciudad de Quito.
💡 ¿Por qué es un buen tema de investigación?
Este proyecto es relevante por cuatro razones:
Aplicación de Métodos Numéricos a un caso real. Los mínimos cuadrados permiten construir y evaluar una función matemática utilizando datos observados, en lugar de trabajar únicamente con ejemplos teóricos.
Interés local. Se estudia una zona reconocible del norte de Quito, cercana al antiguo aeropuerto Mariscal Sucre, hoy transformado en el Parque Bicentenario.
Diversidad de superficies. En el parque y sus alrededores existen espacios verdes, vías y sectores construidos. Estos ambientes pueden tener comportamientos térmicos distintos. Una investigación del Centro de Información Urbana de Quito (CIUQ, 2020) examinó diferencias espaciales de temperatura superficial en varias zonas de Quito, incluida Bicentenario. La temperatura superficial no debe confundirse con la temperatura del aire.
Oportunidad de evaluar los límites de los datos. El trabajo permite estudiar si una predicción obtenida con una serie de referencia puede extenderse a áreas próximas o si se necesitan observaciones adicionales.
La elección del sector es pertinente para investigar; esto no significa que toda la parroquia La Concepción esté ya validada como zona de predicción.
Objetivos
Objetivo general
Desarrollar y evaluar un modelo matemático basado en mínimos cuadrados para estimar la temperatura del aire a 1, 3 y 5 horas en la ubicación meteorológica de referencia del sector del Parque Bicentenario, norte de Quito.
Objetivos específicos
Reunir, revisar y organizar registros meteorológicos horarios del período 2018–2026.
Identificar datos faltantes y documentar los valores complementados mediante productos meteorológicos de Open-Meteo.
Seleccionar variables explicativas y construir funciones de predicción mediante mínimos cuadrados.
Evaluar el desempeño para cada horizonte temporal mediante métricas de error.
Examinar las condiciones geográficas y las limitaciones de representatividad espacial de la serie utilizada.
Presentar los resultados mediante tablas, gráficas y conclusiones reproducibles.
📍 Área de estudio y delimitación geográfica
Ubicación de referencia
Característica	Información
Ciudad	Quito, Ecuador
Parroquia de referencia	La Concepción
Sector central del estudio	Parque Bicentenario
Estación histórica asociada	Quito / Mariscal Sucre
Identificador Meteostat / WMO	`84071`
Identificador ICAO histórico	`SEQU`
Latitud de referencia	`-0.1500`
Longitud de referencia	`-78.4833`
Elevación registrada por Meteostat	`2811 m s. n. m.`
Mapa de consulta: Google Maps: coordenadas de referencia.
> **Aclaración:** las coordenadas identifican la referencia histórica utilizada por Meteostat; por sí solas no prueban que exista un sensor físico operativo actualmente en ese punto, ni que todas las observaciones de 2018–2026 sean mediciones directas del antiguo aeropuerto. Se debe verificar la procedencia y el tipo de cada registro.
La Empresa Pública Metropolitana de Movilidad y Obras Públicas (EPMMOP) señala que el Parque Bicentenario ocupa terrenos del antiguo aeropuerto de Quito y contiene áreas recreativas y vegetación. Un documento técnico municipal de 2025 identifica el predio en la parroquia Concepción, sector Aeropuerto, y describe un relieve mayoritariamente plano, con un declive del orden del 0,5 % al 1 % en el terreno estudiado. Esto no describe necesariamente todas las pendientes de la parroquia.
¿Cuáles son los límites del estudio?
Es importante diferenciar tres áreas:
Área	Alcance que podemos sostener actualmente
Referencia meteorológica	Serie de datos asociada a las coordenadas y al identificador de la estación histórica Mariscal Sucre.
Sector propuesto para investigar	Parque Bicentenario y sectores próximos de La Concepción. Se deben analizar elevación, relieve, vegetación y urbanización antes de proponer una extensión.
Área validada para aplicar el modelo	Todavía no delimitada: hacen falta comparaciones con observaciones independientes en otros puntos.
Los límites administrativos de La Concepción o los límites físicos del parque son útiles para describir el lugar, pero no son automáticamente límites meteorológicos. Tampoco se adopta un radio fijo alrededor de la estación.
Para evaluar posibles extensiones se propone revisar sectores cercanos con condiciones comparables y tratar con especial precaución las laderas y zonas con cambios marcados de uso del suelo. No se afirma todavía que esos sectores tengan temperaturas equivalentes.
La Organización Meteorológica Mundial (OMM/WMO) indica que la representatividad de una observación depende de la variable, el entorno, la exposición del instrumento y el uso previsto. Por eso, la delimitación se tratará como una cuestión a verificar, no como un supuesto.
Propuesta viable de delimitación
Alcance inicial defendible: predicción de temperatura del aire en la ubicación meteorológica de referencia. El entorno del Parque Bicentenario y La Concepción constituye el contexto geográfico y área candidata de evaluación, no una superficie de cobertura ya certificada.
Si se dispone de observaciones horarias simultáneas en una o más estaciones próximas, se compararán sus temperaturas para comprobar si hay evidencia que permita ampliar prudentemente el alcance. Si no hay datos suficientes, el informe mantendrá la delimitación puntual y lo explicará como limitación.
🗂️ Fuentes de datos
Meteostat — estación histórica Quito / Mariscal Sucre
Ficha de la estación: https://meteostat.net/es/station/84071
Referencia espacial: `-0.1500, -78.4833`.
Datos asociados: serie meteorológica horaria seleccionada por el equipo.
Precaución: se debe distinguir entre observaciones instrumentales, registros históricos disponibles y posibles datos derivados o interpolados. El inventario de una plataforma no verifica por sí solo que el sensor histórico continúe funcionando.
Open-Meteo — productos para complementar faltantes
Documentación: https://open-meteo.com/en/docs/historical-weather-api
Producto	Resolución espacial nominal indicada por Open-Meteo	Nota
ERA5	`0,25°`, aproximadamente `25 km`	Reanálisis atmosférico; no equivale a representar cada calle o barrio.
ECMWF IFS histórico	Aproximadamente `9 km`	Producto basado en un modelo atmosférico; su configuración puede cambiar entre versiones.
La elección de una celda de malla y los ajustes topográficos aplicados por el proveedor deben documentarse. Una resolución de 25 km no equivale a un radio de predicción confiable de 25 km; del mismo modo, los 9 km de IFS no representan la cobertura validada de nuestro modelo de mínimos cuadrados.
Trazabilidad de datos
En el conjunto final se recomienda conservar, como mínimo:
Fecha y hora, con zona horaria identificada.
Valor de cada variable y unidad de medida.
Fuente del valor: observación original, ERA5 o IFS.
Indicador de registro faltante o completado.
Reglas de limpieza, ajustes y selección de registros.
No se debe presentar un valor reconstruido mediante reanálisis como si fuera una lectura directa de un sensor.
🌡️ Variables meteorológicas
Las variables consideradas por el proyecto son:
Variable	Uso previsto
Temperatura del aire	Variable objetivo del modelo.
Humedad relativa	Posible variable explicativa.
Velocidad del viento	Posible variable explicativa.
Dirección del viento	Posible variable explicativa; requiere codificación adecuada por su carácter circular.
Presión atmosférica	Posible variable explicativa.
Nubosidad	Posible variable explicativa.
Precipitación	Posible variable explicativa.
Hora y fecha	Permiten explorar patrones horarios y temporales sin introducir datos futuros.
La lista definitiva de predictores se decidirá durante la implementación. Las unidades, nombres de columnas y disponibilidad efectiva se documentarán usando el dataset final.
🔎 Metodología propuesta
Obtención: recopilar la serie horaria de referencia y registrar su origen.
Revisión: comprobar continuidad temporal, duplicados, unidades, valores ausentes y posibles inconsistencias.
Complementación: aplicar la estrategia de completado definida por el equipo y conservar una marca del origen de cada registro.
Preparación: construir variables explicativas a partir de datos disponibles en el instante de emisión de cada predicción.
Ajuste: calcular coeficientes de una función matemática mediante mínimos cuadrados.
Predicción: obtener estimaciones de la temperatura para los horizontes de 1, 3 y 5 horas.
Evaluación: usar un período posterior al utilizado para el ajuste y comparar predicciones con valores de referencia.
Análisis espacial: discutir la representatividad de los datos y, si es posible, contrastar con estaciones próximas.
Comunicación: presentar ecuaciones, métricas, gráficas, limitaciones y conclusiones.
📐 Fundamento matemático
Como punto de partida, se plantea una regresión lineal múltiple ajustada por mínimos cuadrados. Para un horizonte `h` de 1, 3 o 5 horas:
[
\widehat{T}{t+h}=\beta{0,h}+\beta_{1,h}x_{1,t}+\beta_{2,h}x_{2,t}+\cdots+\beta_{p,h}x_{p,t}
]
Donde:
`T̂(t+h)` es la temperatura del aire estimada `h` horas después.
`x(j,t)` son variables conocidas en el instante `t`.
`β(j,h)` son los coeficientes que se deben estimar para cada horizonte.
Los coeficientes se elegirán minimizando la suma de errores cuadrados:
[
\min_{\boldsymbol{\beta}h}\sum{i=1}^{n}\left(T_{i+h}-\widehat{T}_{i+h}\right)^2
]
En notación matricial, cuando se cumplen las condiciones para su utilización:
[
\widehat{\boldsymbol{\beta}}_h=(X^\mathsf{T}X)^{-1}X^\mathsf{T}y_h
]
En el código se preferirá un procedimiento numéricamente estable (por ejemplo, factorización QR o una rutina de mínimos cuadrados) en lugar de calcular explícitamente la inversa de `XᵀX`.
> Esta es la **formulación propuesta**, no una ecuación ajustada con coeficientes ya obtenidos. La selección final de variables y los resultados se incorporarán cuando esté disponible la implementación del equipo.
📊 Evaluación del modelo y representatividad
Calidad de la predicción temporal
Para cada horizonte (1, 3 y 5 horas) se calcularán, al menos, las siguientes métricas entre el dato de referencia `Tᵢ` y el valor estimado `T̂ᵢ`:
Error absoluto medio (MAE)
[
MAE=\frac{1}{n}\sum_{i=1}^{n}|T_i-\widehat{T}_i|
]
Raíz del error cuadrático medio (RMSE)
[
RMSE=\sqrt{\frac{1}{n}\sum_{i=1}^{n}(T_i-\widehat{T}_i)^2}
]
Sesgo (predicción menos referencia)
[
Sesgo=\frac{1}{n}\sum_{i=1}^{n}(\widehat{T}_i-T_i)
]
Para reducir el riesgo de fuga de información, la evaluación debe respetar el orden temporal de los datos. También se debe registrar si los valores usados como referencia proceden de mediciones directas o de productos modelados.
Comprobación espacial sencilla (si se consiguen datos)
Comparar temperaturas observadas a la misma hora en la estación de referencia y en una estación cercana, calculando MAE, RMSE y sesgo de las diferencias entre estaciones. Esta comparación no es lo mismo que evaluar los errores de predicción del modelo.
No se adoptará un umbral universal arbitrario de aceptación. Se reportarán la magnitud de las diferencias, la cantidad de horas comparadas, las condiciones de cada estación y las limitaciones de cobertura. Una comparación con pocas estaciones tampoco valida automáticamente una parroquia completa.
💻 Tecnologías y ejecución
Herramientas previstas: Python y Jupyter Notebook. Las bibliotecas, versiones y dependencias se especificarán cuando el equipo suba el código.
Estado del repositorio
Este README documenta el planteamiento y la metodología del proyecto. La estructura definitiva de archivos y los comandos para ejecutar el análisis aún no están publicados.
Una vez incorporados los archivos, esta sección incluirá:
Estructura real de las carpetas.
Requisitos de software y dependencias.
Procedimiento para obtener o localizar el dataset.
Comandos o pasos para ejecutar el notebook o programa.
Archivos de salida y forma de reproducir las métricas y gráficas.
No se incluyen comandos ficticios para archivos que todavía no existen.
📈 Resultados
Pendientes de implementación y verificación. Aquí se incorporarán:
Ecuaciones finales y coeficientes estimados.
Cantidad de registros originales, faltantes y completados.
Comparación de valores reales y estimados para 1, 3 y 5 horas.
Métricas de error para cada horizonte.
Gráficas de la serie, predicciones y residuos.
Evidencia disponible para la delimitación geográfica.
⚠️ Limitaciones
No se ha demostrado que la estación histórica siga operando físicamente en las coordenadas indicadas.
Es necesario comprobar la procedencia y homogeneidad de la serie 2018–2026.
ERA5 e IFS son productos de modelación atmosférica, no sustitutos exactos de mediciones locales.
La vegetación, el relieve y la urbanización pueden causar diferencias térmicas entre puntos cercanos.
No existe actualmente un radio de representatividad espacial validado para este proyecto.
La predicción se refiere a la temperatura del aire y no debe confundirse con mapas satelitales de temperatura superficial.
El modelo de mínimos cuadrados será una aproximación matemática cuya utilidad debe comprobarse con datos separados de los utilizados para ajustarlo.
👥 Equipo
Escuela Politécnica Nacional — Asignatura Métodos Numéricos
Los integrantes y sus responsabilidades se incorporarán una vez confirmados por el grupo.
📚 Referencias
Organización Meteorológica Mundial (OMM/WMO). (2023). Guide to Instruments and Methods of Observation, WMO-No. 8, Vol. I. Apartado 1.1.2: Representativeness. Consultar guía.
Meteostat. Quito / Mariscal Sucre (84071): ficha de estación e inventario. Ficha oficial de la plataforma.
Open-Meteo. Historical Weather API: ERA5 y ECMWF IFS. Documentación técnica.
Empresa Pública Metropolitana de Movilidad y Obras Públicas (EPMMOP). Parque Bicentenario. Descripción municipal.
EPMMOP. (2025). Memoria de cálculo — Diseño de áreas de biorretención en el marco del proyecto de repotenciación integral del Parque Bicentenario. Documento técnico.
Cubillo, P., Orellana, D. y Maigua, P. (2020). Análisis de la distribución espacial de la temperatura superficial y la valoración de criterios que influyen en la isla de calor urbano (ICU) en el Distrito Metropolitano de Quito. Centro de Información Urbana de Quito (CIUQ). Informe.
Municipio del Distrito Metropolitano de Quito. (2020). Proyecto delimitación de barrios, parroquias urbanas y rurales: Administración Zonal Eugenio Espejo. Informe técnico.
---
Nota académica: el documento distingue los datos de referencia, los productos atmosféricos de apoyo y el área geográfica cuya representatividad queda por comprobar. La documentación se actualizará junto con el código y los resultados del equipo.
