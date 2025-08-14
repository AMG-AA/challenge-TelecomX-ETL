# 📊 Challenge TelecomX ETL  
### Análisis de Evasión de Clientes con Python y Visualizaciones
<p align="center">
  <img width="720" alt="Alura+Oracle" src="https://github.com/user-attachments/assets/1701b8a4-43b5-4bae-9c09-8844db845484" />
</p>

<p align="center"><i>Proyecto desarrollado en el programa Alura + Oracle</i></p>

---

## 🧭 Tabla de Contenidos

- [🚀 Descripción General](#-descripción-general-del-proyecto)
- [📁 Estructura del Repositorio](#-estructura-del-repositorio)
- [🔑 Hallazgos Principales](#-hallazgos-principales)
- [🛠️ Herramientas Utilizadas](#️-herramientas-utilizadas)
- [⚙️ Configuración y Uso](#-configuración-y-uso)
- [🌟 Cómo Extender el Proyecto](#-cómo-extender-el-proyecto)
- [🤝 Contribuciones](#-contribuciones)
- [📬 Contacto](#-contacto)

---



## 🚀 Descripción General del Proyecto

**Telecom X** enfrenta un desafío crítico: una alta tasa de evasión de clientes (churn), con un 26.5% de cancelaciones. Este proyecto realiza un análisis ETL (Extracción, Transformación y Carga) para identificar los factores clave detrás del churn, como costos diarios altos y contratos cortos, y generar insights accionables para estrategias de retención.

Usando **Python**, **Pandas** y **Matplotlib**, procesamos datos de clientes, generamos datasets limpios y visualizamos patrones para apoyar modelos predictivos.

**🎯 Objetivo**: Reducir el churn mediante segmentación de clientes y estrategias basadas en datos, como ofrecer bundles personalizados y contratos a largo plazo.

---

# 📁 Estructura del Repositorio

| Directorio / Archivo | Contenido | Descripción |
|----------------------|-----------|-------------|
| `data/raw/` | `telecomx_raw.json` | Datos crudos extraídos de la API en formato JSON. |
| `data/processed/` | `telecom_df_bin.csv` | Variables Yes/No codificadas como 1/0 (22 columnas). |
|                      | `telecom_df_bin_known.csv` | Subset con churn conocido (7043 filas). |
|                      | `telecom_df_bin_unknown.csv` | Subset con churn desconocido (224 filas). |
|                      | `telecom_df_clean.csv` | Dataset limpio con 22 columnas + Cuentas_Diarias. |
|                      | `telecom_df_full.csv` | Dataset completo con 34 columnas (originales + binarias). |
| `notebooks/` | `01_data_extraction.ipynb` | Extracción y carga inicial de datos desde la API. |
|               | `02_data_cleaning.ipynb` | Limpieza, transformación y creación de variables derivadas. |
|               | `03_data_analysis.ipynb` | Análisis exploratorio (EDA) con métricas y visualizaciones. |
| `src/graficos/` | `*.png / *.html` | Gráficos estáticos e interactivos del análisis. |
| `requirements.txt` | Dependencias del proyecto | Incluye pandas, matplotlib, seaborn, plotly. |
| `README.md` | Documentación del proyecto | Este archivo. |

---

## 🔑 Hallazgos Principales

- 📉 **Alta tasa de churn**: 26.5% de los clientes (1869/7043) cancelan, especialmente en los primeros 18 meses (`kde_churn.png`).
- 💸 **Costo vs. lealtad**: Clientes con gastos diarios altos (> $2.5, correlación 0.19) churnean más, mientras que más servicios contratados (correlación -0.35) los retiene (`heatmap_corr.png`).
- ⚠️ **Factores de riesgo**: Contratos mensuales (42.7% churn) y pagos electrónicos (45.3%) son puntos críticos (`barras_apiladas.png`).
- 💡 **Oportunidad**: Promover bundles con soporte técnico y contratos anuales puede reducir el churn en un 15–20%.

---

## 📈 Gráficos Generados

Durante el análisis exploratorio se generaron **visualizaciones clave** para entender el comportamiento de los clientes y los factores asociados al churn:

<table>
  <tr>
    <td width="50%" valign="top">
      <ul>
        <li>Distribución de churn por número de servicios contratados</li>
        <li>Boxplots de variables numéricas por churn</li>
        <li>Mapa de calor de correlaciones entre variables</li>
        <li>Gráfico de densidad (KDE) por antigüedad del cliente</li>
        <li>Gráfico interactivo de proporciones de churn</li>
      </ul>
    </td>
    <td width="50%" valign="top">
      <ul>
        <li>Barras apiladas por tipo de contrato y método de pago</li>
        <li>Dispersión entre Cuentas_Diarias y Servicios_Contratados</li>
        <li>Conteo de clientes con y sin churn</li>
        <li>Tasas de churn por variables categóricas</li>
        <li>Comparación de gasto diario vs churn</li>
      </ul>
    </td>
  </tr>
</table>

<table style="width:100%; border:0;">
  <tr>
    <td style="width:33%; text-align:center;">
      <img width="3845" height="2056" alt="kde_churn" src="https://github.com/user-attachments/assets/38c34ea2-1625-464d-8605-09fe7d8fbee4" />     
      <br><i>Distribución de churn por número de servicios</i>
    </td>
    <td style="width:33%; text-align:center;">
      <img src="https://github.com/user-attachments/assets/21d0d18e-14c7-4a8d-b4ed-f2a7525e178a" alt="Gráfico 2" style="max-width:100%;">
      <br><i>Boxplot de gasto diario por churn</i>
    </td>
    <td style="width:33%; text-align:center;">
      <img src="https://github.com/user-attachments/assets/55967f8a-0bb1-438a-9c20-ee72834cdeef" alt="Gráfico 3" style="max-width:100%;">
      <br><i>Heatmap de correlaciones entre variables</i>
    </td>
  </tr>
</table>


---



## 🛠️ Herramientas Utilizadas

- **Lenguaje:** [Python](https://www.python.org/) 3.8+
- **Bibliotecas:**
  - [Pandas](https://pandas.pydata.org/) – Manipulación de datos
  - [Matplotlib](https://matplotlib.org/) y [Seaborn](https://seaborn.pydata.org/) – Visualizaciones estáticas
  - [Plotly](https://plotly.com/) – Gráficos interactivos
- **Entorno:** [Jupyter Notebook](https://jupyter.org/) y [Google Colab](https://colab.google/)
- **Control de versiones:** [GitHub](https://github.com/)

---


## ⚙️ Configuración y Uso

1. **Clonar el repositorio**
   ```bash
   git clone <repo-url>
   cd challenge-TelecomX-ETL
   ```

2. **Instalar dependencias**:
   ``` bash
   pip install -r requirements.txt
   ```

3. **Ejecutar notebooks** (en orden):
    - `01_data_extraction.ipynb:` 
	    - Extrae datos desde la API y los guarda en `data/raw/telecomx_raw.json`.
    - `02_data_cleaning.ipynb:` 
	    - Procesa datos, genera variables derivadas (Cuentas_Diarias, Servicios_Contratados) y guarda datasets en `data/processed/`.
    - `03_data_analysys.ipynb:` 
	    - Realiza el EDA, genera métricas (media, mediana, etc.) y visualizaciones en `src/graficos/`.
4. **Explorar visualizaciones**:
    - Abre `src/graficos/` para ver gráficos como heatmap_corr.png (correlaciones) o proporcionChurn_plotly.html (interactivo).
    - Usa `03_data_analysys.ipynb` para personalizar o generar nuevos gráficos.
5. **Datos de entrada/salida**:
    - Entrada: `data/raw/telecomx_raw.json` (7267 clientes).
    - Salida: Datasets procesados en `data/processed/` y gráficos en `src/graficos/`.

---

## 🌟 Cómo Extender el Proyecto
- 📂 **Nuevos datos**: Modifica `01_data_extraction.ipynb` para integrar otras fuentes (CSV, SQL).
- 🤖 **Modelos predictivos**: Usa `telecom_df_bin.csv` para entrenar modelos de ML (Random Forest, Logistic Regression).
- 📊 **Visualizaciones avanzadas**: Agrega gráficos interactivos con Plotly o Power BI en `src/graficos/`.

---

## 🤝 Contribuciones

¡Bienvenidas las mejoras! Por favor:

1. Abre un **`issue`** para discutir cambios o ideas.
2. Crea un **`pull request`** con código limpio y documentado.
3. Enfócate en optimizar el ETL, añadir modelos predictivos o mejorar visualizaciones.

---

## 📬 Contacto

- Desarrollado por: [Aaron Garcia]
- Contacto: [LinkedIn](www.linkedin.com/in/aaron-martinez-garcia](http://www.linkedin.com/in/aaron-martinez-garcia)
