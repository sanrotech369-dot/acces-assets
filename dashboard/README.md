# Agente Seguimiento Gener. ICP Leads AccesGroup

Dashboard de una sola página (`index.html`) para dar seguimiento a la generación, calificación ICP y seguimiento de leads B2B de ACCES GROUP. No necesita servidor: ábrelo en el navegador.

## Qué muestra

- **KPIs**: leads en seguimiento, Score ICP promedio, SQL con decisor mapeado, seguimientos vencidos, tasa de respuesta y pipeline ponderado.
- **Embudo de conversión**: Lead → MQL → SAL → SQL → Trato → Ganado, con la conversión entre fases.
- **Distribución del Score ICP**: leads activos por umbral (0–29, 30–49, 50–64, 65–74, 75–100).
- **Agenda del agente**: acciones vencidas o de los próximos 7 días, en el orden de prioridad diaria.
- **Alertas del agente**: compromisos vencidos, sin siguiente paso, candado de decisor, silencio de más de 14 días, fase por encima del score, aliado sin presentación directa y lead nuevo sin primer contacto. Al hacer clic se filtra la tabla.
- **Pipeline Zoho por etapa**, **leads por sector** (códigos `MEM_AIS_MX_*`) y **leads por fuente**.
- **Cartera de leads**: tabla ordenable; cada fila abre una ficha con el desglose del score, la siguiente mejor acción, la cadencia D+1/D+3/D+7/D+12/D+20, BANT, la oportunidad y las alertas.

## Datos

Abre con datos de ejemplo ficticios. Para ver tu cartera, usa **Importar CSV de Zoho** o arrastra el archivo a la página. `plantilla_leads_zoho.csv` trae las columnas esperadas; también se reconocen los encabezados estándar de un export de Leads de Zoho (Company, Industry, Lead Source, Lead Status, Lead Owner, Rating, Created Time, Last Activity Time, Stage, Amount, Probability).

Si falta `Score_Total`, se suma ICP Fit + Intención + Viabilidad + Engagement. Si falta `Micro_ICP` o `Temperatura`, se calculan a partir del sector y del score. El último CSV importado se guarda solo en tu navegador.

## Reglas que aplica

Tomadas de los skills *Agente Maestro de Seguimiento Comercial B2B* y *Calificador de Leads ICP* de ACCES GROUP: Score Total de 0 a 100 con sus umbrales, candado de decisor (sin Economic Buyer no hay SQL), cadencia sin fecha acordada, orden de prioridad diaria y pre-score máximo de 40 para aliados sin presentación directa.
