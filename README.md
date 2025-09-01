# Solución de Problemas — Modelado de Calificación según Tiempo de Entrega

## Descripción del análisis
El objetivo principal fue **predecir la calificación obtenida por los estudiantes** en función del **tiempo de entrega** de sus actividades, explorando diferentes técnicas de regresión no lineal: polinomial, segmentada y KNN.

La base de datos utilizada incluyó **432 observaciones**, que después de una limpieza de valores atípicos se redujo a **376 registros**.

---

## Variables incluidas
- **Tiempo**: horas restantes al cierre de la bandeja (valores negativos indican entregas posteriores).  
- **Calificacion**: nota obtenida por la entrega (0–110).  

---

## Pasos realizados

### **1. Importación y limpieza de datos**
Se cargó el archivo `A1.6 Tiempo de Entrega.csv` y se eliminaron valores atípicos mediante el método IQR en ambas variables.  
La base pasó de 432 a 376 registros.

### **2. Análisis exploratorio**
Se graficó la dispersión entre **Tiempo** y **Calificacion**, observando una tendencia a que las entregas más tardías se asocian con calificaciones menores.

### **3. División en conjuntos**
Se realizó un **split 70/30** para entrenamiento y prueba, verificando que los promedios entre ambos conjuntos fueran similares.

### **4. Regresión Polinomial**
Se entrenó un modelo polinomial de **grado 3**, logrando capturar la curvatura de la relación entre las variables.

### **5. Regresión Segmentada**
Se calculó un **punto de quiebre (knot)** en la mediana del tiempo y se entrenaron dos cuadráticas, una a la izquierda y otra a la derecha del knot.

### **6. Regresión KNN**
Se probaron distintos valores de *k = {3, 5, 7, 9, 11}*.  
El mejor ajuste se obtuvo con **k = 3**, aunque mostró menor interpretabilidad.

### **7. Evaluación de modelos**
Se calcularon errores **RMSE** en el conjunto de prueba:  
- Polinomial (grado 3): ≈ 17.73  
- Segmentada (2 cuadráticas): ≈ 17.82  
- KNN (k=3): ≈ 19.34  

### **8. Gráfica comparativa**
Se compararon las curvas de los tres modelos contra los datos reales, observando que el **modelo polinomial** ofreció la curva más estable y cercana a la tendencia.

---

## Conclusión
El análisis mostró que el **modelo polinomial de grado 3** fue el que mejor se ajustó a los datos, seguido muy de cerca por la regresión segmentada. El modelo KNN presentó mayor variabilidad y menor interpretabilidad. Sin embargo, aunque el polinomial sea el que más se ajusta, esto no constituye una comprobación definitiva de la relación entre el tiempo de entrega y la calificación, sino que únicamente sugiere una posible tendencia que debería confirmarse con más evidencia.

---

## Archivos generados
- [Notebook en ipynb](Regresion_No_Lineal.ipynb)  
- [Reporte en html](Regresion_No_Lineal.html)  
- [Base de datos](Base_de_Datos_Tiempo_de_Entrega.csv)  
