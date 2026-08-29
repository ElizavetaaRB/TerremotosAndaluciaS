# Cantidad de Terremotos por Año

Una línea del tiempo que permite ver la evolución histórica y detectar en qué años ha habido más enjambres sísmicos.

<div class='tableauPlaceholder' id='viz1788011245484' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;76&#47;76S4K6Z48&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='path' value='shared&#47;76S4K6Z48' /> <param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;76&#47;76S4K6Z48&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='es-ES' /></object></div> 
<div class='tableauPlaceholder' id='viz1788039141913' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;te&#47;terremotos_17880080596350&#47;DashboardAnlisisdeFrecuenciaSsmicayEvolucinTemporalHomogneaMagnitud&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='terremotos_17880080596350&#47;DashboardAnlisisdeFrecuenciaSsmicayEvolucinTemporalHomogneaMagnitud' /><param name='tabs' value='yes' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;te&#47;terremotos_17880080596350&#47;DashboardAnlisisdeFrecuenciaSsmicayEvolucinTemporalHomogneaMagnitud&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='es-ES' /></object></div>                

## 1. Marco Metodológico y Tratamiento de Valores Nulos

Para garantizar la validez científica de la serie temporal (1406–2026), se ha implementado un proceso de homogeneización a la escala de Magnitud Momento ($M_w$). El catálogo histórico del Instituto Geográfico Nacional (IGN) emplea hasta 15 metodologías de cálculo de magnitud según la época y la instrumentalización disponible.En este análisis, los registros sísmicos que carecen de valor instrumental (terremotos históricos pre-1910 o eventos no calculados donde [Mag.] es NULL o $0$) se han excluido automáticamente del modelado de magnitudes para evitar distorsiones en los agregados de energía.

## 2. Mapeo de Codificación del IGN y Ecuaciones de Conversión

La transformación se basa en las relaciones empíricas de conversión de Cabañas et al. (2015) y la normativa técnica del IGN:


| Código IGN (`[Tipo Mag.]`) | Metodología de Origen | Ecuación de Conversión Aplicada | Justificación Técnica |
| :---: | :--- | :--- | :--- |
| **5, 6, 11, 12, 13, 15** | $M_w$, $M(m_b)$, $M_w(m_B)$, $M_w(M_{wp})$, $M$, $M_t$ | $M_w = \text{Mag}$ | Magnitudes ya expresadas en escala de momento o equivalencias directas. |
| **2, 4** | $m_{bLg}(M\text{-}MS)$ y $m_{bLg}(L)$ | $M_w = 0{,}594 \cdot m_{bLg} + 1{,}623$ | Calibración empírica estándar para la fase $Lg$ en la Península Ibérica. |
| **3, 8, 9, 10** | $m_b(V\text{-}C)$, $m_b$, $m_B$, $M_{wp}$ | $M_w = 0{,}90 \cdot m_b + 0{,}40$ | Corrección de saturación para magnitudes de ondas internas. |
| **1, 7** | $M_D(M\text{-}MS)$ y $M_{Lv}$ | $M_w = 0{,}85 \cdot M_{Lv} + 0{,}65$ | Ajuste para magnitud por duración y escala Local de Richter (componente vertical). |
| **`NULL` / 0** | Datos no instrumentados o sin registro | Excluido (`NULL`) | Filtro de gobernanza de datos para no desvirtuar las agregaciones históricas. |


## 3. Ajuste del Modelo Estadístico e Interpretación Analítica

Tras aplicar la unificación a escala $M_w$, se ha recalculado el modelo de regresión exponencial sobre el recuento de eventos para evaluar el crecimiento temporal de la sismicidad registrada:
$$\text{Recuento de } M_w = 4{,}04833 \times 10^{-64} \cdot e^{0{,}0762523 \cdot \text{Año}}$$

Coeficiente de Determinación ($R^2$): $0{,}952699$

Significatividad Estadística ($p\text{-valor}$): $< 0{,}0001$

## Interpretación de Resultados:

1. Robustez Estadística Extrema ($R^2 = 95{,}27\%$): El modelo ajusta con altísima precisión el comportamiento exponencial de los registros a lo largo de la serie histórica.
2. Efecto de la Homogeneización: Al convertir las magnitudes heterogéneas a $M_w$, la curva de tendencia se estabiliza reduciendo la dispersión atípica (outliers producidos por la diferencia de escalas entre el siglo XX y el XXI).
3. Conclusión de Negocio / Dominio: La pendiente positiva de la curva ($\beta = 0{,}07625$) confirma que el incremento constante de sismos responde exclusivamente a la evolución de la red instrumental del IGN (capaz de medir microterremotos de $M_w < 2.0$ y registrar enjambres sísmicos completos) y no a un aumento de la peligrosidad tectónica real en la región de Andalucía Oriental.








