.

📊 Dashboard de Análisis de Ventas

Empresa: Distribuciones Rehobot
Autor: Nicolás Gómez
Herramienta: Power BI
Fecha: Septiembre 2025

🔎 Contexto

La empresa Distribuciones Rehobot se encuentra en un proceso de transformación digital, migrando sus ventas del modelo presencial hacia el canal online con el objetivo de:

Alcanzar un 80% de ventas digitales y un 20% presenciales.

Reducir costos operativos.

Mejorar la gestión de cartera vencida.

Optimizar la atención a los clientes más valiosos.

Los datos utilizados provienen de registros reales en Excel (ventas, clientes y productos) recolectados desde junio de 2025.

🎯 Objetivo del Proyecto

Construir un dashboard interactivo en Power BI que permita a la empresa:

Monitorear la evolución de las ventas y la cartera.

Identificar productos de alta/baja rotación.

Detectar clientes estratégicos y de riesgo.

Evaluar la eficiencia de los métodos de pago.

❓ Preguntas de Negocio Respondidas

¿Cuál es la evolución de las ventas y cartera desde junio hasta la fecha?

¿Qué productos son los más vendidos y cuáles tienen baja rotación?

¿Qué clientes representan la mayor proporción de ingresos y deudas?

¿Cómo se comportan los métodos de pago (contado vs crédito) a lo largo del tiempo?

🛠️ Herramientas Utilizadas

Power BI → Visualización y modelado.

Excel → Fuente de datos (ventas diarias, clientes, productos, cartera).

DAX → Creación de medidas y KPIs personalizados.

GitHub → Documentación técnica y portafolio.

📈 Resultados y Visualizaciones Clave

Ventas Totales y Evolución Temporal → Tendencias semanales/mensuales.

Top Productos y Rotación → Clasificación por volumen y rentabilidad.

Clientes Estratégicos y Cartera → Identificación de clientes cumplidos vs vencidos.

Métodos de Pago → Comparación contado vs crédito.

Ventas y Cartera por Zona → Insights regionales.

📌 Ejemplo de visual:


📂 Estructura del Repositorio
├── DAX_Measures/
│   ├── Ventas.md
│   ├── Clientes.md
│   ├── Productos.md
├── images/
│   ├── dashboard_portada.png
│   ├── ventas_clientes.png
│   ├── productos.png
│   ├── cartera.png
├── README.md

🧮 Principales Medidas DAX

Ejemplo de algunas medidas clave (más en DAX_Measures/):

Ventas Totales = SUM(Ventas_Diarias[Precio_Venta])

Ticket Promedio = DIVIDE([Ventas Totales], [Cantidad de Ventas])

Clientes Únicos = DISTINCTCOUNT(Clientes[ID_Cliente])

🚀 Impacto del Proyecto

Decisiones informadas en gestión de productos y clientes.

Mejor control de ventas digitales vs presenciales.

Estrategia de cobranza más clara gracias al análisis de cartera.

Portafolio profesional para demostrar habilidades en análisis de datos, modelado en Power BI y aplicación de DAX.

🔗 Cómo Navegar el Proyecto

Explora las medidas DAX en la carpeta DAX_Measures/
.

Revisa las visualizaciones en images/
.

Documento de alcance inicial: Alcance_Proyecto.pdf
.

👨‍💻 Autor

Nicolás Gómez
Data Analyst Jr. | Enfocado en proyectos de Business Intelligence y migración digital.

📌 Conéctate conmigo en LinkedIn
