# Plan operativo DMKINGS

## Base de decision

Este plan queda actualizado tomando como referencia principal `DMKINGS Blueprint Operativo.docx`, descargado en este workspace el 2026-05-13. Ese documento sustituye al enfoque anterior centrado en vender una build Windows propia como producto inicial.

La direccion actual es construir DMKINGS como una empresa AI-native de despliegue operativo para pymes industriales: servicios, agentes, RAGs, automatizaciones, skills privadas, conectores y workflows mantenibles. OpenWork sigue siendo un activo importante, pero no debe ser el primer requisito de venta ni el centro unico de la oferta.

## Tesis

DMKINGS convierte procesos industriales repetitivos en workflows asistidos por IA, medibles y mantenibles.

El cliente no compra una app de agentes, prompts sueltos ni horas de consultoria. Compra menos trabajo manual, menos errores, mas velocidad comercial, documentacion mas usable, soporte mas rapido y una forma ordenada de incorporar IA a procesos reales.

La oportunidad inicial esta en Burgos y Castilla y Leon, especialmente en pymes industriales, B2B tecnico, maquinaria, fabricacion a medida, SAT, documentacion pesada, oficina tecnica y equipos de software internos.

Problemas prioritarios:

- ofertas tecnicas lentas
- documentacion dispersa
- tickets y SAT repetitivos
- reporting manual
- Excel eternos
- procesos entre sistemas
- conocimiento tribal dependiente de personas clave

Promesa:

- reducir horas
- reducir errores
- acelerar respuestas y entregables
- hacer reutilizable el conocimiento del cliente
- dejar sistemas versionados, medibles y mejorables

## Principios operativos

- Vender resultado, no IA.
- Empezar con servicios acotados, no con una plataforma enorme.
- Cada cliente debe dejar un activo reusable: skill, template, conector, evaluacion, playbook o modulo.
- Ser tool-agnostic por defecto.
- Usar OpenWork como upsell cuando el cliente necesite workspace propio, permisos, historial, aprobaciones, conectores o experiencia de producto.
- Mantener humano en el loop para decisiones sensibles.
- Medir antes/despues siempre que sea posible.
- Versionar skills, prompts, modulos, evals y entregables.
- Aislar datos y configuraciones por cliente desde el primer dia.

## Posicionamiento

Frase corta:

```text
DMKINGS convierte procesos industriales repetitivos en workflows asistidos por IA, medibles y mantenibles.
```

Frase comercial:

```text
Ensenadnos un proceso que os quite horas y lo convertimos en un workflow de IA util, revisable y medible.
```

Lo que no se debe vender como mensaje principal:

- "Vendemos prompts."
- "Instalamos una app de agentes."
- "Hacemos cualquier cosa con IA."
- "Sustituimos a vuestro equipo."
- "Automatizamos todo sin revision."

Lo que si se debe vender:

- procesos concretos
- pilotos acotados
- ahorro de tiempo
- calidad y trazabilidad
- soporte y mejora continua
- skills privadas y mantenidas
- integraciones con herramientas existentes

## Lineas de negocio

DMKINGS debe arrancar con dos lineas desde el principio.

### 1. Soluciones IA a medida

Incluye agentes, RAGs, automatizaciones, conectores, evaluaciones y workflows para un proceso concreto.

Como se vende:

- discovery pagado
- piloto con scope cerrado
- metrica antes/despues
- decision clara de escalar, mantener o cerrar

Riesgo:

- convertirse en consultoria infinita si no hay limites, reutilizacion y medicion.

### 2. Plugins y packs privados de skills

Incluye skills, comandos, plantillas, instrucciones, criterios, ejemplos, conectores ligeros y documentacion por cliente o vertical.

Como se vende:

- setup inicial
- suscripcion mensual
- mantenimiento, mejoras y biblioteca privada

Riesgo:

- parecer prompts baratos si no hay criterio, versionado, soporte, ejemplos reales y resultados.

## Ofertas iniciales

### AI Process Sprint

Duracion: 1-2 semanas.

Entregables:

- mapa del proceso
- ranking de oportunidades
- ROI estimado
- riesgos
- datos necesarios
- propuesta de piloto

Precio orientativo: 3k-6k EUR.

Objetivo: convertir interes difuso en un caso de uso vendible, medible y con sponsor.

### Custom Agent / RAG Pilot

Duracion: 4-6 semanas.

Entregables:

- un workflow funcional
- usuarios reales
- datos controlados
- evals basicas
- handover
- decision de escalado

Precio orientativo: 8k-25k EUR.

Casos preferentes:

- generador de ofertas tecnicas
- RAG documental serio
- copiloto SAT/postventa
- reporting automatizado

### Private Skill Pack

Formato: mensual.

Entregables:

- biblioteca privada de skills
- versionado
- soporte
- nuevas rutinas
- documentacion
- revision mensual

Precio orientativo: 500-3k EUR/mes.

Objetivo: crear recurrencia ligera y mantener el sistema vivo.

### OpenWork Custom

Duracion: 2-6 semanas.

Entregables:

- workspace propio
- marca
- usuarios
- permisos
- conectores
- skills
- historial
- aprobaciones

Modelo: setup + cuota mensual.

Regla: OpenWork Custom solo se ofrece cuando haya necesidad real de control, adopcion amplia, permisos, historial, conectores o experiencia propia. No debe bloquear la venta inicial.

## Decision de runtime

La decision importante no es Claude, Codex, ChatGPT u OpenWork. La decision importante es reducir friccion y elegir el runtime que encaje con el cliente.

| Opcion | Cuando usarla | Ventaja | Limite |
| --- | --- | --- | --- |
| Claude / ChatGPT | Cliente no tecnico, trabajo documental, analisis, redaccion, soporte y conocimiento interno. | Adopcion facil y poca infraestructura propia. | Menos control sobre workflows, permisos y versionado. |
| Codex / Cursor | Equipos tecnicos, software interno, scripts, repos, tests, docs y ticket-to-PR. | Productividad alta en desarrollo y automatizacion tecnica. | No encaja como interfaz principal para usuarios no tecnicos. |
| OpenWork privado | Cliente necesita entorno propio, marca, usuarios, permisos, conectores, historial y aprobaciones. | Mas margen, control y producto defendible. | Mas coste de soporte. No debe ser requisito inicial. |
| Custom backend/API | RAG serio, integraciones, procesos recurrentes, jobs programados y trazabilidad. | Control tecnico, logs, evals y escalabilidad. | Requiere disciplina de arquitectura y operaciones. |

Regla practica:

```text
Empezar en la herramienta que reduzca friccion. Migrar a OpenWork o backend propio solo cuando haya uso, datos, permisos o recurrencia que lo justifiquen.
```

## Infraestructura interna minima

No construir una plataforma grande al principio. Construir un sistema operativo interno pequeno, versionado y repetible.

### Repos y carpetas recomendadas

| Repositorio/carpeta | Contenido | Regla |
| --- | --- | --- |
| `dmkings-os` | Playbooks, plantillas comerciales, templates de delivery, prompts internos y checklists. | Es el sistema operativo interno de la empresa. |
| `dmkings-skills` | Skills base, skills por vertical, plugins, ejemplos, tests y changelogs. | Cada skill debe tener version, objetivo, inputs, limites y formato de salida. |
| `dmkings-modules` | RAG docs, agent offers, agent SAT, connector packs, eval pack y OpenWork adapter. | Cada modulo debe ser configurable por cliente. |
| `clients/<cliente>` | Config privada, documentos permitidos, skills personalizadas, evals y entregables. | Aislamiento por cliente desde el primer dia. |

### Herramientas iniciales

| Capa | Herramienta inicial | Funcion | Evolucion |
| --- | --- | --- | --- |
| CRM y pipeline | Notion, Airtable, Linear o HubSpot ligero | Leads, conversaciones, oportunidades y propuestas. | CRM formal con metricas de conversion, MRR y pipeline por vertical. |
| Repos y versionado | GitHub privado | Skills, playbooks, templates, modulos, prompts, evals y adaptadores. | Monorepo o repos por modulo con releases y changelogs. |
| Skill registry | Git + indice simple | Catalogo de skills base, verticales y privadas. | Portal con versiones, permisos y telemetria de uso. |
| RAG stack | Supabase/pgvector o Qdrant + storage | Ingesta, embeddings, busqueda, fuentes, permisos y evals. | Multi-cliente con aislamiento fuerte y evaluacion continua. |
| Automations | Cron jobs, GitHub Actions o workers simples | Ingestas, reportes, revision de logs y tareas recurrentes. | Orquestador por cliente con observabilidad y alertas. |
| Observabilidad | Logs simples + costes por cliente | Saber uso, fallos, coste y mejoras. | Dashboard de calidad, coste, errores y ROI. |
| Documentacion | Docs versionados + handover | Manual, changelog, instrucciones y limites. | Centro de conocimiento cliente con onboarding y soporte. |

## Modulos reutilizables

La escalabilidad esta en modulos que se configuran, no proyectos que se reinventan.

| Modulo | Primer uso comercial | Output | Reutilizacion |
| --- | --- | --- | --- |
| `rag-docs` | Copiloto documental para manuales, procedimientos, fichas, contratos o SharePoint. | Respuesta con fuentes, resumen, citas y nivel de confianza. | Casi todos los clientes industriales tienen documentacion pesada. |
| `agent-offers` | Generador de ofertas tecnicas y memoria comercial. | Borrador de oferta, checklist de revision y email al cliente. | Buen caso para oficina tecnica y ventas. |
| `agent-sat` | Asistente de tickets, incidencias, repuestos y respuestas. | Resumen, diagnostico sugerido, piezas, pasos y borrador. | Encaja en empresas con postventa o mantenimiento. |
| `agent-reporting` | Reportes desde Excel, ERP, CRM o exports manuales. | Informe semanal, alertas, KPIs y narrativa para direccion. | Repetible en operaciones, finanzas y ventas. |
| `skill-pack` | Biblioteca privada de rutinas por rol o vertical. | Skills instalables, versionadas y documentadas. | Base del paywall mensual. |
| `connector-pack` | Drive, SharePoint, email, hojas, repos o CRM ligero. | Lectura/escritura controlada y logs. | Reduce coste de nuevas implantaciones. |
| `eval-pack` | Pruebas de calidad y regresion para RAGs/agentes. | Dataset, tests, criterios y reporte de fallos. | Evita que cada mejora rompa lo anterior. |

Cada modulo debe definir:

- input esperado
- herramientas necesarias
- output
- limites
- criterios de calidad
- casos de prueba
- configuracion por cliente
- logs/evidencia de ejecucion

## Agentes internos

DMKINGS debe usar agentes internamente para que dos personas puedan llevar varios clientes sin rehacer todo cada vez. Los agentes producen borradores buenos; el equipo humano aporta criterio, revision y responsabilidad.

| Agente interno | Input | Output | Revision humana |
| --- | --- | --- | --- |
| Discovery Agent | Grabacion, notas, web del cliente y documentos iniciales. | Mapa de proceso, dolores, sistemas, datos, riesgos y quick wins. | Validar que entiende el negocio y no inventa procesos. |
| Proposal Agent | Discovery validado, paquete elegido y restricciones. | Propuesta, scope, precio, timeline, exclusiones y datos necesarios. | Ajustar precio, promesa y limites. |
| Solution Architect Agent | Caso de uso, herramientas, datos y usuarios. | Arquitectura recomendada, modulos, runtime y plan de integracion. | Elegir tradeoffs y bloquear scope. |
| Skill Builder Agent | Ejemplos, documentos, tono, criterios y output esperado. | Skills privadas con instrucciones, validaciones y formatos. | Probar con casos reales y editar criterio. |
| RAG Builder Agent | Documentos, taxonomia, permisos y preguntas frecuentes. | Plan de ingesta, chunking, metadatos, evals y queries de prueba. | Revisar seguridad, fuentes y calidad. |
| QA / Evals Agent | Sistema construido, dataset y casos extremos. | Reporte de fallos, respuestas malas, gaps y regresiones. | Decidir si se entrega o se corrige. |
| Client Success Agent | Uso, feedback, tickets, logs y cambios solicitados. | Resumen mensual, mejoras propuestas y renovacion de valor. | Priorizar y convertir mejoras en roadmap. |
| Docs Agent | Sistema final, skills, limites y ejemplos. | Manual del cliente, changelog y guia de uso. | Asegurar claridad y no prometer capacidades falsas. |
| Security Agent | Datos, permisos, acciones sensibles e integraciones. | Checklist de riesgos, aprobaciones y limites. | Bloquear automatizaciones peligrosas. |

Regla:

```text
Todo output de agente interno queda como borrador revisable. En clientes reales, DMKINGS vende criterio y responsabilidad, no automatismo ciego.
```

## Primer cliente

El primer cliente debe validar un proceso, cobrar, aprender y crear activos reutilizables. No debe servir para demostrar todas las posibilidades de DMKINGS.

### Caso recomendado

El primer caso mas vendible probablemente sea uno de estos:

1. Generador de ofertas tecnicas.
2. RAG documental serio.

Por que:

- se entienden rapido
- aparecen en muchas pymes industriales
- permiten medir tiempo ahorrado
- generan activos reutilizables
- no exigen una plataforma completa desde el primer dia

Computer-use y automatizacion de navegador pueden ser demos potentes, pero no deberian ser la primera promesa si el proceso es fragil o dificil de mantener.

### Flujo de trabajo con el primer cliente

| Paso | Objetivo | Entregable | Decision |
| --- | --- | --- | --- |
| 1. Conversacion inicial | Detectar dolor real, sponsor, frecuencia, datos y urgencia. | Notas estructuradas y resumen del Discovery Agent. | Aceptar discovery o descartar. |
| 2. AI Process Sprint | Mapear 1-3 procesos y elegir uno. | Mapa, ROI estimado, riesgos y propuesta de piloto. | Elegir un solo caso de uso. |
| 3. Scope de piloto | Cerrar alcance, duracion, usuarios, datos y metricas. | Propuesta con precio, limites y calendario. | Firmar piloto o no avanzar. |
| 4. Setup cliente | Crear espacio, permisos, repo/carpeta, datos y canales. | Cliente aislado con config, docs y checklist de seguridad. | Validar acceso y datos. |
| 5. Construccion | Instanciar modulos base y personalizar skills/RAG/agente. | Workflow funcional en Claude, Codex, backend u OpenWork. | Probar con casos reales. |
| 6. QA y evals | Detectar alucinaciones, errores, permisos y outputs malos. | Reporte de calidad y lista de correcciones. | Entregar solo si supera criterios minimos. |
| 7. Handover | Que usuarios lo usen sin depender de DMKINGS. | Manual, ejemplos, limites, formacion y canal de soporte. | Pasar a uso real. |
| 8. Medicion | Comparar antes/despues. | Horas ahorradas, errores evitados, uso y feedback. | Escalar, mantener o cerrar. |
| 9. Retainer | Convertir piloto en sistema vivo. | Private Skill Pack mensual, mejoras y success report. | Crear MRR y roadmap. |

## Roadmap

### 0-30 dias

Objetivo: preparar venta y delivery sin plataforma pesada.

Activos:

- pitch de una pagina
- discovery template
- ROI template
- proposal template
- demo de ofertas tecnicas o RAG documental
- 5 skills base
- cliente workspace template
- checklist de seguridad
- evals basicas
- handover template

Indicador de exito:

- poder mandar propuestas en menos de 48 horas.

### 30-90 dias

Objetivo: cerrar primer cliente/piloto y convertirlo en caso reusable.

Activos:

- cliente aislado
- modulo inicial
- evals
- manual
- reporte de resultados
- skill pack privado

Indicador de exito:

- primer piloto cobrado y medido.

### 3-6 meses

Objetivo: repetir en 2-4 clientes sin rehacer todo.

Activos:

- catalogo de skills
- playbooks afinados
- portal simple o indice privado
- reporting mensual
- paquetes comerciales

Indicador de exito:

- MRR inicial y menos horas por entrega.

### 6-12 meses

Objetivo: consolidar verticales y producto opcional.

Activos:

- OpenWork custom para clientes que lo justifiquen
- modulos maduros
- observabilidad
- seguridad
- pricing por niveles
- casos publicables

Indicador de exito:

- varios clientes recurrentes y biblioteca reusable real.

## Pricing operativo

El pricing detallado vive en `DMKINGS Pricing Model y Cobro.docx`, pero este plan adopta sus reglas base:

- discovery pagado
- piloto cerrado
- setup inicial si pasa a produccion
- mensualidad por sistema vivo
- costes de herramientas y consumo separados
- OpenWork como licencia/setup solo si hay producto real alrededor

Regla central:

```text
Cobrar por resultado operativo y continuidad, no por horas visibles.
```

Uso de horas:

- calculo interno de margen
- ampliaciones fuera de scope
- soporte puntual
- bolsa mensual
- nunca como producto principal

## Riesgos y reglas duras

| Riesgo | Sintoma | Regla |
| --- | --- | --- |
| Scope creep | El cliente pide mas procesos antes de validar el primero. | Un piloto, un proceso, una metrica. Lo demas entra en backlog. |
| Cliente sin sponsor | Interes difuso, nadie decide, nadie mide. | No empezar piloto sin responsable, usuarios y metrica de exito. |
| Datos caoticos | No hay documentos, permisos ni ejemplos suficientes. | Discovery pagado antes de prometer delivery. |
| Integraciones raras | ERP o legacy sin API ni entorno claro. | Cobrar investigacion tecnica o dejarlo fuera del primer piloto. |
| Prometer demasiado | El cliente espera autonomia total sin revision. | Humano en el loop para acciones sensibles y outputs criticos. |
| Seguridad floja | Documentos sensibles sin permisos ni trazabilidad. | Aislamiento por cliente y checklist de datos antes de ingestar. |
| Dependencia de herramienta | Todo vive en una plataforma que puede cambiar. | Mantener skills, prompts, datos y evals en formatos portables. |
| Producto prematuro | Meses construyendo OpenWork sin clientes usando el sistema. | Producto solo despues de demanda repetida o necesidad real de control. |

## Relacion con OpenWork y Matrix

La build Windows propia y el trabajo anterior sobre Matrix siguen siendo utiles, pero cambian de posicion estrategica.

Antes:

- Matrix como producto principal.
- Venta centrada en app Windows personalizada.
- OpenWork como base tecnica para empaquetar.

Ahora:

- DMKINGS como empresa de despliegue AI-native.
- Venta centrada en procesos industriales y resultados medibles.
- OpenWork/Matrix como runtime premium cuando el cliente necesita control, permisos, historial, conectores, marca o experiencia propia.

Acciones recomendadas:

- no abandonar OpenWork
- no convertir la build Windows en requisito de cada venta
- usar el conocimiento de OpenWork para crear demos y opciones premium
- mantener skills y workflows portables para Claude, Codex, ChatGPT y OpenWork
- evitar meses de producto antes de tener pilotos reales

## Checklist antes de vender agresivamente

- Pitch de una pagina.
- Discovery template.
- ROI template.
- Proposal template.
- Demo de generador de ofertas tecnicas o RAG documental.
- 5 skills base.
- Cliente workspace template.
- Checklist de seguridad.
- Evals basicas.
- Handover template.
- Pricing base con discovery, piloto, setup y retainer.
- Lista de exclusiones y condiciones de scope.

## Decision final

DMKINGS debe vender servicios AI-native ahora y construir producto solo donde el uso real lo pida.

La maquina correcta es:

```text
discovery pagado -> piloto acotado -> modulos reutilizables -> skills privadas -> evaluacion -> soporte -> mejora continua
```

Si cada cliente deja un activo reusable, dos personas pueden llevar varios clientes sin que el negocio se rompa. Si cada cliente exige una solucion artesanal sin versionado, limites ni metricas, DMKINGS se convertira en una consultora dificil de escalar.
