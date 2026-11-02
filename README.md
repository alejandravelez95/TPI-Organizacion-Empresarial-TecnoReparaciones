# TPI-Organizacion-Empresarial-TecnoReparaciones
Trabajo Práctico Integrador y Progresivo
Tecnicatura Universitaria en Programación a Distancia (TUP AD) — Universidad Tecnológica Nacional
Asignatura: Organización Empresarial | Docente titular: Prof. Gabriela Martínez | Tutora: Prof. Martina Zabala

## Descripción del sistema
Sistema centralizado para sistematizar la administración de clientes, equipos, órdenes de trabajo, diagnósticos, presupuestos, repuestos y cobros de TECNO REPARACIONES. Garantiza trazabilidad completa del 100% de las órdenes, control automático de stock con alertas de reposición (margen de error < 1%) y tiempos de respuesta inferiores a 2 segundos en el 95% de las transacciones. Ciclo de vida del software planificado en 24 semanas (Análisis → Diseño → Codificación → Pruebas → Implementación).

## Integrante
- Alejandra Luján Vélez

 ## Contenido del repositorio
| Carpeta | Contenido |
|---|---|
| `/docs` | Informes de las entregas 1 a 4 (PDF) e indicadores de control |
| `/bpmn` | Diagrama BPMN del proceso "Gestión de Órdenes de Reparación" (.bpmn + PNG) y su narrativa |
| `/diccionario-datos` | Diccionario de Datos inicial (entidades: cliente, equipo, orden, repuesto, repuesto_orden, cobro) |
| `/backlog` | Historias de usuario y gestión del tablero ágil |

## Flujo de trabajo (Git Flow simplificado)
- `main`: versión estable de la documentación.
- `develop`: integración de las ramas de trabajo antes de producción.
- `feature/*`: ramas por unidad de trabajo (bpmn, historias-usuario, control-indicadores).
- Todo merge a `main` se realiza mediante Pull Request con revisión.

## Historias de usuario
1. **HU-01 (Alta)** — Como recepcionista del Área Comercial, quiero registrar al cliente, su equipo y generar la orden de trabajo en menos de 2 minutos, para agilizar la recepción y darle al cliente un número de seguimiento.
2. **HU-02 (Alta)** — Como técnico del Área de Servicios Técnicos, quiero consultar el stock de repuestos desde la orden y recibir alertas automáticas de reposición, para evitar demoras y mantener el margen de error de stock por debajo del 1%.
3. **HU-03 (Media)** — Como cliente, quiero consultar en línea el estado de mi orden con su historial completo (recepcion, diagnostico, presupuestado, en_reparacion, reparado, entregado), para no depender de llamados telefónicos.

## Declaración de Uso de IA
En el desarrollo de este proyecto utilicé asistentes de Inteligencia Artificial como apoyo para diagramar las figuras (matriz FODA, Gantt, organigrama, BPMN), corregir la redacción de los informes y estructurar borradores de textos. Las decisiones de diseño fueron propias: la elección del proceso a
modelar, la priorización de las historias de usuario según las metas cuantitativas del proyecto, la incorporación de la tarea T9a (preparación del entorno de simulación de carga) y la estrategia de ramas del repositorio.
Las correcciones sobre como armar (2 pools, lanes, compuertas exclusivas y caminos de excepción) y validar la coherencia de los indicadores de control con las seis metas de la Entrega 2.

---
*Enlaces: [Repositorio](https://github.com/alejandravelez95/TPI-Organizacion-Empresarial-TecnoReparaciones) | Tablero ágil: https://github.com/users/alejandravelez95/projects/3/views/1*
