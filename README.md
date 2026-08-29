# TerremotosAndaluciaS
Análisis Histórico de la Sismicidad en el Sur de Andalucía y Mar de Alborán (1406 – 2026)

https://public.tableau.com/views/terremotos_17880080596350/Dashboard1?:language=es-ES&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

Este proyecto analiza la localización, el historial y la frecuencia de los terremotos en el sur de la Península Ibérica y la zona del Mar de Alborán (coordenadas $35^\circ\text{--}38^\circ\text{N}$ y $0^\circ\text{--}19^\circ\text{O}$). El estudio trabaja con el catálogo oficial del **Instituto Geográfico Nacional (IGN)**, procesando un total de **87.420 registros sísmicos** desde el año 1406 hasta agosto de 2026.

Mediante la limpieza de datos, la unificación toponímica de localidades en Tableau y la homogeneización matemática de magnitudes, el trabajo se organiza en tres secciones:

1. Mapa de Terremotos: Muestra la ubicación exacta de los epicentros sobre el mapa para ver qué zonas concentran más actividad.
        

2.  Cantidad de Terremotos por Año: Una línea del tiempo que permite ver la evolución histórica y detectar en qué años ha habido más enjambres sísmicos.
        

3.  Tabla por Localidad: Una lista detallada con un buscador integrado para consultar en qué municipios ha temblado, qué magnitudes han tenido y cuántos terremotos se han producido en cada uno.

---        
## Principales Conclusiones del Estudio

El análisis econométrico y de series temporales revela que el incremento observado en el recuento de sismos a lo largo del tiempo se debe a **un aumento en la frecuencia de detección (volumen) por mejoras tecnológicas y no a un incremento en la peligrosidad tectónica real**.

* **Proceso de Homogeneización ($M_w$):** Al unificar las 15 metodologías históricas del IGN a la escala de **Magnitud Momento ($M_w$)**, la curva de tendencia se estabiliza, alcanzando un coeficiente de determinación del **$R^2 = 95{,}27\%$**.

* **Evolución Tecnológica ($M_c$):** La capacidad de detección ha mejorado drásticamente. En la era digital moderna (2002–2026), el **$97{,}3\%$ de los eventos registrados corresponden a microterremotos ($M_w < 4.0$)**, los cuales antes pasaban desapercibidos por la red de instrumentos.
---

## Estructura de la Documentación Técnica

Para profundizar en la metodología aplicada, puedes consultar los documentos específicos:

*  **[Homogeneización de Magnitudes a Escala ](homogeneizacion.md):** Detalle de las ecuaciones de conversión de Cabañas et al. (2015), tabla de códigos del IGN y comparativa del modelo estadístico antes vs. después de homogeneizar.
*  **[Análisis de Compleción del Catálogo ](analisis_complecion.md):** Evaluación del umbral de completitud ($M_c$) por eras tecnológicas de la red del IGN.

## Líneas de Trabajo Futuras y Próximos Pasos

Para evolucionar este estudio en fases posteriores, se proponen las siguientes mejoras técnicas:

- Mapeo por Escala de Intensidad (EMS-98 / MSK): Diseñar una capa de visualización geográfica basada en la intensidad sísmica percibida en superficie para complementar la magnitud en aquellos terremotos históricos anteriores a 1910.

- Filtro Estacional y De-clustering (Eliminación de Réplicas): Aplicar algoritmos de declustering (ej. método de Gardner-Knopoff) para separar los enjambres sísmicos y réplicas del flujo de sismicidad principal de fondo.

