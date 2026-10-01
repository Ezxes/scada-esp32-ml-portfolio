# SCADA inteligente con ESP32 y Machine Learning

## Descripción

Sistema SCADA desarrollado para el monitoreo de nodos de comunicación mediante ESP32, análisis de métricas de red y detección de anomalías mediante Machine Learning.

## Problema abordado

El proyecto busca supervisar el comportamiento de nodos de comunicación mediante métricas como:

- Latencia
- Pérdida de paquetes
- RSSI

## Arquitectura

ESP32
↓
HTTP
↓
FastAPI
↓
PostgreSQL
↓
Machine Learning
↓
Dashboard SCADA
↓
Alertas

## Tecnologías

- ESP32
- Python
- FastAPI
- PostgreSQL
- SQLAlchemy
- Isolation Forest
- StandardScaler
- Jinja2
- Chart.js

## Machine Learning

Se utiliza Isolation Forest para identificar comportamientos anómalos a partir de las métricas de red monitoreadas.

## Dashboard SCADA

El sistema permite visualizar:

- Estado de los nodos
- Latencia
- Pérdida de paquetes
- RSSI
- Estado generado por reglas
- Estado generado mediante Machine Learning

## Validación

El sistema incluye una metodología de validación basada en:

- Condiciones normales
- Perturbaciones controladas
- Ground truth
- Registro de muestras
- Comparación entre reglas y Machine Learning

## Resultados

Aquí se mostrarán capturas, gráficos y resultados generales obtenidos durante las pruebas.

## Código fuente

El código fuente completo se mantiene en un repositorio privado debido a que forma parte de un trabajo académico y contiene componentes desarrollados específicamente para la investigación.

## Autor

Steven Soria Jima  
Egresado de Ingeniería en Telecomunicaciones

LinkedIn:
https://www.linkedin.com/in/steven-soria-jima
