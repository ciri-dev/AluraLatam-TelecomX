# 📉 Análisis de Evasión de Clientes (Churn) - TelecomX

Este proyecto consiste en un análisis de datos exploratorio (EDA) para **TelecomX**, una empresa de telecomunicaciones. El objetivo principal es identificar los factores que contribuyen a la evasión de clientes (Churn) y proponer estrategias basadas en datos para mejorar la retención.

## 📋 Tabla de Contenidos
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Estructura de los Datos](#estructura-de-los-datos)
- [Metodología (ETL y EDA)](#metodología-etl-y-eda)
- [Principales Hallazgos](#principales-hallazgos)
- [Cómo Ejecutar el Proyecto](#cómo-ejecutar-el-proyecto)

## 📖 Descripción del Proyecto
La pérdida de clientes es uno de los problemas más costosos para las empresas de servicios. Este análisis procesa un dataset en formato JSON anidado, lo limpia, lo transforma y visualiza patrones clave para responder a preguntas como:
- ¿Qué tipo de contrato tiene mayor tasa de abandono?
- ¿Influye el método de pago en la lealtad del cliente?
- ¿Cómo afecta la antigüedad y el monto de la factura en la decisión de irse?

## 🛠 Tecnologías Utilizadas
El proyecto está desarrollado en **Python** utilizando las siguientes librerías:
*   **Pandas:** Manipulación de datos y normalización de JSON.
*   **NumPy:** Operaciones numéricas.
*   **Matplotlib & Seaborn:** Visualización de datos y generación de gráficos estadísticos.
*   **JSON:** Módulo nativo para la carga de datos estructurados.

## 📂 Estructura de los Datos
El archivo fuente es `TelecomX_Data.json`. Originalmente contiene objetos anidados (ej. `account.Charges.Total`), los cuales fueron aplanados durante el proceso.

Las variables principales analizadas (traducidas al español) incluyen:
*   `Abandono` (Target): Si el cliente canceló el servicio.
*   `Meses_Permanencia`: Tiempo en meses que el cliente lleva en la empresa.
*   `Cargos_Mensuales`: Monto facturado mensualmente.
*   `Tipo_Contrato`: Mensual, 1 año o 2 años.
*   `Metodo_Pago`: Cheque electrónico, tarjeta de crédito, etc.

## ⚙️ Metodología (ETL y EDA)

### 1. Limpieza y Preprocesamiento
*   **Carga:** Ingesta de JSON y normalización con `pd.json_normalize`.
*   **Limpieza:** Eliminación de registros con `Churn` vacío y conversión de `TotalCharges` a numérico (rellenando nulos con 0).
*   **Transformación:** Traducción de columnas al español y creación de variables binarias (`Abandono_Binario`) y calculadas (`Cuentas_Diarias`).

### 2. Análisis Exploratorio
*   Estadísticas descriptivas para detectar outliers.
*   Visualización de la distribución del Churn (desbalance de clases).
*   Análisis bivariado (Categóricas vs Churn y Numéricas vs Churn).

## 💡 Principales Hallazgos (Insights)
1.  **Contratos:** Los clientes con contratos **"Mes a mes"** tienen la tasa de abandono más alta.
2.  **Antigüedad:** El riesgo de fuga es crítico durante los **primeros 12 meses**.
3.  **Pagos:** El método de pago **"Electronic check"** está fuertemente correlacionado con el abandono.
4.  **Costos:** Los clientes que abandonan suelen tener facturas mensuales más elevadas que el promedio.

## 🚀 Cómo Ejecutar el Proyecto

1.  Clona este repositorio o descarga los archivos.
2.  Asegúrate de tener instalado Python y las librerías necesarias:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
3.  Coloca el archivo `TelecomX_Data.json` en el mismo directorio que el script o notebook.
4.  Ejecuta el archivo `.py` o abre el Jupyter Notebook para ver el análisis paso a paso.

---
**Autor:** Ciro Rivera  
**Estado:** Finalizado
