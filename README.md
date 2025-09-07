
 Objetivo: demostrar manejo de definiciones/funciones, bucles, condicionales y EDA con
 pandas, numpy y matplotlib.
 Dataset: temperaturasDiariasPorEstaciones2012.csv (delimitado por ;).
 Limpieza y preparación (10 pts)
 1. Construya una columna fecha desde Año, Mes, Dia y configúrela como índice temporal.
 2. Asegure tipos correctos (float para temperaturas; int/str donde corresponda).
 3. Elimine duplicados, si es que los hay. Para esto basate en la columna de fecha.
 4. Reporte el % de datos faltantes por columna.
 5. Documente en una celda Markdown las decisiones tomadas.
 Funciones utilitarias (30 pts)
 1. Defina las siguientes tres funciones:
 daily_range(tmin: float, tmax: float) -> float : retorna el rango diario (tmax 
tmin) de viariacion de la temperatura.
 classify_day(tmin: float, tmax: float, q_low: float, q_high: float) -> str :
 retorna una etiqueta ("frío", "templado", "caluroso") según el siguiente criterio:
 frio < 10 °C, templado > 10 °C pero < 24 °C y caluroso => 25°C Respecto a los valores
 máximos presentados por día
 monthly_quantiles(df_estacion: pd.DataFrame, month: int) ->
 tuple[float,float]: retorna (q10, q90) de TMaxima para ese mes por estación.
 2. Usando las funciones anteriores:
 En que fecha se registro la variación de temperatura más grande en la estación C.M.A.
 Eduardo Frei Montalva, Antartica.
 En el año 2012 cuantos dias calurosos hubo en el país.
 Genera una Gráfica donde se muestren la distrubución los días frios registrados por
 estación.
 De acuedo a las temperaturas máximas registradas por cada estación:
 Cuál fue el mes del año más caluroso.
 Cuál fue el mes del año más frio.
 Qué estación documento la temperatura máxima más alta y en qué mes fue.
 Qué estación documento la temperatura máxima más baja y en qué mes fue.
 3. Documente en una celda Markdown las conclusiones a las que llegaste.
 Detección de olas de calor (30 pts)
 Defina una ola de calor como ≥ 3 días consecutivos con TMaxima > Percentil 90 del mes y
 estación.
 1. Para cada estación, calcule P90 mensual de TMaxima.
2. Detecte eventos (inicio, fin, duración) y obtenga: número de eventos y duración máxima
 por estación.
 3. Para una estación Maquehue, Temuco Ad., crea una matriz día-del-mes × mes (o día-del
año × semana) con: 1 si es día en ola, 0 si no.
 4. Calcula el Top-10 eventos por severidad y por duración
 5. Existe una correlacion entre lo eventos de ola de calor y la Latitud y altura
 Genera una correlación de Pearson
 Genera un gráfico de dispersión con línea de tendencia
 6. Documente en una celda Markdown las conclusiones a las que llegaste
 Tendencia anual (15 pts)
 Para cada estación, estime la pendiente (°C/día) de TMaxima usando numpy.polyfit con x =
 día del año y y = TMaxima.
 Reporte la pendiente y ordene las 10 estaciones con pendiente más alta (calentamiento) y
 más baja (enfriamiento).
 Visualizaciones (15 pts)
 1. Para una estación Chacalluta, Arica Ap, grafique series de TMinima y TMaxima a lo
 largo del año.
 2. : Resumir TMaxima por mes con dispersión.
 Pasos:
 Agrupa por mes y calcula mean y std de TMaxima.
 Grafica barras de medias con barras de error (±SD).
 3. Resaltar días extremadamente cálidos.
 Pasos:
 Calcula umbral Percentil 99 de TMaxima para cada estación.
 Grafica serie de TMaxima y marca con puntos los ≥ P99; agrega línea horizontal en
 P99.
 4. En otra figura, cree un boxplot del Rango por mes para cada estación de medición
