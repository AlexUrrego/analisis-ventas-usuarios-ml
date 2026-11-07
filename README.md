# Análisis de ventas y preparación de datos para machine learning

Proyecto en **Python** que analiza datos de compras de usuarios de una tienda en línea: limpia los datos, crea variables nuevas (RFM e interacciones), codifica y escala las variables y divide el conjunto en entrenamiento, validación y prueba.

## Qué muestra este proyecto
- Análisis exploratorio y limpieza de datos (valores atípicos, variables de fecha, categorías).
- **Ingeniería de características:** recencia, frecuencia y valor monetario (RFM), ticket promedio, tiempo entre compras y variables de interacción.
- **Codificación** de variables categóricas con `LabelEncoder`.
- **Escalado** con `MinMaxScaler` y `StandardScaler`.
- **División estratificada** 70 % / 15 % / 15 % con `train_test_split`.

## Archivos

| Archivo | Contenido |
|---|---|
| `analisis_datos_ventas.ipynb` | Análisis completo: exploración, limpieza, gráficas y preparación de datos |
| `procesamiento_datos.py` | Script con la etapa de ingeniería de características, codificación, escalado y división |
| `datos_ventas_usuarios.csv` | Datos originales (sintéticos) |
| `datos_limpios.csv` | Datos ya limpios, entrada del script |
| `requirements.txt` | Dependencias de Python |

## Cómo ejecutarlo

**Requisito:** Python 3.

```
pip install -r requirements.txt
```

Para el análisis completo, abre el notebook:

```
jupyter notebook analisis_datos_ventas.ipynb
```

Para ejecutar solo el procesamiento:

```
python procesamiento_datos.py
```

El script genera `dataset_minmax.csv`, `dataset_std.csv` y los archivos `X_*.csv` y `y_*.csv`.

## Variables creadas

| Grupo | Variables |
|---|---|
| RFM | `recencia`, `frecuencia`, `valor_monetario`, `ticket_promedio`, `dias_como_cliente`, `tiempo_entre_compras` |
| Interacción | `precio_por_minuto_sesion`, `ratio_descuento_total`, `compras_por_dia` |

**Variable objetivo:** `cliente_frecuente`.

## Limitaciones
- Los datos son **sintéticos** y muy pocos: 40 compras de 24 usuarios. Sirven para practicar el proceso, no para sacar conclusiones reales.
- `cliente_frecuente` se deriva del número de compras del usuario, por lo que `num_compras` no debe usarse como variable de entrada.