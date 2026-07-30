# Redes convolucionales para clasificación de señales bursátiles

Este proyecto aplica redes neuronales convolucionales a imágenes generadas a partir de ventanas de precios de la acción de Loews Corporation. Cada imagen se clasifica como **Buy**, **Hold** o **Sell**.

## ¿Qué es una red convolucional?

Una **CNN** utiliza filtros convolucionales para detectar patrones locales en imágenes. En este caso, la serie temporal se transforma en una representación visual de siete días y la red aprende formas asociadas a movimientos posteriores del precio.

## Metodología

- Descarga de datos históricos mediante `yfinance`.
- Normalización de precios con `MinMaxScaler`.
- Ventanas de siete días y etiquetado según una variación de ±2%.
- Generación de 6.246 imágenes: 1.431 Buy, 3.667 Hold y 1.148 Sell.
- Comparación de tres arquitecturas CNN y diferentes cantidades de épocas.

## Resultado principal

El Modelo 2 alcanza accuracy 0,8322 y loss 0,3915 a cinco épocas. El análisis selecciona la configuración de tres épocas como alternativa más conservadora frente al riesgo de sobreajuste.

## Estructura

- `notebooks/`: notebook principal con rutas relativas y datos preparados para ejecutarse desde el repositorio.
- `data/`: archivo de imágenes comprimido y dividido en partes menores a 25 MB.
- `assets/figures/`: gráficos bursátiles y curvas de entrenamiento.
- `results/`: comparación de modelos en CSV.
- `reports/`: informe profesional en PDF y Word.

## Ejecución

```bash
pip install -r requirements.txt
jupyter notebook notebooks/cnn-stock-signal-classification.ipynb
```

El notebook reconstruye y extrae automáticamente el dataset de imágenes dentro de `data/`.

## Autor

**Lea Lambrecht**  
LinkedIn: linkedin.com/in/lealambrecht  
GitHub: github.com/leanlambrecht
