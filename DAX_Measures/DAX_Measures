# 📊 Medidas DAX - Proyecto de Ventas

Este documento recopila las medidas DAX **más reelevantes** utilizadas en el desarrollo del dashboard de análisis de ventas.  
Cada medida incluye su definición, el uso dentro del reporte y el insight que aporta.

---
# 📌 Medidas de Ventas
## 🧮 Ciudad con mayores Ventas
```DAX
-- Ciudad con Mayores Ventas = 
VAR TotalCiudad = 
    SUMMARIZE ( Ventas_Diarias, Ventas_Diarias[Ciudad], "TotalVentas", SUM ( Ventas_Diarias[Precio_Venta] ) )
VAR MaxCiudad = 
    TOPN ( 1, TotalCiudad, [TotalVentas], DESC )
RETURN 
    MAXX ( MaxCiudad, Ventas_Diarias[Ciudad] )

```
Uso: KPI en la página "Ventas por Zona".

Insight: Identifica la ciudad con mayores ventas.
## 🧮 Total Ventas
```DAX
Total Ventas =
SUM ( Ventas_Diarias[Precio_Venta] )

```
Uso: KPI principal en la primera página del dashboard.

Insight: Evalúa el desempeño general de las ventas en un período específico.
## 🧮 Cantidad Vendida
```DAX
Cantidad Vendida =
SUM ( Ventas_Diarias[Cantidad] )

```
## 🧮 Venats Mensuales
```DAX
Ventas Mensuales =
CALCULATE (
    [Total Ventas],
    DATESMTD ( 'Calendario'[Fecha] )
)
```
# 📌 Medidas de Productos
## 🧮 Promedio Ganancia Producto
```DAX
Promedio Ganancia por Producto =
AVERAGEX (
    VALUES ( Ventas_Diarias[Producto] ),
    AVERAGE ( Ventas_Diarias[Ganancia] )
)

```
Uso: KPI en la página "Productos y Proveedores".

Insight: Determina la ganancia media ganada en un producto.

## 🧮 Productos más vendidos
```DAX
Productos Más Vendidos =
SUMX (
    VALUES ( Ventas_Diarias[Producto] ),
    [Cantidad Vendida]
)
```
# 📌 Medidas de Clientes
## 🧮 Top cliente en Ventas
```DAX
Top Cliente por Ventas =
VAR ClienteTop =
    TOPN ( 1, SUMMARIZE ( Ventas_Diarias, Ventas_Diarias[Cliente], "Ventas", [Total Ventas] ), [Total Ventas], DESC )
RETURN
    MAXX ( ClienteTop, Ventas_Diarias[Cliente] )
```
Uso: KPI tarjeta en la página "Clientes".

Insight: Determina cliente que más compras hizo.
## 🧮 %Cartera Recuperada
```DAX
% Recuperación Cartera =
DIVIDE (
    SUM ( Resumen_Diario[Cartera_Recuperada] ),
    SUM ( Resumen_Diario[Cartera_Total] ),
    0
)
```
# 📌 Medidas de Pagos
## 🧮 Ventas Contado
```DAX
Ventas Contado =
CALCULATE (
    [Total Ventas],
    Ventas_Diarias[Pago] = "Contado"
)
```
## 🧮 Ventas Crédito
```DAX
## 🧮 Ventas Contado
```DAX
Ventas Contado =
CALCULATE (
    [Total Ventas],
    Ventas_Diarias[Pago] = "Contado"
)
```
