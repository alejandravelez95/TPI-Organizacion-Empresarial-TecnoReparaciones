# Narrativa del proceso — Gestión de Órdenes de Reparación

## Flujo estándar
1. El CLIENTE entrega el equipo (inicio del proceso).
2. El Área Comercial recepciona el equipo y registra la solicitud.
3. El Sistema SGST registra al cliente y al equipo, y genera la orden de trabajo (estado: recepcion).
4. El Área de Servicios Técnicos diagnostica el equipo; si es reparable, elabora el presupuesto (estado: presupuestado) y el sistema se lo envía al cliente.
5. El CLIENTE aprueba el presupuesto y autoriza la reparación (evento de mensaje).
6. El técnico repara el equipo; si necesita repuestos, Compras y Logística verifica stock y gestiona la compra. Luego prueba el funcionamiento (estado: reparado).
7. El Sistema SGST notifica al cliente que el equipo está listo para retirar.
8. El Área Administrativa registra el cobro (entidad COBRO, pagado = true) y emite el comprobante; el sistema registra el pago y cierra la orden (estado: entregado). Fin.

## Excepciones (compuertas XOR)
- ¿Equipo reparable? → No: fin "Equipo irreparable".
- ¿Cliente aprueba presupuesto? → No: fin "Orden cancelada".
- ¿Necesita repuestos? → No: salta directo a la prueba.
- ¿Hay stock disponible? → No: solicitar compra y recepcionar repuesto (loop).
- ¿Reparación exitosa? → No: vuelve a reparación.
- ¿Pago realizado? → No: queda en espera.
