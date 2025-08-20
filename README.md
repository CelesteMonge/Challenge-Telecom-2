# Challenge-Telecom-2

# Telecom Customer Churn Analysis

## Descripción del Proyecto
Este proyecto analiza la cancelación de clientes (churn) en una empresa de telecomunicaciones. El objetivo es identificar los factores que más influyen en la cancelación y construir modelos predictivos que permitan anticipar clientes en riesgo.

Se utilizaron técnicas de **preprocesamiento de datos**, **normalización**, **codificación de variables categóricas**, y se aplicaron distintos modelos de machine learning para evaluar su desempeño.

---

## Dataset
El dataset utilizado se encuentra en formato CSV y contiene información sobre clientes, sus contratos, servicios contratados, actividad diaria y si cancelaron o no.

Columnas principales:
- `customerID`: Identificador único del cliente
- `Monthly`: Gasto mensual
- `Cuentas_Diarias`: Actividad diaria promedio
- `tenure`: Tiempo de permanencia con la empresa (meses)
- `Churn`: Indica si el cliente canceló (Yes/No)
- Servicios de telecomunicaciones (InternetService, TechSupport, StreamingTV, etc.)

El dataset fue limpiado y procesado para eliminar columnas irrelevantes y transformar las variables categóricas a formato numérico.

Fuente: [Telecomx Churn Dataset](https://raw.githubusercontent.com/CelesteMonge/Challenge-Telecom-2/main/telecomx_churn_clean.csv)

---

## Preprocesamiento de Datos
1. Eliminación de columnas irrelevantes (`customerID`, `customer`, `account`, `Total` y columnas constantes).  
2. Transformación de diccionarios en columnas separadas (`internet`, `phone`).  
3. Codificación de variables categóricas mediante **One-Hot Encoding**.  
4. Normalización de variables continuas (`Monthly`, `Cuentas_Diarias`, `tenure`) usando MinMaxScaler.

---

## Modelos Predictivos
Se entrenaron y evaluaron los siguientes modelos:

### Regresión Logística
- Sensible a la escala de los datos (requiere normalización).  
- Métricas obtenidas:
  - Accuracy: 0.791
  - Precision: 0.638
  - Recall: 0.494
  - F1-score: 0.557

### Random Forest
- No requiere normalización.  
- Métricas obtenidas:
  - Accuracy: 0.767
  - Precision: 0.576
  - Recall: 0.467
  - F1-score: 0.516

---

## Variables más importantes
### Regresión Logística
- `tenure` (negativo): mayor antigüedad → menor cancelación  
- `InternetService_Fiber optic` (positivo): mayor riesgo de churn  
- `TechSupport_Yes` (negativo): reduce cancelación  
- `OnlineSecurity_Yes` (negativo): reduce cancelación  

### Random Forest
- `tenure`: mayor antigüedad reduce churn  
- `Monthly`: clientes con mayor gasto presentan mayor churn  
- `Cuentas_Diarias`: actividad diaria influye en la cancelación  

---

## Estrategias de Retención
1. Programas de fidelización para clientes antiguos.  
2. Promover servicios de soporte y seguridad como valor agregado.  
3. Incentivos para clientes con fibra óptica y servicios de streaming.  
4. Evaluar y optimizar planes de múltiples líneas.  
5. Programas de engagement para aumentar la satisfacción y reducir churn.

---

## Librerías Utilizadas
- `pandas`  
- `numpy`  
- `scikit-learn`  
- `matplotlib` y `seaborn` (para visualización opcional)  

---

## Uso
1. Clonar el repositorio:
```bash
git clone https://github.com/CelesteMonge/Challenge-Telecom-2.git
