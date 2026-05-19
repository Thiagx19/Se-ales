# Quiz Señales Viales — Historial de versiones

---

## V.6.3 — (actual)
- **Fix error `scores[7].c`**: agregado `scores[8]` en la declaración inicial; guard en `updateStreak` para app 8
- **Fix tab Teoría no se coloreaba**: la lógica `i+1===n` fallaba porque Teoría es tab 4 pero app 6. Reemplazado por mapeo explícito `tabApps = [1,2,3,6]`
- **Color Flash rediseñado**: fondo cambiado de naranja oscuro (`#3d1a00`) a azul-gris (`#252836`), formando una progresión coherente con Escribir (`#1b2838`) y Veloz (`#1a1a2e`). Tab activo y botón Siguiente actualizados al mismo tono (`#3d4f6e`)
- **Botón cruzado señales↔teoría**: aparece en el bottom-nav solo cuando hay errores del tipo opuesto. En modos señales muestra "📋 Ver errores de teoría"; en modos teoría muestra "🚦 Ver errores de señales"

---

## V.6.2
- **Errores de teoría separados**: `errorMapT6` independiente de `errorMap` (señales), persistido en `sq_errors_t6` en localStorage
- **App 7 — Repaso Teoría**: igual que app 4 para señales, usa preguntas falladas con MC/VF alternante y timer 15s. Acertar reduce el contador de error
- **App 8 — Errores Teoría**: lista de preguntas falladas ordenadas por frecuencia, con botones Repasar y Limpiar errores
- **Bottom-nav dinámico**: en modos señales (1/2/3/4/5) muestra 🔁 Repaso señales + ❌ Errores señales; en modos teoría (6/7/8) muestra 🔁 Repaso teoría + ❌ Errores teoría
- **`addErrorT6`**: los errores de teoría se registran al fallar o agotar el tiempo en app 6 y app 7

---

## V.6.1
- **Fix centrado modo Teoría**: pregunta, afirmación V/F y opciones MC ahora están todas centradas
- **Fix botón Siguiente**: aparece correctamente tras responder o agotar el tiempo en app 6
- **Fix errores JS**: eliminada referencia a `showFeedback` (no existía); reemplazado por el patrón real del proyecto (`fb.className`, `fb.textContent`, `fb.style.display`)
- **Fix timer app 6**: `updateTimerUI` usa `TIMER_SEC_6` (15s) al calcular el porcentaje de la barra
- **Versión renombrada**: formato sin ceros de relleno (V.6.x en lugar de V.006.x)

---

## V.6.0
- **Nuevo modo: 📋 Teoría** (App 6) — cuarta tab en la card principal
  - 111 preguntas del Manual de Educación Vial de Tigre, embebidas en el archivo
  - Timer de 15 segundos (vs 10s de los otros modos)
  - Fondo verde oscuro `#071a0e`, barra de progreso verde `#0d5c2e`
  - Modo alternante por pregunta (50/50): Multiple choice o Verdadero/Falso
  - La misma pregunta puede aparecer como MC en una vuelta y V/F en otra
  - Badge de color indica el tipo antes de responder: verde (MC) o azul (V/F)
  - Score, progreso y racha integrados igual que los otros modos
  - Botón ↺ Reiniciar resetea score y cola del modo Teoría

---

## V.005.3
- **Card más limpia**: eliminados el título de modo, subtítulo 'Manual de Educación Vial' y contador de pregunta
- **Racha de aciertos** movida entre las tabs y el contenido, visible en todos los modos
- **Tab App 3**: renombrada de '🌙 Difícil' a '⚡ Veloz'
- **Modo Flash**:
  - Timer oculto mientras se muestra la imagen; aparece recién cuando la imagen desaparece y hay que elegir
  - '¿Cuál era?' ahora aparece grande (1.15rem, negrita fuerte) como encabezado de las opciones
- Removidas referencias JS a elementos eliminados (counter, app-title) para evitar errores silenciosos

---

## V.005.2
- Score bar completamente centrado (eliminado margin-left:auto del botón)
- Reiniciar movido debajo del score como botón de ancho completo con texto '↺ Reiniciar'
- Racha de aciertos movida entre el score y el botón reiniciar

---

## V.005.1
- **Pulido general de UI/UX**:
  - Card con bordes más redondeados y sombra más profunda
  - Tabs con mejor espaciado y letter-spacing
  - Input con glow sutil al hacer foco
  - Botones con feedback táctil (scale en :active) en toda la app
  - Score bar simplificada: ✓ / ✗ en lugar de texto largo, porcentaje más pequeño
  - Barra de progreso movida encima del score
  - Labels de opciones en negrita para mayor legibilidad
  - Espaciado general más ajustado para pantallas pequeñas
  - Transición de progreso más suave (0.35s ease)

---

## V.005.0.4
- **Fix Limpiar errores (App 5)**: eliminado `confirm()`, bloqueado silenciosamente por Android en archivos locales
- **Reiniciar limpia errores también**: el botón ↺ resetea puntaje, cola Y lista de errores del modo actual

---

## V.005.0.3
- **Fix Reiniciar**: eliminado `confirm()` que Android bloquea en archivos locales
- **Modo Flash rediseñado**:
  - Imagen visible 1 segundo, sin countdown
  - Al desaparecer, aparecen 4 opciones en grilla 2×2
  - Timer de 10 segundos con barra naranja → amarillo → rojo
  - Al agotar el tiempo, se muestra la correcta y se registra como error
  - Al elegir, la imagen vuelve como confirmación

---

## V.005.0.2
- Fix Modo Flash — imagen no desaparecía: `clearTimeout` → `clearInterval`
- Fix botón Reiniciar — no respondía al toque en mobile
- Rediseño visual Flash: grilla 2×2, mayúsculas, sombras, glow en estados

---

## V.005.0.1
- Fix crash Modo Difícil: guards en `a23Pick()` y `onTimeout()`
- Fix Modo Flash que no aparecía

---

## V.005
- Modo Flash reemplaza App 2 (Elegir)
- App 2 original preservada como comentario HTML

---

## V.004.2.1
- Fix crash al iniciar: null-check + DOMContentLoaded

---

## V.004.2
- Botones Repaso/Errores fuera de la card (bottom-nav)
- Badge rojo con contador de errores

---

## V.004.1
- App 4: Repaso de errores
- App 5: Panel de errores
- localStorage: persistencia entre sesiones
- Racha de aciertos, botón Reiniciar por modo

---

## V.004
- Leyenda de versión al pie
- Fix layout flex-direction

---

## V.003 y anteriores
- App 1 (Escribir), App 2 (Elegir), App 3 (Difícil 10 seg)
- 202 señales, grupos, smart peers

---

## V.6.4
- **Botón cruzado movido dentro de la card**: ahora aparece en sec4, sec5, sec7 y sec8 (no en el bottom-nav)
  - sec4 (Repaso señales) → "📋 Ir a Repaso de Teoría"
  - sec5 (Errores señales) → "📋 Ver Errores de Teoría"
  - sec7 (Repaso teoría) → "🚦 Ir a Repaso de Señales"
  - sec8 (Errores teoría) → "🚦 Ver Errores de Señales"

---

## V.6.5
- **Fix raíz crash `scores[X].w`**: `loadScores()` reemplazaba el objeto `scores` completo con el guardado en localStorage de versiones anteriores sin los keys 6/7/8. Ahora hace merge — inicializa cualquier key faltante en `{c:0,w:0}`
- **Fix onTimeout en app7**: el timer expiraba sin hacer nada. Agregado `onTimeout7()` con feedback, reveal de correcta y botón Siguiente
- **Fix timer app7**: `startTimer()` y `updateTimerUI()` ahora usan `TIMER_SEC_6` (15s) también para app7
- **Botones cruzados en bottom-nav**: removidos de dentro de la card y reubicados debajo de los botones principales. Aparecen solo cuando estás en repaso/errores (app 4/5/7/8) y hay errores del tipo contrario


---

## V.6.6
- **Limpieza total de botones cruzados**: removidos de dentro de la card (sec5, sec8 donde estaban duplicados y mal ubicados)
- **CSS `.btn-cross-internal` eliminado**: ya no se usa
- **Botones cruzados únicamente en el bottom-nav**:
  - "📋 Errores de Teoría" → visible cuando estás en app 4 o 5 (repaso/errores señales)
  - "🚦 Errores de Señales" → visible cuando estás en app 7 u 8 (repaso/errores teoría)
  - Siempre visibles al estar en las secciones correspondientes, sin condición adicional

---

## V.6.7
- **Errores persistentes en repaso**: acertar en modo Repaso de Señales (app 4) y Repaso de Teoría (app 7) ya no elimina el error del registro. Los errores solo se limpian con "Limpiar errores" o "↺ Reiniciar"
