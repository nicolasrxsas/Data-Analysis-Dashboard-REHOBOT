Total_Ventas = SUM(Ventas_Diarias[Precio_Venta])

Uso: KPI principal en la primera página del dashboard.
Insight: Permite evaluar el desempeño general de las ventas en un período específico.
-------------------------------------------------

Ciudad con Mayores Ventas = 
VAR TotalCiudad =
    SUMMARIZE (
        Ventas_Diarias,
        Ventas_Diarias[Ciudad],
        "TotalVentas", SUM ( Ventas_Diarias[Precio_Venta] )
    )
VAR MaxCiudad =
    TOPN ( 1, TotalCiudad, [TotalVentas], DESC )
RETURN
    MAXX ( MaxCiudad, Ventas_Diarias[Ciudad] )
    
Uso: KPI en la página "Ventas por Zona"
Insight: Determina la ciudad con mayores Ventas.
-------------------------------------------------
