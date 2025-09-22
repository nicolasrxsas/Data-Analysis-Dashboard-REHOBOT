# Proyecto: Análisis de Ventas

...

## 📐 Modelo de Datos

![Modelo de Datos](assets/model.png)

### 🔗 Relaciones entre tablas

| Tabla Hechos / Dimensión | Columna Clave | Relación con | Columna Relacionada | Cardinalidad | Dirección |
|--------------------------|---------------|--------------|---------------------|--------------|-----------|
| Ventas_Diarias           | Cliente       | Clientes     | ID                  | Muchos-1     | Simple    |
| Ventas_Diarias           | P_ID          | Productos    | ID                  | Muchos-1     | Simple    |
...
