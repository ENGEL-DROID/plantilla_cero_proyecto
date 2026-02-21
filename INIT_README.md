## Flujo de inicio:

1. Pedir al agente: 
```bash
Lea y siga las instrucciones que se encuentran en el archivo prompts\prompt_01_estrategia.md
```

2. El agente lee idea_app.md → genera PROJECT_BRIEF.md

3. Revisar y corregir el brief en esa misma conversación.

4. Nueva conversación y pedir al agente:
```bash
Lea y siga las instrucciones que se encuentran en el archivo prompts\prompt_02_accion.md
```

5. El agente lee PROJECT_BRIEF.md

6. Escribir "INICIA FASE 0" y ya.

7. Diferentes sesiones:
```bash
Lea y siga las instrucciones que se encuentran en el archivo prompts\prompt_02_accion.md
```

---

## 🔴 Cómo responder a los hitos

### ✅ Si todo funciona correctamente:
```bash
✅ APROBADO
```
O con comentarios opcionales:
```bash
✅ APROBADO — el formulario carga bien pero el botón podría ser más visible
```

### ❌ Si algo no funciona o no te convence:
```bash
❌ RECHAZADO — describe exactamente qué falla o qué no cumple
```
Ejemplo:
```bash
❌ RECHAZADO — al enviar el formulario aparece error 500 en consola 
y no se crea el caso en la base de datos
```

### ⚠️ Si funciona pero quieres ajustes antes de continuar:
```bash
⚠️ APROBADO CON CAMBIOS — lista los cambios que quieres
```
Ejemplo:
```bash
⚠️ APROBADO CON CAMBIOS — 
- cambiar el color del botón principal a azul
- el mensaje de confirmación debe aparecer arriba, no abajo
```

## 🔄🚨 Si la conversación se corta o pierde contexto

Si el agente empieza a perder el hilo o tienes que abrir una nueva 
sesión, simplemente escribe la misma orden de inicio:
```bash
Lea y siga las instrucciones del archivo prompts/prompt_02_accion.md
```
El agente leerá `ESTADO_DEL_PROYECTO.md`, sabrá exactamente en qué 
punto quedó el proyecto y continuará desde ahí sin perder progreso.

---

## 📋🙋🏼 Reglas de oro para el promotor

- **Una conversación para estrategia, otra para construcción** — no mezcles
- **Nunca escribas "continúa" o "sigue"** sin haber probado el hito — el 
  agente podría saltarse tu revisión
- **El archivo `ESTADO_DEL_PROYECTO.md` es la fuente de verdad** — si algo 
  no cuadra, ábrelo y revísalo
- **Puedes pedir cambios en cualquier momento** — pero si estás en medio 
  de una subfase, espera a que termine antes de pedirlos
- **Si rechazas un hito dos veces seguidas**, describe el problema con 
  capturas o logs — ayuda al agente a entender exactamente qué falla