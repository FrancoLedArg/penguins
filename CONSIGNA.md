# Nivel 9 — Proyecto integrador: pingüinos de la Antártida

El proyecto integrador recorre el flujo completo del nivel 0: preparar los datos, explorar con métodos no supervisados, entrenar y comparar modelos supervisados con validación cruzada, evaluar una sola vez con datos de prueba y comunicar los resultados. Es individual o grupal y se resuelve en RStudio o en un notebook de Python.

## Objetivo

Aplicar de punta a punta los métodos supervisados y no supervisados del manual sobre un mismo conjunto de datos, y comunicar las conclusiones en lenguaje no técnico.

## Dataset

`penguins` (paquete `palmerpenguins`): 344 pingüinos de tres especies y tres islas del archipiélago Palmer, Antártida.

Variables numéricas:

- `bill_length_mm` — largo del pico
- `bill_depth_mm` — profundidad del pico
- `flipper_length_mm` — largo de la aleta
- `body_mass_g` — masa corporal

Variable a predecir en la parte supervisada: `species`.

## Consigna

Los pasos van numerados de corrido. El conjunto de prueba del paso 3 no se usa hasta el paso 10.

### Parte A. Exploración y preparación (nivel 1)

1. Cargar los datos, contar los valores faltantes y eliminar las filas incompletas de las cuatro variables numéricas y de la especie.
2. Resumir las variables (medias por especie) y hacer un gráfico de dispersión del largo de la aleta contra el largo del pico, coloreado por especie.
3. Separar el 20 % de los datos como prueba final (semilla 42, estratificada por especie) y no tocarlo hasta el paso 10.

### Parte B. Enfoque no supervisado, sin usar la especie (niveles 2 a 4)
4. Con el 80 % restante (entrenamiento), estandarizar las variables y aplicar PCA. Indicar cuánta varianza explican las dos primeras componentes e interpretar los loadings.
5. Aplicar K-means sobre las dos primeras componentes con k de 2 a 6, y elegir k con el codo y la silueta.
6. Comparar los grupos obtenidos con la especie real mediante una tabla de contingencia.

### Parte C. Enfoque supervisado (niveles 5 a 8)

7. Con solo los datos de entrenamiento, comparar con validación cruzada de 5 pliegues: k-NN, regresión logística (multiclase), árbol de decisión y random forest. Elegir el k de k-NN por validación cruzada.
8. Elegir el modelo ganador justificando la decisión con la media y el desvío de la exactitud (ante un empate técnico, elegir el más simple).
9. Reentrenar el modelo elegido con todo el entrenamiento.
10. Evaluarlo una sola vez sobre la prueba final: matriz de confusión, exactitud, y precisión y sensibilidad de cada especie.
11. Obtener la importancia de las variables con un random forest y compararla con los loadings del PCA.

### Parte D. Comunicación

12. Redactar un informe de una página para una persona que no sabe estadística, con: la pregunta, los datos, qué se hizo y

> El texto copiado del PDF termina en esa frase.
