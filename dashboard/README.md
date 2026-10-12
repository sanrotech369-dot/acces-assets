# Agente Seguimiento Gener. ICP Leads AccesGroup

Dashboard de una sola página (`index.html`) para los leads que genera ACCES GROUP: su calificación ICP, su seguimiento y los datos de cada empresa y contacto. No necesita servidor: ábrelo en el navegador.

## Qué muestra

- **KPIs**: leads en seguimiento, Score ICP promedio, SQL con decisor mapeado, seguimientos vencidos, tasa de respuesta y contactos con datos completos.
- **Embudo de calificación**: Lead → MQL → SAL → SQL → SQL con decisor, con la conversión entre fases.
- **Distribución del Score ICP**: leads activos por umbral (0–29, 30–49, 50–64, 65–74, 75–100).
- **Agenda del agente**: acciones vencidas o de los próximos 7 días, en el orden de prioridad diaria.
- **Alertas del agente**: compromisos vencidos, sin siguiente paso, candado de decisor, silencio de más de 14 días, fase por encima del score, contacto sin correo ni teléfono, aliado sin presentación directa y lead nuevo sin primer contacto. Al hacer clic se filtra la tabla.
- **Avance de la cadencia** (toques D+1 a D+20 y su tasa de respuesta), **leads por sector** (códigos `MEM_AIS_MX_*`) y **leads por fuente**.
- **Calidad de datos de empresas y contactos**: qué porcentaje de leads tiene nombre, cargo, correo, teléfono, LinkedIn, rol en la compra, consentimiento, sitio web y tamaño de empresa.
- **Rol del contacto en la compra**: Economic Buyer, Champion, Validador técnico, Usuario final, Influenciador o sin identificar.
- **Cartera de leads**: tabla ordenable con empresa y contacto; cada fila abre una ficha con el desglose del score, la siguiente mejor acción, los datos del contacto (con botón para copiar correo y teléfono), los datos de la empresa, la cadencia, BANT y las alertas.

## Datos

Abre con datos de ejemplo ficticios. Para ver tus leads, usa **Importar CSV de leads** o arrastra el archivo a la página. `plantilla_leads.csv` trae las columnas esperadas; las que falten se calculan o quedan vacías. Si falta `Score_Total`, se suma ICP Fit + Intención + Viabilidad + Engagement. Si falta `Micro_ICP` o `Temperatura`, se calculan a partir del sector y del score. El último CSV importado se guarda solo en tu navegador.

## Reglas que aplica

Tomadas de los skills *Agente Maestro de Seguimiento Comercial B2B* y *Calificador de Leads ICP* de ACCES GROUP: Score Total de 0 a 100 con sus umbrales, candado de decisor (sin Economic Buyer no hay SQL), cadencia sin fecha acordada, orden de prioridad diaria y pre-score máximo de 40 para aliados sin presentación directa.
