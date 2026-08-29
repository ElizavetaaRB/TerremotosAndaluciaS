# TerremotosAndaluciaS
Análisis Histórico de la Sismicidad en el Sur de Andalucía y Mar de Alborán (1406 – 2026)

https://public.tableau.com/views/terremotos_17880080596350/Dashboard1?:language=es-ES&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

Este proyecto es un cuadro de mando interactivo diseñado en Tableau para analizar la localización, el historial y la frecuencia de los terremotos en el sur de la Península Ibérica y la zona de Alborán. El proyecto trabaja con una base de datos de 87.420 terremotos registrados desde el año 1406 hasta agosto de 2026, acotados en las coordenadas de latitud 35°–38°N y longitud 0°–19°O.

Mediante la limpieza y unificación de las localidades en Tableau (para agrupar nombres y quitar tildes o direcciones como Norte/Sur/Este), el trabajo se organiza en tres secciones:

1. Mapa de Terremotos: Muestra la ubicación exacta de los epicentros sobre el mapa para ver qué zonas concentran más actividad.

   <div class='tableauPlaceholder' id='viz1788011072575' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;te&#47;terremotos_17880080596350&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='terremotos_17880080596350&#47;Dashboard1' /><param name='tabs' value='yes' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;te&#47;terremotos_17880080596350&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='es-ES' /></object></div>                

2.  Cantidad de Terremotos por Año: Una línea del tiempo que permite ver la evolución histórica y detectar en qué años ha habido más enjambres sísmicos.


  <div class='tableauPlaceholder' id='viz1788011245484' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;76&#47;76S4K6Z48&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='path' value='shared&#47;76S4K6Z48' /> <param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;76&#47;76S4K6Z48&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='es-ES' /></object></div>                

3.  Tabla por Localidad: Una lista detallada con un buscador integrado para consultar en qué municipios ha temblado, qué magnitudes han tenido y cuántos terremotos se han producido en cada uno.

<div class='tableauPlaceholder' id='viz1788011484712' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;te&#47;terremotos_17880080596350&#47;Dashboard3&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='terremotos_17880080596350&#47;Dashboard3' /><param name='tabs' value='yes' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;te&#47;terremotos_17880080596350&#47;Dashboard3&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='es-ES' /></object></div>                


## Consideraciones sobre la Fuente y Calidad de los Datos
El conjunto de datos proviene del catálogo oficial del Instituto Geográfico Nacional (IGN), con registros históricos que datan desde el año 1406. No obstante, se deben considerar las siguientes particularidades metodológicas:
1. Heterogeneidad en la Medición (Magnitud vs. Intensidad): Las mediciones instrumentales de magnitud no se incorporaron al catálogo de forma sistemática hasta aproximadamente 1910. Por ello, los eventos anteriores a esta fecha carecen de un valor de magnitud homogéneo, estando caracterizados principalmente por su escalas de intensidad macrosísmica (daños observados).
2. Variabilidad en las Escalas de Magnitud: A lo largo de la serie temporal, el IGN ha empleado diversas funciones de cálculo y escalas de magnitud ($m_b$, $M_w$, $m_{bLg}$, etc.) en función de la tecnología y normativa vigente en cada época. Esta variabilidad metodológica implica que los valores de magnitud deben interpretarse dentro del contexto instrumental de su periodo correspondiente.

## Análisis Estadístico y Conclusiones del Estudio
El análisis econométrico y de tendencias temporales revela que el incremento observado en el recuento de sismos se debe a un aumento en la frecuencia de detección (volumen) y no a un incremento en la severidad (magnitud) de los eventos.

### 1.Tendencia General (Todos los rangos de magnitud combinados)

La serie histórica global muestra un ajuste exponencial casi perfecto respecto al tiempo: $$\text{Recuento} = 8{,}973 \times 10^{-64} \cdot e^{0{,}0758416 \cdot \text{Año}}$$ 

Bondad de ajuste ($R^2$): $0{,}953$ (explica el $95.3\%$ de la varianza histórica).

Significatividad ($p\text{-valor}$): $< 0{,}0001$ (estadísticamente significativo al $99{,}9\%$).

### 2. Desglose por Niveles de Magnitud

Sismos leves o no instrumentados ($M < 4$ o sin dato específico): Presentan una aceleración exponencial pronunciada en la curva de registro ($\text{Recuento} = 7{,}8527 \times 10^{-71} \cdot e^{0{,}0839 \cdot \text{Año}}$, $R^2 = 0{,}949$, $p < 0{,}0001$). Esto responde principalmente a la mejora de la red sísmica local e instalación de más sismógrafos en las últimas décadas, capturando microterremotos que antes pasaban desapercibidos.

Sismos moderados y mayor severidad ($M \ge 4$): El crecimiento temporal es significativamente más moderado ($\text{Recuento} = 3{,}0408 \times 10^{-26} \cdot e^{0{,}0309 \cdot \text{Año}}$, $R^2 = 0{,}598$, $p < 0{,}0001$).

Conclusión Principal: Existe una mayor tasa de registro de eventos sísmicos impulsada por la densidad tecnológica de detección actual. El fenómeno responde a un incremento en el volumen de datos capturados (mayor resolución de medición) y no a una intensificación en la magnitud media de la actividad tectónica.



## Líneas de Trabajo Futuras y Próximos Pasos

Para evolucionar este estudio en fases posteriores, se proponen las siguientes mejoras técnicas:

- Homogeneización de Escalas de Magnitud: Desarrollar un modelo de conversión/normalización que unifique las distintas métricas históricas del IGN ($m_b$, $M_w$, etc.) a una única escala estándar ($M_w$), reduciendo la dispersión en las comparativas temporales.

- Mapeo por Escala de Intensidad (EMS-98 / MSK): Diseñar una capa de visualización geográfica basada en la intensidad sísmica percibida en superficie para complementar la magnitud en aquellos terremotos históricos anteriores a 1910.

- Análisis de Compleción del Catálogo ($M_c$): Estimar el umbral de completitud (Magnitud de Compleción) para determinar a partir de qué magnitud el catálogo se considera $100\%$ completo en cada época histórica.

- Filtro Estacional y De-clustering (Eliminación de Réplicas): Aplicar algoritmos de declustering (ej. método de Gardner-Knopoff) para separar los enjambres sísmicos y réplicas del flujo de sismicidad principal de fondo.

