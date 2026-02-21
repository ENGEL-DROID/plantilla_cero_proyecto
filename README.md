# 🚀 Guía del Promotor — Cómo usar este sistema

Este proyecto usa un sistema de dos prompts que separan el pensamiento 
de la ejecución. Tú eres el director: apruebas, rechazas y desbloqueas 
el avance en cada hito importante.

---

## 📁 Estructura de archivos clave
```
prompts/
├── idea_app.md              ← tu idea inicial (edita esto antes de empezar)
├── prompt_01_estrategia.md  ← el agente analiza y genera el brief
├── prompt_02_accion.md      ← el agente construye la app fase a fase
docs/
├── PROJECT_BRIEF.md         ← generado por el agente en Fase Estrategia
├── STACK.md                 ← decisiones técnicas
├── FOLDER_STRUCTURE.md      ← arquitectura de carpetas
├── EXECUTION_PLAN.md        ← fases, subfases e hitos
└── ESTADO_DEL_PROYECTO.md   ← tracker vivo del progreso (tu brújula)
```

---

## 🔁 Flujo completo

### FASE ESTRATEGIA — Analizar y planificar

**1. Escribe tu idea en** `prompts/idea_app.md` antes de hacer cualquier 
otra cosa. Sé libre, no hace falta que esté perfecta.

**2. Abre una conversación nueva con el agente y escribe:**
```
Lea y siga las instrucciones del archivo prompts/prompt_01_estrategia.md
```

**3.** El agente leerá `idea_app.md`, analizará la idea y generará 
todos los documentos en `/docs/` incluyendo el `PROJECT_BRIEF.md`.

**4.** Revisa los documentos generados. En la misma conversación puedes 
pedir ajustes hasta que el brief refleje exactamente tu visión.

**5.** Cuando estés conforme, da el visto bueno explícito:
```
Aprobado, el brief está correcto. Puedes cerrar esta fase.
```

---

### FASE CONSTRUCCIÓN — Ejecutar fase a fase

**6. Abre una conversación NUEVA (contexto limpio) y escribe:**
```
Lea y siga las instrucciones del archivo prompts/prompt_02_accion.md
```

**7.** El agente leerá todos los documentos de `/docs/` y te confirmará 
que entendió el proyecto. Revisará el estado actual en 
`ESTADO_DEL_PROYECTO.md` y te propondrá por dónde empezar.

**8.** Para arrancar escribe:
```
INICIA FASE 0
```

**9.** El agente ejecuta subfase a subfase y se detiene solo en cada 
hito 🔴 esperando tu respuesta.

---

## 🔴 Cómo responder a los hitos

Cuando el agente se detenga en un hito, prueba lo que te indica y 
responde con una de estas tres opciones:

### ✅ Si todo funciona correctamente:
```
✅ APROBADO
```
O con comentarios opcionales:
```
✅ APROBADO — el formulario carga bien pero el botón podría ser más visible
```
El agente marcará la fase como completada, actualizará el tracker 
y anunciará el inicio de la siguiente fase.

---

### ❌ Si algo no funciona o no te convence:
```
❌ RECHAZADO — [describe exactamente qué falla o qué no cumple]
```
Ejemplo:
```
❌ RECHAZADO — al enviar el formulario aparece error 500 en consola 
y no se crea el caso en la base de datos
```
El agente analizará el problema, lo corregirá y repetirá el mismo 
hito para que vuelvas a probarlo.

---

### ⚠️ Si funciona pero quieres ajustes antes de continuar:
```
⚠️ APROBADO CON CAMBIOS — [lista los cambios que quieres]
```
Ejemplo:
```
⚠️ APROBADO CON CAMBIOS — 
- cambiar el color del botón principal a azul
- el mensaje de confirmación debe aparecer arriba, no abajo
```
El agente implementará los cambios y repetirá el hito para 
confirmación final antes de avanzar.

---

## 🔄 Si la conversación se corta o pierde contexto

Si el agente empieza a perder el hilo o tienes que abrir una nueva 
sesión, simplemente escribe la misma orden de inicio:
```
Lea y siga las instrucciones del archivo prompts/prompt_02_accion.md
```
El agente leerá `ESTADO_DEL_PROYECTO.md`, sabrá exactamente en qué 
punto quedó el proyecto y continuará desde ahí sin perder progreso.

---

## 📋 Reglas de oro para el promotor

- **Una conversación para estrategia, otra para construcción** — no mezcles
- **Nunca escribas "continúa" o "sigue"** sin haber probado el hito — el 
  agente podría saltarse tu revisión
- **El archivo `ESTADO_DEL_PROYECTO.md` es la fuente de verdad** — si algo 
  no cuadra, ábrelo y revísalo
- **Puedes pedir cambios en cualquier momento** — pero si estás en medio 
  de una subfase, espera a que termine antes de pedirlos
- **Si rechazas un hito dos veces seguidas**, describe el problema con 
  capturas o logs — ayuda al agente a entender exactamente qué falla