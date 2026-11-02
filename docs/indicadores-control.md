# Indicadores de Control — Proyecto SGST Tecno Reparaciones

Los indicadores de control se derivan de las seis metas cuantitativas definidas en la Entrega 2
y permiten auditar el desempeño del sistema durante y después del desarrollo.

| Indicador de control | Estándar de desempeño | Frecuencia / momento de medición | Meta vinculada |
|---|---|---|---|
| Tiempo de respuesta de operaciones core | &lt; 2 segundos en el 95% de las transacciones diarias (ingreso de órdenes, actualización de diagnósticos, emisión de presupuestos) | Pruebas de carga (T9), en el entorno de simulación preparado en T9a | Meta 1 |
| Trazabilidad de órdenes | 100% de las órdenes con historial completo (estado, diagnóstico, presupuesto, repuestos, cobro y entrega) | Auditoría mensual de registros | Meta 5 |
| Error de stock | Margen máximo del 1% en repuestos y componentes | Reporte semanal durante los primeros 90 días de funcionamiento | Meta 4 |
| Tiempo del proceso técnico | Reducción del 30% respecto a la gestión manual (de recepción a entrega) | Medición a los 6 meses de implementado | Meta 3 |
| Cumplimiento del cronograma | Desviación máxima de 1 semana, absorbida por el margen de contingencia (T11) | Comparación semanal del avance real contra el Gantt (24 semanas) | Meta 6 |
| Calidad del versionado | 100% de los cambios con commit descriptivo y revisión de PR antes de mergear a main | Auditoría del historial del repositorio (GitHub) | Buena práctica |

## Notas de control
- El indicador de tiempos de respuesta se mide en el entorno de carga preparado en la tarea T9a,
  dado que el equipo no dispone de infraestructura física propia (debilidad registrada en el FODA).
- El pago no forma parte de los estados de la orden: se registra únicamente en la entidad COBRO
  (campo pagado), para no duplicar datos (definición del diccionario de datos, Entrega 3).
