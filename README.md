# 🏢 Customer Segmentation: Psychographic Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue) ![Pandas](https://img.shields.io/badge/Pandas-2.0-green) ![Scikit‑learn](https://img.shields.io/badge/Scikit--learn-1.3-orange) ![License](https://img.shields.io/badge/License-Internal%20Use-lightgrey)

> **De K‑Means a reglas de negocio**: un enfoque híbrido para segmentar clientes inmobiliarios con total interpretabilidad.

---

## 🎯 Objetivo del Proyecto

Diseñar e implementar un sistema de segmentación de clientes basado en datos históricos de compra de inmuebles, con el fin de:

- Identificar perfiles comerciales diferenciados (**Alto Valor**, **Inversionista**, **Aspiracional**, **Patrimonial**).
- Personalizar estrategias de marketing, ventas y fidelización.
- Priorizar recursos comerciales según el retorno esperado.
- Proveer **explicabilidad total** de la asignación de cada cliente.

El proyecto evolucionó desde un enfoque de **Machine Learning no supervisado (K‑Means)** hacia un **sistema de reglas de negocio** que refleja el conocimiento experto del equipo y garantiza la transparencia en la toma de decisiones.

---

## 🤖 ¿Qué algoritmo se usó y por qué?

### 🔍 Fase 1: Exploración con Machine Learning (K‑Means)

Inicialmente se aplicó **K‑Means** (clustering no supervisado) sobre características como: edad, precio total, hijos, profesión codificada, interés en inversión y rasgos de personalidad. El objetivo era encontrar agrupaciones naturales en los datos.

**Resultados obtenidos:**

- ✅ Se generaron 4 clústeres con distribuciones demográficas y de gasto diferenciadas.
- ✅ La **interpretación comercial** de los clústeres se alineó con la lógica del negocio.
- ✅ Se incluye clúster de inversionistas de alto poder adquisitivo vs patrimoniales.

<img width="778" height="485" alt="image" src="https://github.com/user-attachments/assets/ef4ecda7-38f9-4237-b461-d59a08b59c17" />


### ✅ Fase 2: Adopción de Reglas de Negocio (enfoque actual)

Tras evaluar los resultados, se optó por un **sistema basado en reglas explícitas** (ML ajustado):
## 📐 Reglas de Segmentación (orden de prioridad)

| Segmento         | Reglas (aplicadas secuencialmente)                                                                                 |
|------------------|---------------------------------------------------------------------------------------------------------------------|
| 🥇 **Alto Valor**   | – Precio Mínimo individual > **2.5 M MXN**<br>– Profesión = “figura pública”<br>– Posee **> 3 propiedades**            |
| 📈 **Inversionista**| – Compró **> 1 propiedad** con nosotros<br>– Precio máximo > **2.5 M MXN**<br>– Contiene “inversionista” en comentarios |
| 🌱 **Aspiracional** | – Edad ≤ **39 años** Precio máximo individual > **2.5 M MXN**<br>                                                      |
| 🏡 **Patrimonial**  | – Edad > **39 años** Tiene hijos, precio moderado)                                             |

---

<img width="1183" height="670" alt="image" src="https://github.com/user-attachments/assets/0222f8ca-97e8-468d-84ac-6c3d617b8d57" />


## 📊 Perfiles de Segmento (estadísticas reales)

### 🥇 Cluster 0: Alto Valor  
**14 clientes (6% del total)**

| Característica       | Valor                                      |
|----------------------|--------------------------------------------|
| Edad media (rango)   | 54 años (40–71)                            |
| Género               | 64% hombres / 36% mujeres                  |
| Ticket promedio      | **$4,350,000 MXN**                         |
| Propiedades promedio | 2.8 inmuebles                              |
| Rasgos               | Alto poder adquisitivo, decisiones rápidas, buscan exclusividad y plusvalía. |
| Objetivo comercial   | Captar referidos, proyectos premium, relación personalizada. |
| **Ejemplo real**     | *Adriana Marcela Sidorchuk* – Magistrada, 53 años, 4 propiedades, inversión total > $7 M MXN. |

---

### 📈 Cluster 1: Inversionistas Estratégicos  
**28 clientes (12% del total)**

| Característica       | Valor                                      |
|----------------------|--------------------------------------------|
| Edad media (rango)   | 45 años (30–65)                            |
| Género               | 68% hombres / 32% mujeres                  |
| Ticket promedio      | **$1,950,000 MXN**                         |
| Propiedades promedio | 1.8 inmuebles                              |
| Rasgos               | Controladores, racionales, desconfiados al inicio, buscan rendimiento (renta o reventa). |
| Objetivo comercial   | Proyectos con plusvalía, opciones de renta, financiamiento flexible. |
| **Ejemplo real**     | *Gerardo Alvirde Acosta* – Comerciante, 53 años, 3 propiedades, inversión total $2.5 M MXN. |

---

### 🌱 Cluster 2: Aspiracionales (Primera Vivienda)  
**16 clientes (7% del total)**

| Característica       | Valor                                      |
|----------------------|--------------------------------------------|
| Edad media (rango)   | 31 años (20–39)                            |
| Género               | 56% mujeres / 44% hombres                  |
| Ticket promedio      | **$620,000 MXN**                           |
| Anticipo promedio    | $280,000 MXN                               |
| Rasgos               | Jóvenes, entusiastas, sensibles al precio, buscan independencia. |
| Objetivo comercial   | Créditos accesibles, propiedades funcionales, contenido educativo. |
| **Ejemplo real**     | *Anahi Uribe Fuentes* – Diseñadora gráfica, 27 años, primera propiedad con apoyo familiar. |

---

### 🏡 Cluster 3: Patrimonial (Hogar y Familia)  
**172 clientes (75% del total)**

| Característica       | Valor                                      |
|----------------------|--------------------------------------------|
| Edad media (rango)   | 53 años (40–78)                            |
| Género               | 52% hombres / 48% mujeres                  |
| Ticket promedio      | **$890,000 MXN**                           |
| Hijos promedio       | 0.8 (muchos con 2 o más)                   |
| Rasgos               | Buscan estabilidad, vivienda para habitar, valoran ubicación y seguridad. |
| Objetivo comercial   | Zonas familiares, escuelas, servicios, promociones de referidos. |
| **Ejemplo real**     | *Mario Alberto Chávez Díaz* – Jubilado, 70 años, compró 3 propiedades para sus hijos. |

---

## 📁 Estructura del Repositorio

```bash
📦 customer-segmentation/
├── 📄 segmentacion_clientes.py          # Script principal (reglas + gráficos)
├── 📄 segmentacion_con_explicacion.csv  # Resultado final (cliente + segmento + explicación)
├── 📊 barras_segmentos.png              # Gráfico de barras de distribución
├── 📈 scatter_segmentos_final.png       # Dispersión: Edad vs Precio Máximo
├── 📄 requirements.txt                  # Dependencias Python
└── 📖 README.md                         # Este documento

👥 Equipo y Contacto
Desarrollado para Altaltium – Inversiones Inmobiliarias
Por el equipo de Analítica de Datos.

📧 Correo: analytics@altaltium.com
🌐 Web: www.altaltium.com
