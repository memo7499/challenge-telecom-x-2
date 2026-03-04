# 📊 Telecom X Parte 2 – Predicción de Cancelación de Clientes (Churn)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/16nI_WZJiZEXTaVtGaLnwuPkvYWKdtqyl?usp=sharing)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black?logo=github)](https://github.com/memo7499/challenge-telecom-x-2)
![Python](https://img.shields.io/badge/Python-3.12.12-blue?logo=python)
![Made with](https://img.shields.io/badge/Hecho%20con-Pandas%20|%20Matplotlib%20|%20Numpy%20|%20Seaborn-green)

---

## 📋 Tabla de contenidos

1. [🚀 Descripción del Proyecto](#-Descripción-del-Proyecto)
2. [🎯 Problema de Negocio](#-Problema-de-Negocio)
3. [🧠 Enfoque de Machine Learning](#-Enfoque-de-Machine-Learning)
4. [📊 Desempeño de Modelos](#-Desempeño-de-Modelos)
5. [🏆 Modelo Seleccionado](#-Modelo-Seleccionado)
6. [🔎 Matriz de Confusión – Modelo Final](#-Matriz-de-Confusión–Modelo-Final)
7. [📈 Principales Factores que Influyen en la Cancelación](#-Principales-Factores-que-Influyen-en-la-Cancelación)
8. [🔍 Interpretación de los Factores](#-Interpretación-de-los-Factores)
9. [💡 Insight Estratégico](#-Insight-Estratégico)
10. [🎯 Estrategias de Retención](#-Estrategias-de-Retención)
11. [💰 Simulación de Impacto de Negocio](#-Simulación-de-Impacto-de-Negocio)
12. [💻 Tecnologías Utilizadas](#-Tecnologías-Utilizadas)
13. [🏁 Conclusión](#-Conclusión)
14. [👤 Autor](#-Autor)

---

## 🚀 Descripción del Proyecto

La cancelación de clientes (churn) es uno de los principales desafíos en empresas con modelo de suscripción.

En este proyecto se desarrolla un pipeline completo de Machine Learning para predecir la cancelación de clientes en una empresa de telecomunicaciones, permitiendo:
- Identificar clientes con alto riesgo de cancelar.
- Comprender los principales factores que impulsan el churn.
- Proponer estrategias de retención basadas en datos.
- Estimar el impacto financiero potencial de aplicar el modelo.

## 🎯 Problema de Negocio

Telecom X enfrenta pérdida de ingresos recurrentes debido a la cancelación de clientes.

Preguntas clave que aborda el proyecto:
- ¿Qué clientes tienen mayor probabilidad de cancelar?
- ¿Cuáles son los factores más influyentes?
- ¿Qué acciones estratégicas pueden reducir la tasa de cancelación?
- ¿Cuál sería el impacto económico de retener clientes en riesgo?

## 🧠 Enfoque de Machine Learning

El proyecto incluye:

- Limpieza y preparación de datos.
- Ingeniería de variables.
- Balanceo de clases mediante SMOTE.
- Análisis de multicolinealidad (VIF).
- Regresión Logística (modelo base).
- Random Forest (modelo base y versión regularizada).
- Detección y corrección de overfitting.
- Comparación de modelos.
- Análisis de importancia de variables.
- Propuestas estratégicas de retención.

## 📊 Desempeño de Modelos

| Modelo | Accuracy | Recall | F1	| ROC-AUC |
|------|------|------|------|------|
| Regresión Logística | 0.76 | 0.65 | 0.58 |	0.82 |
| Random Forest	 | 0.77 |	0.59 | 0.57 | 0.81 |
| ***Random Forest Regularizado*** | ***0.77*** | ***0.71*** | ***0.62*** | ***0.84*** |

## 🏆 Modelo Seleccionado

El Random Forest regularizado fue el modelo con mejor desempeño general, logrando:
- Mayor capacidad de detección de churn (Recall ≈ 71%).
- Mejor equilibrio entre precisión y recall.
- Reducción significativa del overfitting.
- Mayor capacidad de generalización.

## 🔎 Matriz de Confusión – Modelo Final

- Verdaderos Positivos (TP): 267
- Verdaderos Negativos (TN): 855
- Falsos Positivos (FP): 225
- Falsos Negativos (FN): 107

El modelo detecta correctamente aproximadamente el 71% de los clientes que cancelan.

![Matriz de Confusión – Modelo Final](https://github.com/memo7499/challenge-telecom-x-2/blob/main/images/Matriz_Confusion_RFR.png)

## 📈 Principales Factores que Influyen en la Cancelación

Las variables más importantes identificadas por el modelo fueron:
- Tipo de contrato.
- Método de pago (Electronic Check).
- Antigüedad del cliente (Tenure).
- Servicio de Internet (Fiber Optic).
- Dependents.
- Partner.

![Top 15 Variables más importantes](https://github.com/memo7499/challenge-telecom-x-2/blob/main/images/Top_Variables_Importantes.png)

## 🔍 Interpretación de los Factores

### 1️⃣ Tipo de Contrato (Factor más determinante)
Los contratos mes a mes presentan una probabilidad significativamente mayor de cancelación.
### 2️⃣ Método de Pago – Electronic Check
Clientes que utilizan este método muestran mayor riesgo de churn, posiblemente asociado a menor compromiso o mayor sensibilidad al precio.
### 3️⃣ Antigüedad (Tenure)
- Clientes nuevos presentan mayor probabilidad de cancelar.
- La probabilidad de churn disminuye conforme aumenta la permanencia.
### 4️⃣ Servicio Fiber Optic
Clientes con este servicio muestran mayor riesgo, posiblemente debido a mayores expectativas o competencia en ese segmento.

## 💡 Insight Estratégico

El churn está impulsado principalmente por factores estructurales del servicio, no por variables demográficas.

Esto implica que:
- Es un fenómeno gestionable.
- Puede abordarse mediante decisiones estratégicas.
- Existen oportunidades claras de intervención preventiva.

## 🎯 Estrategias de Retención
### 1️⃣ Incentivar contratos de largo plazo
Promover la migración de contratos mensuales a anuales mediante beneficios o descuentos.
### 2️⃣ Fomentar pagos automáticos
Reducir la dependencia del método Electronic Check incentivando pagos con tarjeta o débito automático.
### 3️⃣ Estrategia de retención temprana
Implementar seguimiento y programas de fidelización durante los primeros meses del cliente.
### 4️⃣ Monitoreo de clientes Fiber Optic
Desarrollar controles de satisfacción y calidad de servicio para este segmento.

## 💰 Simulación de Impacto de Negocio

Para estimar el impacto potencial del modelo, se realiza una simulación simple.

Supuestos:
- Ingreso promedio mensual por cliente: $70
- Permanencia promedio adicional si se retiene: 12 meses
- Valor por cliente retenido: $840

El modelo detecta correctamente:
- 267 clientes que iban a cancelar
- Si la empresa logra retener solo el 30% de los clientes detectados:
- Clientes retenidos ≈ 80

Impacto estimado:
- 80 × $840 = $67,200 en ingresos recuperados

***Esto demuestra que el modelo no solo tiene valor predictivo, sino también impacto financiero estratégico.***

## 💻 Tecnologías Utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Statsmodels (VIF)
- Matplotlib
- Seaborn

## 🏁 Conclusión

Este proyecto demuestra cómo el uso de Machine Learning permite:
- Identificar clientes en riesgo de cancelación.
- Comprender los factores clave que impulsan el churn.
- Proponer estrategias de retención basadas en evidencia.
- Estimar el impacto financiero de implementar modelos predictivos.

El Random Forest regularizado logró el mejor equilibrio entre rendimiento y generalización, convirtiéndose en una herramienta viable para implementación real.

## 👤 Autor

**[JUAN G SALAZAR MARTINEZ](https://www.linkedin.com/in/guillermo-sa-ma/)**

Data Analyst | Data Science Jr | Challenge Académico de Oracle ONE - Alura LATAM.
