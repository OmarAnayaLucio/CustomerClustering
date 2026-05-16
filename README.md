# 🎯 Customer Segmentation: RFM + Psychographic Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

Este proyecto utiliza K-Means Clustering para segmentar clientes basándose en su comportamiento financiero, rasgos psicológicos y datos demográficos. El objetivo es definir parámetros precisos para campañas en Facebook e Instagram y optimizar una inversión mensual de $5,000 MXN.

📌 Resumen del Modelo
Combinamos variables transaccionales (precio_total, anticipo) con rasgos de personalidad (tranquilo, insistente, desconfiado, etc.) e intereses (inversión, patrimonio) para identificar patrones de compra que el RFM tradicional no captura.

Algoritmo: K-Means Clustering

Selección de clusters: Método del Codo + Silhouette Score + validación de tamaño mínimo por cluster

<img width="504" height="329" alt="image" src="https://github.com/user-attachments/assets/0b4e0898-5dd2-4267-a7cc-f2739831e038" />

<img width="438" height="296" alt="image" src="https://github.com/user-attachments/assets/4e53551f-2741-45a5-a3ca-fbe6e2167425" />


Preprocesamiento:

Estandarización con StandardScaler

Eliminación de outliers (percentil 99 para precio_total y anticipo)

Manejo de valores nulos

Número de clusters: k=3 (balanceados, ninguno con menos del 5% de los datos)

## 📊 Variables utilizadas en la segmentación

| Categoría | Variables usadas | ¿Por qué importan para el negocio? |
|-----------|----------------|--------------------------------------|
| **Valor económico** | `precio_total`, `anticipo`, `duración` | Diferencian el poder adquisitivo y la capacidad de pago. Un inversionista paga más y da anticipos mayores. |
| **Intención de compra** | `interes_inversion`, `interes_patrimonio`, `interes_rapidez` | Capturan el objetivo del cliente: ¿quiere ganar dinero o tener un hogar? Es la base de la segmentación. |
| **Rasgos de personalidad** | `rasgo_tranquilo`, `insistente`, `desconfiado`, `emocional`, `controlador`, `hostil` | Determinan cómo debemos comunicarnos. Un controlador necesita datos duros; un emocional, testimonios y confianza. |
| **Datos demográficos** | `edad`, `sexo`, `profesión_cat` | Ayudan a afinar los parámetros de audiencia en Meta Ads (rangos de edad, género, intereses laborales). |


📈 Resultados e Interpretación

El modelo asigna a cada cliente un cluster (0,1,2) y una etiqueta descriptiva. Los resultados se guardan en resultados/clientes_segmentados.csv. A continuación, los perfiles obtenidos de tus datos reales (después de limpiar outliers):

🔴 Cluster 0: Inversionistas Estratégicos
32 clientes (42% del total)

Edad media: 52 años (rango 40-67)

Género: 60% hombres, 40% mujeres

Ticket promedio: $1,850,000 MXN

Rasgos: Controladores, racionales, desconfiados al inicio, buscan rendimiento

Objetivo: Plusvalía, renta, múltiples propiedades

Ejemplo real: Gerardo Alvirde Acosta (comerciante, 53 años, varias propiedades)

🔵 Cluster 1: Patrimoniales Tranquilos
28 clientes (37% del total)

Edad media: 44 años (rango 30-60)

Género: 75% mujeres, 25% hombres

Ticket promedio: $850,000 MXN

Rasgos: Emocionales, tranquilos, buscan seguridad, a veces ansiosos

Objetivo: Hogar permanente, cercanía a escuelas/trabajo

Ejemplo real: Lilia Parra Hernández (docente, 54 años)

🟢 Cluster 2: Aspiracionales / Alto Nivel
16 clientes (21% del total)

Edad media: 36 años (rango 25-50)

Género: Equilibrado (50% hombres, 50% mujeres)

Ticket promedio: $1,200,000 MXN

Rasgos: Confiados, buscan reconocimiento, sin prisa pero con altas expectativas

Objetivo: Estatus, zonas premium (Roma, Condesa, Polanco), calidad de vida

Ejemplo real: Roberto Allan David Sohn (comediante, 59 años, alto nivel)

✅ Nota: Ningún cluster tiene menos de 15 clientes, garantizando viabilidad para campañas de marketing.

🎯 Aplicación a Estrategia de Pauta (Meta Ads)
Con estos clusters, puedes asignar $5,000 mensuales de la siguiente manera:

Cluster	% Gasto	Monto	Objetivo Meta	Parámetros clave
Inversionista	40%	$2,000	Leads / Conversiones	Edad 40-65, intereses financieros, horario 7-10 pm
Patrimonial	35%	$1,750	Tráfico / Mensajes	Edad 30-55, mujeres, intereses hogar, 12-3 pm
Aspiracional	25%	$1,250	Alcance / Engagement	Edad 25-45, zonas trendy, horario 6-9 pm


## 📁 Estructura del Repositorio

├── src/
│ └── cluster_segmentacion.py # Script principal: carga datos, limpia, clusteriza y exporta
├── resultados/
│ ├── clientes_segmentados.csv # Dataset original + columna 'cluster' y 'segmento_nombre'
│ ├── elbow_silhouette.png # Gráfico de validación (método del codo y silhouette score)
│ └── scatterplot_clusters.png # Visualización 2D (precio_total vs anticipo) por cluster
├── requirements.txt # Dependencias del proyecto (pandas, scikit-learn, matplotlib, seaborn)
└── README.md # Documentación completa del proyecto



<div align="center">

# 🏢 Segmentación Estratégica de Clientes
### *Machine Learning aplicado al sector inmobiliario*

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.4+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Status](https://img.shields.io/badge/Estado-Producción-59B2B2?style=for-the-badge)](.)
[![License](https://img.shields.io/badge/Licencia-MIT-green?style=for-the-badge)](LICENSE)

<img src="https://img.shields.io/badge/Powered%20by-Altaltium-000000?style=flat-square&logoColor=white" />

---

> **Modelo de K-Means Clustering** que combina variables transaccionales, rasgos psicológicos y datos demográficos para identificar perfiles de compradores y optimizar campañas de pauta digital en Meta Ads con un presupuesto de **$5,000 MXN/mes**.

</div>

---

## 📋 Tabla de Contenidos

- [¿Por qué este modelo?](#-por-qué-este-modelo)
- [Arquitectura del pipeline](#-arquitectura-del-pipeline)
- [Variables del modelo](#-variables-del-modelo)
- [Resultados: Perfiles de Clientes](#-resultados-perfiles-de-clientes)
- [Estrategia de Pauta Meta Ads](#-estrategia-de-pauta-meta-ads)
- [Instalación y Uso](#-instalación-y-uso)
- [Estructura del Repositorio](#-estructura-del-repositorio)
- [Stack Tecnológico](#-stack-tecnológico)

---

## 🎯 ¿Por qué este modelo?

El RFM tradicional *(Recency, Frequency, Monetary)* no es suficiente para el sector inmobiliario. Una sola compra puede representar más de **$1,000,000 MXN** y la decisión está influenciada por factores emocionales, de estatus y de perfil financiero que un modelo transaccional no captura.

```
RFM clásico  →  ¿Cuándo / cuántas veces / cuánto compró?  ✗  Incompleto
Este modelo  →  ¿Quién es, qué quiere y cómo decide?     ✓  Estratégico
```

Este proyecto combina **tres dimensiones** para segmentar con precisión:

| Dimensión | Qué captura |
|---|---|
| 💰 **Transaccional** | Poder adquisitivo real, ticket, frecuencia, recencia |
| 🧠 **Psicológica** | Rasgos de personalidad que definen cómo se comunica el cliente |
| 👤 **Demográfica** | Edad, género y ubicación para afinar audiencias en Meta |

---

## ⚙️ Arquitectura del Pipeline

```
┌─────────────────────────────────────────────────────────────────┐
│                        PIPELINE COMPLETO                        │
└─────────────────────────────────────────────────────────────────┘

  [Google Sheets]  ──→  [Limpieza & Parseo]  ──→  [Agregación RFM]
        │                      │                          │
        │               • Precios (MXN)              • Monetary
        │               • Fechas (multi-fmt)         • Frequency
        │               • Columnas inválidas         • Recency
        │
        ▼
  [Preprocesamiento]  ──→  [K-Means k=4]  ──→  [Perfilado]
        │                       │                    │
        │  • SimpleImputer       │  • StandardScaler  │  • Etiquetas
        │  • OneHotEncoder       │  • n_init=10       │  • Dashboard
        │  • Validación cols     │  • random_state=42 │  • CSV Export
```

**Selección de K óptimo:**
- 📈 Método del Codo *(Elbow Method)*
- 📊 Silhouette Score
- ✅ Validación: ningún cluster con menos del **5%** de los datos

---

## 📊 Variables del Modelo

### Variables Transaccionales (RFM)
| Variable | Descripción |
|---|---|
| `Monetary` | Suma total de compras por cliente |
| `Frequency` | Número de transacciones |
| `Recency` | Días desde la última compra |

### Variables de Intención de Compra
| Variable | Escala | Insight de negocio |
|---|---|---|
| `interes_inversion` | 1-5 | ¿Busca rendimiento económico? |
| `interes_patrimonio` | 1-5 | ¿Busca un hogar permanente? |
| `interes_rapidez` | 1-5 | ¿Tiene urgencia en la decisión? |

### Rasgos de Personalidad
| Variable | Cómo impacta la comunicación |
|---|---|
| `rasgo_tranquilo` | Proceso de venta largo, sin presión |
| `rasgo_controlador` | Necesita datos duros, cifras y comparativas |
| `rasgo_emocional` | Responde a testimonios y confianza |
| `rasgo_desconfiado` | Requiere pruebas sociales y garantías escritas |
| `rasgo_insistente` | Follow-up frecuente, alta motivación |
| `rasgo_impaciente` | Cierres rápidos, procesos simplificados |
| `hostil` | Manejo especial, sin presión |

---

## 🔬 Resultados: Perfiles de Clientes

### 🔴 Cluster 0 — Inversionistas Estratégicos
> *42% del total · 32 clientes*

```
Edad media    ████████████████████  52 años (rango 40-67)
Género        ██████████████        60% hombres / 40% mujeres
Ticket prom.  $1,850,000 MXN
```

**Perfil:** Racionales, controladores y desconfiados al inicio. Buscan plusvalía, rendimiento y múltiples propiedades. Responden a datos duros y proyecciones financieras.

**Ejemplo real:** *Gerardo Alvirde Acosta, comerciante, 53 años, varias propiedades.*

---

### 🔵 Cluster 1 — Patrimoniales Tranquilos
> *37% del total · 28 clientes*

```
Edad media    ████████████████      44 años (rango 30-60)
Género        ██████████████████    75% mujeres / 25% hombres
Ticket prom.  $850,000 MXN
```

**Perfil:** Emocionales, tranquilos, buscan seguridad y hogar permanente. Valoran cercanía a escuelas y trabajo. Deciden con el corazón, necesitan confianza antes de avanzar.

**Ejemplo real:** *Lilia Parra Hernández, docente, 54 años.*

---

### 🟢 Cluster 2 — Aspiracionales de Alto Nivel
> *21% del total · 16 clientes*

```
Edad media    ████████████          36 años (rango 25-50)
Género        ██████████            50% hombres / 50% mujeres
Ticket prom.  $1,200,000 MXN
```

**Perfil:** Confiados, orientados al estatus y calidad de vida. Sin prisa pero con altas expectativas. Prefieren zonas premium (Roma, Condesa, Polanco) y responden al lifestyle branding.

**Ejemplo real:** *Roberto Allan David Sohn, comediante, 59 años, alto nivel.*

---

## 📣 Estrategia de Pauta Meta Ads

> Distribución mensual optimizada de **$5,000 MXN**

| Cluster | Presupuesto | Objetivo Meta | Edad | Género | Horario clave |
|---|---|---|---|---|---|
| 🔴 Inversionista | **$2,000** (40%) | Leads / Conversiones | 40–65 | Mixto | 🕖 7–10 pm |
| 🔵 Patrimonial | **$1,750** (35%) | Tráfico / Mensajes | 30–55 | Mujeres | 🕛 12–3 pm |
| 🟢 Aspiracional | **$1,250** (25%) | Alcance / Engagement | 25–45 | Mixto | 🕕 6–9 pm |

**Intereses sugeridos por cluster:**
- 🔴 *Inversión inmobiliaria, bienes raíces, finanzas personales, FIBRAS*
- 🔵 *Hogar, familia, educación, comunidad, seguridad*
- 🟢 *Lifestyle, arquitectura, diseño, zonas premium, viajes*

---

## 🚀 Instalación y Uso

### Requisitos
```bash
Python >= 3.10
```

### 1. Clona el repositorio
```bash
git clone https://github.com/tuusuario/segmentacion-clientes-altaltium.git
cd segmentacion-clientes-altaltium
```

### 2. Instala dependencias
```bash
pip install -r requirements.txt
```

### 3. Ejecuta el modelo
```bash
python src/SegmentacionClientes.py
```

### Outputs generados
```
✅  dashboard_altaltium.png   →  Dashboard visual con 4 gráficas analíticas
✅  segmentos_clientes.csv    →  Dataset con cluster asignado por cliente
```

---

## 📁 Estructura del Repositorio

```
segmentacion-clientes-altaltium/
│
├── 📂 src/
│   └── SegmentacionClientes.py      # Pipeline completo: carga → limpieza → clusters → export
│
├── 📂 resultados/
│   ├── clientes_segmentados.csv     # Dataset + columnas 'Segmento' y 'Segmento_Nombre'
│   ├── dashboard_altaltium.png      # Dashboard: edad, boxplot, alcaldías, scatter
│   ├── elbow_silhouette.png         # Validación del k óptimo
│   └── scatterplot_clusters.png     # Visualización 2D por cluster
│
├── requirements.txt                 # Dependencias del proyecto
├── LICENSE
└── README.md
```

---

## 🛠️ Stack Tecnológico

<div align="center">

| Librería | Uso |
|---|---|
| `pandas` | Carga, limpieza y agregación de datos |
| `numpy` | Operaciones numéricas y manejo de nulos |
| `scikit-learn` | K-Means, StandardScaler, Imputers, OneHotEncoder |
| `matplotlib` + `seaborn` | Dashboard visual y gráficas analíticas |
| `requests` | Ingesta desde Google Sheets vía URL |

</div>

---

<div align="center">

**Desarrollado con ❤️ para [Altaltium](https://altaltium.com)**

*¿Tienes preguntas sobre el modelo o quieres adaptarlo a tu negocio?*
*Abre un [Issue](../../issues) o contáctanos directamente.*

---

`#MachineLearning` `#RealEstate` `#CustomerSegmentation` `#KMeans` `#MetaAds` `#Python`

</div>
