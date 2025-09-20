# 📊 Medidas DAX - Proyecto de Ventas

Este documento recopila las medidas DAX utilizadas en el desarrollo del dashboard de análisis de ventas.  
Cada medida incluye su definición, el uso dentro del reporte y el insight que aporta.

---

## 🧮 Ciudad con Mayores Ventas
```DAX
-- Ciudad con Mayores Ventas = 
VAR TotalCiudad = 
    SUMMARIZE ( Ventas_Diarias, Ventas_Diarias[Ciudad], "TotalVentas", SUM ( Ventas_Diarias[Precio_Venta] ) )
VAR MaxCiudad = 
    TOPN ( 1, TotalCiudad, [TotalVentas], DESC )
RETURN 
    MAXX ( MaxCiudad, Ventas_Diarias[Ciudad] )

```
Este documento recopila las medidas DAX utilizadas en el desarrollo del dashboard de análisis de ventas.  
Cada medida incluye su definición, el uso dentro del reporte y el insight que aporta.

