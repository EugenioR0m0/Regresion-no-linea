# Regresion-no-linea

# Regresión No Lineal

Este proyecto analiza la relación entre el **Tiempo de entrega** y la **Calificacion** mediante distintos modelos de regresión no lineal.

---

## Contenido del análisis

### 1 — Importación, limpieza y dispersión
- Se importó el archivo de datos y se eliminaron valores atípicos con el criterio **IQR**.
- El dataset pasó de 432 a 376 registros.
- La gráfica de dispersión mostró que a mayor tiempo de entrega (más tardío), las calificaciones tienden a disminuir.

### 2 — División entrenamiento/prueba
- Se dividió el dataset en **70% entrenamiento** y **30% prueba**.
- Los promedios de ambos subconjuntos resultaron similares, garantizando representatividad.

### 3 — Regresión Polinomial
- Se entrenó un modelo **polinomial de grado 3**.
- Capturó de forma adecuada la tendencia no lineal entre Tiempo y Calificacion.

### 4 — Regresión Segmentada
- Se calculó un **punto de quiebre (knot)** en la mediana del Tiempo.
- Se entrenaron dos cuadráticas: una para valores menores/iguales al knot y otra para valores mayores.

### 5 — Regresión KNN
- Se probaron distintos valores de **k = {3, 5, 7, 9, 11}**.
- El mejor resultado se obtuvo con **k = 3**, aunque el modelo mostró menor interpretabilidad.

### 6 — Evaluación de los modelos
Se calcularon los errores **RMSE** en el conjunto de prueba:
- Polinomial (grado 3): ≈ 17.73  
- Segmentada (2 cuadráticas): ≈ 17.82  
- KNN (k=3): ≈ 19.34  

El **modelo polinomial** obtuvo el menor error, seguido muy de cerca por el segmentado.

### 7 — Gráfica comparativa
- Se graficaron los puntos reales junto con las curvas de los tres modelos.  
- La curva polinomial resultó más estable y coherente con la tendencia observada.

---

## Conclusión
El análisis permitió explorar distintas técnicas de regresión no lineal para modelar la relación entre el tiempo de entrega y la calificación. Aunque el **modelo polinomial de grado 3** fue el que mostró mejor desempeño y mayor estabilidad, esto no constituye una comprobación definitiva de la hipótesis sobre la relación entre entregar más tarde y obtener menor calificación, sino que sugiere una posible tendencia que debería validarse con más evidencia y datos adicionales.
