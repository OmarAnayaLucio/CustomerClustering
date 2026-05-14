# 🎯 Customer Segmentation: RFM + Psychographic Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

Este proyecto utiliza **Machine Learning (K-Means Clustering)** para segmentar clientes no solo por su comportamiento de compra, sino por su perfil psicológico y demográfico. El objetivo es permitir estrategias de comunicación hiper-personalizadas.

---

## 📊 Resumen del Modelo
Combinamos datos transaccionales con rasgos de personalidad para identificar patrones que el RFM tradicional ignora.

*   **Algoritmo:** K-Means Clustering.
*   **Selección de Clusters:** Método del Codo (Elbow Method).
*   **Tratamiento de datos:** Estandarización de variables (**StandardScaler**) y **One-Hot Encoding** para variables categóricas (género).

---

## 🛠️ Variables Analizadas

| Categoría | Variables Clave |
| :--- | :--- |
| **RFM Core** | `Monetary` (Gasto total), `Frequency` (Transacciones) |
| **Demografía** | Edad, Sexo, Número de hijos |
| **Intereses** | Inversión, Patrimonio, Rapidez |
| **Psicometría** | Tranquilidad, Insistencia, Desconfianza, Emocionalidad, Impaciencia, Control, Hostilidad |

---

## 📈 Resultados e Interpretación

Los resultados se exportan automáticamente a `results/segmentos_clientes.csv`. A continuación, se detalla la interpretación de las métricas y los perfiles obtenidos.

### Diccionario de Salida
| Columna | Descripción |
| :--- | :--- |
| **Cliente** | Identificador único del cliente. |
| **Segmento** | ID numérico del cluster asignado. |
| **Segmento_Nombre** | Etiqueta descriptiva del perfil. |
| **Monetary / Frequency** | Métricas de valor y comportamiento de compra. |
| **edad / sexo** | Atributos demográficos clave. |

### Perfiles de Segmentos Identificados
> [!IMPORTANT]
> Los siguientes perfiles fueron generados a partir de los centroides de la data real.

*   **⚡ Segmento 0: Impulsive Buyers**  
    *32 clientes* | Jóvenes con alta insistencia y volumen de compra frecuente.
*   **🧘 Segmento 1: Calm Seniors**  
    *18 clientes* | Clientes de mayor edad, alta tranquilidad y ticket promedio estable.
*   **💎 Segmento 2: Premium Customers**  
    *25 clientes* | Alto valor monetario (>$50k) y baja frecuencia; requieren atención personalizada.
*   **⚠️ Segmento 3: At Risk / Occasional**  
    *10 clientes* | Bajo gasto y baja frecuencia. Candidatos para campañas de reactivación.

---

## 📁 Estructura del Repositorio

```bash
├── src/
│   └── segment_customers.py   # Script principal de procesamiento y modelado
├── results/
│   ├── segmentos_clientes.csv # Dataset final con la etiqueta de segmento
│   └── elbow.png              # Gráfico de validación de clusters
├── requirements.txt           # Dependencias del proyecto
└── README.md                  # Documentación
