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
