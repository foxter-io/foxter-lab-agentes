# Diccionario de datos · Brisa Clima

Todos los datos son inventados. Cubren del 1 de diciembre de 2024 al 24 de noviembre de 2026. Los archivos son CSV separados por comas, con cabecera y codificación UTF-8. Las fechas tienen el formato `AAAA-MM-DD` y los importes están en euros.

Los archivos están conectados entre sí por `cliente_id`, `equipo_id`, `oportunidad_id`, `incidencia_id` y `campana_id`.

## clientes.csv · 1.264 filas
Clientes de Brisa Clima.

| Columna | Qué es |
|---|---|
| cliente_id | Identificador (C0001) |
| nombre | Nombre del cliente |
| sector | Oficinas, Hotel, Retail, Sanitario, Educación o Restauración |
| zona | Barcelonès, Vallès Occidental, Vallès Oriental, Baix Llobregat, Maresme o Garraf |
| municipio | Municipio |
| fecha_alta | Fecha en la que se hizo cliente |
| contrato_mantenimiento | Sí o No |
| importe_anual_contrato_eur | Importe anual del contrato de mantenimiento (0 si no tiene) |
| comercial | Comercial asignado |

## oportunidades.csv · 609 filas
Oportunidades de venta. Las usa sobre todo **Max**.

| Columna | Qué es |
|---|---|
| oportunidad_id | Identificador (OP0001) |
| fecha_creacion | Fecha de creación |
| empresa | Empresa |
| cliente_id | Cliente, si ya lo era o si se ganó la oportunidad |
| sector, zona | Sector y zona |
| servicio | Servicio ofrecido |
| origen | Canal del que viene: Google Ads, LinkedIn Ads, SEO, Directorios, Ferias o Referidos |
| comercial | Comercial responsable |
| importe_eur | Importe de la propuesta |
| estado | Ganada, Perdida o Abierta |
| etapa | Visita técnica, Propuesta enviada, Negociación, Cerrada ganada o Cerrada perdida |
| fecha_cierre | Fecha de cierre (o fecha prevista si está abierta) |
| motivo_perdida | Precio, Sin presupuesto, Plazo, Sin respuesta o Eligió otra solución |
| competidor | Competidor que ganó, si se conoce |
| nota | Comentario del comercial |

## campanas.csv · 60 filas
Campañas de marketing. Las usa **Mara**.

| Columna | Qué es |
|---|---|
| campana_id | Identificador (CA001) |
| nombre | Nombre de la campaña |
| canal | Google Ads, LinkedIn Ads, SEO, Directorios, Ferias o Referidos |
| fecha_inicio, fecha_fin | Fechas de la campaña |
| coste_eur | Coste total de la campaña |

## leads.csv · 4.000 filas
Contactos interesados que llegan por cada canal. Los usa **Mara**.

| Columna | Qué es |
|---|---|
| lead_id | Identificador (LD00001) |
| fecha | Fecha de entrada |
| canal | Canal de entrada |
| campana_id | Campaña de la que viene |
| empresa, sector, zona | Datos de la empresa (sector puede ser también Industrial o Particular) |
| estado | Nuevo, Contactado, Descartado u Oportunidad |
| oportunidad_id | Oportunidad creada a partir del lead, si la hay |
| es_cliente | Sí, si la oportunidad se ganó |
| motivo_descarte | Por qué se descartó |

## equipos.csv · 800 filas
Equipos de climatización instalados en clientes con contrato. Los usan **Clara** y **Otto**.

| Columna | Qué es |
|---|---|
| equipo_id | Identificador (EQ0001) |
| cliente_id, cliente, sector, zona | Cliente donde está instalado |
| modelo | Modelo del equipo |
| tipo | Tipo de equipo |
| potencia_kw | Potencia en kW |
| fecha_instalacion | Fecha de instalación |
| monitorizado | Sí, si envía lecturas diarias |

## incidencias.csv · 2.709 filas
Incidencias del servicio técnico. Las usan **Clara**, **Otto** y **Diana**.

| Columna | Qué es |
|---|---|
| incidencia_id | Identificador (IN00001) |
| fecha_apertura, fecha_cierre | Fechas |
| cliente_id, cliente, sector, zona | Cliente |
| equipo_id, modelo | Equipo afectado (vacío en algunas consultas) |
| tipo | Avería, Ruido o vibraciones, Fuga de refrigerante, Termostato o control, No enfría o no calienta lo suficiente, Revisión solicitada o Consulta |
| prioridad | Alta, Media o Baja |
| horas_resolucion | Horas desde la apertura hasta la solución |
| horas_tecnico | Horas de trabajo del técnico |
| horas_extra | Parte de esas horas hechas fuera de horario |
| tecnico | Técnico que la atendió |
| descripcion | Descripción breve |

## nps.csv · 1.447 filas
Encuestas de satisfacción (de 0 a 10). Las usan **Clara** y **Diana**.

| Columna | Qué es |
|---|---|
| respuesta_id | Identificador |
| fecha | Fecha de respuesta |
| cliente_id, cliente, sector, zona | Cliente |
| puntuacion | De 0 a 10. NPS = % de 9 y 10 menos % de 0 a 6 |
| comentario | Comentario libre (puede estar vacío) |

## lecturas_equipos.csv · 52.938 filas
Lecturas diarias de los equipos monitorizados durante los últimos 12 meses. Las usa **Otto**.

| Columna | Qué es |
|---|---|
| fecha | Día |
| equipo_id | Equipo |
| consumo_kwh | Consumo del día |
| horas_uso | Horas de funcionamiento |
| temp_impulsion_c | Temperatura del aire que sale del equipo |
| alarma | Vacía, «Temperatura alta» o «Fallo» |

## facturas.csv · 4.526 filas
Facturas y costes de cada trabajo. Las usa **Diana**.

| Columna | Qué es |
|---|---|
| factura_id | Identificador (FA00001) |
| fecha | Fecha |
| cliente_id, cliente, sector, zona | Cliente |
| concepto | Cuota de mantenimiento, Reparación, Reparación incluida en contrato, Instalación · anticipo o Instalación · final de obra |
| referencia | Incidencia u oportunidad relacionada |
| importe_eur | Importe facturado (0 si la reparación está incluida en el contrato) |
| coste_materiales_eur | Coste de materiales |
| horas_tecnico | Horas de técnico |
| horas_extra | Horas fuera de horario (cuestan un 75 % más) |
| coste_horas_eur | Coste de las horas |
| margen_eur | Importe menos costes |
