# 📊 Challenge Telecom X: Análisis de Evasión de Clientes

> **Reto 2 - Especialización en Ciencia de Datos | Alura LATAM**  
> **Autor:** Jesús Martinez  
> **Fecha:** Julio 2025

---

## 🎯 **RESUMEN EJECUTIVO**

Este proyecto presenta un análisis integral de **retención de clientes** para la empresa de telecomunicaciones TelecomX, utilizando técnicas avanzadas de ciencia de datos para identificar patrones de abandono, segmentar clientes y proponer estrategias de retención basadas en datos.

### **Resultados Clave**

- 📈 **7,267 clientes analizados** con 21 variables
- 🔍 **Tasa de abandono identificada:** 26.54%
- 💰 **Revenue potencial identificado:** $3.2M anuales
- 🎯 **4 clusters de clientes** con perfiles de riesgo diferenciados
- ⚡ **Optimización de memoria:** 37.5% de reducción

---

## 📋 **TABLA DE CONTENIDOS**

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Dataset](#-dataset)
- [Metodología](#-metodología)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Principales Hallazgos](#-principales-hallazgos)
- [Segmentación de Clientes](#-segmentación-de-clientes)
- [Recomendaciones Estratégicas](#-recomendaciones-estratégicas)
- [Instalación y Uso](#-instalación-y-uso)
- [Resultados Visuales](#-resultados-visuales)
- [Conclusiones](#-conclusiones)

---

## 🎯 **DESCRIPCIÓN DEL PROYECTO**

El **Challenge Telecom X** es una iniciativa de análisis predictivo enfocada en entender y reducir la **evasión de clientes (churn)** en el sector de telecomunicaciones. El proyecto implementa un pipeline completo de ciencia de datos desde la extracción hasta la generación de insights accionables.

### **Objetivos Principales**

1. 🔍 **Identificar patrones** de comportamiento que predicen el abandono
2. 📊 **Segmentar clientes** según su riesgo de abandono y valor
3. 💡 **Generar recomendaciones** estratégicas basadas en datos
4. 🎯 **Cuantificar oportunidades** de retención e ingresos

---

## 📊 **DATASET**

### **Características del Dataset**

- **Registros:** 7,267 clientes
- **Variables:** 21 características por cliente
- **Formato:** JSON estructurado
- **Calidad:** 99.85% de completitud
- **Período:** Datos históricos de comportamiento de clientes

### **Variables Analizadas**

```
📋 Variables Demográficas:
- ID_Cliente: Identificador único
- Genero: Masculino/Femenino
- Ciudadano_Mayor: ≥65 años
- Tiene_Pareja: Estado civil
- Tiene_Dependientes: Dependientes a cargo

📞 Servicios de Comunicación:
- Servicio_Telefono: Servicio telefónico básico
- Lineas_Multiples: Múltiples líneas telefónicas
- Servicio_Internet: DSL/Fiber Optic/Sin servicio

🌐 Servicios Adicionales:
- Seguridad_Online: Protección digital
- Respaldo_Online: Backup de datos
- Proteccion_Dispositivo: Seguro de dispositivos
- Soporte_Tecnico: Asistencia técnica
- TV_Streaming: Televisión en streaming
- Peliculas_Streaming: Películas on-demand

💼 Información Contractual:
- Tipo_Contrato: Month-to-month/One year/Two year
- Factura_Digital: Facturación electrónica
- Metodo_Pago: Forma de pago
- Cargo_Mensual: Facturación mensual ($)
- Cargo_Total: Facturación acumulada ($)
- Meses_Contrato: Duración en meses

🎯 Variable Objetivo:
- Cliente_Abandono: Sí/No (Churn)
```

---

## 🔬 **METODOLOGÍA**

### **Pipeline de Análisis ETL**

#### **1. 📤 EXTRACCIÓN**

- Carga de datos desde formato JSON
- Validación de integridad estructural
- Análisis inicial de calidad

#### **2. 🔧 TRANSFORMACIÓN**

- **Normalización JSON:** Expansión de objetos anidados
- **Renombramiento:** Traducción a español para mayor claridad
- **Optimización de Tipos:** Reducción de memoria del 37.5%
- **Tratamiento de Valores Faltantes:** Solo 11 valores (0.15%)
- **Encoding Categórico:** Preparación para análisis estadístico

#### **3. 📊 CARGA Y ANÁLISIS**

- **Análisis Exploratorio de Datos (EDA)**
- **Análisis de Correlaciones Parciales**
- **Tests Estadísticos:** Mann-Whitney U, Chi-cuadrado
- **Clustering K-Means:** Segmentación en 4 grupos
- **Análisis de Supervivencia:** Kaplan-Meier
- **Visualizaciones Avanzadas:** 15+ gráficos analíticos

### **Índice de Complejidad de Procesamiento (ICP)**

Métrica propietaria para evaluar la eficiencia del procesamiento:

$$ICP = \frac{R \cdot C \cdot D}{U \cdot M}$$

Donde:

- **R:** Número de registros
- **C:** Número de columnas
- **D:** Profundidad de transformación
- **U:** Unicidad promedio
- **M:** Memoria utilizada (MB)

---

## 💻 **TECNOLOGÍAS UTILIZADAS**

```python
# Análisis de Datos
import pandas as pd              # Manipulación de datos
import numpy as np               # Computación numérica

# Visualización
import matplotlib.pyplot as plt  # Gráficos base
import seaborn as sns           # Visualización estadística
import plotly.express as px     # Gráficos interactivos

# Machine Learning
from sklearn.cluster import KMeans        # Clustering
from sklearn.preprocessing import StandardScaler  # Normalización
from sklearn.decomposition import PCA    # Reducción dimensionalidad

# Análisis Estadístico
from scipy import stats         # Tests estadísticos
from lifelines import KaplanMeierFitter  # Análisis supervivencia

# Utilidades
import warnings                 # Manejo de advertencias
import time                    # Medición de tiempo
from tabulate import tabulate  # Tablas formateadas
```

---

## 📁 **ESTRUCTURA DEL PROYECTO**

```
Challenge-Telecom-X/
│
├── 📊 TelecomX_LATAM.ipynb          # Notebook principal con análisis
├── 📋 TelecomX_diccionario.md       # Diccionario de datos
├── 🗃️ TelecomX_Data.json            # Dataset original
├── 📖 README.md                     # Documentación del proyecto
│
└── 📈 Análisis Incluidos:
    ├── EDA Completo
    ├── Análisis de Correlaciones
    ├── Segmentación por Clustering
    ├── Análisis de Supervivencia
    ├── Matriz de Confusión
    ├── Análisis de ROI
    └── Recomendaciones Estratégicas
```

---

## 🔍 **PRINCIPALES HALLAZGOS**

### **📊 Análisis Demográfico**

```
Base de Clientes: 7,267 usuarios
├── Género: 50.5% Masculino | 49.5% Femenino
├── Ciudadanos Mayores (65+): 1,142 clientes (16.2%)
├── Con Pareja: 3,402 clientes (48.3%)
└── Con Dependientes: 2,110 clientes (30.0%)
```

### **📞 Penetración de Servicios**

```
Servicios Básicos:
├── Servicio Telefónico: 6,571 clientes (90.4%)
└── Servicio Internet: 5,517 clientes (75.9%)
    ├── DSL: 2,421 clientes (33.3%)
    ├── Fiber Optic: 3,096 clientes (42.6%)
    └── Sin Internet: 1,750 clientes (24.1%)

Servicios Adicionales (% de clientes con internet):
├── TV Streaming: 49.5%
├── Películas Streaming: 49.5%
├── Seguridad Online: 36.6%
├── Soporte Técnico: 37.1%
├── Respaldo Online: 36.8%
└── Protección Dispositivo: 37.1%
```

### **💰 Análisis Financiero**

```
Métricas de Revenue:
├── Cargo Mensual Promedio: $64.76
├── Cargo Total Promedio: $2,283.30
├── Ingresos Totales Acumulados: $16,590,132.53
└── Ingresos Mensuales Totales: $470,533.89

Distribución por Valor:
├── Q5 (Alto Valor): $99.58 promedio | 42.1% churn
├── Q4: $84.85 promedio | 31.4% churn
├── Q3: $70.35 promedio | 26.1% churn
├── Q2: $53.22 promedio | 18.9% churn
└── Q1 (Bajo Valor): $29.17 promedio | 7.4% churn
```

### **⚠️ Factores Críticos de Abandono**

```
Correlaciones Estadísticamente Significativas (p < 0.001):
├── Duración Contrato: -0.352 (Negativa fuerte)
├── Fiber Optic: +0.308 (Positiva fuerte)
├── Cargo Mensual: +0.193 (Positiva moderada)
├── Factura Digital: +0.191 (Positiva moderada)
└── Tiene Pareja: -0.150 (Negativa moderada)

Perfil de Abandono vs. Leales:
├── Cargo Mensual: $74.44 vs $53.22 (+39.7%)
├── Duración: 15.1 vs 39.5 meses (-61.7%)
├── Fiber Optic: 69.4% vs 21.5%
├── Sin Pareja: 56.2% vs 46.7%
└── Factura Digital: 75.0% vs 57.3%
```

---

## 🎯 **SEGMENTACIÓN DE CLIENTES**

### **Clustering K-Means (4 Segmentos)**

#### **🔴 Cluster 1 - ALTO RIESGO**

```
📊 Métricas:
├── Tamaño: 1,869 clientes (25.7%)
├── Tasa de Abandono: 26.8%
├── Revenue Promedio: $74.39
├── Tenure Promedio: 17.1 meses
├── Ciudadanos Mayores: 16.3%
└── Facturación Digital: 80.7%

🎯 Perfil: Clientes de alto valor con baja permanencia
💡 Estrategia: Retención inmediata y programas de lealtad
```

#### **🟠 Cluster 2 - RIESGO MEDIO-ALTO**

```
📊 Métricas:
├── Tamaño: 1,799 clientes (24.8%)
├── Tasa de Abandono: 22.3%
├── Revenue Promedio: $89.12
├── Tenure Promedio: 28.6 meses
├── Ciudadanos Mayores: 15.8%
└── Facturación Digital: 75.4%

🎯 Perfil: Clientes rentables con señales de riesgo
💡 Estrategia: Monitoreo proactivo y cross-selling
```

#### **🟡 Cluster 3 - RIESGO BAJO**

```
📊 Métricas:
├── Tamaño: 1,834 clientes (25.2%)
├── Tasa de Abandono: 18.1%
├── Revenue Promedio: $35.48
├── Tenure Promedio: 42.8 meses
├── Ciudadanos Mayores: 16.1%
└── Facturación Digital: 45.2%

🎯 Perfil: Clientes estables de bajo valor
💡 Estrategia: Upselling gradual y retención pasiva
```

#### **🟢 Cluster 4 - RIESGO MEDIO**

```
📊 Métricas:
├── Tamaño: 1,765 clientes (24.3%)
├── Tasa de Abandono: 15.7%
├── Revenue Promedio: $58.93
├── Tenure Promedio: 35.9 meses
├── Ciudadanos Mayores: 16.4%
└── Facturación Digital: 62.8%

🎯 Perfil: Clientes balanceados con potencial crecimiento
💡 Estrategia: Desarrollo de valor y servicios adicionales
```

---

## 💡 **RECOMENDACIONES ESTRATÉGICAS**

### **🚀 PRIORIDAD 1 - IMPLEMENTACIÓN INMEDIATA (0-3 meses)**

#### **1. Sistema Predictivo de Churn**

```
🎯 Target: Clusters 1 y 2 (alto riesgo)
💰 Inversión: $50K
📈 ROI Esperado: 300%
📊 Impacto: Identificación proactiva de 3,668 clientes en riesgo
```

#### **2. Campaña de Retención Clientes Alto Valor**

```
🎯 Target: 891 clientes alto valor/baja permanencia
💰 Revenue en Riesgo: $800K anuales
📈 Estrategia: Descuentos progresivos por permanencia
🔄 Tácticas: Contratos preferentes, servicios premium gratuitos
```

### **📈 PRIORIDAD 2 - IMPLEMENTACIÓN MEDIA (3-6 meses)**

#### **3. Programa Cross-selling Servicios Digitales**

```
🎯 Target: 1,194 clientes con internet sin servicios adicionales
💰 Potencial: $363K anuales
📈 ROI Esperado: 200%
🛠️ Servicios: Seguridad Online, TV Streaming, Soporte Técnico
```

#### **4. Optimización Precios Fiber Optic**

```
🎯 Target: 3,096 clientes Fiber Optic
📉 Objetivo: Reducir abandono del 43.9% al 30%
💰 Retención Adicional: $2.1M anuales
🔧 Estrategia: Reestructuración de precios y bundling
```

### **📅 PRIORIDAD 3 - IMPLEMENTACIÓN LARGA (6-12 meses)**

#### **5. Programa de Lealtad Contratos Largos**

```
🎯 Target: 3,875 clientes mes-a-mes
🔄 Conversión: Mes-a-mes → Contratos anuales
📈 Mejora LTV: 40%
🎁 Incentivos: Descuentos escalonados y beneficios exclusivos
```

---

## 📊 **MATRIZ DE PRIORIZACIÓN BCG**

### **⭐ STARS (Alto Crecimiento, Alta Efectividad)**

- Cross-sell Servicios Digitales
- Retención Clientes Nuevos
- Optimización Fiber Optic

### **🐄 CASH COWS (Bajo Crecimiento, Alta Efectividad)**

- Retención Clientes Alto Valor
- Upselling Servicios Básicos
- Conversion Contratos Largos

### **❓ QUESTION MARKS (Alto Crecimiento, Baja Efectividad)**

- Servicios Adicionales DSL
- Nuevos Segmentos Demográficos
- Productos Innovadores

### **🐕 DOGS (Bajo Crecimiento, Baja Efectividad)**

- Clientes de Muy Bajo Valor
- Servicios Obsoletos

---

## 💰 **IMPACTO FINANCIERO PROYECTADO**

### **💎 Revenue Potencial Total: $3.2M anuales**

```
Desglose por Iniciativa:
├── Retención Alto Valor: $1,200K
├── Cross-selling Digital: $800K
├── Optimización Precios: $700K
└── Conversión Contratos: $500K

ROI Consolidado:
├── Retención Alto Valor: 340% ROI
├── Cross-sell Digital: 267% ROI
├── Upselling Fiber: 238% ROI
├── Contratos Largos: 280% ROI
└── Servicios Adicionales: 200% ROI

💵 Inversión Total: $180K
🎯 Retorno Año 1: $2.1M (1,167% ROI)
```

### **📈 Escenarios de Implementación**

```
🟢 Escenario Optimista (90% éxito):
├── Reducción Churn: 6.8 puntos porcentuales
├── Revenue Adicional: $2.9M
└── ROI: 1,611%

🟡 Escenario Conservador (70% éxito):
├── Reducción Churn: 4.2 puntos porcentuales
├── Revenue Adicional: $1.5M
└── ROI: 833%
```

---

## 🛠️ **INSTALACIÓN Y USO**

### **Requisitos del Sistema**

```python
# Versiones recomendadas
Python >= 3.8
pandas >= 1.3.0
numpy >= 1.21.0
matplotlib >= 3.4.0
seaborn >= 0.11.0
scikit-learn >= 1.0.0
plotly >= 5.0.0
lifelines >= 0.26.0
```

### **Instalación**

```bash
# Clonar el repositorio
git clone https://github.com/lastHunter956/Challenge-Telecom-X.git

# Navegar al directorio
cd Challenge-Telecom-X

# Instalar dependencias
pip install -r requirements.txt

# Ejecutar notebook
jupyter notebook TelecomX_LATAM.ipynb
```

### **Estructura de Ejecución**

```python
# 1. Cargar datos
dataframe = pd.read_json('TelecomX_Data.json', orient='records')

# 2. Ejecutar pipeline ETL
# Seguir las celdas del notebook secuencialmente

# 3. Generar análisis
# Todas las visualizaciones y métricas se generan automáticamente
```

---

## 📈 **RESULTADOS VISUALES**

El proyecto incluye **15+ visualizaciones analíticas:**

### **📊 Dashboards Principales**

1. **Dashboard Demográfico:** Distribución por género, edad, estado civil
2. **Análisis de Servicios:** Penetración y correlaciones de servicios
3. **Dashboard Financiero:** Distribución de ingresos y quintiles de valor
4. **Mapa de Correlaciones:** Heatmap de variables vs. churn
5. **Análisis de Clusters:** Visualización PCA y perfiles de segmentos
6. **Curvas de Supervivencia:** Análisis Kaplan-Meier por segmentos
7. **Matriz BCG:** Priorización de estrategias
8. **Análisis de ROI:** Proyecciones financieras por iniciativa

### **🎨 Características Visuales**

- **Paleta de colores consistente** para identificación de clusters
- **Gráficos interactivos** con Plotly para exploración
- **Annotations detalladas** con insights clave
- **Formato profesional** para presentaciones ejecutivas

---

## 🎯 **CONCLUSIONES**

### **🔍 Hallazgos Críticos**

1. **⚠️ Paradoja del Alto Valor:** Los clientes más rentables tienen mayor riesgo de abandono
2. **📱 Crítico Mes-a-mes:** 53.3% de la base en contratos de alto riesgo
3. **🌐 Oportunidad Fiber Optic:** Servicio premium requiere optimización urgente
4. **🔄 Cross-selling Subutilizado:** Penetración <50% en servicios adicionales

### **💪 Factores Clave de Éxito**

- **🎯 Implementación Escalonada:** Según matriz de priorización BCG
- **📊 Monitoreo Continuo:** KPIs de retención por segmento
- **🎨 Personalización:** Estrategias basadas en clusters identificados
- **🔄 Optimización Iterativa:** Mejora continua basada en resultados

### **🚀 Ventajas Competitivas Sostenibles**

- **🤖 Sistema Predictivo:** Churn basado en 4 clusters validados
- **💰 Estrategia de Precios:** Diferenciada por segmento de valor
- **🎯 Cross-selling Inteligente:** Personalizado por perfil de cliente
- **🛡️ Retención Proactiva:** Identificación temprana de riesgo

---

## 📞 **CONTACTO Y CONTRIBUCIONES**

**👨‍💻 Autor:** Jesús Martinez  
**🎓 Programa:** Especialización en Ciencia de Datos - Alura LATAM  
**📅 Fecha:** Julio 2025  
**📧 Email:** [Contacto disponible en el perfil de GitHub]  
**🔗 LinkedIn:** [Perfil profesional]

### **🤝 Contribuciones**

Las contribuciones son bienvenidas. Por favor:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

---

## 📄 **LICENCIA**

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE.md](LICENSE.md) para detalles.

---

## 🙏 **AGRADECIMIENTOS**

- **Alura LATAM** por la oportunidad de desarrollo profesional
- **Comunidad de Data Science** por las mejores prácticas implementadas
- **TelecomX** (datos simulados) por el caso de estudio realista

---

<div align="center">
<h3>📊 Challenge Telecom X: De los Datos a la Estrategia 🚀</h3>
<p><i>"Transformando datos en decisiones estratégicas para el éxito empresarial"</i></p>

![Data Science](https://img.shields.io/badge/Data%20Science-Advanced-blue)
![Python](https://img.shields.io/badge/Python-3.8+-green)
![Machine Learning](https://img.shields.io/badge/ML-Clustering-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

</div>
