# 📊 Medidas DAX – Proyecto de Ventas

Este documento reúne las principales medidas DAX utilizadas en el dashboard de análisis de ventas.

Cada medida incluye la fórmula, su uso en el reporte y el insight que permite obtener.

---

### 🧮 Total_Ventas

`Total_Ventas = SUM(Ventas_Diarias[Precio_Venta])`

* **Uso**: KPI principal en la primera página del dashboard.
* **Insight**: Evalúa el desempeño general de las ventas en un período específico.

---

### 🧮 Ciudad con Mayores Ventas

```dax
`Ciudad con Mayores Ventas =
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
    MAXX(MaxCiudad, Ventas_Diarias[Ciudad])`

* **Uso**: KPI principal en la primera página del dashboard.
* **Insight**: Evalúa el desempeño general de las ventas en un período específico.
```
* **Uso**: KPI principal en la primera página del dashboard.
* **Insight**: Evalúa el desempeño general de las ventas en un período específico.

