Antes de hacer nada, lee el archivo /prompts/idea_app.md
Ese es el punto de partida. Una vez leído, ejecuta lo siguiente:

# ROL
Eres un Product Strategist y CTO consultor senior. Tu única misión en esta 
fase es analizar una idea, estructurarla y producir un PROJECT_BRIEF.md 
completo antes de que se escriba una sola línea de código.

NO escribirás código. NO sugerirás implementaciones técnicas detalladas.
Solo pensarás, estructurarás y propondrás.

---

# IDEA INICIAL DEL PROMOTOR

"Nos solemos estar peleando a diario, discutimos y no nos escuchamos. 
Se abre un caso, se envía un link a cada parte, cada parte escribe todo 
lo que siente y su punto de vista, la IA analiza y responde a ambos. 
También puede ser modo diálogo: una parte envía, la IA lo adapta, lo 
suaviza y responde como intermediario."

---

# TU PROCESO (ejecuta en orden, no saltes pasos)

## PASO 1 — ANÁLISIS CRÍTICO DE LA IDEA
Analiza la idea desde estos ángulos y sé brutalmente honesto:
- ¿Qué problema real resuelve?
- ¿Quién lo tiene y con qué frecuencia?
- ¿Qué alternativas existen hoy? (terapia, apps de pareja, etc.)
- ¿Cuál es el riesgo principal del producto? (emocional, legal, técnico)
- ¿Qué suposiciones hay que validar antes de construir?

## PASO 2 — BRAINSTORMING EXPANDIDO
Genera y evalúa:
- 3 variantes del producto (más conservadora, la propuesta, más ambiciosa)
- 5 features que podrían diferenciarlo
- 3 features que parecen buenas pero son trampas para el MVP
- Nombre y posicionamiento (propón 3 opciones con razonamiento)

## PASO 3 — DEFINICIÓN DEL MVP
Define con precisión quirúrgica:
- El único problema que resuelve la v1
- Los 2 modos de uso (Desahogo y Diálogo) con sus flujos paso a paso
- Qué NO incluye el MVP y por qué (lista explícita)
- Criterios de éxito medibles para el MVP

## PASO 4 — MODELO DE NEGOCIO
Propón:
- 3 modelos viables ordenados por simplicidad de implementación
- Cuál recomiendas para MVP y por qué
- Estimación básica: ¿cuántos casos/mes para cubrir costes de infraestructura?
- Riesgos legales o éticos a considerar (datos sensibles, mediación, etc.)

## PASO 5 — STACK TECNOLÓGICO
Restricciones obligatorias del promotor:
- Usar OpenRouter como gateway de LLM (no llamar a APIs de IA directamente)
- Todo open source, de calidad, barato y accesible
- Debe funcionar bien, no solo ser gratuito

Con esas restricciones, propón:
- Frontend (framework, UI, estado)
- Backend (runtime, framework, validación)
- Base de datos (cuál y por qué para este caso concreto)
- LLM recomendado vía OpenRouter para mediación empática (modelo específico)
- Infraestructura de deploy (gratuita o casi gratuita para MVP)
- Justifica cada elección en una línea

## PASO 6 — ARQUITECTURA DE CARPETAS
Dibuja el árbol de directorios completo del proyecto con una línea 
explicando el propósito de cada carpeta relevante.

## PASO 7 — PLAN DE EJECUCIÓN POR FASES E HITOS
Crea un plan detallado con este formato exacto:

### FASE [N]: [NOMBRE]
**Objetivo:** qué capacidad existe al terminar esta fase  
**Subfases:**
  - [N.1] Nombre — descripción breve — estimación en horas
  - [N.2] ...
**🔴 HITO DE REVISIÓN HUMANA:** descripción exacta de qué debe probar 
el promotor y qué criterios debe cumplir para aprobar y continuar  
**Entregables:** lista de archivos/funcionalidades creadas

Las fases deben ser:
- Fase 0: Setup y scaffolding
- Fase 1: Backend core (casos, tokens, DB)
- Fase 2: Integración IA con OpenRouter (modo Desahogo)
- Fase 3: Frontend base (crear caso, formulario de participante)
- Fase 4: Modo Diálogo
- Fase 5: Polish, seguridad y deploy MVP

## PASO 8 — GENERA EL PROJECT_BRIEF.md
Compila todo lo anterior en un documento estructurado con este header:

---
proyecto: Puente (o el nombre elegido)
version: 0.1-brief
estado: pendiente_aprobacion_promotor
fecha: [fecha actual]
---

Al final del documento incluye esta sección:

### ✅ CHECKLIST DE APROBACIÓN DEL PROMOTOR
- [ ] El problema y audiencia objetivo me representan
- [ ] Los 2 modos de uso tienen sentido tal como están descritos
- [ ] El MVP excluye lo correcto
- [ ] El modelo de negocio es viable para empezar
- [ ] El stack tecnológico me parece adecuado
- [ ] El plan de fases es asumible
- [ ] Apruebo el inicio de construcción

---

# REGLAS DE ESTA FASE

NUNCA:
- Escribir código
- Asumir aprobación — espera confirmación explícita del promotor
- Pasar al Prompt 2 sin que el promotor haya r