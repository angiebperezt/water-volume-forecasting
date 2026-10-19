# Pronóstico de volumen facturado de agua potable

Proyecto de series de tiempo desarrollado en R para estimar el volumen facturado mensual de agua potable y apoyar la planificación financiera de una empresa prestadora de servicios en Perú.

Se estudian dos enfoques: un modelo univariado SARIMA y un modelo multivariado VARX que incorpora conexiones facturadas y temperatura.

## Problema de negocio

La definición de metas de facturación requiere estimaciones sustentadas en el comportamiento histórico del servicio.

Este proyecto busca aportar una base estadística para establecer metas realistas de volumen facturado y apoyar la elaboración del presupuesto anual. La variable pronosticada es el volumen de agua facturado, no los ingresos monetarios.

## Objetivo

Evaluar la capacidad de un modelo SARIMA para pronosticar el volumen mensual y explorar la viabilidad de un modelo VARX que considere otras variables relacionadas con su comportamiento.

## Datos del estudio original

El análisis utilizó información mensual de enero de 2014 a junio de 2025.

| Variable | Descripción | Uso |
|---|---|---|
| Volumen facturado | Volumen mensual de agua potable facturado | Variable objetivo en SARIMA y endógena en VARX |
| Conexiones facturadas | Número mensual de conexiones facturadas | Variable endógena en VARX |
| Temperatura | Temperatura media mensual obtenida de NASA POWER | Variable exógena en VARX |

Los datos empresariales originales se mantienen privados por confidencialidad.

## Metodología

### SARIMA

- Exploración de tendencia y estacionalidad.
- Descomposición de la serie y análisis ACF/PACF.
- Pruebas de estacionariedad ADF y KPSS.
- Ajuste del modelo con `auto.arima()`.
- Diagnóstico de residuos.
- Evaluación temporal reservando los últimos 12 meses.
- Evaluación mediante RMSE, MAE, MAPE y MASE.

### VARX

- Integración de volumen, conexiones facturadas y temperatura.
- Análisis de estacionariedad y diferenciación.
- Estimación de modelos con distintos rezagos.
- Refinamiento del modelo y revisión de AIC y BIC.
- Diagnóstico de residuos y evaluación de estabilidad.

## Hallazgos del estudio original

El estudio seleccionó el modelo SARIMA
ARIMA(0,1,4)(0,1,1)[12] como alternativa para elaborar
los pronósticos del volumen facturado.

El análisis de VARX identificó limitaciones de estabilidad.
Su implementación original no incluye una evaluación predictiva
sobre el mismo conjunto de prueba de SARIMA. Por ello, el proyecto
no presenta una comparación equivalente de errores fuera de muestra
entre ambos modelos.

## Confidencialidad y versión pública

Este repositorio no incluye las bases empresariales originales
ni la presentación que contiene cifras internas.

La versión pública está en preparación. Se incorporarán scripts
adaptados y datos sintéticos para demostrar el flujo de trabajo
sin divulgar información confidencial.

Los resultados obtenidos con datos sintéticos se identificarán
como demostrativos y no reproducirán necesariamente las conclusiones
del estudio original.

## Herramientas

- R
- forecast
- tseries
- MTS
- nasapower
- ggplot2
- dplyr

## Contexto académico y autoría

Proyecto final del curso Modelos Avanzados de Análisis de Datos I,
Maestría en Inteligencia Analítica para la Toma de Decisiones,
Universidad de los Andes, 2025.

**Autoras:** Catalina Manjarres y Angie Perez.
