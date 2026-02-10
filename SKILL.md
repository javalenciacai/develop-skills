---
name: orchestrator
description: Sistema de orquestación de roles. TODA tarea debe pasar por un orquestador de rol (CTO → PM/TL → PO/QA/Dev/DevOps). Los orquestadores delegan a suborquestadores o usan skills directos. Si no existe el skill, se busca con find-skills o se crea.
---

# Sistema de Orquestación

## ⚠️ REGLA OBLIGATORIA

**TODA tarea debe seguir el flujo de orquestación por roles.**

## Jerarquía de Orquestadores

```
                    ┌─────────┐
                    │   CTO   │  ← Orquestador Principal
                    └────┬────┘
                         │
           ┌─────────────┴─────────────┐
           │                           │
      ┌────┴────┐                 ┌────┴────┐
      │   PM    │                 │   TL    │  ← Suborquestadores
      └────┬────┘                 └────┬────┘
           │                           │
      ┌────┴────┐                 ┌────┴────┐
      │         │                 │         │
   ┌──┴──┐  ┌───┴──┐          ┌──┴──┐  ┌───┴───┐
   │ PO  │  │  QA  │          │ Dev │  │DevOps │  ← Ejecutores
   └─────┘  └──────┘          └─────┘  └───────┘
```

## Flujo de Orquestación

### 1. Tarea llega al CTO

El CTO analiza y decide:
- **Producto/Prioridades** → Delegar a PM
- **Técnico/Código** → Delegar a TL
- **Mixto** → Coordinar PM + TL

### 2. Suborquestador recibe la tarea

PM o TL delegan a ejecutores:
- **PM** → PO (requisitos) o QA (testing)
- **TL** → Dev (código) o DevOps (infra)

### 3. Ejecutor busca skill

El rol ejecutor (PO, QA, Dev, DevOps):

1. **Busca skill local** en `.agents/skills/`
2. **Si no existe**: `npx skills find [tarea]`
3. **Si no existe en skills.sh**: Pregunta al usuario para crear skill
4. **Ejecuta** usando el skill encontrado/creado

### 4. Reporta hacia arriba

```
Ejecutor → Suborquestador → CTO
```

## Ubicación de Skills

```
.agents/skills/
├── cto/SKILL.md      # Orquestador principal
├── pm/SKILL.md       # Suborquestador de producto
├── tl/SKILL.md       # Suborquestador técnico
├── po/SKILL.md       # Ejecutor: Product Owner
├── qa/SKILL.md       # Ejecutor: QA
├── dev/SKILL.md      # Ejecutor: Desarrollador
└── devops/SKILL.md   # Ejecutor: DevOps
```

## Cuándo Crear Skills Nuevos

Un ejecutor puede proponer crear un skill nuevo cuando:

1. La tarea es repetitiva
2. Requiere conocimiento especializado
3. No existe en skills.sh

Usar `skill-creator` para crear:

```bash
npx skills add vercel-labs/skills --skill skill-creator
```

## Ejemplo de Flujo Completo

```
Usuario: "Implementar autenticación con Google OAuth"

1. CTO recibe → Es técnico → Delega a TL
2. TL recibe → Es código + infra → Delega a Dev (código) + DevOps (config)
3. Dev busca skill "oauth passport" → Encuentra → Implementa
4. DevOps configura variables de entorno
5. Dev reporta a TL → TL reporta a CTO
6. CTO solicita validación → PM delega a QA
7. QA valida → Reporta a PM → PM reporta a CTO
8. CTO marca como completado
```

## Referencias

- `.agents/skills/` — Skills de roles del proyecto
- `AGENTS.md` — Guía completa para agentes
- `GEMINI.md` — Lineamientos de desarrollo
