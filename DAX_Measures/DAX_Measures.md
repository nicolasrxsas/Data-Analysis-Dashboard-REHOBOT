# 📊 Medidas DAX - Proyecto de Ventas

Este documento contiene las medidas DAX utilizadas en el proyecto de
análisis de ventas.\
Las medidas se han organizado por secciones para mayor claridad.

------------------------------------------------------------------------

## 🔹 Ventas

``` dax
Total Ventas = SUM(FactVentas[MontoVenta])
```

``` dax
Ventas 2023 = CALCULATE([Total Ventas], YEAR(FactVentas[Fecha]) = 2023)
```

``` dax
Ventas YTD = TOTALYTD([Total Ventas], FactVentas[Fecha])
```

------------------------------------------------------------------------

## 🔹 Clientes

``` dax
Clientes Únicos = DISTINCTCOUNT(FactVentas[ClienteID])
```

``` dax
Clientes Nuevos = 
CALCULATE(
    DISTINCTCOUNT(FactVentas[ClienteID]),
    FILTER(
        FactVentas,
        FactVentas[Fecha] = CALCULATE(MIN(FactVentas[Fecha]), ALLEXCEPT(FactVentas, FactVentas[ClienteID]))
    )
)
```

------------------------------------------------------------------------

## 🔹 Productos

``` dax
Productos Únicos Vendidos = DISTINCTCOUNT(FactVentas[ProductoID])
```

``` dax
Top Producto = 
TOPN(
    1,
    SUMMARIZE(FactVentas, Productos[NombreProducto], "Ventas", [Total Ventas]),
    [Ventas], DESC
)
```

------------------------------------------------------------------------

## 🔹 Finanzas

``` dax
Margen = [Total Ventas] - [Costo Total]
```

``` dax
Margen % = DIVIDE([Margen], [Total Ventas], 0)
```

------------------------------------------------------------------------

## 📌 Notas finales

-   Estas medidas fueron implementadas en Power BI como parte del
    **proyecto de análisis de ventas con datos reales de la empresa**.
-   Se recomienda usarlas junto con el **diagrama de relaciones del
    modelo de datos** para comprender mejor su contexto.
