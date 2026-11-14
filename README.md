
# Modelado matemático para la predicción de temperatura del aire a corto plazo en el sector del Parque Bicentenario, Quito

**Escuela Politécnica Nacional (EPN)** · **Métodos Numéricos**  
**Área de estudio:** entorno del Parque Bicentenario, parroquia La Concepción, Quito, Ecuador  
**Horizontes de predicción:** 1, 3 y 5 horas  
**Método principal:** mínimos cuadrados  
**Estado:** proyecto en desarrollo  
**Actualización documental:** noviembre de 2026

> **Alcance científico:** El proyecto busca estimar la temperatura del aire asociada a una ubicación meteorológica de referencia. No se ha demostrado que sus predicciones sean válidas para toda La Concepción ni para todo Quito. La delimitación espacial ampliada depende de una validación adicional.

---

## 1. Resumen

El proyecto plantea construir y evaluar funciones matemáticas de predicción de temperatura del aire a 1, 3 y 5 horas mediante ajuste por mínimos cuadrados.

La base de trabajo descrita por el equipo corresponde a registros horarios del período **2018–2026**, asociados a la estación histórica **Quito / Mariscal Sucre** de Meteostat.

Para tratar valores faltantes, el equipo contempla datos de los productos **ERA5** y **ECMWF IFS**, consultados mediante Open-Meteo.

La fecha inicial y final exacta, el número de registros y el origen de cada observación deben verificarse contra los archivos finales.

El estudio se sitúa en el entorno del Parque Bicentenario, en el norte de Quito.

Se investigará la posibilidad de extender la interpretación del modelo a sectores próximos, sin confundir proximidad geográfica con equivalencia meteorológica.

---

## 2. Problema y justificación

Una serie de temperatura varía a lo largo del día y responde a condiciones meteorológicas cambiantes.

El problema numérico consiste en determinar si una función ajustada con datos anteriores permite estimar la temperatura futura con errores cuantificables.

### 2.1 ¿Por qué es pertinente este tema?

**1. Aplicación directa de Métodos Numéricos**

Se formula un problema de ajuste, se estiman coeficientes mediante mínimos cuadrados y se analiza el error de predicción.

**2. Disponibilidad de series horarias**

Permite trabajar con observaciones ordenadas temporalmente y evaluar tres horizontes distintos.

**3. Interés local**

El antiguo aeropuerto Mariscal Sucre constituye una referencia meteorológica histórica identificable. Actualmente, el terreno forma parte del entorno del Parque Bicentenario [1, 2].

**4. Relevancia del microclima urbano**

En Quito se han documentado contrastes térmicos asociados con vegetación, materiales y morfología urbana [3].

Por ello, el alcance espacial del modelo es una pregunta de investigación y no una suposición.

**5. Resultados verificables**

MAE, RMSE y sesgo permiten evaluar el desempeño en datos no utilizados durante el ajuste.

### 2.2 Pregunta de investigación

¿Qué capacidad tiene un modelo por mínimos cuadrados para estimar la temperatura del aire a 1, 3 y 5 horas en la ubicación meteorológica de referencia, y qué evidencia sería necesaria para extender esa interpretación a áreas cercanas?

---

## 3. Objetivos

### 3.1 Objetivo general

Construir y evaluar un modelo matemático de predicción de la temperatura del aire a 1, 3 y 5 horas, mediante mínimos cuadrados, para la ubicación meteorológica de referencia del sector del Parque Bicentenario.

### 3.2 Objetivos específicos

- Revisar la procedencia, continuidad temporal, unidades y valores faltantes de los registros horarios.
- Identificar los datos originales y los complementados con productos atmosféricos.
- Seleccionar variables predictoras disponibles al momento de emitir cada predicción.
- Ajustar los coeficientes de modelos para los tres horizontes temporales.
- Evaluar el error en un período cronológicamente posterior al de entrenamiento.
- Examinar la representatividad espacial y explicitar el límite territorial sustentado por los datos.

---

## 4. Ubicación y delimitación geográfica

### 4.1 Referencia meteorológica

| Elemento | Dato |
|---|---|
| Estación histórica de referencia | Quito / Mariscal Sucre |
| Identificador Meteostat / WMO | 84071 |
| Identificador ICAO histórico | SEQU |
| Latitud de referencia | -0.1500 |
| Longitud de referencia | -78.4833 |
| Elevación indicada en la ficha | 2811 m s. n. m. |
| Entorno de interés | Parque Bicentenario y La Concepción, Quito |

**Fuente de metadatos:** Meteostat [1].

[Consultar coordenada de referencia en Google Maps](https://www.google.com/maps?q=-0.1500,-78.4833)

**Precaución:** La ficha de una estación histórica y su inventario de datos no prueban la operación actual de un sensor físico en esas coordenadas.

El antiguo aeropuerto dejó de funcionar en ese emplazamiento en 2013 [2].

El equipo debe revisar la procedencia específica de los registros recientes antes de describirlos como mediciones *in situ*.

### 4.2 ¿Por qué estudiar La Concepción?

La Concepción ofrece un contexto pertinente porque incluye el entorno del Parque Bicentenario, desarrollado sobre parte del antiguo aeropuerto [2, 4].

El parque reúne superficies abiertas y vegetación, mientras sus alrededores incluyen edificaciones y vías urbanas.

Hacia sectores occidentales cercanos se observan cambios de relieve que deben comprobarse con un modelo digital de elevaciones antes de delimitar unidades comparables.

La literatura de **zonas climáticas locales (LCZ)** establece que la estructura urbana, la cobertura del suelo y las actividades humanas son relevantes para comparar temperaturas entre lugares [5].

Un trabajo realizado en Quito analizó islas de calor y diferencias térmicas entre ámbitos arbolados y no arbolados [3].

Esto justifica investigar la heterogeneidad térmica del sector, pero no demuestra que todos los puntos de La Concepción tengan temperaturas equivalentes.

### 4.3 Áreas que no deben confundirse

| Categoría | Interpretación y situación actual |
|---|---|
| Ubicación con datos de referencia | Coordenada histórica asociada a Meteostat; debe auditarse la procedencia de cada serie. |
| Área candidata de estudio | Parque Bicentenario y sectores próximos de La Concepción, que se examinarán según elevación, relieve y cobertura del suelo. |
| Área de aplicación espacial validada | No delimitada todavía: faltan mediciones independientes y una comparación cuantitativa. |

**Decisión metodológica:**

El modelo se presentará inicialmente como una estimación para la ubicación meteorológica de referencia, no como un pronóstico validado para toda la parroquia.

No se asigna un radio de cobertura arbitrario.

### 4.4 Sectores a contrastar

**Parque Bicentenario**

Núcleo de la investigación territorial. Se debe distinguir el interior vegetado de sus bordes urbanizados.

**La Concepción**

Entorno urbano candidato que requiere verificar topografía, materiales y observaciones meteorológicas comparables.

**La Florida y Cotocollao**

Sectores próximos que podrían servir como sitios de contraste, sin afirmar de antemano similitud térmica.

**Atucucho y laderas occidentales**

Requieren especial cautela por las diferencias de relieve y exposición. No se incorporan automáticamente al dominio de predicción.

Estos nombres son hipótesis de trabajo geográfico, no límites acreditados.

Para trazar un polígono técnico se necesitan, como mínimo:

- Cartografía de elevación.
- Información de uso y cobertura del suelo.
- Identificación de las características del entorno.
- Preferiblemente, mediciones de temperatura independientes.

### 4.5 Representatividad espacial

La representatividad describe hasta qué punto una observación caracteriza las condiciones que se quieren estudiar.

Depende de:

- Ubicación y exposición del instrumento.
- Relieve y elevación.
- Superficies circundantes.
- Vegetación.
- Edificaciones y obstáculos.
- Circulación del viento.
- Escala de aplicación del estudio.

La Organización Meteorológica Mundial recomienda documentar las condiciones de emplazamiento y exposición de las estaciones [6].

**No existe un radio universal que garantice representatividad de temperatura del aire en cualquier sector urbano.**

### 4.6 Conclusión geográfica provisional

La Concepción es apropiada como sector de investigación, pero no es todavía un área de predicción validada.

La ubicación de referencia será el alcance cuantitativo inicial; una extensión territorial exigirá evidencia adicional.

---

## 5. Datos meteorológicos y procedencia

### 5.1 Fuentes utilizadas

| Fuente | Naturaleza | Función prevista |
|---|---|---|
| Meteostat, estación 84071 | Archivo meteorológico asociado a estación histórica | Serie horaria de referencia |
| ERA5 | Reanálisis atmosférico | Complementación de datos faltantes |
| ECMWF IFS vía Open-Meteo | Producto de modelo atmosférico histórico | Complementación de datos faltantes |

**Advertencias:**

- Se debe verificar la continuidad y procedencia de los registros recientes de Meteostat [1].
- ERA5 no constituye una observación puntual directa [7, 8].
- Las versiones de IFS pueden cambiar durante el período histórico [7].

### 5.2 Variables meteorológicas

Según la descripción del dataset del equipo, se consideran:

| Variable | Descripción |
|---|---|
| Temperatura del aire | Variable principal de predicción |
| Humedad relativa | Condición de humedad atmosférica |
| Velocidad del viento | Rapidez del movimiento del aire |
| Dirección del viento | Dirección desde la cual sopla |
| Presión atmosférica | Estado de la presión del aire |
| Nubosidad | Cobertura de nubes |
| Precipitación | Cantidad de precipitación |
| Fecha y hora | Referencia temporal del registro |

Las unidades, los nombres exactos de columnas, las alturas de medición y los porcentajes de valores faltantes deben registrarse después de inspeccionar los archivos definitivos.

### 5.3 Resolución espacial de ERA5

ERA5 es un producto de reanálisis atmosférico desarrollado por ECMWF.

La serie horaria atmosférica distribuida en malla regular utiliza una resolución de **0,25°**, aproximadamente **25 km** [7, 8].

Esta resolución describe la escala de la malla publicada, no un radio de precisión meteorológica local.

No significa que todos los lugares dentro de 25 km tengan necesariamente las mismas condiciones de temperatura.

### 5.4 Resolución espacial de ECMWF IFS

El producto histórico ECMWF IFS documentado en Open-Meteo ofrece una resolución aproximada de **9 km** [7].

Es necesario registrar la opción de modelo y el período descargado.

Esta resolución no determina por sí sola la precisión de las predicciones en calles, barrios o parques.

### 5.5 Selección de celdas en Open-Meteo

Open-Meteo ofrece opciones como:

- `cell_selection=land`
- `cell_selection=nearest`
- `cell_selection=sea`

La opción `land`, utilizada de forma predeterminada, puede priorizar una celda terrestre con elevación parecida a la solicitada [7].

Se deben conservar las coordenadas y la elevación devueltas por la API, no solamente las coordenadas solicitadas.

### 5.6 Implicaciones para Quito

En un entorno montañoso pueden existir variaciones importantes de elevación y uso del suelo a escalas menores que la resolución de una malla meteorológica.

Por tanto:

**Resolución espacial del modelo atmosférico ≠ representatividad espacial de la estación ≠ área validada de predicción.**

Estas tres características deben evaluarse por separado.

### 5.7 Control de procedencia

Para cada registro debe conservarse, cuando corresponda:

- Fecha y hora.
- Variable meteorológica.
- Unidad.
- Fuente original.
- Identificación de datos complementados.
- Modelo atmosférico utilizado.
- Fecha de consulta.
- Configuración de descarga.
- Zona horaria.
- Procedimiento de transformación.

Los registros observados y las estimaciones de modelos atmosféricos no deben mezclarse sin identificarlos.

### 5.8 Control de calidad del conjunto final

| Indicador | Estado |
|---|---|
| Fecha y hora inicial/final exactas | Pendiente de auditar |
| Zona horaria aplicada y manejo de UTC | Pendiente |
| Registros horarios esperados y presentes | Pendiente de calcular |
| Registros duplicados y ausentes | Pendiente de calcular |
| Porcentaje completado mediante ERA5 / IFS | Pendiente de calcular |
| Columnas, unidades y conversiones | Pendiente de confirmar |
| Coordenada y elevación efectivas de cada producto | Pendiente de guardar |

---

## 6. Metodología numérica propuesta

El procedimiento siguiente describe el diseño previsto del proyecto.

No se presentan coeficientes ni resultados antes de ejecutar y verificar el análisis.

### Etapa 1. Auditoría temporal

- Ordenar los registros por fecha y hora.
- Detectar valores duplicados.
- Unificar unidades.
- Revisar discontinuidades.
- Identificar datos faltantes.

### Etapa 2. Tratamiento de faltantes

Documentar los criterios de complementación.

Cada valor deberá conservar la identificación de su fuente.

Se evitará utilizar información futura al simular condiciones de pronóstico real.

### Etapa 3. Definición de variables

Seleccionar variables explicativas disponibles al instante de pronóstico `t`.

Por ejemplo, temperatura actual y otras variables meteorológicas conocidas en ese instante.

### Etapa 4. Construcción de objetivos

Para cada horizonte:

- h = 1 hora.
- h = 3 horas.
- h = 5 horas.

Se asociarán las variables conocidas en `t` con la temperatura correspondiente a `t+h`.

### Etapa 5. Partición cronológica

Separar los datos en:

- Entrenamiento.
- Validación.
- Prueba.

La separación deberá respetar el orden temporal.

El período de prueba no participará en el ajuste del modelo.

### Etapa 6. Ajuste por mínimos cuadrados

Determinar los coeficientes para cada horizonte de predicción.

Verificar las condiciones numéricas de la matriz utilizada.

### Etapa 7. Evaluación

Calcular:

- Error absoluto medio (MAE).
- Raíz del error cuadrático medio (RMSE).
- Sesgo.

Comparar las predicciones con los valores de referencia.

### Etapa 8. Interpretación

Analizar los resultados obtenidos y explicar las restricciones temporales y espaciales del modelo.

### 6.1 Formulación matemática

Sea:

- `T_t`: temperatura conocida en el instante `t`.
- `h`: horizonte de predicción.
- `x_t`: vector de variables disponibles en el instante `t`.
- `β`: coeficientes por determinar.

Se propone el siguiente modelo lineal en sus parámetros:

$$
\widehat{T}_{t+h}
=
\beta_{0,h}
+
\sum_{j=1}^{p}
\beta_{j,h}x_{j,t}
$$

Con:

$$
h \in \{1,3,5\}
$$

Para cada horizonte se estiman los coeficientes minimizando:


```math
\hat{T}_{t+h} = \beta_{0,h} + \sum_{j=1}^{p} \beta_{j,h} x_{j,t}
```


### 6.2 Formulación matricial

El problema de mínimos cuadrados se expresa como:


```math
\hat{\beta}_h =
\arg\min_{\beta_h}
\left\|X_h\beta_h-y_h\right\|_2^2
```



Donde:

- `X_h`: matriz de variables predictoras.
- `y_h`: vector de temperaturas observadas futuras.
- `β_h`: vector de coeficientes por calcular.

### 6.3 Consideraciones numéricas

Se recomienda resolver el problema mediante una rutina basada en:

- Factorización QR.
- Descomposición en valores singulares (SVD).

Estas alternativas permiten evitar la inversión explícita de `XᵀX`, que puede presentar dificultades de estabilidad numérica.

La selección definitiva de variables y el tratamiento de multicolinealidad se documentarán cuando exista código verificable.

### 6.4 Modelo de comparación

Se utilizará como referencia sencilla el método de persistencia:

$$
\widehat{T}^{\text{persistencia}}_{t+h}=T_t
$$

Este método supone que la temperatura futura será igual a la temperatura actual.

El modelo de mínimos cuadrados deberá compararse con esta referencia utilizando los mismos datos de prueba para cada horizonte.

---

## 7. Evaluación y validación

### 7.1 Error de predicción

Se define:

$$
e_i=T_i-\widehat{T}_i
$$

Donde:

- `T_i`: temperatura observada.
- `T̂_i`: temperatura estimada.
- `e_i`: diferencia entre ambos valores.

### 7.2 Error absoluto medio (MAE)

$$
MAE=
\frac{1}{n}
\sum_{i=1}^{n}
|T_i-\widehat{T}_i|
$$

Permite conocer la magnitud promedio de los errores absolutos.

Si la temperatura se expresa en grados Celsius, el MAE también se expresa en grados Celsius.

### 7.3 Raíz del error cuadrático medio (RMSE)

$$
RMSE=
\sqrt{
\frac{1}{n}
\sum_{i=1}^{n}
(T_i-\widehat{T}_i)^2
}
$$

Penaliza en mayor medida los errores grandes.

### 7.4 Sesgo

$$
Sesgo=
\frac{1}{n}
\sum_{i=1}^{n}
(\widehat{T}_i-T_i)
$$

Interpretación:

- Sesgo positivo: sobreestimación media.
- Sesgo negativo: subestimación media.
- Sesgo cercano a cero: ausencia de sesgo medio importante, aunque pueden existir errores individuales.

### 7.5 Validación temporal

Los errores predictivos se calcularán en datos futuros no utilizados durante el ajuste.

Los resultados se informarán por separado para:

- Predicción a 1 hora.
- Predicción a 3 horas.
- Predicción a 5 horas.

También se compararán con el modelo de persistencia.

La complementación de faltantes y cualquier transformación estadística deberán diseñarse evitando filtraciones de información del conjunto de prueba.

### 7.6 Validación espacial

Para estudiar la representatividad espacial se propone seleccionar una o más estaciones meteorológicas cercanas con observaciones correspondientes a períodos coincidentes.

El procedimiento será:

1. Identificar estaciones de comparación.
2. Verificar sus coordenadas y elevaciones.
3. Comprobar la compatibilidad de las mediciones.
4. Alinear los registros por fecha y hora.
5. Calcular MAE, RMSE y sesgo de las diferencias entre estaciones.
6. Interpretar los resultados considerando relieve, exposición y cobertura del suelo.

La comparación entre estaciones permite cuantificar diferencias espaciales.

**El error entre estaciones no es equivalente al error predictivo de un modelo matemático.**

No se utilizará un umbral universal de aceptación sin justificación científica.

Si no se consiguen observaciones independientes, se informará que la representatividad espacial ampliada no pudo validarse.

---

## 8. Implementación y reproducibilidad

**Repositorio oficial del proyecto:**

https://github.com/infismal/AnalisisMeteorologico

Este README documenta la propuesta científica.

La estructura real de carpetas, los programas ejecutables, las versiones de dependencias y los comandos de ejecución se añadirán cuando el equipo publique y verifique esos archivos.

No se incluyen instrucciones de instalación no comprobadas.

### 8.1 Documentación necesaria

Cuando esté disponible el código, el repositorio deberá indicar:

- Archivos de entrada.
- Ubicación y formato de los datos.
- Licencias o restricciones de redistribución.
- Scripts o notebooks utilizados.
- Orden de ejecución.
- Versión de Python.
- Bibliotecas y dependencias.
- Procedimiento de instalación.
- Parámetros empleados.
- Intervalo temporal.
- Variables seleccionadas.
- Partición de los datos.
- Procedimiento para reproducir resultados.

---

## 9. Resultados y criterios de entrega

Aún no se publican resultados calculados ni áreas de predicción validadas.

### 9.1 Productos esperados

- Dataset meteorológico documentado.
- Indicadores de calidad de los registros.
- Identificación del origen de cada observación.
- Funciones ajustadas para 1, 3 y 5 horas.
- Coeficientes de los modelos.
- Tabla de MAE, RMSE y sesgo.
- Comparación con el modelo de persistencia.
- Gráficas de temperaturas observadas y estimadas.
- Análisis de errores.
- Informe de representatividad geográfica.
- Conclusiones sobre el alcance del modelo.

### 9.2 Estado de verificación

| Componente | Estado |
|---|---|
| Pregunta de investigación | Definida |
| Área candidata de estudio | Definida |
| Ficha de la estación histórica | Identificada |
| Procedencia de registros recientes | Por verificar |
| Resoluciones de ERA5 e IFS | Documentadas |
| Dataset definitivo y calidad | Pendiente de auditoría |
| Código de mínimos cuadrados | Pendiente de revisión |
| Resultados numéricos | Pendientes de cálculo |
| Validación espacial | Pendiente de evidencia |

---

## 10. Limitaciones y precauciones

**1. Ubicación de la estación**

La coordenada histórica no confirma que exista un sensor activo en el Parque Bicentenario durante todo el período 2018–2026.

**2. Procedencia de los datos**

ERA5 e IFS son productos atmosféricos modelados y no equivalen automáticamente a observaciones instrumentales locales.

**3. Resolución espacial**

Una mayor resolución de malla no garantiza precisión en cada calle o barrio.

**4. Diferencias entre variables térmicas**

La temperatura superficial obtenida mediante imágenes satelitales no es intercambiable con la temperatura del aire registrada por una estación.

**5. Características geográficas**

El relieve, la vegetación y los materiales urbanos pueden producir diferencias de temperatura entre sectores próximos.

**6. Capacidad predictiva**

Un buen ajuste durante el entrenamiento no garantiza precisión con datos futuros.

**7. Representatividad espacial**

Sin comparación con estaciones independientes, no se puede afirmar que las predicciones sean válidas para toda La Concepción.

Por tanto, el alcance deberá permanecer asociado a la ubicación meteorológica de referencia.

---

## 11. Equipo y datos académicos

**Institución:** Escuela Politécnica Nacional (EPN)

**Asignatura:** Métodos Numéricos

**Proyecto:** Modelado matemático para la predicción de temperatura del aire a corto plazo en el sector del Parque Bicentenario, Quito.

**Integrantes y responsabilidades:** pendiente de completar con la lista confirmada por el equipo.

**Docente:** pendiente de completar.

---

## 12. Referencias bibliográficas

### 12.1 Estaciones, territorio y organismos oficiales

**[1] Meteostat.**

*Quito / Mariscal Sucre, estación 84071.*

Metadatos de ubicación e inventario meteorológico.

https://meteostat.net/es/station/84071

**[2] Quito Turismo. (2024).**

*Plan de emergencia / información de instalaciones del antiguo aeropuerto.*

Documento que registra el traslado de las operaciones aeroportuarias en febrero de 2013.

https://www.quito-turismo.gob.ec/descargas/LOTAIP_2024/junio/UGR.pdf

**[3] Cubillo, P., Orellana, D. y Maigua, P. (2020).**

*Análisis de la distribución espacial de la temperatura superficial y la valoración de criterios que influyen en la isla de calor urbano en el Distrito Metropolitano de Quito.*

Centro de Información Urbana de Quito.

Estudio de temperatura superficial y mediciones de temperatura del aire en espacios arbolados y no arbolados.

https://www.ciuq.ec/INFORME%20FINAL%20ISLAS%20DE%20CALOR.pdf

**[4] Empresa Pública Metropolitana de Movilidad y Obras Públicas (EPMMOP).**

*Parque Metropolitano Bicentenario.*

Información institucional del parque y su origen en el antiguo aeropuerto.

https://www.epmmop.gob.ec/parques/parque-bicentenario/

**[5] Stewart, I. D. y Oke, T. R. (2012).**

*Local Climate Zones for Urban Temperature Studies.*

Bulletin of the American Meteorological Society, 93(12), 1879–1900.

DOI: https://doi.org/10.1175/BAMS-D-11-00019.1

**[6] Organización Meteorológica Mundial (OMM).**

*Guide to Instruments and Methods of Observation (WMO-No. 8).*

Edición 2024.

Orientaciones sobre emplazamiento, exposición y mediciones meteorológicas.

https://community.wmo.int/site/knowledge-hub/programmes-and-initiatives/instruments-and-methods-of-observation-programme-imop/guide-instruments-and-methods-of-observation-wmo-no-8-0

### 12.2 Reanálisis y modelos meteorológicos

**[7] Open-Meteo.**

*Historical Weather API Documentation.*

Documentación de resoluciones espaciales, modelos atmosféricos, selección de celdas y variables disponibles.

https://open-meteo.com/en/docs/historical-weather-api

**[8] Hersbach, H., et al. (2020).**

*The ERA5 global reanalysis.*

Quarterly Journal of the Royal Meteorological Society, 146, 1999–2049.

DOI: https://doi.org/10.1002/qj.3803

**[9] European Centre for Medium-Range Weather Forecasts (ECMWF).**

*ERA5 hourly time-series data on single levels from 1940 to present.*

Documentación sobre datos horarios, resolución y características del reanálisis.

https://www.ecmwf.int/en/forecasts/datasets/era5-hourly-time-series-data-single-levels-1940-present

---

## Nota de alcance científico

La selección de La Concepción como zona de investigación está fundamentada por su localización y la diversidad de características del entorno.

Sin embargo, su utilización como área completa de predicción aún no ha sido validada.

Las predicciones del modelo deberán interpretarse inicialmente como estimaciones asociadas a la ubicación meteorológica de referencia.

La ampliación del alcance territorial requerirá evidencia adicional mediante mediciones comparativas y análisis geográfico.

Este documento será actualizado conforme se incorporen datos, código y resultados verificables del equipo.

---

**Escuela Politécnica Nacional — Métodos Numéricos — 2026**
