# Predicción de retención de clientes bancarios 🏦🔮

> **Análisis estratégico de fuga de clientes (Churn) y segmentación de cartera con Machine Learning.**

![Python](https://img.shields.io/badge/Python-3.8%2B-green)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Pandas](https://img.shields.io/badge/Library-Pandas-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 Tabla de contenidos
1. [Introducción y objetivos](#-introducción-y-objetivos)
2. [El equipo](#-el-equipo)
3. [Sobre el dataset](#-sobre-el-dataset)
4. [Tecnologías utilizadas](#-tecnologías-utilizadas)
5. [Metodología paso a paso](#-metodología-paso-a-paso)
6. [Resultados y conclusiones](#-resultados-y-conclusiones)
7. [Cómo ejecutar el proyecto](#-cómo-ejecutar-el-proyecto)

---

## 📖 Introducción y objetivos

En el entorno bancario actual, la retención de clientes es significativamente más rentable que la adquisición de nuevos. Este proyecto nace de la necesidad de transformar un enfoque reactivo en uno **proactivo**.

Nuestro análisis se centra en dos grandes misiones para responder a preguntas críticas de negocio:

* **Misión 1: Predicción (Supervisada)**: ¿Podemos anticipar con alta precisión qué clientes abandonarán la entidad (Churn) para activar protocolos de retención?
* **Misión 2: Segmentación (No Supervisada)**: ¿Existen perfiles de clientes ocultos que requieran estrategias de marketing diferenciadas?

## 👥 El equipo

Este trabajo ha sido desarrollado con rigor académico y visión de negocio por:

* **María Luisa Ros Bolea**
* **Pablo Martínez Seco de Herrera**
* **Juan Diego Valencia Marín**

---

## 📊 Sobre el dataset

Hemos trabajado con un conjunto de datos de **10.000 clientes** de una entidad bancaria europea (Francia, Alemania y España).

**Variables clave:**
* `CreditScore`: Puntuación crediticia.
* `Geography` y `Gender`: Datos demográficos.
* `Age` y `Tenure`: Edad y antigüedad en el banco.
* `Balance`: Saldo en cuenta.
* `NumOfProducts`: Productos contratados.
* `HasCrCard` y `IsActiveMember`: Tenencia de tarjeta y actividad.
* `EstimatedSalary`: Salario estimado.
* **Target (`Exited`)**: 1 si el cliente abandonó, 0 si permanece.

---

## 🛠 Tecnologías utilizadas

El proyecto se ha desarrollado íntegramente en **Python**, utilizando las siguientes librerías para el análisis y modelado:

* **Procesamiento de datos**: `pandas`, `numpy`
* **Visualización**: `matplotlib`, `seaborn` (mapas de calor, distribución de variables)
* **Machine Learning**: `scikit-learn`
    * *Preprocesado*: `LabelEncoder`, `StandardScaler`, `OneHotEncoder`
    * *Modelos*: `RandomForestClassifier`, `GradientBoostingClassifier`, `KMeans`, `DBSCAN`

---

## 🚀 Metodología paso a paso

Para garantizar la excelencia técnica ("Matrícula de Honor"), hemos seguido un flujo de trabajo estructurado:

### 1. Limpieza y análisis exploratorio (EDA)
Realizamos una "radiografía" inicial de los datos.
* Detectamos un desbalance de clases: la tasa de abandono real es del **20,4%**.
* Identificamos correlaciones clave: la **Edad** y el **Saldo** influyen positivamente en el abandono, mientras que ser un **Miembro Activo** lo reduce.

### 2. Preprocesado de datos
Preparamos los datos para que los algoritmos puedan "digerirlos" correctamente:
* Eliminación de variables ruidosas (`RowNumber`, `Surname`).
* Transformación de categóricas (`Geography`, `Gender`) mediante **One-Hot Encoding**.
* Escalado de variables numéricas para modelos sensibles a la distancia.

### 3. Modelado supervisado (Predicción de Churn)
Probamos y comparamos varios algoritmos. Nuestra métrica estrella fue el **Recall (Sensibilidad)**, ya que en este negocio es más costoso no detectar a un cliente que se va (Falso Negativo) que equivocarnos con uno que se queda.
* **Modelos ganadores**: *Gradient Boosting* y *Random Forest*. Ofrecieron el mejor equilibrio para detectar clientes en riesgo.

### 4. Modelado no supervisado (Clustering)
Buscamos patrones ocultos.
* Fuimos críticos con *DBSCAN* (no se ajustó bien a la densidad de estos datos).
* Optamos por **K-Means**, logrando identificar segmentos claros (ej. "Ahorradores Senior", "Jóvenes Activos") para personalizar campañas.

---

## 🏆 Resultados y conclusiones

La aplicación de estos modelos permite al banco:

1.  **Reducir la fuga**: Identificando a 1 de cada 5 clientes que estadísticamente abandonaría la entidad.
2.  **Optimizar Marketing**: Dejar de "matar moscas a cañonazos" y dirigir ofertas específicas según el cluster del cliente (ej. productos de inversión para seniors con alto saldo).
3.  **Monitoreo continuo**: Establecer un sistema de alerta temprana basado en el comportamiento transaccional.

> *Hemos demostrado que el uso de datos no solo predice el futuro, sino que permite cambiarlo.*

---

## 💻 Cómo ejecutar el proyecto

1.  Clona este repositorio:
    ```bash
    git clone [https://github.com/tu-usuario/bank-churn-prediction.git](https://github.com/tu-usuario/bank-churn-prediction.git)
    ```
2.  Instala las dependencias necesarias:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  Abre el notebook principal para ver el análisis completo:
    ```bash
    jupyter notebook "Practica Final.ipynb"
    ```

---
*Proyecto realizado en diciembre de 2025.*
