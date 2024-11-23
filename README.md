# LungAI: Modelo Predictivo para la Detección Temprana del Cáncer de Pulmón

**LungAI** es un modelo de aprendizaje automático diseñado para identificar pacientes de alto riesgo de cáncer de pulmón de manera eficiente y precisa. Este proyecto busca complementar los métodos tradicionales de diagnóstico con un enfoque que mejora la velocidad, el coste y la accesibilidad del proceso.

## 🌟 **Motivación**

El cáncer de pulmón es el tumor más diagnosticado en el mundo y la principal causa de muerte por cáncer, con:
- **2,5 millones de nuevos casos** en 2022.
- **1,8 millones de fallecimientos** estimados en el mismo año.

En España, más del **70% de los casos** se diagnostican en una etapa avanzada, lo que reduce significativamente las posibilidades de tratamiento efectivo. Este modelo predictivo puede ayudar a identificar pacientes de alto riesgo en etapas tempranas, marcando una diferencia crucial en la atención médica.

---

## 🛠️ **Características del proyecto**

- **Modelo base:** ExtraTreesClassifier, con una precisión del **91%**.
- **Manejo de desbalanceo de clases:** Upsampling para mejorar el rendimiento en datos desbalanceados.
- **Análisis exploratorio:** Identificación de variables clave como edad, tabaquismo y nivel de ingresos.
- **Próximos pasos:** Incorporar imágenes de TAC para mejorar la precisión con visión por computadora.

---

## 📂 **Estructura del Proyecto**

```plaintext
LungAI/
├── data/              # Datos utilizados para el análisis y modelado
├── notebooks/         # Notebooks de análisis, EDA y preprocesamiento
├── models/            # Modelos entrenados y archivos relacionados
├── src/               # Código fuente del proyecto
│   ├── preprocessing/ # Scripts de limpieza y transformación de datos
│   ├── eda/           # Scripts para el análisis exploratorio de datos
│   ├── training/      # Entrenamiento y selección del modelo
│   ├── evaluation/    # Evaluación del modelo
├── README.md          # Documentación principal del proyecto
└── requirements.txt   # Dependencias del proyecto
```


## 🚀 **Cómo usar LungAI**

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/tuusuario/LungAI.git
   cd LungAI
2. Instalar dependencias:
   ```bash
   pip install -r requirements.txt
3. Explorar los datos: Usa los notebooks en la carpeta notebooks/ para realizar un análisis exploratorio o ajustar parámetros.
4. Entrenar el modelo: Ejecuta el script principal de entrenamiento en src/training/:
   ```bash
   python src/training/train_model.py
5. Evaluar el modelo: Utiliza los scripts en src/evaluation/ para medir la precisión, sensibilidad y otros indicadores clave:
   ```bash
   python src/evaluation/evaluate_model.py

## 📊 Flujo del proyecto

### 1. Exploración y limpieza de los datos
- **Variables incluidas:** edad, nivel de ingresos, fumador, entre otras.
- **Limpieza de datos:**
  - Eliminación de valores nulos.
  - Estandarización de formatos.
  - Homogeneización de variables para análisis consistente.

### 2. Análisis exploratorio de los datos (EDA)
- **Univariante:** Análisis de la variable objetivo (cáncer: sí/no).
- **Bivariante:**
  - **Pruebas estadísticas:**
    - Chi-cuadrado para variables categóricas y la variable objetivo.
    - T-student para variables numéricas y la variable objetivo.
- **Insights clave:**
  - La edad es un factor importante: a mayor edad, mayor probabilidad de cáncer.
  - Fumar aumenta significativamente el riesgo de cáncer.
  - Un nivel de ingresos más bajo se asocia con mayor probabilidad de cáncer, probablemente debido a una calidad de vida más baja, trabajo exigente, menor acceso a chequeos médicos, etc.
  - En cuanto a otros comportamientos, parece que los pacientes que no juegan videojuegos tienen menos probabilidades de tener cáncer, aunque esto podría explicarse por la edad (personas mayores no suelen jugar videojuegos).

### 3. Manejo del desbalanceo y preprocesamiento
- **Desbalanceo de clases:** Se utilizó upsampling y SMOTE para equilibrar las clases.
- **Codificación de variables categóricas:** Se empleó OneHotEncoding para convertir variables como fumador en formato numérico.
- **Feature Engineering:** Eliminación de variables con alta multicolinealidad o baja correlación con la variable objetivo (cáncer).

### 4. Modelado y selección del modelo
- Se probaron varios modelos, incluyendo Regresión Logística, Árboles de Decisión y K-Neighbors.
- Se realizó Hyperparameter Tuning para encontrar los mejores valores en el modelo K-Neighbors, obteniendo una precisión de 0.86 con n=1.
- Se utilizó LazyClassifier para encontrar el modelo óptimo, el cual resultó ser el ExtraTreesClassifier con una precisión del 91%.

### 5. Evaluación del modelo
- El ExtraTreesClassifier logró una precisión del 91%.
- Aunque se intentaron escalados con MinMaxScaler y StandardScaler, la precisión no mejoró significativamente con respecto al modelo sin escalado.
- El modelo se consideró adecuado para apoyar decisiones clínicas y la predicción temprana del cáncer de pulmón.

## 🔮 Próximos pasos
- **Uso de imágenes de TAC de pulmones:** Integrar técnicas de visión por computadora para mejorar la precisión del diagnóstico mediante la identificación de patrones visuales en imágenes médicas.
- **Optimización del modelo:** Continuar trabajando en la mejora del modelo con más datos, ajustando parámetros y explorando técnicas de aprendizaje profundo.





