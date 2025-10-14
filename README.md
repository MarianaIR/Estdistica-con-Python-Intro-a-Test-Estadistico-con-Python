# 🔬 ESTADÍSTICA CON PYTHON: INTRODUCCIÓN AL TEST ESTADÍSTICO

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=ffdd54)](https://www.python.org/)  
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)  
[![SciPy](https://img.shields.io/badge/SciPy-8DAA90?style=flat&logo=scipy&logoColor=white)](https://scipy.org/)

Este proyecto sirve como una **introducción práctica al Test Estadístico** para comparar diferentes muestras de datos, utilizando dos bases de datos de películas y valoraciones (`TMDB` y `MovieLens`). El objetivo es aplicar y comprender cuándo utilizar tests paramétricos (como el **Test t**) y no paramétricos (como el **Test de Wilcoxon**), basándose en si la distribución de los datos es normal o no.

---

## 🧠 Contenido del Proyecto

### 1️⃣ Preparación de Datos y Análisis
- **Datasets Utilizados:**
    * **TMDB 500:** Datos de películas y valoraciones de la plataforma Kaggle.
    * **MovieLens:** Datos de valoraciones de usuarios recopilados por GroupLens.
- **Análisis de Distribución:** El primer paso crucial antes de aplicar cualquier test es determinar si las variables de las muestras siguen una **Distribución Normal**.
    * El análisis determina que los datos de **valoraciones de las películas NO siguen una Distribución Normal**.

### 2️⃣ Comparación de Muestras (Tests Paramétricos)
- **Test t de Student (`ttest_ind`):** Se utiliza para comparar las **medias** de dos muestras, asumiendo que ambas siguen una distribución normal.
- **Caso de Uso:** Se compara la media de votos entre dos películas (`Toy Story` y `Avatar`) para determinar si son significativamente diferentes.

### 3️⃣ Comparación de Muestras (Tests No Paramétricos)
Debido a que las valoraciones de películas (como las de *MovieLens*) a menudo **no siguen una distribución normal**, es necesario recurrir a tests no paramétricos.

- **Test de Wilcoxon (`ranksums`):** Se utiliza para comparar si las **distribuciones** de dos muestras son iguales, sin depender de la suposición de normalidad.
- **Hipótesis y Decisión:**
    * **Hipótesis Nula (H₀):** Las dos muestras tienen la misma distribución (son iguales).
    * **Hipótesis Alternativa (H₁):** Los valores de una muestra tienden a ser mayores o menores que los de la otra (son diferentes).
- **Conclusión Práctica:** Al comparar las valoraciones de `Toy Story` y `Silence of the Lambs`, y al obtener un P-valor menor que el $\alpha$ (0.05), se concluye que **se rechaza H₀**, indicando que las valoraciones de las dos películas **no son iguales**.

---

## 🛠️ Librerías Utilizadas

| Librería       | Uso principal                               |
|----------------|---------------------------------------------|
| **Pandas**     | Carga y manipulación de los DataFrames de películas|
| **SciPy.stats**| Implementación de tests estadísticos: `ttest_ind` (Test t) y `ranksums` (Wilcoxon)|

---

## 🎯 Objetivo del Proyecto
Introducir la distinción fundamental entre **tests paramétricos y no paramétricos** en Data Science. El proyecto enseña a un analista de datos a seleccionar el test correcto (Test t vs. Test de Wilcoxon) y a tomar decisiones rigurosas (rechazar o no rechazar H₀) al comparar muestras de datos.

---

## 📈 Resultados Clave
- Se establece la regla clave: **P-valor $<\alpha$ (0.05) implica rechazar H₀**.
- Se identifica que la **Distribución Normal** es el factor determinante para la elección del test.
- La aplicación del **Test de Wilcoxon** sobre valoraciones de películas demuestra que hay una **diferencia estadísticamente significativa** en la percepción del público entre `Toy Story` y `Silence of the Lambs`.

