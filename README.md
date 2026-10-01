# SCADA inteligente con ESP32 y Machine Learning

Sistema SCADA orientado al monitoreo de nodos de comunicación mediante ESP32, análisis de métricas de red y detección de anomalías con Machine Learning.

> El código fuente completo del proyecto se mantiene en un repositorio privado debido a que forma parte de un trabajo académico y contiene componentes desarrollados específicamente para la investigación.

---

## Descripción

El proyecto consiste en el desarrollo de un sistema SCADA capaz de supervisar el comportamiento de nodos de comunicación en una red local.

Cada nodo es evaluado mediante métricas de red y el sistema combina reglas de operación con un modelo de Machine Learning para identificar comportamientos habituales, condiciones que requieren observación y posibles desviaciones.

El sistema integra adquisición de datos, backend, almacenamiento, procesamiento, visualización y generación de alertas.

---

## Objetivo

Desarrollar una solución de monitoreo que permita:

- Medir el comportamiento de nodos de comunicación.
- Analizar latencia, pérdida de paquetes y RSSI.
- Almacenar las mediciones para su análisis.
- Visualizar la información mediante un dashboard SCADA.
- Detectar comportamientos anómalos mediante Machine Learning.
- Generar alertas ante condiciones relevantes.

---

## Métricas monitoreadas

El sistema utiliza principalmente:

- **Latencia:** tiempo de respuesta de los nodos monitoreados.
- **Pérdida de paquetes:** porcentaje de paquetes sin respuesta durante cada ciclo de medición.
- **RSSI:** nivel de intensidad de la señal inalámbrica percibida por el ESP32.

---

## Arquitectura general

```text
┌──────────────┐
│    ESP32     │
│ Adquisición  │
└──────┬───────┘
       │ HTTP
       ▼
┌──────────────┐
│   FastAPI    │
│   Backend    │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ PostgreSQL   │
│ Base de datos│
└──────┬───────┘
       │
       ├──────────────► Machine Learning
       │                 Isolation Forest
       │
       ▼
┌──────────────┐
│  Dashboard   │
│    SCADA     │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│   Alertas    │
└──────────────┘

-------------------------Tecnologías utilizadas------------------------------------

Hardware

- ESP32 DevKit
Backend
- Python
- FastAPI
- Uvicorn
- SQLAlchemy

Base de datos

- PostgreSQL
Machine Learning
- Isolation Forest
- StandardScaler

Frontend

- HTML
- Jinja2
- Chart.js

Otros

- HTTP
- ICMP
- Git
- GitHub

Machine Learning

Para la detección de comportamientos anómalos se utiliza Isolation Forest.
El modelo analiza las métricas obtenidas durante la operación del sistema y permite identificar mediciones que se alejan del comportamiento aprendido durante el entrenamiento.
La solución emplea modelos independientes para los nodos monitoreados, permitiendo considerar las características particulares de cada uno.
Los estados utilizados por el sistema de análisis son:

- HABITUAL
- OBSERVACIÓN
- DESVIACIÓN

Dashboard SCADA

El dashboard permite visualizar en tiempo real información como:

- Estado de los nodos.
- Latencia.
- Pérdida de paquetes.
- RSSI.
- Estado determinado mediante reglas.
- Estado generado mediante Machine Learning.
- Historial de mediciones.
- Información del modelo utilizado.

Validación

El sistema incorpora una metodología de validación para comparar el comportamiento del modelo frente a condiciones controladas.
La validación considera:

- Condiciones normales.
- Perturbaciones controladas.
- Ground truth.
- Registro de muestras.
- Inferencias del modelo.
- Comparación entre estados basados en reglas y Machine Learning.
- Revisión de resultados.

Flujo general:

Medición
   ↓
Recepción en FastAPI
   ↓
Almacenamiento en PostgreSQL
   ↓
Evaluación mediante reglas
   ↓
Inferencia con Isolation Forest
   ↓
Clasificación del estado
   ↓
Visualización en SCADA
   ↓
Generación de alertas

-------------------Capturas del sistema------------------
Próximamente se incorporarán capturas de:

- Dashboard principal.
- Monitoreo de nodos.
- Visualización de métricas.
- Estados generados por Machine Learning.
- Proceso de validación.
- Resultados obtenidos durante las pruebas.

Resultados

El proyecto se encuentra orientado a evaluar la capacidad de un sistema de monitoreo basado en ESP32 y Machine Learning para identificar variaciones en el comportamiento de nodos de comunicación.
Los resultados obtenidos durante las pruebas y la validación serán documentados en esta sección mediante gráficos, capturas y métricas representativas.

Código fuente

El código fuente completo no se encuentra disponible públicamente.
El repositorio privado contiene la implementación completa del sistema, incluyendo:
- Backend.
- Firmware del ESP32.
- Modelos de Machine Learning.
- Base de datos.
- Lógica de validación.
- Dashboard.
- Scripts y herramientas auxiliares.

Este repositorio público tiene como finalidad presentar la arquitectura, metodología, tecnologías y resultados generales del proyecto sin exponer la implementación completa.

Autor
Steven Soria Jima

Egresado de Ingeniería en Telecomunicaciones

LinkedIn:
linkedin.com/in/steven-soria-jima

GitHub:
github.com/Ezxes
