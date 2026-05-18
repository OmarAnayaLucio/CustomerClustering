# 🎯 Customer Segmentation: Psychographic Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

🎯 Objetivo del Proyecto
Diseñar e implementar un sistema de segmentación de clientes basado en datos históricos de compra de inmuebles, con el fin de:

Identificar perfiles comerciales diferenciados (Alto Valor, Inversionista, Aspiracional, Patrimonial).

Personalizar estrategias de marketing, ventas y fidelización.

Priorizar recursos comerciales según el retorno esperado.

Proveer explicabilidad total de la asignación de cada cliente.

El proyecto evolucionó desde un enfoque de Machine Learning no supervisado (K‑Means) hacia un sistema de reglas de negocio que refleja el conocimiento experto del equipo y garantiza la transparencia en la toma de decisiones.

🤖 ¿Qué algoritmo se usó y por qué?
🔍 Fase 1: Exploración con Machine Learning (K‑Means)
Inicialmente se aplicó K‑Means (algoritmo de clustering no supervisado) sobre características como: edad, precio total, hijos, profesión codificada, interés en inversión y rasgos de personalidad. El objetivo era encontrar agrupaciones naturales en los datos.

Resultados obtenidos:

Se generaron 4 clústeres con distribuciones demográficas y de gasto diferenciadas.

Sin embargo, la interpretación comercial de los clústeres era ambiguay no alineada con la lógica del negocio.

Por ejemplo, un clúster mezclaba inversionistas de alto poder adquisitivo con patrimoniales de mediano ticket.

La falta de explicabilidad (no se podía decir fácilmente por qué un cliente caía en un clúster) dificultaba su uso en el día a día.

✅ Fase 2: Adopción de Reglas de Negocio (enfoque actual)
Tras evaluar los resultados, se optó por un sistema basado en reglas explícitas (no ML) que:

Utiliza conocimiento de dominio (equipo comercial, históricos de comportamiento).

Es totalmente interpretable: cada cliente tiene una razón clara de su segmento.

Permite ajustes ágiles (cambiar umbrales, agregar condiciones) sin reentrenar modelos.

Se puede auditar y validar fácilmente con el equipo de negocio.

Conclusión: El proyecto demuestra que no siempre el ML es la mejor opción. Cuando la interpretabilidad y la alineación con el negocio son críticas, las reglas simples pueden superar a modelos complejos.

📐 Reglas de Segmentación (orden de prioridad)
Segmento	Reglas (aplicadas secuencialmente)
🥇 Alto Valor	– Precio máximo individual > 4 M MXN
– Profesión = “figura pública”
– Posee > 3 propiedades
📈 Inversionista	– Compró > 1 propiedad con nosotros
– Precio máximo > 2.5 M MXN
– Contiene “inversionista” en comentarios
🌱 Aspiracional	– Edad ≤ 39 años (y no clasificado antes)
🏡 Patrimonial	– Resto de clientes (edad > 39, puede tener hijos, precio moderado)
📊 Perfiles de Segmento (con estadísticas reales)
🥇 Cluster 0: Alto Valor
14 clientes (6% del total)

Edad media: 54 años (rango 40–71)

Género: 64% hombres, 36% mujeres

Ticket promedio: $4,350,000 MXN

Propiedades promedio: 2.8 inmuebles

Rasgos: Alto poder adquisitivo, toman decisiones rápidas, buscan exclusividad y plusvalía.

Objetivo comercial: Captar referidos, ofrecer proyectos premium, mantener relación personalizada.

Ejemplo real: Adriana Marcela Sidorchuk – Magistrada, 53 años, con 4 propiedades y una inversión total que supera los $7 M MXN.

📈 Cluster 1: Inversionistas Estratégicos
28 clientes (12% del total)

Edad media: 45 años (rango 30–65)

Género: 68% hombres, 32% mujeres

Ticket promedio: $1,950,000 MXN

Propiedades promedio: 1.8 inmuebles

Rasgos: Controladores, racionales, desconfiados al inicio, buscan rendimiento (renta o reventa).

Objetivo comercial: Mostrar proyectos con alta plusvalía, opciones de renta, esquemas de financiamiento flexibles.

Ejemplo real: Gerardo Alvirde Acosta – Comerciante, 53 años, ha comprado 3 propiedades con nosotros, con una inversión total de $2.5 M MXN.

🌱 Cluster 2: Aspiracionales (Primera Vivienda)
16 clientes (7% del total)

Edad media: 31 años (rango 20–39)

Género: 56% mujeres, 44% hombres

Ticket promedio: $620,000 MXN

Anticipo promedio: $280,000 MXN

Rasgos: Jóvenes, entusiastas, sensibles al precio, buscan independencia.

Objetivo comercial: Ofrecer créditos accesibles, propiedades funcionales, contenido educativo sobre compra de vivienda.

Ejemplo real: Anahi Uribe Fuentes – Diseñadora gráfica, 27 años, su primera propiedad con apoyo familiar.

🏡 Cluster 3: Patrimonial (Hogar y Familia)
172 clientes (75% del total)

Edad media: 53 años (rango 40–78)

Género: 52% hombres, 48% mujeres

Ticket promedio: $890,000 MXN

Hijos promedio: 0.8 (muchos con 2 o más)

Rasgos: Buscan estabilidad, vivienda para habitar, valoran ubicación y seguridad.

Objetivo comercial: Enfoque en zonas familiares, escuelas, servicios; promociones de referidos.

Ejemplo real: Mario Alberto Chávez Díaz – Jubilado, 70 años, compró 3 propiedades para sus hijos.




📁 Estructura del Repositorio

📦 customer-segmentation/
├── 📄 segmentacion_clientes.py          # Script principal (reglas + gráficos)
├── 📄 segmentacion_con_explicacion.csv  # Resultado final (cliente + segmento + explicación)
├── 📊 barras_segmentos.png              # Gráfico de barras de distribución
├── 📈 scatter_segmentos_final.png       # Dispersión Edad vs Precio Máximo
├── 📄 requirements.txt                  # Dependencias Python
└── 📖 README.md                         # Este documento


📄 Licencia
Uso interno. No redistribuir sin autorización.
