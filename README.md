# Monitor de Fuga de Clientes — TP Ingeniería del Software (UGR)

**Grupo 14:** Agustín Alsop · Marcos Gomez Hollger · Alexia Aubone · Germán Ponce · Agustin Serra Rivero
**Docentes:** Ing. Ignacio Sanseovich · Lic. Briant Gauna
**Carrera:** Licenciatura en Ciencia de Datos

## 🔗 App publicada
**https://prompt-sopa.github.io/TP_INGSOFT_Alsop_Gomez_Aubone_Ponce_Serra/app/**

## De qué se trata
Una empresa de telecomunicaciones pierde 1 de cada 4 clientes (26,5 %). Aplicamos la metodología **CRISP-DM** para predecir qué clientes tienen alta probabilidad de darse de baja (*churn*) y llevamos el modelo a una aplicación web para el equipo de retención.

- **Dataset:** [Telco Customer Churn (IBM)](https://github.com/IBM/telco-customer-churn-on-icp4d), con 7.043 clientes y 21 variables.
- **Modelo:** regresión logística con pesos balanceados, comparada con un árbol de decisión y un baseline.
- **Resultados en datos de prueba:** recall 0,79 (detecta 8 de cada 10 fugas) y ROC-AUC 0,84.

## La aplicación
| Vista | Qué muestra |
|---|---|
| 1. Tablero | Indicadores del modelo, tasa de fuga por segmento, factores de riesgo y matriz de confusión |
| 2. Simulador de riesgo | Se cambian los datos de un cliente y se recalcula su riesgo, con acciones de retención sugeridas |
| 3. Bandeja de retención | Clientes ordenados por riesgo, con búsqueda y filtros |

La app usa **los mismos coeficientes** del modelo entrenado en la notebook. Es una página estática (HTML + JavaScript), sin servidor ni base de datos.

## Estructura del repositorio
```
├── UGR_IdS_TP_Telco_Churn.ipynb   # Notebook con las 6 fases de CRISP-DM
├── data/
│   └── Telco-Customer-Churn.csv   # Dataset original
└── app/
    ├── index.html                 # App publicada (generada por la notebook)
    ├── plantilla_app.html         # Plantilla de la app
    ├── modelo_churn.json          # Modelo exportado (coeficientes, escalado y métricas)
    └── capturas/                  # Capturas de las vistas
```

## Cómo actualizar el modelo
1. Ejecutar la notebook completa (en Jupyter o Google Colab).
2. La celda de la Fase 6 exporta `app/modelo_churn.json` y regenera `app/index.html`.
3. Subir los archivos nuevos al repositorio: GitHub Pages publica la app actualizada en 1 o 2 minutos.
