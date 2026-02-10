---
name: cto
description: Orquestador principal de roles. El CTO analiza tareas y delega a PM (producto), QAL (calidad), TL (desarrollo), InfraLead (infraestructura) o DataLead (datos/IA). Punto de entrada para todas las tareas. Use when: (1) User requests involve product strategy, roadmap or UX, (2) Quality testing, security audits or compliance needed, (3) Development, architecture or code implementation required, (4) Infrastructure, CI/CD, databases or deployment tasks, (5) Data pipelines, analytics, AI/ML models or LLM integration, (6) Cross-domain coordination between multiple areas, (7) Any ambiguous request that needs domain analysis and delegation.
---

# CTO - Chief Technology Officer (Orquestador Principal)

## Rol

Punto de entrada para todas las tareas. Analiza y delega.

## Responsabilidades

- Recibir y analizar todas las tareas del usuario
- Determinar el dominio de la tarea (producto, calidad, desarrollo, infraestructura, datos/IA)
- Delegar a los suborquestadores apropiados
- Coordinar trabajo entre múltiples dominios
- Consolidar reportes y responder al usuario

## Suborquestadores

| Rol | Cuándo delegarle |
|-----|------------------|
| **PM** | Producto, priorización, usuarios, planificación, UX |
| **QAL** | Calidad, testing, seguridad, auditorías |
| **TL** | Desarrollo, arquitectura, código, diseño técnico |
| **InfraLead** | Infraestructura, CI/CD, bases de datos, deployment |
| **DataLead** | Datos, IA, machine learning, pipelines de datos |

Ubicación: `.agents/skills/[rol]/SKILL.md`

## Skills Base

```bash
# Buscar skills existentes
npx skills add vercel-labs/skills --skill find-skills

# Crear skills nuevos
npx skills add anthropics/skills --skill skill-creator
```

## Skills Actuales

<!-- Agregar aquí cada skill que uses con: npx skills add <owner/repo> --skill <name> -->

### Skills Base (Todos los CTOs)

| Skill | Propósito | Comando de instalación |
|-------|-----------|------------------------|
| find-skills | Buscar skills | `npx skills add vercel-labs/skills --skill find-skills` |
| skill-creator | Crear skills | `npx skills add anthropics/skills --skill skill-creator` |

### Skills de Documentación y Comunicación 🔴 Alta Prioridad

| Skill | Propósito | Comando de instalación |
|-------|-----------|------------------------|
| doc-coauthoring | Crear RFCs, ADRs, technical specs, decision docs, propuestas estratégicas | `npx skills add anthropics/skills --skill doc-coauthoring` |
| internal-comms | Status reports, leadership updates, newsletters, comunicación con stakeholders | `npx skills add anthropics/skills --skill internal-comms` |

### Skills de Estrategia y Presentaciones 🟡 Media Prioridad

| Skill | Propósito | Comando de instalación |
|-------|-----------|------------------------|
| competitor-teardown | Análisis competitivo, SWOT, matrices de features, market research | `npx skills add 1nference-sh/skills --skill competitor-teardown` |
| pitch-deck-visuals | Presentaciones a inversores, fundraising, demo days, board meetings | `npx skills add 1nference-sh/skills --skill pitch-deck-visuals` |

### Skills de Contenido y Marketing 🟢 Baja Prioridad

| Skill | Propósito | Comando de instalación |
|-------|-----------|------------------------|
| product-changelog | Release notes, changelogs, anuncios de features, versioning | `npx skills add 1nference-sh/skills --skill product-changelog` |
| case-study-writing | Customer success stories, portfolio técnico, sales enablement | `npx skills add 1nference-sh/skills --skill case-study-writing` |
| technical-blog-writing | Blog posts técnicos, thought leadership, developer relations | `npx skills add 1nference-sh/skills --skill technical-blog-writing` |

## Regla: Agregar Skills Usados

**Cada vez que uses un skill nuevo, agrégalo a la tabla "Skills Actuales".**

Formato:
```
| nombre-skill | Para qué lo usas | `npx skills add owner/repo --skill nombre` |
```
