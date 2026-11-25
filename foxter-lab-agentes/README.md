# Foxter LAB #2 · Crea tu primer agente de IA

Repositorio del taller práctico de [FOXTER](https://hikefoxter.com) para crear tu primer agente de IA. Funciona con **Claude Code** y con **Codex** (ChatGPT). No hace falta saber programar.

**Guía paso a paso del taller:** https://foxter-io.github.io/foxter-lab-agentes/

## Hoy trabajas en Brisa Clima

Brisa Clima es una **empresa ficticia** de climatización de Barcelona. Tiene clientes, oportunidades de venta, campañas, equipos instalados, incidencias, encuestas y facturas de los últimos 24 meses: miles de filas de datos para que tu agente trabaje con algo parecido a la realidad.

Todos los datos son **inventados**. Cualquier parecido con empresas o personas reales es casualidad.

## Los cinco agentes

| Agente | Área | Qué hace en el taller | Datos principales |
|---|---|---|---|
| **Mara** | Marketing | Dashboard de leads, coste y conversión por canal | 4.000 leads y 60 campañas |
| **Max** | Ventas | Dashboard de oportunidades perdidas por motivo, competidor y zona | 609 oportunidades |
| **Clara** | Experiencia de cliente | Dashboard de incidencias y satisfacción por modelo y sector | 2.709 incidencias y 1.447 encuestas |
| **Otto** | Datos y operaciones | Dashboard de equipos con consumo anómalo y riesgo de avería | 52.938 lecturas de 149 equipos |
| **Diana** | Dirección | Informe para el comité con tres decisiones | 4.526 facturas, ventas y satisfacción |

Cada agente tiene su ficha en `agentes/<área>/FICHA.md`. Los cinco trabajan sobre la misma empresa: lo que descubre uno ayuda a entender lo que ve otro.

## Qué hay en cada carpeta

```
foxter-lab-agentes/
├── CLAUDE.md          Reglas comunes (las lee Claude Code)
├── AGENTS.md          Las mismas reglas (las lee Codex)
├── agentes/           La ficha de cada agente
├── datos/             Los datos de Brisa Clima (CSV) y su diccionario
├── .claude/skills/    Aquí se guarda la skill si usas Claude Code
├── .agents/skills/    Aquí se guarda la skill si usas Codex
├── soluciones/        Una skill terminada por agente, por si te atascas
├── tareas/            La tarea programada de cada agente
├── salidas/           Lo que generan los agentes
└── docs/              La guía del taller (web)
```

## Cómo empezar

1. Clona este repositorio con **GitHub Desktop** (`File › Clone repository › URL`).
2. Abre la carpeta `foxter-lab-agentes`:
   - **Claude Code:** app de Claude › pestaña **Code** › selecciona la carpeta.
   - **Codex:** app de Codex › añade la carpeta como proyecto.
3. Sigue la guía del taller.

## Requisitos

- **Claude:** plan Pro o superior y la app de escritorio actualizada.
- **Codex:** plan ChatGPT Plus o superior y la app de Codex actualizada.
- Cuenta de GitHub y GitHub Desktop.
- No hace falta instalar nada más: los agentes calculan con las herramientas que ya trae el ordenador.

## Sobre las tareas programadas

Las tareas programadas (Claude Code) y las automatizaciones (Codex) se ejecutan en tu ordenador: solo funcionan con la app abierta y el ordenador encendido.

---

FOXTER · [hikefoxter.com](https://hikefoxter.com)
