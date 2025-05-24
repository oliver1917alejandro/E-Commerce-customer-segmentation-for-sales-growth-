# 📊 Análisis RFM de Clientes de E-commerce 🛍️

Este proyecto realiza un análisis exhaustivo de un conjunto de datos de comercio electrónico para comprender el comportamiento de los clientes y segmentarlos utilizando el modelo RFM (Recencia, Frecuencia, Valor Monetario). El objetivo principal es identificar diferentes grupos de clientes para aplicar estrategias de marketing personalizadas y efectivas.

## 🎯 Descripción del Proyecto

El proyecto, contenido en el Jupyter Notebook `EcomerceProject.ipynb`, está diseñado para realizar las siguientes tareas clave:

1.  💧 **Carga de Datos:** Importación de múltiples archivos CSV que contienen información detallada sobre clientes, pedidos, productos, pagos, geolocalizaciones, vendedores, ítems de pedidos y reseñas de pedidos.
2.  🧹 **Limpieza y Preparación de Datos (Data Wrangling):**
    *   Verificación y reporte de valores faltantes en cada conjunto de datos.
    *   Identificación y eliminación de registros duplicados.
    *   Conversión de columnas de fecha/hora al formato `datetime` para análisis temporales.
    *   Análisis exploratorio básico de precios (promedio, mínimo, máximo).
    *   Traducción de nombres de categorías de productos del portugués al inglés para consistencia.
    *   Ingeniería de características: Creación de nuevas columnas útiles como mes y año de compra, y cálculo del tiempo de entrega.
3.  📈 **Análisis RFM (Recencia, Frecuencia, Valor Monetario):**
    *   Cálculo de:
        *   **Recencia (R):** Días transcurridos desde la última compra del cliente.
        *   **Frecuencia (F):** Número total de compras (transacciones únicas) realizadas por el cliente.
        *   **Valor Monetario (M):** Gasto total realizado por el cliente.
    *   Segmentación de clientes en categorías significativas basadas en sus puntuaciones RFM (e.g., Campeones, Leales, En Riesgo, etc.).
    *   **Nota Importante sobre la Frecuencia**: Es importante destacar que, para este conjunto de datos particular, la métrica de Frecuencia en el análisis RFM mostró una varianza mínima, con la mayoría de los clientes teniendo una sola transacción registrada en el período analizado. Por lo tanto, la segmentación se basa principalmente en la Recencia y el Valor Monetario.
4.  🖼️ **Visualización de Resultados:**
    *   `segmentos_rfm.png`: Gráfico de barras que muestra la distribución de clientes entre los diferentes segmentos RFM (e.g., Campeones, Leales, etc.), permitiendo visualizar el tamaño de cada grupo.
    *   `metricas_por_segmento.png`: Gráficos de barras que comparan las métricas promedio de Recencia, Frecuencia y Valor Monetario para cada segmento de clientes, facilitando la comprensión de sus características distintivas.
    *   `rfm_heatmap_segmentos.png`: Heatmap que visualiza las métricas RFM promedio (Recencia, Frecuencia, Valor Monetario) para cada segmento, ofreciendo una vista consolidada y comparativa de sus perfiles.
    *   `rfm_scatter_recency_frequency.png`: Diagrama de dispersión que muestra la relación entre la Recencia y la Frecuencia de los clientes. Los puntos están coloreados y dimensionados según su Valor Monetario, ayudando a identificar clusters de clientes y patrones de comportamiento.
5.  📤 **Exportación de Resultados:**
    *   Guardado de la tabla de segmentación RFM, con cada cliente asignado a un segmento, en un archivo CSV (`segmentacion_clientes_rfm.csv`). Este archivo es ideal para uso en campañas de marketing dirigidas u otros análisis subsecuentes.
    *   Guardado de las visualizaciones generadas como archivos de imagen (`.png`).

## 📚 Origen de los Datos

El análisis se basa en archivos de datos del [conjunto de datos de Olist E-Commerce en Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), que incluyen información sobre clientes, pedidos, productos, etc.

## 🔑 Archivos Clave del Proyecto

*   `EcomerceProject.ipynb`: El Jupyter Notebook que contiene todo el código de análisis, desde la carga de datos hasta la visualización y exportación de resultados.
*   `*.csv`: Archivos CSV con los datos de origen (no incluidos en este repositorio, deben descargarse de Kaggle).
*   `*.png`: Imágenes de los gráficos generados por el análisis (e.g., `segmentos_rfm.png`, `metricas_por_segmento.png`, `rfm_heatmap_segmentos.png`, `rfm_scatter_recency_frequency.png`).

## ⚙️ Requisitos y Ejecución

Para ejecutar este proyecto, necesitará **Python 3.x** instalado junto con las siguientes bibliotecas esenciales:

*   **pandas:** Para manipulación y análisis de datos.
*   **numpy:** Para operaciones numéricas.
*   **matplotlib:** Para crear gráficos estáticos.
*   **seaborn:** Para crear visualizaciones estadísticas más atractivas.

El análisis completo se puede ejecutar ejecutando las celdas del Jupyter Notebook `EcomerceProject.ipynb` en un entorno Python configurado con las bibliotecas mencionadas.

## 📊 Resultados Clave del Análisis (Ejemplo basado en el Notebook)

(Esta sección resume los hallazgos típicos que el notebook puede generar. Los valores exactos pueden variar según la ejecución o pequeñas modificaciones en el preprocesamiento.)

*   **Valores Faltantes Identificados (Antes del Tratamiento Específico):**
    *   `olist_products_dataset.csv`: ~2,448 registros con valores faltantes.
    *   `olist_orders_dataset.csv`: ~4,908 registros con valores faltantes.
    *   `olist_order_reviews_dataset.csv`: ~145,903 registros con valores faltantes.
*   **Análisis de Precios (Sobre `olist_order_items_dataset.csv`):**
    *   Precio promedio del ítem: ~$120.65 BRL
    *   Precio mínimo del ítem: $0.85 BRL
    *   Precio máximo del ítem: $6735.00 BRL
*   **Dimensiones de Datos (Post-Limpieza y Merge para RFM):**
    *   Clientes únicos analizados para RFM: ~98,666
*   **Resultados del Análisis RFM:**
    *   Recencia Promedio: ~289 días.
    *   Frecuencia Promedio: 1.0 (Nota: la mayoría de los clientes tienen una sola compra, como se mencionó anteriormente).
    *   Valor Monetario Promedio: ~$137.75 BRL por cliente.
*   **Distribución de Clientes por Segmento (Ejemplo):**
    *   🌟 Campeones: ~35,592 clientes
    *   💡 Potenciales Leales: ~19,965 clientes
    *   💖 Clientes Leales: ~19,540 clientes
    *   ⚠️ En Riesgo: ~19,393 clientes
    *   😥 Necesitan Atención: ~4,176 clientes

*   **Características de los Segmentos (Promedios Ejemplo):**

| Segmento             | Recencia Prom. (días) | Frecuencia Prom. | Valor Monetario Prom. (BRL) |
|---------------------|------------------------|-------------------|------------------------------|
| 🌟 Campeones        | 136                    | 1.0               | $153                         |
| 💖 Clientes Leales  | 255                    | 1.0               | $131                         |
| 💡 Potenciales Leales | 348                    | 1.0               | $139                         |
| ⚠️ En Riesgo          | 493                    | 1.0               | $140                         |
| 😥 Necesitan Atención   | 528                    | 1.0               | $25                          |

## 📢 Recomendaciones de Marketing Sugeridas

Basado en la segmentación RFM, se pueden proponer las siguientes estrategias:

*   **🌟 Campeones:** Implementar programas de lealtad VIP. Ofrecer acceso temprano a nuevos productos. Fomentar que se conviertan en embajadores de la marca.
*   **💖 Clientes Leales:** Fomentar la venta cruzada y el up-selling. Implementar programas de referidos. Solicitar reseñas de productos y servicios.
*   **💡 Potenciales Leales:** Enviar ofertas personalizadas. Ofrecer incentivos para aumentar la frecuencia de compra. Comunicar novedades y beneficios.
*   **⚠️ En Riesgo:** Lanzar campañas de reactivación con descuentos especiales. Recordarles el valor de la marca. Realizar encuestas para entender por qué no han vuelto a comprar.
*   **😥 Necesitan Atención:** Enviar recordatorios amigables y ofertas de "bienvenida de nuevo" muy atractivas. Considerar la rentabilidad de intentar reactivar a todos los clientes de este segmento.

## 🚀 Mejoras Futuras / Próximos Pasos
*   Manejo Avanzado de Valores Faltantes.
*   Análisis Detallado de Valores Atípicos en métricas RFM.
*   Optimización de la Segmentación RFM (explorar clustering k-means, diferentes umbrales).
*   Profundizar en el Análisis Exploratorio de Datos (EDA): productos más vendidos por segmento, análisis geográfico, tendencias temporales, etc.
*   Modelado Predictivo: Predicción de abandono de clientes (Churn), estimación del Valor de Vida del Cliente (CLV), sistemas de recomendación de productos.
