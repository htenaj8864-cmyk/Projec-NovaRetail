# Projec-NovaRetail: Explorando factores de comportamiento en NovaRetail+

Este repositorio contiene el análisis correlacional y exploratorio enfocado en identificar qué factores del comportamiento del usuario de una plataforma de comercio electrónico en Latinoamérica están más fuertemente asociados con el ingreso anual generado al cierre de 2024.
Se puede abrir el notebook en google colab 
https://colab.research.google.com/drive/1RowLswAHLndBCwf2ygA1sHZRhzAvvbA3#scrollTo=8f8d4263-0369-44b0-aa9a-e938236203e7

⚠️ Nota metodológica: Correlación no es = a causalidad. Este estudio identifica relaciones y patrones estadísticos, pero no prueba efectos de causa y efecto.

📂 Contexto del Negocio y ObjetivoNovaRetail+ cuenta con millones de usuarios activos. Para el cierre de 2024, el equipo de Crecimiento y Retención necesitaba responder a la pregunta clave:
¿Qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado?
El objetivo principal de este proyecto es analizar el comportamiento de los clientes mediante técnicas estadísticas y visuales para guiar futuras estrategias comerciales de manera informada.

📋 Descripción del Dataset
El conjunto de datos contiene 15,000 registros y 12 columnas, sin valores nulos:
* id_cliente: Identificador único del cliente.
* edad / nivel_ingreso: Datos demográficos y socioeconómicos del usuario.
* visitas_mes / compras_mes: Métricas de interacción y frecuencia transaccional mensual.
* gasto_publicidad_dirigida: Presupuesto de marketing asignado al usuario.
* satisfaccion: Calificación del cliente en escala del 1 al 5.
* miembro_premium / abandono: Variables binarias (0 = No, 1 = Sí).
* tipo_dispositivo / region: Variables categóricas del usuario.
* ingreso_anual: Métrica principal de negocio (ingreso generado para la empresa).
  
🛠️ Tecnologías y Librerías
El proyecto fue desarrollado en Python utilizando el siguiente stack tecnológico:
* Pandas y NumPy: Para manipulación, limpieza y transformación de datos.
* Seaborn y Matplotlib: Para visualización de datos (gráficos de dispersión y mapas de calor).
* SciPy (scipy.stats): Para el cálculo de coeficientes estadísticos avanzados (Pearson, Spearman, Punto-biserial y Chi-cuadrada / V de Cramér).

🔍 Fases del Análisis
1. Limpieza y Exploración Inicial:
   * Validación de tipos de datos (conversión de decimales a enteros en edad y satisfaccion).
   * Análisis de estadísticas descriptivas y distribuciones de variables numéricas, binarias y categóricas.
2. Visualización de Relaciones:
   * Creación de matrices de correlación (Heatmap) para identificar interacciones fuertes.
   * Gráficos de dispersión (Scatterplot) con líneas de tendencia para pares clave.
3. Evidencia Numérica:
   * Aplicación de Pearson y Spearman para variables numéricas.
   * Coeficiente Punto-biserial para relacionar variables binarias con continuas.
   * V de Cramér para evaluar la asociación entre variables categóricas.
     
💡 Hallazgos Clave e Implicaciones de Negocio 
* Frecuencia de compras vs Ingreso anual: Presenta una correlación extremadamente alta (aprox 0.967). Sugierenq que os clientes que realizan más compras mensuales generan consistentemente los mayores ingresos. 
Implicación: Enfocar los programas de lealtad en mantener alta la frecuencia transaccional.

* Gasto publicitario vs Visitas mensuales: Muestra una correlación positiva moderada-alta (aprox 0.579).
Implicación: La pauta digital está cumpliendo su objetivo de atraer tráfico, pero requiere optimización del ROI para asegurar conversiones.

* Membresía Premium y Abandono: La membresía muestra una relación débil pero positiva con el ingreso, mientras que el abandono no presenta vinculación estadística directa con el ingreso anual de los usuarios.
Implicación: Las estrategias de prevención de churn deben aplicarse de forma transversal a toda la base de clientes.

⚠️ Limitaciones

* Correlación no es = a causalidad: Las asociaciones estadísticas no garantizan que modificar una variable cause un impacto directo en la otra.
* Alta multicolinealidad: Existe una redundancia informativa crítica entre compras_mes e ingreso_anual, lo que limita su uso conjunto en modelos de regresión tradicionales.
* Datos de un solo momento: El dataset no cuenta con mayor información solo al cierre de 2024, por lo que no es posible analizar tendencias temporales o estacionalidad a lo largo del año.
* Ausencia de variables contextuales: No se cuenta con historial de categorías de productos ni detalles de atención al cliente.
