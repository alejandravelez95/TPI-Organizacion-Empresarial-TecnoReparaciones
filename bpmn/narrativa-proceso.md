
# Sistema de Gestión de Servicios Técnicos (SGST) - TECNO REPARACIONES

A continuación se desarrollará el modelado del proceso de negocio para el desarrollo del **SGST**, un sistema diseñado para automatizar y transformar digitalmente la Gestión de Órdenes de Reparación de la empresa TECNO REPARACIONES. La implementación del SGST transformará esta operación al registrar cada evento de manera digital, garantizando una trazabilidad del 100% sobre las órdenes de trabajo y optimizando la comunicación con el cliente.

## Arquitectura del Proceso

El proceso se encuentra modelado bajo el estándar internacional BPMN 2.0, estructurado de la siguiente manera:

*   **Pools (Interacción Externa):** 
    *   `CLIENTE`: Actor externo que interactúa con el sistema solicitando el servicio, aprobando presupuestos y retirando el equipo.
    *   `TECNO REPARACIONES`: Organización interna encargada de la logística y ejecución técnica.
*   **Lanes (Roles Internos y Automatización):**
    *   `Área Comercial`: Recepción física del equipo y apertura de la solicitud.
    *   `Sistema SGST`: Carril automatizado encargado del registro de entidades (clientes, equipos, órdenes), actualizaciones de estado en tiempo real, control de flujos y notificaciones automáticas.
    *   `Área de Servicios Técnicos`: Diagnóstico físico, elaboración de presupuestos y reparación.
    *   `Compras y Logística`: Control de stock de repuestos y gestión con proveedores.
    *   `Área Administrativa`: Gestión de cobros, facturación y registro de deudas.

## Flujo Operativo y Gestión

El modelo cubre el ciclo de vida completo del servicio técnico (desde la admisión hasta la entrega de la unidad) e integra compuertas lógicas exclusivas para resolver de la mejor manera las excepciones críticas del negocio:
1.  **Viabilidad técnica:** Desvío inmediato para equipos categorizados como *irreparables*.
2.  **Validación del cliente:** Control de aprobación o rechazo del presupuesto (con cancelación automática de la orden).
3.  **Abastecimiento:** Bucle de control de stock y solicitudes de compra automatizadas a proveedores en caso de faltantes.
4.  **Control de calidad:** Bucle de retorno al técnico si el equipo no supera las pruebas de funcionamiento.
5.  **Cierre financiero:** Compuesta por dos ramas entre la emisión del comprobante de pago o el registro de deudas pendientes en el sistema.
