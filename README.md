# Predicción de Deserción de Clientes (Churn Prediction)

Este proyecto aplica **Machine Learning** para predecir la deserción de clientes en una empresa de telecomunicaciones.  
Se probaron diferentes modelos de clasificación, enfocándose en **Decision Tree Classifier** y **K-Nearest Neighbors (KNN)**, con el objetivo de identificar los factores que más influyen en la cancelación de clientes y proponer estrategias de retención.

---

## 📂 Flujo del Proyecto

### 1. Preprocesamiento de Datos
- Se eliminan columnas irrelevantes:  
  `customerID`, `gender`, `MultipleLines`, `StreamingTV`, `StreamingMovies`, `Cuentas_Mensual`
- Se convierten variables binarias de texto a numéricas (`0` y `1`):
  - `Desercion`, `Partner`, `Dependents`, `PhoneService`, `Facturacion_electronica`
- Se aplicó **One-Hot Encoding** a las variables categóricas:
  - `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `Contract`, `PaymentMethod`

### 2. Análisis Exploratorio
- Se detectó **desbalance en la variable objetivo** (`Desercion`).
- Se analizaron correlaciones con variables como:
  - Contrato mensual
  - Antigüedad
  - Seguridad online
  - Soporte técnico
  - Tipo de servicio de internet
- Se realizaron gráficos comparativos con `seaborn` y `matplotlib`.

### 3. Balanceo de Clases
Se aplicó **SMOTE (Synthetic Minority Oversampling Technique)** para balancear la variable objetivo y mejorar la calidad del entrenamiento.

### 4. Entrenamiento de Modelos
#### 🔹 Decision Tree Classifier
- Se usó validación cruzada con **KFold (5 folds)**.
- Se evaluaron métricas: **accuracy, recall, precision y F1-score**.
- Se obtuvieron las **importancias de las variables**.

**Factores más influyentes:**
- Clientes con **contratos mensuales**.
- Clientes con **menor gasto total**.
- Clientes con **antigüedad baja**.

#### 🔹 K-Nearest Neighbors (KNN)
- Se aplicó **normalización con MinMaxScaler**.
- Se evaluaron métricas con **validación cruzada**.
- Se aplicó **importancia por permutación** para analizar variables relevantes.

**Factores más influyentes:**
- **Antigüedad baja**.  
- **Menor gasto total**.

### 5. Comparación de Modelos
- **Decision Tree** obtuvo un rendimiento ligeramente superior a **KNN**.  
- Ambos modelos coinciden en los factores más influyentes en la deserción.

---

## 📊 Conclusiones
- Los clientes con **contratos mensuales** tienen mayor probabilidad de desertar.  
- La **antigüedad** y el **gasto total** son factores tambien importantes en la predicción de la deserción.  

---

## 🛠 Estrategia de Retención
- Minimizar contratos mensuales: ofrecer planes más largos con promociones.  
- Incentivar la fidelidad con **ofertas y beneficios** a clientes nuevos.  
- Mejorar los servicios complementarios (seguridad online, soporte técnico).  

---

## 📌 Tecnologías Utilizadas
- **Python 3**
- **Pandas, NumPy**
- **Scikit-learn**
- **Imbalanced-learn (SMOTE)**
- **Matplotlib, Seaborn**

---

## 🚀 Próximos Pasos
- Probar modelos más avanzados (**Random Forest, XGBoost**).  
- Implementar un pipeline automático de preprocesamiento y modelado.  
- Desplegar el modelo en una aplicación web para predicción en tiempo real.

---
👤 **Autor:** Nilson  
📅 Proyecto desarrollado en 2025
