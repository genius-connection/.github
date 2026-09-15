# Genius Connection Holding Capital

Mapa central de las marcas y verticales del grupo: qué existe, en qué repo vive y qué stack usa. Es lo primero que debería consultar el agente orquestador (o cualquier persona nueva) antes de tocar un repo específico.

---

## Verticales

### Vitalegal
Servicios legales de inmigración, nacionalidad, laboral, fiscal en España.

| Producto | Repo | Stack |
|---|---|---|
| Web principal / landings | `vl-landing-page-core` | Astro, Tailwind, React, Cloudflare Workers |
| Regularizates (SaaS trámites de residencia) - *proyecto en pausa*| `regularizates-saas` | Next.js 15, Firebase, Google Gemini, Stripe |

CRM: Clientify · Telefonía: Zadarma

### Genius Connection
Consultoría de software / transformación digital para pymes.

| Producto | Repo | Stack |
|---|---|---|
| Web / captación de leads | `gc-landing-page-core` | Astro, Tailwind, React |

---

## Infraestructura compartida

### `gc-agents-toolkit`
Sistema de agentes y skills de Claude Code (orquestador + agentes especializados), instalado como plugin a nivel usuario. Usado por todas las verticales — no contiene contexto de ninguna marca en particular. Ese contexto vive en el `.claude/` de cada repo de producto.

---

## Cómo se organiza el grupo

- Un repo por vertical/producto dentro de esta organización — sin organizaciones separadas por marca.
- El contexto específico de cada marca (APIs, IDs de tracking, guía de estilo, etc.) vive en `.claude/` dentro de su propio repo, nunca en el toolkit.
- Los permisos se gestionan con **Teams** de GitHub por vertical (ej. `legal`, `consultoria`).

### Al añadir una marca nueva
1. Crear el repo dentro de esta organización: `{marca}-{tipo-producto}`.
2. Añadir su `.claude/` con el contexto de esa marca.
3. Añadir su fila en la tabla correspondiente de este README.
4. Asignar el Team de GitHub que debe tener acceso.