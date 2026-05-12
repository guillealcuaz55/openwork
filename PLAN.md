# Plan de empaquetado y venta de Matrix

## Idea del proyecto

Matrix es una version propia basada en OpenWork, empaquetada para Windows y preparada para ofrecerse a clientes con configuraciones, skills y workflows personalizados.

La idea no es revender directamente la version comercial de OpenWork, sino trabajar sobre el codigo open source, modificarlo, compilarlo y distribuir una build propia. Esto da mas control sobre marca, instalador, experiencia de usuario, skills incluidas y modelo comercial.

## Lo que ya funciona

Ya se ha comprobado que el proyecto puede compilarse en Windows desde el codigo fuente.

Se clono el repositorio de OpenWork, se preparo el entorno de compilacion y se genero un instalador Windows propio con Electron Builder y NSIS.

El instalador generado fue:

```text
C:\matrix\apps\desktop\dist-electron\openwork-win-x64-0.13.5.exe
```

El paquete incluye los binarios necesarios:

- `opencode.exe`
- `openwork-orchestrator.exe`
- servidor OpenWork integrado en proceso
- interfaz desktop Electron

Esto demuestra que no es obligatorio comprar la build Windows oficial para tener una version Windows propia, siempre que se compile y mantenga desde el repo open source.

## Que se necesito para compilar

Para construir la version Windows hizo falta preparar una maquina de build con:

- Node.js
- pnpm via Corepack
- Bun
- Visual Studio Build Tools 2022 con soporte C++
- Electron Builder

El primer bloqueo fue `better-sqlite3`, que necesitaba compilar codigo nativo con `node-gyp`. Tras instalar Visual Studio Build Tools, la instalacion de dependencias funciono correctamente.

Despues se ejecuto el build de escritorio y se genero el instalador Windows.

## Punto importante sobre la firma

El instalador actual se genero sin firma de codigo.

Para pruebas y desarrollo esto es suficiente. Para venderlo a clientes, lo recomendable seria firmar el `.exe` con un certificado de firma de codigo, porque Windows SmartScreen puede mostrar avisos de editor desconocido si el instalador no esta firmado.

La firma no impide vender el producto, pero mejora la confianza y reduce friccion al instalarlo.

## Como se customiza

No se modifica el `.exe` directamente.

El flujo correcto es:

1. Modificar el codigo fuente en `C:\matrix`.
2. Cambiar marca, textos, iconos, configuracion y skills.
3. Commit y push a un fork propio.
4. Generar de nuevo el instalador Windows.
5. Entregar el instalador al cliente.

Cambios tipicos:

- nombre de la app
- iconos
- `appId`
- nombre del instalador
- pantalla inicial
- textos de onboarding
- skills preinstaladas
- configuracion por defecto
- conectores o MCPs incluidos
- plantillas de trabajo por sector

## Modelo comercial

El proyecto puede venderse como una herramienta personalizada para clientes.

El valor no esta solo en OpenWork, sino en:

- empaquetado Windows listo para instalar
- skills hechas para el negocio del cliente
- workflows repetibles
- configuracion inicial
- soporte
- formacion
- actualizaciones
- integraciones con herramientas del cliente

Ejemplos de oferta:

- instalador Matrix para inmobiliarias
- Matrix para despachos profesionales
- Matrix para equipos comerciales
- Matrix para creadores de contenido
- Matrix para backoffice y automatizacion documental

## Desarrollo del valor comercial

Matrix no se vende como "una app de agentes" generica. Se vende como una solucion operativa empaquetada para que un cliente pueda empezar a usar agentes en su negocio sin tener que entender OpenCode, MCP, skills, configuraciones, compilaciones o servidores.

El valor comercial principal esta en reducir friccion, riesgo y tiempo de adopcion.

### Instalador listo para Windows

Para muchos clientes, especialmente pymes, despachos, inmobiliarias, equipos comerciales y backoffice, Windows sigue siendo el entorno principal. Un instalador `.exe` listo para usar convierte un proyecto tecnico en un producto comprensible.

El cliente no compra un repositorio ni una guia de instalacion. Compra una aplicacion que puede instalar, abrir y usar.

Este punto permite ofrecer:

- instalador con marca Matrix o marca blanca del cliente
- nombre, icono, `appId` y artefactos personalizados
- version portable o instalable segun el caso
- configuracion inicial ya incluida
- binarios necesarios empaquetados
- actualizaciones controladas por version
- instalacion asistida en equipos del cliente

Tambien permite crear una oferta simple:

```text
Matrix para Windows: instalacion, configuracion inicial y puesta en marcha.
```

### Skills por sector

Las skills son una de las partes mas vendibles porque convierten la herramienta general en una herramienta especifica para el negocio del cliente.

En vez de vender "puedes pedirle cosas a un agente", se vende:

- "genera descripciones de inmuebles desde estos datos"
- "prepara respuestas a leads comerciales"
- "resume expedientes"
- "convierte documentos en tareas"
- "clasifica solicitudes de clientes"
- "redacta informes con el tono del despacho"
- "prepara publicaciones para redes"
- "audita una carpeta de documentos"

Ejemplos de skills por sector:

- inmobiliarias: importacion de anuncios, descripcion de propiedades, respuestas a interesados, comparativas de mercado, checklist de publicacion
- despachos profesionales: resumen de expedientes, borradores de email, analisis de documentos, preparacion de notas internas
- equipos comerciales: enriquecimiento de leads, seguimiento de oportunidades, guiones de llamada, propuestas comerciales
- creadores de contenido: calendario editorial, guiones, reutilizacion de contenido, posts por canal
- backoffice: clasificacion documental, extraccion de datos, generacion de reportes, control de tareas repetitivas

El valor no esta solo en escribir prompts. Esta en empaquetar criterio operativo: contexto, tono, pasos, validaciones, formatos de salida y ejemplos reales del cliente.

### Workflows repetibles

Un workflow repetible es un proceso que el cliente puede ejecutar muchas veces con resultados consistentes.

Esto es mas valioso que una conversacion suelta con un chat, porque convierte Matrix en una herramienta de produccion. El cliente puede decir: "cada vez que entra un documento, hacemos este flujo" o "cada vez que llega un lead, seguimos estos pasos".

Ejemplos:

- recibir datos de un inmueble -> generar descripcion -> preparar respuestas -> crear checklist de publicacion
- recibir un PDF -> resumirlo -> extraer puntos clave -> generar tareas -> redactar email de respuesta
- recibir un lead -> clasificarlo -> preparar contexto -> proponer siguiente accion -> registrar seguimiento
- recibir una carpeta de archivos -> revisar faltantes -> generar informe -> preparar mensaje al cliente

Cada workflow puede incluir:

- instrucciones paso a paso
- skills concretas
- conectores MCP
- plantillas de documentos
- reglas de validacion
- formato final de entrega
- puntos donde el usuario debe aprobar antes de continuar

Esto permite vender paquetes por proceso, no solo horas de consultoria.

### Soporte

El soporte es parte del producto porque los clientes no solo necesitan que Matrix funcione, sino que encaje en su forma real de trabajar.

El soporte puede incluir:

- instalacion inicial
- resolucion de problemas de Windows
- actualizaciones
- ajuste de skills
- recuperacion ante errores de configuracion
- ayuda con permisos, modelos y proveedores
- formacion de usuarios
- sesiones de mejora mensual

El soporte tambien protege el margen comercial: una build personalizada sin soporte puede convertirse en una carga; una build con soporte se convierte en servicio recurrente.

Modelos posibles:

- setup inicial de pago
- mantenimiento mensual
- bolsa de horas
- soporte premium por cliente
- SLA para equipos que dependan de Matrix diariamente

### Integraciones

Las integraciones hacen que Matrix pase de ser una app aislada a formar parte del sistema operativo del negocio.

El objetivo no es integrarlo todo desde el primer dia, sino conectar las herramientas que ya generan trabajo para el cliente.

Integraciones posibles:

- Google Drive o OneDrive para documentos
- Gmail, Outlook o email corporativo
- CRM del cliente
- hojas de calculo
- Slack, WhatsApp, Telegram o canales internos
- bases de datos o paneles propios
- APIs sectoriales
- herramientas de firma, facturacion o gestion documental

La integracion se puede vender por niveles:

- basica: importar/exportar archivos y plantillas
- intermedia: conectar cuentas y leer/escribir datos
- avanzada: automatizar flujos completos con aprobaciones

Este apartado puede convertirse en una fuente importante de ingresos porque cada cliente suele tener sistemas distintos.

### Personalizacion por cliente

La personalizacion convierte Matrix en una solucion percibida como propia.

Puede incluir:

- marca del cliente
- icono y nombre del producto
- pantalla inicial
- tono de comunicacion
- skills propias
- workflows internos
- plantillas de documentos
- conectores preconfigurados
- proveedores/modelos permitidos
- reglas de permisos
- estructura de carpetas recomendada
- configuracion para usuarios tecnicos y no tecnicos

Hay dos lineas comerciales claras:

1. Matrix como producto propio, con marca Matrix y paquetes por sector.
2. Matrix marca blanca, adaptado para que el cliente lo use internamente con su identidad.

La marca blanca puede cobrarse mas cara porque incluye mas configuracion, mas responsabilidad y mas valor percibido.

### Capas de personalizacion vendibles

Para vender Matrix, la personalizacion debe ir mas alla de cambiar el logo. La promesa comercial fuerte es que cada cliente sienta que Matrix entiende sus herramientas, reglas, tono, procesos y marca.

Capas principales:

- personalizacion visual: nombre, logo, icono, colores, tipografia, tema claro/oscuro, pantalla inicial y dashboard por rol
- personalizacion del agente: perfiles como CTO, product manager, soporte, ventas, analista o asistente documental
- tono y estilo: directo, pedagogico, formal, creativo, tecnico, ejecutivo o adaptado al manual de marca del cliente
- autonomia configurable: solo sugerir, pedir permiso antes de actuar, ejecutar cambios pequenos o funcionar en modo mas automatico
- reglas por workspace: `AGENTS.md`, skills, permisos, prompts, proveedores y modelos permitidos para cada cliente
- memoria de preferencias: frameworks favoritos, forma de explicar, idioma, estructura de entregables, estilo de codigo y criterios de decision
- conocimiento del cliente: documentacion interna, FAQs, procesos, manuales, historico de casos, plantillas y ejemplos reales

Esta capa permite vender Matrix como una herramienta que aprende la forma de trabajar del cliente, no como un chat generico.

### Personalizacion por industria

Una estrategia potente es crear ediciones verticales. Cada edicion comparte la misma base tecnica, pero cambia las skills, workflows, conectores, pantallas iniciales y plantillas.

Ideas de ediciones:

- Matrix para agencias: briefs, landings, propuestas, reporting, campanas y contenido multicanal
- Matrix para inmobiliarias: anuncios, respuestas a leads, comparativas, Idealista, CRM y documentacion comercial
- Matrix para SaaS: issues, PRs, soporte, changelogs, onboarding, releases y documentacion tecnica
- Matrix para ecommerce: fichas de producto, atencion al cliente, inventario, campanas y analisis de pedidos
- Matrix para despachos legales o profesionales: borradores, revision documental, expedientes, compliance y comunicaciones
- Matrix para educacion: tutoria, materiales, seguimiento de alumnos, evaluaciones y comunicacion con familias o alumnos

La clave es no vender "un agente", sino un paquete operativo por sector.

### Workflows y botones propios

El mayor valor percibido aparece cuando Matrix ofrece acciones concretas que el usuario reconoce como parte de su trabajo diario.

Ejemplos de botones o acciones propias:

- crear PR
- responder cliente
- generar informe
- revisar contrato
- preparar release
- importar inmueble
- clasificar lead
- resumir expediente
- preparar propuesta comercial
- generar checklist

Cada accion puede ejecutar un workflow completo:

- leer datos
- razonar con contexto del cliente
- usar una skill concreta
- pedir aprobacion humana si hace falta
- crear un documento, tarea, email o PR
- registrar lo ocurrido

Esto hace que Matrix sea mas facil de vender a usuarios no tecnicos, porque no tienen que saber que skill usar ni que prompt escribir. Solo ven acciones claras.

### Conectores como fuente de valor

Cada cliente tiene un sistema de trabajo distinto. Por eso, los conectores pueden ser una fuente importante de personalizacion y facturacion.

Conectores prioritarios:

- GitHub, GitLab, Linear o Jira
- Slack, Teams, WhatsApp o Telegram
- Google Drive, OneDrive, Notion, Airtable o Sheets
- Gmail, Outlook o email corporativo
- CRM como HubSpot, Pipedrive o Salesforce
- ecommerce como Shopify o WooCommerce
- infra y producto como Vercel, Supabase, Neon, Docker o AWS

La oferta puede dividirse en:

- integracion basica: importar y exportar archivos
- integracion intermedia: leer y escribir datos en herramientas del cliente
- integracion avanzada: automatizar flujos completos con aprobaciones y auditoria

### Permisos y seguridad como diferencial

Si Matrix se vende a empresas, la personalizacion de permisos es tan importante como la personalizacion visual.

Capacidades necesarias:

- roles por organizacion: admin, manager, operator y viewer
- permisos por agente, skill, conector y workspace
- aprobaciones antes de acciones sensibles
- modo sandbox para tareas peligrosas
- auditoria de acciones: quien pidio que, que hizo el agente y que archivos o sistemas toco
- politicas por cliente: no tocar produccion, no enviar emails sin revision, no publicar sin aprobacion, no leer carpetas no autorizadas

Esto permite vender confianza, no solo automatizacion.

### Paquetes comerciales posibles

Matrix puede empaquetarse por niveles:

- Starter: app local, agentes basicos, personalizacion visual ligera y skills iniciales
- Pro: skills personalizadas, workflows, memoria por workspace y conectores basicos
- Team: roles, permisos, colaboracion, auditoria y plantillas compartidas
- Enterprise: marca blanca, self-hosting, SSO, politicas, conectores privados y soporte premium
- Vertical editions: paquetes especificos como Matrix para inmobiliarias, agencias, SaaS, ecommerce o despachos profesionales

El posicionamiento recomendado:

```text
Matrix no es solo una app de agentes. Es un sistema operativo personalizado para trabajar con agentes en tu negocio.
```

La frase comercial podria ser:

```text
Matrix se adapta a las herramientas, reglas, tono, workflows y marca de tu equipo.
```

### Posibles mejoras sobre el OpenCode actual

Ademas de la personalizacion visual y de las skills personalizadas, Matrix puede diferenciarse tocando codigo del producto para mejorar la experiencia base de OpenCode/OpenWork. La idea no es convertir Matrix en un CRM, ClickUp o software vertical clasico, sino en una capa mas potente para manejar el PC, el navegador, las tools y el negocio con lenguaje natural.

Mejoras con mas sentido:

- UI en skills: permitir que una skill no sea solo texto/instrucciones, sino que pueda exponer una mini-interfaz con inputs, formularios, checklist, progreso, preview de resultado y botones de aprobacion.
- Opcion chat-first: aunque exista UI para skills, mantener siempre la opcion de usar la misma capacidad desde chat o voz. La UI debe ayudar a empresas y usuarios menos tecnicos, no sustituir el lenguaje natural.
- Integracion profunda con navegador: muchas empresas viven dentro de CRMs, ERPs, bancos, portales, marketplaces y herramientas web internas. Matrix deberia poder observar tabs, controlar sesiones, extraer datos, rellenar formularios, descargar archivos, recordar rutinas web y repetirlas con aprobacion.
- Memoria como ciclo de autoaprendizaje: despues de ejecutar tareas, Matrix puede capturar resultados, pasos, tools usadas, errores, permisos y feedback; despues proponer memorias, reglas, skills o automations nuevas.
- Autoaprendizaje gobernado: el agente no deberia modificarse libremente en silencio. Deberia observar, proponer y pedir aprobacion antes de guardar memoria, crear una skill, refinar una skill existente o activar una automation.
- Skill proposals: al terminar una sesion, Matrix puede sugerir "guardar esto como skill", "crear accion rapida" o "recordar esta regla".
- Skill diff: cuando Matrix proponga mejorar una skill, debe mostrar que cambio, por que, de que sesion viene y permitir aceptar, editar o rechazar.
- Memory inbox: una bandeja de aprendizajes pendientes de aprobar, olvidar o convertir en regla. Ejemplos: preferencias detectadas, rutinas repetidas, errores recurrentes, pasos de navegador aprendidos o permisos habituales.
- Run recorder: guardar un registro estructurado de cada ejecucion con objetivo, pasos, tools, archivos/webs tocadas, aprobaciones, resultado y evaluacion del usuario.
- Pattern detector: detectar tareas repetidas, formatos corregidos varias veces, portales usados de forma recurrente o skills que fallan por el mismo motivo.
- Tool readiness: cuando Matrix no pueda hacer algo, deberia proponer que falta: conectar un MCP, instalar una tool, crear una skill, dar permiso a una carpeta, configurar navegador o preparar una credencial.
- Browser memory: recordar como se opera una web concreta: donde estan los leads, que boton exporta, que filtro usar, como se rellena un formulario, donde se descarga un informe o que pasos requieren confirmacion.
- Automations desde memoria: convertir rutinas repetidas en tareas programadas o disparadas por evento, manteniendo aprobaciones para acciones sensibles.

La propuesta fuerte:

```text
Matrix no reemplaza tus herramientas. Aprende como usas tu PC, navegador y tools, y convierte trabajo repetido en capacidades reutilizables.
```


## Diferencia con comprar la licencia oficial

Comprar una licencia oficial de OpenWork puede servir para probar o validar, pero no queda claro que permita revender o sublicenciar su build comercial a clientes.

Trabajar desde el codigo open source permite crear una version propia, siempre respetando las licencias aplicables.

El repo indica que el contenido fuera de `/ee` esta bajo MIT, mientras que `/ee` tiene otra licencia. Por eso, para una version comercial propia conviene evitar depender de partes Enterprise o revisar bien sus condiciones.

## Riesgos principales

Los principales riesgos no son que Windows sea imposible, sino mantener el producto:

- futuras actualizaciones pueden romper el build
- Electron, Node, Bun o dependencias nativas pueden cambiar
- Windows puede mostrar avisos si no se firma el instalador
- antivirus pueden generar falsos positivos
- clientes con entornos corporativos pueden tener permisos bloqueados
- hay que probar cada release en un Windows limpio

Estos riesgos son normales en software desktop. Se gestionan con una maquina de build estable, versiones bloqueadas, firma de codigo y un proceso de QA.

## Flujo recomendado

1. Crear fork propio del repo.
2. Renombrar el producto a Matrix.
3. Cambiar iconos, nombre, `appId` y artefacto de instalacion.
4. Definir una carpeta o sistema de skills base.
5. Crear una build generica de Matrix.
6. Crear ramas o configuraciones por cliente.
7. Firmar instaladores cuando el producto vaya a venderse.
8. Probar cada instalador en Windows limpio.
9. Cobrar por setup, licencia/uso, soporte y personalizacion.

## Conclusion

El proyecto es viable tecnicamente.

Ya se ha probado que una build Windows propia puede generarse desde el codigo fuente. El siguiente paso es convertir esta build en una version de producto llamada Matrix, con marca propia, skills personalizadas y un proceso repetible para generar instaladores por cliente.
