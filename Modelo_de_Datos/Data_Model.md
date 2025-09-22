### 🔗 Relaciones entre tablas

| Tabla Hechos / Dimensión | Columna Clave            | Relación con | Columna Relacionada | Cardinalidad | Dirección |
|--------------------------|--------------------------|--------------|---------------------|--------------|-----------|
| Ventas_Diarias           | Cliente                  | Clientes     | ID                  | Muchos-1     | Simple    |
| Ventas_Diarias           | P_ID                     | Productos    | ID                  | Muchos-1     | Simple    |
| Ventas_Diarias           | Ciudad                   | Zonas        | Zona                | Muchos-1     | Simple    |
| Ventas_Diarias           | Fecha                    | Calendario   | Fecha               | Muchos-1     | Simple    |
| Resumen_Diario           | Fecha                    | Calendario   | Fecha               | Muchos-1     | Simple    |
| Resumen_Diario           | Zona                     | Zonas        | Zona                | Muchos-1     | Simple    |

## El modelo está basado en una tabla de hechos central (`Ventas_Diarias`), conectada a dimensiones clave:

- **Clientes** → permite segmentar ventas por cliente y fecha de última compra.  
- **Productos** → análisis por categoría, marca y proveedor.  
- **Zonas** → análisis geográfico por ciudades y departamentos.  
- **Calendario** → soporte de inteligencia temporal (tendencias, YOY, MOM).  
- **Resumen_Diario** → facilita la consolidación diaria de cartera y zona.  

Este diseño favorece la escalabilidad y el rendimiento de los cálculos DAX.
