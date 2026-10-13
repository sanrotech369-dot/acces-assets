# Agente Seguimiento Gener. ICP Leads AccesGroup

Dashboard de una sola página (`index.html`) para los leads que genera el agente de ACCES GROUP: su calificación ICP, su seguimiento y los datos de cada empresa y contacto. No necesita servidor: ábrelo en el navegador.

## Dos vistas

- **Presentación** (la que abre por defecto): una sola pantalla para mostrar resultados. Tiene lo que ha hecho el agente en 5 pasos (generados → calificados → contactados → respondieron → reuniones), dónde está cada lead hoy (estados del agente agrupados en etapas) y qué sigue (las alertas más importantes). **Copiar resumen** deja el mismo contenido en texto para pegarlo en un correo, WhatsApp o una lámina. Si el agente usa un estado que el dashboard no conoce, aparece como "Otros estados" con su nombre, para que no se pierda.
- **Operación**: la herramienta de trabajo diario con filtros, agenda, alertas, paneles y la cartera completa. Se abre directo con `#operacion` al final del enlace.

## Cargar los leads de hoy del agente

1. Abre la hoja **ICP_CRM_ACCES** en la pestaña `Leads_SRC-001`.
2. Archivo → Descargar → **Valores separados por comas (.csv)**. También sirve **Microsoft Excel (.xlsx)** con todo el libro: el dashboard toma la pestaña `Leads_SRC-001` (o la pestaña con columna `Empresa` y más filas).
3. Pulsa **Importar CSV o Excel** o arrastra el archivo a la página.

El archivo se procesa en el navegador; no se sube a ningún servidor ni a este repositorio. El último archivo importado se recuerda solo en ese navegador cuando cabe en su almacenamiento local.

## Columnas que reconoce

Las de `Leads_SRC-001` del agente (`ID_Lead`, `Source_ID`, `Empresa`, `Dominio`, `Sector`, `Contacto`, `Cargo`, `Correo`, `Correo_Estado`, `Telefono`, `Ciudad`, `Estado_Region`, `Estado`, `Anti_ICP`, `Suprimido`, `Correo_Dup`, `Dup_Maestro`, `Enriquecer`, `Micro_ICP`, `Pre_Score`, `Decisor_Mapeado`, `Cadencia_Paso`, `Num_Toques`, `Ultimo_Contacto`, `Fecha_Siguiente_Paso`, `Trigger_Regulatorio`, `Gancho`, `Asunto`, `Notas`…) y las de `plantilla_leads.csv`. Las columnas que falten se calculan o quedan vacías.

- **Estado del agente → fase**: `respondio` es MQL, `agendado` es SQL, `descartado`, `descalificado_sin_contacto` y `suprimido` son Descartado; el resto (`sin_prescore`, `en_investigacion`, `en_revision`, `revisar_duplicado`, `borrador_creado`, `contactado`, `rebotado`, `nurture`…) sigue como Lead.
- **Anti-ICP abierto**: `Anti_ICP = SI` (o un motivo de descarte que diga anti-ICP) ya no descarta el lead; aparece como "Anti-ICP reabierto" para abordarlo. Solo los suprimidos (opt-out) y los descartados por otra causa quedan cerrados.
- **Pre-score**: si solo viene `Pre_Score`, el dashboard lo muestra como prioridad de abordaje (no como fase). El score completo (ICP Fit + Intención + Viabilidad + Engagement) se usa cuando viene en el archivo.
- **Seguimiento**: un lead está en seguimiento si tiene toques, último contacto, respuesta o un estado de seguimiento. Si la exportación no trae `Fecha_Siguiente_Paso`, esos leads aparecen "En cadencia del agente" en lugar de marcarse como sin siguiente paso.

## Qué muestra

KPIs, embudo de calificación, distribución del score o pre-score, agenda del agente, alertas (compromisos vencidos, sin siguiente paso, candado de decisor, correo rebotado, silencio prolongado, fase por encima del score, contacto sin correo válido ni teléfono, duplicado por revisar, aliado sin presentación, lead nuevo sin contacto), estado en el agente, avance de la cadencia, leads por sector (`MEM_AIS_MX_*`), por fuente y por puesto del contacto, calidad de datos, estado del correo y la cartera completa (paginada) con ficha por lead.

## Reglas que aplica

Tomadas de los skills *Agente Maestro de Seguimiento Comercial B2B* y *Calificador de Leads ICP* de ACCES GROUP: umbrales del Score Total, candado de decisor, cadencia sin fecha acordada, orden de prioridad diaria y pre-score máximo de 40 para aliados sin presentación directa.
