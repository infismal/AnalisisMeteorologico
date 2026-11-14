
# 🌤️ Modelado matemático para la predicción de temperatura del aire a corto plazo en el sector del Parque Bicentenario, Quito

**Escuela Politécnica Nacional (EPN)**  
**Facultad de Ingeniería de Sistemas**

**Área de estudio:** Parque Bicentenario, parroquia La Concepción, norte de Quito, Ecuador.

**Horizontes de predicción:** 1, 3 y 5 horas.

**Estado:** Proyecto en desarrollo.

---

## 📑 Contenido

1. [Descripción del proyecto](#1--descripción-del-proyecto)
2. [Justificación de la investigación](#2--justificación-de-la-investigación)
3. [Objetivos](#3--objetivos)
4. [Área de estudio y delimitación geográfica](#4--área-de-estudio-y-delimitación-geográfica)
5. [Fuentes de datos](#5--fuentes-de-datos)
6. [Variables meteorológicas](#6--variables-meteorológicas)
7. [Metodología](#7--metodología)
8. [Fundamento matemático](#8--fundamento-matemático)
9. [Evaluación del modelo](#9--evaluación-del-modelo)
10. [Tecnologías utilizadas](#10--tecnologías-utilizadas)
11. [Resultados esperados](#11--resultados-esperados)
12. [Limitaciones](#12--limitaciones)
13. [Integrantes](#13--integrantes)
14. [Referencias bibliográficas](#14--referencias-bibliográficas)

---

## 1. 📌 Descripción del proyecto

El presente proyecto tiene como finalidad desarrollar un modelo matemático que permita estimar la temperatura del aire a corto plazo en el sector del Parque Bicentenario, ubicado en la parroquia La Concepción, al norte de Quito, Ecuador.

Para realizar este análisis se utilizará información meteorológica horaria correspondiente al período 2018–2026, asociada a la estación histórica Mariscal Sucre, registrada en la plataforma Meteostat.

Los registros disponibles incluyen variables como temperatura, humedad relativa, velocidad y dirección del viento, presión atmosférica, nubosidad y precipitación.

Para complementar los registros faltantes, el equipo utiliza información procedente de ERA5 y ECMWF IFS, obtenida mediante Open-Meteo.

La técnica principal será el método de mínimos cuadrados, con el objetivo de construir funciones matemáticas capaces de estimar la temperatura del aire para los siguientes horizontes:

- Predicción a 1 hora.
- Predicción a 3 horas.
- Predicción a 5 horas.

El proyecto se enfoca en una ubicación meteorológica específica del norte de Quito y no busca desarrollar un pronóstico general para toda la ciudad.

---

## 2. 💡 Justificación de la investigación

### ¿Por qué es un buen tema para Métodos Numéricos?

La predicción de temperatura mediante métodos numéricos permite aplicar conceptos matemáticos a un problema real, utilizando información meteorológica histórica para analizar patrones y estimar valores futuros.

El método de mínimos cuadrados permite encontrar una función matemática que se ajuste a los datos disponibles y evaluar posteriormente su capacidad de predicción.

Este proyecto resulta importante porque permite relacionar la programación, el análisis de datos y los métodos numéricos con un fenómeno cotidiano como la variación de la temperatura.

### ¿Por qué se seleccionó el sector de La Concepción?

La parroquia La Concepción se encuentra en el norte de Quito y contiene el Parque Bicentenario, construido sobre los terrenos del antiguo aeropuerto Mariscal Sucre.

Se considera una zona adecuada para desarrollar la investigación por las siguientes razones:

**1. Relación con la información meteorológica**

El proyecto utiliza datos asociados a la estación histórica Quito / Mariscal Sucre, cuya ubicación de referencia se encuentra en este sector.

Esta relación permite establecer un punto geográfico de referencia para el análisis de temperatura.

Sin embargo, la existencia de registros recientes en una plataforma no confirma que actualmente funcione un sensor físico en el antiguo aeropuerto.

**2. Características geográficas**

El Parque Bicentenario presenta un terreno predominantemente plano en su área central.

En sus alrededores existen sectores residenciales, vías de circulación, edificaciones y áreas verdes.

Estas características hacen que el sector sea interesante para estudiar el comportamiento de la temperatura del aire.

**3. Diferencias de cobertura del suelo**

Las áreas vegetadas y las superficies urbanizadas pueden presentar comportamientos térmicos diferentes.

La vegetación, los materiales de construcción y la presencia de superficies asfaltadas influyen en el intercambio de energía con la atmósfera.

Por este motivo, resulta relevante investigar si los datos de una estación meteorológica pueden representar las condiciones de ubicaciones próximas.

**4. Importancia de la delimitación geográfica**

El proyecto permite estudiar no solamente la predicción de temperatura, sino también las limitaciones espaciales de los datos utilizados.

No sería correcto afirmar que una estación meteorológica representa toda la parroquia únicamente por encontrarse dentro de ella.

Es necesario evaluar las características geográficas y, cuando sea posible, comparar observaciones de estaciones próximas.

### Conclusión de la justificación

La Concepción es una zona pertinente para investigar debido a su relación con los datos históricos del antiguo aeropuerto y a la diversidad de características urbanas y ambientales existentes en sus alrededores.

No obstante, la cobertura geográfica de las predicciones deberá justificarse mediante evidencia y no únicamente por la cercanía con la estación de referencia.

---

## 3. 🎯 Objetivos

### Objetivo general

Desarrollar un modelo matemático mediante mínimos cuadrados para estimar la temperatura del aire a 1, 3 y 5 horas en el sector de referencia del Parque Bicentenario, al norte de Quito.

### Objetivos específicos

- Recopilar y organizar datos meteorológicos horarios del período 2018–2026.
- Revisar y completar los registros faltantes mediante fuentes meteorológicas complementarias.
- Analizar las variables relacionadas con el comportamiento de la temperatura.
- Construir funciones matemáticas mediante el método de mínimos cuadrados.
- Calcular predicciones de temperatura a 1, 3 y 5 horas.
- Evaluar los resultados utilizando medidas de error.
- Investigar la representatividad espacial de la estación meteorológica.
- Establecer las limitaciones geográficas del modelo.
- Presentar resultados mediante tablas y gráficas.

---

## 4. 📍 Área de estudio y delimitación geográfica

### 4.1 Ubicación

El área de investigación corresponde al entorno del Parque Bicentenario, ubicado en la parroquia La Concepción, al norte de Quito, Ecuador.

La referencia meteorológica utilizada corresponde a la estación histórica Quito / Mariscal Sucre.

| Característica | Información |
|---|---|
| País | Ecuador |
| Provincia | Pichincha |
| Ciudad | Quito |
| Parroquia | La Concepción |
| Sector | Parque Bicentenario |
| Estación histórica | Mariscal Sucre |
| Código de estación | 84071 |
| Código ICAO histórico | SEQU |
| Latitud | -0.1500 |
| Longitud | -78.4833 |
| Elevación de referencia | 2811 m s. n. m. |
| Período de estudio | 2018–2026 |

**Ubicación de referencia:**

[Ver coordenadas en Google Maps](https://www.google.com/maps?q=-0.1500,-78.4833)

### 4.2 Características geográficas

El Parque Bicentenario ocupa parte del antiguo aeropuerto Mariscal Sucre, que dejó de operar como aeropuerto comercial en 2013.

La zona se encuentra dentro del valle urbano de Quito, rodeada de áreas residenciales, comerciales y espacios recreativos.

Entre sus principales características se encuentran:

- Terreno relativamente plano dentro del área principal del parque.
- Presencia de vegetación y espacios abiertos.
- Sectores residenciales y comerciales alrededor del parque.
- Calles y avenidas con superficies asfaltadas.
- Variaciones de relieve hacia las laderas occidentales.

Estas características deben considerarse al estudiar la temperatura del aire porque pueden producir diferencias entre ubicaciones cercanas.

### 4.3 Límites geográficos del área de investigación

Para el desarrollo inicial se propone utilizar como referencia el Parque Bicentenario y estudiar sectores próximos de la parroquia La Concepción.

Se deben diferenciar tres niveles:

| Zona | Interpretación |
|---|---|
| Ubicación meteorológica de referencia | Punto asociado a los datos históricos de Meteostat |
| Zona propuesta para investigar | Parque Bicentenario y sectores próximos de La Concepción |
| Zona validada para predicción | Pendiente de determinar mediante evidencia meteorológica |

Los límites administrativos de La Concepción no deben considerarse automáticamente límites de cobertura meteorológica.

### 4.4 Sectores cercanos que podrían investigarse

**Parque Bicentenario**

Constituye el sector central de estudio por su relación con la ubicación histórica de referencia.

**La Concepción**

Es el entorno urbano inmediato del parque. Se deben investigar las diferencias entre áreas residenciales, espacios verdes y avenidas.

**La Florida**

Puede considerarse un sector candidato de comparación, siempre que se evalúen las diferencias de elevación y cobertura del suelo.

**Cotocollao**

Es otro sector del norte de Quito que podría estudiarse, pero su proximidad no demuestra equivalencia térmica.

**Atucucho y laderas occidentales**

Estas zonas presentan características topográficas diferentes, por lo que no se deben incluir automáticamente dentro de la cobertura del modelo.

La selección de estos sectores es orientativa y no constituye una validación de representatividad.

### 4.5 Representatividad espacial de la estación

La representatividad espacial indica hasta qué punto las mediciones de una estación meteorológica pueden describir razonablemente las condiciones de otros lugares.

Según la Organización Meteorológica Mundial (OMM), esta representatividad depende del entorno, la exposición de los instrumentos, la variable medida y la finalidad de las observaciones.

Entre los factores importantes se encuentran:

- Distancia horizontal.
- Diferencias de altitud.
- Relieve y pendientes.
- Cobertura vegetal.
- Presencia de edificios.
- Superficies asfaltadas.
- Circulación del viento.
- Condiciones meteorológicas locales.

No existe un radio universal que permita establecer automáticamente el alcance de una estación de temperatura en cualquier entorno.

### 4.6 Delimitación recomendada

Se propone mantener inicialmente las predicciones asociadas a la ubicación meteorológica de referencia del Parque Bicentenario.

El área circundante de La Concepción se utilizará como zona de investigación para analizar la posible extensión espacial del modelo.

No se establecerá un radio fijo de cobertura hasta disponer de información suficiente que permita justificarlo.

Si no se obtienen mediciones independientes en otros puntos, el alcance del modelo permanecerá limitado a su ubicación meteorológica de referencia.

---

## 5. 🗂️ Fuentes de datos

### 5.1 Meteostat

Meteostat es una plataforma que permite consultar registros meteorológicos históricos.

Para este proyecto se utiliza una serie asociada a la estación histórica Quito / Mariscal Sucre.

**Estación:** 84071

**Coordenadas de referencia:** -0.1500, -78.4833

**Fuente:**

https://meteostat.net/es/station/84071

Es importante comprobar la procedencia de los registros, especialmente después del cierre del antiguo aeropuerto.

No debe asumirse que todos los valores recientes proceden directamente de un sensor ubicado en ese lugar.

### 5.2 Open-Meteo

Open-Meteo proporciona acceso a información meteorológica histórica y productos de modelos atmosféricos.

Se utiliza para complementar registros faltantes mediante ERA5 y ECMWF IFS.

**Fuente:**

https://open-meteo.com/en/docs/historical-weather-api

### 5.3 ERA5

ERA5 es un producto de reanálisis atmosférico desarrollado por el Centro Europeo de Previsiones Meteorológicas a Medio Plazo (ECMWF).

Integra observaciones y modelos atmosféricos para generar información meteorológica histórica.

La resolución espacial nominal de ERA5 es de aproximadamente 0,25 grados, equivalente a unos 25 km.

Esta resolución no significa que los datos representen con igual precisión cada ubicación dentro de un radio de 25 km.

### 5.4 ECMWF IFS

IFS es el sistema de predicción meteorológica del ECMWF.

El producto histórico IFS utilizado mediante Open-Meteo puede ofrecer una resolución aproximada de 9 km, dependiendo de la versión y el período disponible.

Su resolución espacial debe diferenciarse de la precisión local de una predicción.

### 5.5 Comparación de fuentes

| Fuente | Tipo de información | Uso en el proyecto |
|---|---|---|
| Meteostat | Registros meteorológicos históricos | Serie principal de referencia |
| ERA5 | Reanálisis atmosférico | Complementación de registros |
| ECMWF IFS | Modelo atmosférico | Complementación de registros |
| Open-Meteo | Plataforma de consulta | Acceso a productos meteorológicos |

Los valores completados mediante modelos atmosféricos deben identificarse y no presentarse como mediciones directas.

---

## 6. 🌡️ Variables meteorológicas

El conjunto de datos contempla las siguientes variables:

| Variable | Descripción |
|---|---|
| Temperatura | Temperatura del aire |
| Humedad relativa | Cantidad relativa de vapor de agua |
| Velocidad del viento | Rapidez de desplazamiento del aire |
| Dirección del viento | Dirección desde la que sopla |
| Presión atmosférica | Presión ejercida por la atmósfera |
| Nubosidad | Cobertura de nubes |
| Precipitación | Cantidad de precipitación registrada |
| Fecha y hora | Momento de cada observación |

La temperatura del aire será la variable principal que el modelo buscará estimar.

Las demás variables podrán utilizarse como variables explicativas según su disponibilidad y el análisis realizado por el equipo.

---

## 7. 🔎 Metodología

El desarrollo del proyecto se plantea en las siguientes etapas.

### Etapa 1. Recolección de información

Obtener los registros meteorológicos correspondientes al período de estudio.

### Etapa 2. Limpieza de datos

Identificar:

- Valores faltantes.
- Registros duplicados.
- Inconsistencias.
- Diferencias de unidades.
- Problemas de fecha y hora.

### Etapa 3. Complementación de registros

Completar los datos faltantes utilizando los productos meteorológicos seleccionados.

Se conservará la identificación de la fuente utilizada para cada valor.

### Etapa 4. Preparación de variables

Seleccionar las variables meteorológicas que se utilizarán para construir las funciones matemáticas.

### Etapa 5. Aplicación de mínimos cuadrados

Calcular los coeficientes necesarios para ajustar las funciones de predicción.

### Etapa 6. Predicción de temperatura

Estimar la temperatura del aire a:

- 1 hora.
- 3 horas.
- 5 horas.

### Etapa 7. Evaluación

Comparar los valores estimados con los valores de referencia mediante métricas de error.

### Etapa 8. Interpretación

Analizar los resultados y explicar las limitaciones del modelo.

---

## 8. 📐 Fundamento matemático

El método principal utilizado será el ajuste por mínimos cuadrados.

Este método permite encontrar los coeficientes de una función matemática que minimice la suma de los cuadrados de los errores entre los valores observados y los valores estimados.

### 8.1 Modelo propuesto

Se plantea utilizar una función de regresión lineal múltiple:

\[
\widehat{T}_{t+h} =
\beta_{0,h}+
\beta_{1,h}x_{1,t}+
\beta_{2,h}x_{2,t}+
\cdots+
\beta_{p,h}x_{p,t}
\]

Donde:

- T̂ representa la temperatura estimada.
- h representa el horizonte de predicción.
- x representa las variables explicativas.
- β representa los coeficientes del modelo.

Los horizontes considerados serán:

\[
h \in \{1,3,5\}
\]

### 8.2 Función de mínimos cuadrados

Los coeficientes se determinan minimizando:

\[
\min_{\beta}
\sum_{i=1}^{n}
(T_i-\widehat{T}_i)^2
\]

En notación matricial, bajo las condiciones matemáticas correspondientes:

\[
\widehat{\beta} =
(X^TX)^{-1}X^Ty
\]

Para la implementación se recomienda utilizar procedimientos numéricamente estables, evitando calcular directamente la inversa cuando no sea necesario.

Los coeficientes finales dependerán de los datos procesados y de las variables seleccionadas.

---

## 9. 📊 Evaluación del modelo

Para evaluar las predicciones se propone utilizar las siguientes métricas.

### 9.1 Error absoluto medio (MAE)

\[
MAE =
\frac{1}{n}
\sum_{i=1}^{n}
|T_i-\widehat{T}_i|
\]

Permite calcular el promedio de los errores absolutos.

### 9.2 Raíz del error cuadrático medio (RMSE)

\[
RMSE =
\sqrt{
\frac{1}{n}
\sum_{i=1}^{n}
(T_i-\widehat{T}_i)^2
}
\]

Permite evaluar la magnitud de los errores, dando mayor importancia a las diferencias grandes.

### 9.3 Sesgo

\[
Sesgo =
\frac{1}{n}
\sum_{i=1}^{n}
(\widehat{T}_i-T_i)
\]

Permite identificar si el modelo tiende a sobreestimar o subestimar la temperatura.

### 9.4 Validación temporal

Los datos destinados a evaluar el modelo deben corresponder a un período posterior al utilizado para el ajuste.

Esto permite analizar su comportamiento con información que no fue utilizada para calcular los coeficientes.

### 9.5 Validación espacial

Para comprobar la representatividad espacial se propone comparar observaciones horarias de estaciones meteorológicas cercanas, cuando existan datos disponibles.

La comparación deberá realizarse utilizando mediciones correspondientes a las mismas fechas y horas.

Se podrán calcular:

- MAE entre estaciones.
- RMSE entre estaciones.
- Sesgo de temperatura entre estaciones.

Esta evaluación permitirá cuantificar diferencias térmicas entre ubicaciones.

No se establecerá un umbral universal de aceptación sin una justificación científica.

La comparación entre estaciones no debe confundirse con la evaluación de los errores de predicción del modelo.

---

## 10. 💻 Tecnologías utilizadas

### Herramientas previstas

- Python.
- Jupyter Notebook.
- GitHub.

Las bibliotecas y dependencias definitivas se incorporarán conforme avance la implementación.

### Estado del repositorio

El repositorio se encuentra en desarrollo.

Las instrucciones de instalación, estructura de carpetas y ejecución se documentarán una vez incorporados los programas y archivos correspondientes.

**Repositorio:**

https://github.com/infismal/AnalisisMeteorologico

---

## 11. 📈 Resultados esperados

Se espera obtener:

- Una serie meteorológica organizada y depurada.
- Funciones matemáticas ajustadas mediante mínimos cuadrados.
- Predicciones de temperatura a 1, 3 y 5 horas.
- Tablas comparativas de valores observados y estimados.
- Gráficas de temperatura.
- Métricas de evaluación del modelo.
- Un análisis de las limitaciones geográficas de las predicciones.

Los resultados numéricos se incorporarán después de ejecutar y verificar el modelo.

---

## 12. ⚠️ Limitaciones

El proyecto considera las siguientes limitaciones:

1. No se ha confirmado la operación actual de un sensor meteorológico en el antiguo aeropuerto Mariscal Sucre.

2. Se debe verificar la procedencia de los datos disponibles para el período 2018–2026.

3. Los registros obtenidos mediante ERA5 y ECMWF IFS no equivalen necesariamente a observaciones locales directas.

4. La topografía y la urbanización de Quito pueden generar diferencias de temperatura entre ubicaciones próximas.

5. No existe todavía un radio de representatividad espacial validado para los datos del proyecto.

6. Los resultados del modelo no deben interpretarse como predicciones válidas para toda la ciudad de Quito.

7. La precisión del modelo deberá evaluarse mediante datos diferentes de los utilizados durante su ajuste.

---

## 13. 👥 Integrantes

**Escuela Politécnica Nacional**

**Asignatura:** Métodos Numéricos

**Equipo de trabajo:** Pendiente de completar con los integrantes y responsabilidades confirmados por el grupo.

---

## 14. 📚 Referencias bibliográficas

### Organización Meteorológica Mundial

World Meteorological Organization. (2023).

*Guide to Instruments and Methods of Observation (WMO-No. 8).*

https://wmo.int/guide-instruments-and-methods-of-observation-wmo-no-8

### Meteostat

Meteostat. *Quito / Mariscal Sucre — Station 84071.*

https://meteostat.net/es/station/84071

### Open-Meteo

Open-Meteo. *Historical Weather API Documentation.*

https://open-meteo.com/en/docs/historical-weather-api

### ECMWF

European Centre for Medium-Range Weather Forecasts.

*ERA5: Data documentation.*

https://www.ecmwf.int/en/forecasts/dataset/ecmwf-reanalysis-v5

### Municipio de Quito

Empresa Pública Metropolitana de Movilidad y Obras Públicas.

*Parque Bicentenario.*

https://epmmop.quito.gob.ec/parque-bicentenario/

### Investigación sobre temperatura urbana de Quito

Cubillo, P., Orellana, D. y Maigua, P. (2020).

*Análisis de la distribución espacial de la temperatura superficial y la valoración de criterios que influyen en la isla de calor urbano en el Distrito Metropolitano de Quito.*

Centro de Información Urbana de Quito.

https://www.ciuq.ec/Engl2/INFORME%20FINAL%20ISLAS%20DE%20CALOR.pdf



**Escuela Politécnica Nacional — Métodos Numéricos — 2026**
