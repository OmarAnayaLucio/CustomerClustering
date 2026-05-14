# Customer Segmentation using K‑Means (RFM + Psychographic Data)

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

This project segments customers who have made a purchase based on their:

- **Monetary value** (total spent)
- **Purchase frequency** (number of transactions)
- **Demographics** (age, gender, number of children)
- **Psychographic traits** (interest in investment, patrimony, speed; personality traits like tranquility, insistence, distrust, emotionality, impatience, control, hostility, etc.)

The segmentation is performed using **K‑Means clustering** after standardizing the features. The optimal number of clusters is selected via the **elbow method**.

## Data Source

The raw data comes from a **public Google Sheet**
The script downloads the sheet directly as a CSV (no authentication required because it is public).

## Features Used

| Category | Features |
|----------|----------|
| **RFM** | Monetary (sum of `PRECIO TOTAL`), Frequency (count of records per customer) |
| **Demographics** | `edad`, `sexo` (M/F), `hijos` |
| **Interests** | `interes_inversion`, `interes_patrimonio`, `interes_rapidez` |
| **Personality traits** | `rasgo_tranquilo`, `rasgo_insistente`, `rasgo_desconfiado`, `rasgo_emocional`, `rasgo_impaciente`, `rasgo_controlador`, `hostil`, `insistencia_num` |

Missing values are imputed with the median (numerical) or mode (categorical). The `sexo` column is one‑hot encoded.

## Project Structure

├── README.md
├── requirements.txt
├── .gitignore
├── src/
│ └── segment_customers.py
├── results/
│ ├── segmentos_clientes.csv # (generated)
│ └── elbow.png # (generated)
└── notebooks/ # optional

 ----------------------------- RESULTS --------------------------------

results/segmentos_clientes.csv – each customer with assigned segment.
results/elbow.png – plot to validate the number of clusters.

Output Interpretation
The CSV file contains the following columns:

Column	Description
Cliente	Customer name (original)
Segmento	Cluster ID (0, 1, 2, …)
Segmento_Nombre	Descriptive label (Alto Valor, Adulto Tranquilo, Impaciente, Estándar)
Monetary	Total amount spent
Frequency	Number of purchase records
edad	Age
sexo	Gender (M/F)

Example of Segment Profiles (from real data)

Segment 0: 32 customers – High Monetary, high insistence, young age → "Impulsive Buyers"
Segment 1: 18 customers – Older, high tranquility, medium spend → "Calm Seniors"
Segment 2: 25 customers – Very high Monetary (>50k), low Recency → "Premium Customers"
Segment 3: 10 customers – Low spend, low frequency, medium age → "At Risk / Occasional"

Dependencies
Python 3.8+

pandas

numpy

requests

scikit‑learn

matplotlib

See requirements.txt for exact versions.

License
MIT – use freely for business or academic purposes.

Author
[Your Name] – [your.email@example.com]
