# Diccionario de Datos - TECNO REPARACIONES

Este documento formaliza el diseño de datos inicial para el Sistema de Gestión de Servicios Técnicos (SGST), estructurando las 6 entidades críticas del negocio para garantizar la integridad referencial y el flujo de información.

---

## Entidades del Sistema


### 1. Entidad: `Cliente`
Almacena los datos personales de cada cliente que solicita servicios técnicos.
* **`id_cliente`**: `Integer (PK)` - Identificador único autoincremental del cliente.
* **`nombre_apellido`**: `String` - Nombre y apellido completo.
* **`telefono`**: `String` - Número de contacto principal para notificaciones de reparación.
* **`direccion`**: `String` - Domicilio del cliente para retiros o entregas a domicilio.
* **`email`**: `String` - Correo electrónico para envío de presupuestos y comprobantes digitales.
* **`fecha_alta`**: `Date` - Fecha de registro en el sistema.
* **`activo`**: `Boolean` - Estado de habilitación del cliente.

### 2. Entidad: `Equipo`
Representa los dispositivos ingresados al taller para su revisión o reparación.
* **`id_equipo`**: `Integer (PK)` - Identificador único del equipo en el taller.
* **`id_cliente`**: `Integer (FK)` - Relación con el cliente propietario del dispositivo.
* **`tipo_equipo`**: `String` - Tipo de dispositivo ingresado.
* **`marca_modelo`**: `String` - Marca y modelo específico del dispositivo.
* **`numero_serie`**: `String` - Número de serie oficial del equipo.
* **`accesorios_recibidos`**: `String` - Detalle de accesorios entregados junto al dispositivo a reparar (ej. cargador)


### 3. Entidad: `Orden`
Gestiona y controla cada reparación realizada.
* **`id_orden`**: `Integer (PK)` - Número único de orden de trabajo.
* **`id_equipo`**: `Integer (FK)` - Relación con el equipo a reparar.
* **`fecha_recepcion`**: `Date` - Fecha y hora de recepción del dispositivo.
* **`estado`**: `String` - Estado actual (Recepción, diagnóstico, presupuesto, en reparación, reparado, entregado).
* **`tipo_servicio`**: `String` - Tipo solicitado (Reparación, mantenimiento o garantía).
* **`prioridad`**: `String` - Nivel de atención (Normal o Urgente).
* **`tecnico_asignado`**: `String` - Nombre del técnico responsable de la reparación del dispositivo.
* **`fecha_estimada`**: `Date` - Fecha estipulada de entrega.
* **`fecha_entrega`**: `DateTime` - Fecha y hora real de entrega al cliente.


### 4. Entidad: `Repuesto`
Administra el inventario de piezas y componentes[cite: 8].
* **`id_repuesto`**: `Integer (PK)` - Identificador único del repuesto.
* **`codigo_interno`**: `String` - Código de referencia para alta y baja de stock.
* **`descripcion`**: `String` - Nombre y características técnicas del repuesto.
* **`stock_actual`**: `Integer` - Cantidad disponible en depósito.
* **`stock_minimo`**: `Integer` - Límite que muestra una alerta automática de reposición.
* **`precio`**: `Decimal` - Precio de venta del repuesto.
* **`compatible_con`**: `String` - Marcas o modelos de equipos compatibles con el repuesto.

### 5. Entidad Intermedia: `Repuesto_Orden`
Registra qué repuestos se usaron en cada orden para el descuento de stock y cálculo de costos.
* **`id_repuesto_orden`**: `Integer (PK)` - Identificador único del registro.
* **`id_orden`**: `Integer (FK)` - Referencia a la orden de reparación.
* **`id_repuesto`**: `Integer (FK)` - Referencia al repuesto utilizado.
* **`cantidad`**: `Integer` - Unidades utilizadas en la orden.
* **`precio_aplicado`**: `Decimal` - Precio del repuesto al momento de la reparación.


### 6. Entidad: `Cobro`
Registra los pagos y transacciones financieras.
* **`id_cobro`**: `Integer (PK)` - Identificador único del registro de cobro.
* **`id_orden`**: `Integer (FK)` - Vinculación del pago con el historial de la reparación.
* **`monto_total`**: `Decimal` - Importe total (mano de obra más repuestos).
* **`metodo_pago`**: `String` - Medio utilizado (Efectivo, tarjeta, transferencia).
* **`fecha_cobro`**: `DateTime` - Fecha y hora en que se efectuó el pago.
* **`comprobante_emitido`**: `Boolean` - Indica si se generó y se envió el comprobante digital.
* **`pagado`**: `Boolean` - Estado del pago (Confirmado / Pendiente).

