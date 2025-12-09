# Telecom X - Análisis de Evasión de Clientes (Churn)

## 1. Introducción y Objetivo del Proyecto

Este proyecto se enfoca en el análisis exploratorio de datos (AED) para identificar los factores clave que impulsan la alta tasa de cancelación de clientes (Churn) en Telecom X. El objetivo principal es comprender el perfil del cliente en riesgo y generar *insights* estratégicos para reducir la evasión.

## 2. Resumen del Procesamiento de Datos

El *pipeline* de procesamiento de datos incluyó los siguientes pasos esenciales para preparar la información para el análisis:

* **Limpieza de Valores Nulos:** Se identificaron y trataron los valores nulos, asegurando la integridad de las variables numéricas.
* **Aplanamiento de Datos (Feature Engineering):** Se extrajeron y convirtieron los datos anidados de las columnas `customer`, `phone`, `internet`, y `account` en columnas independientes.
* **Codificación de Variables:**
    * **Variables Binarias:** Se mapearon los valores categóricos de 'Sí'/'No' (o similares) a la codificación binaria de `1` y `0`.
    * **One-Hot Encoding:** Se aplicó esta técnica a variables con múltiples categorías (como `InternetService`, `Contract` y `PaymentMethod`) para facilitar el análisis estadístico.
* **Conversión de Tipos:** Se corrigieron los tipos de datos, convirtiendo columnas como `Cargos_Totales` a formato numérico (`float`) para permitir el cálculo de estadísticas descriptivas.

## 3. Análisis Exploratorio de Datos (Hallazgos Clave)

El análisis de distribución y segmentación de la evasión reveló los siguientes patrones críticos:

### 3.1. Riesgo por Variables Categóricas

Los tres principales impulsores de la evasión son:
* **Compromiso Contractual:** Los clientes con **Contrato Mes a Mes** son el grupo de más alto riesgo, con una tasa de evasión muy superior a los contratos de uno o dos años.
* **Tipo de Servicio:** El servicio de **Fibra Óptica** está fuertemente correlacionado con una mayor tasa de cancelación, sugiriendo problemas de calidad o experiencia de usuario en este servicio.
* **Método de Pago:** El **Pago con Cheque Electrónico** es el método de pago con la mayor propensión a la evasión, indicando fricción operacional.

### 3.2. Riesgo por Variables Numéricas

* **Permanencia (Tenure):** La gran mayoría de la evasión se produce en la **etapa inicial del ciclo de vida del cliente** (los primeros meses), destacando una debilidad en el proceso de *onboarding* o satisfacción inicial.
* **Cargos Mensuales:** Los clientes con **cargos mensuales altos** (servicios *premium* o *bundles*) son más propensos a evadir que los clientes con cargos bajos.

### 3.3. Palancas de Retención

Los servicios de valor añadido como **Soporte Técnico** y **Seguridad Online** actúan como fuertes factores de retención, ya que su presencia disminuye significativamente la tasa de evasión.