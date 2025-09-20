📊 Medidas DAX – Proyecto de Ventas

Este documento reúne las principales medidas DAX utilizadas en el dashboard de análisis de ventas.
Cada medida incluye la fórmula, su uso en el reporte y el insight que permite obtener.

🧮 Total_Ventas
Total_Ventas = SUM(Ventas_Diarias[Precio_Venta])


Uso: KPI principal en la primera página del dashboard.
Insight: Evalúa el desempeño general de las ventas en un período específico.

🧮 Ciudad con Mayores Ventas
Ciudad con Mayores Ventas =
VAR TotalCiudad =
    SUMMARIZE(
        Ventas_Diarias,
        Ventas_Diarias[Ciudad],
        "TotalVentas",
        SUM(Ventas_Diarias[Precio_Venta])
    )
VAR MaxCiudad =
    TOPN(1, TotalCiudad, [TotalVentas], DESC)
RETURN
    MAXX(MaxCiudad, Ventas_Diarias[Ciudad])


Uso: KPI en la página "Ventas por Zona".
Insight: Identifica la ciudad con mayores ventas.

🧮 Ticket_Promedio
Ticket_Promedio = 
DIVIDE([Total_Ventas], DISTINCTCOUNT(Ventas_Diarias[ID_Venta]))


Uso: KPI en la página "Tendencias en el Tiempo".
Insight: Permite medir el valor promedio de cada transacción.

🧮 % Cartera Recuperada
%_Cartera_Recuperada = 
DIVIDE([Total_Cobrado], [Total_Cartera], 0)


Uso: Tarjeta en la página "Clientes / Talleres".
Insight: Mide el porcentaje de recuperación de cartera por cliente o zona.

🧮 Top Talleres por Ventas
Top_Talleres_Ventas = 
TOPN(
    10,
    SUMMARIZE(
        Ventas_Diarias,
        Ventas_Diarias[Cliente],
        "TotalVentas", [Total_Ventas]
    ),
    [TotalVentas], DESC
)


Uso: Visual de ranking en la página "Clientes / Talleres".
Insight: Permite identificar los clientes que generan mayor volumen de ventas.