# Foxter LAB #2 · Reglas comunes

Este repositorio es el material del taller Foxter LAB #2. La persona que trabaja contigo forma parte del equipo de **Brisa Clima**, una empresa ficticia de climatización de Barcelona. Todos los datos de `datos/` son inventados.

Este archivo y `AGENTS.md` tienen las mismas reglas: `CLAUDE.md` lo lee Claude Code y `AGENTS.md` lo lee Codex.

## Los cinco agentes

| Agente | Área | Ficha | Skill |
|---|---|---|---|
| **Mara** | Marketing | `agentes/marketing/FICHA.md` | `marketing` |
| **Max** | Ventas | `agentes/ventas/FICHA.md` | `ventas` |
| **Clara** | Experiencia de cliente | `agentes/experiencia-cliente/FICHA.md` | `experiencia-cliente` |
| **Otto** | Datos y operaciones | `agentes/operaciones/FICHA.md` | `operaciones` |
| **Diana** | Dirección | `agentes/direccion/FICHA.md` | `direccion` |

## Dónde se guardan las skills

- **Claude Code:** `.claude/skills/<skill>/SKILL.md`
- **Codex:** `.agents/skills/<skill>/SKILL.md`

Guarda la skill solo en la carpeta de la herramienta con la que estás trabajando. En `soluciones/<skill>/SKILL.md` hay una skill terminada de cada agente, por si alguien se atasca.

## Reglas

1. Escribe siempre en español de España, con frases cortas y claras.
2. Trabaja solo con la información de `datos/`. No busques en internet.
3. Los datos llegan hasta el **24 de noviembre de 2026**. Usa esa fecha como «hoy» para calcular periodos como «los últimos 12 meses».
4. **No leas los archivos CSV enteros en la conversación.** Tienen miles de filas. Consulta `datos/DICCIONARIO.md` para conocer las columnas y calcula con las herramientas que ya tiene el ordenador: `sqlite3` o `awk` en Mac, PowerShell (`Import-Csv`, `Group-Object`, `Measure-Object`) en Windows. No instales nada y no uses `git` (en algunos Mac abre un aviso para instalar herramientas de desarrollo).
   - Truco para `sqlite3`: importa con `.import --csv datos/archivo.csv tabla` y convierte los números con `CAST(columna AS REAL)`, porque se importan como texto.
5. **Trabaja con pocos pasos.** Agrupa los cálculos en pocas consultas, no repitas cálculos que ya tienes y no muestres listados largos de filas. Si una petición necesita mucho más trabajo que un dashboard normal, para y propón una versión más pequeña.
6. No inventes datos. Si algo no está en los archivos, dilo: «No lo encuentro en los datos».
7. Los resultados se guardan en `salidas/<skill>/`, con la fecha de hoy en el nombre (`2026-11-24-nombre.html`).
8. Los dashboards son **un único archivo HTML** que se abre con doble clic: datos ya calculados dentro, gráficos hechos con HTML, CSS o SVG, sin librerías ni recursos de internet.
9. **Al terminar, resume en el chat** en no más de 8 líneas:
   - qué archivos y cuántas filas has analizado, y de qué periodo;
   - qué has encontrado (las cifras clave);
   - por qué llegas a esa conclusión: qué dato o comparación la sostiene;
   - dónde has guardado el resultado.
10. Cuando te pidan una mejora, parte del dashboard que ya existe y recalcula solo lo que haga falta.
11. No modifiques nada de `datos/` ni de `soluciones/`.
12. Antes de guardar una skill nueva, enséñala y espera confirmación.
