# Quiz Señales Viales — Historial de versiones

---

## V.005.3 — (actual)
- **Card más limpia**: eliminados el título de modo, subtítulo 'Manual de Educación Vial' y contador de pregunta
- **Racha de aciertos** movida entre las tabs y el contenido, visible en todos los modos
- **Tab App 3**: renombrada de '🌙 Difícil' a '⚡ Veloz'
- **Modo Flash**:
  - Timer oculto mientras se muestra la imagen; aparece recién cuando la imagen desaparece y hay que elegir
  - '¿Cuál era?' ahora aparece grande (1.15rem, negrita fuerte) como encabezado de las opciones
- Removidas referencias JS a elementos eliminados (counter, app-title) para evitar errores silenciosos

---

## V.005.2 — (actual)
- Score bar completamente centrado (eliminado margin-left:auto del botón)
- Reiniciar movido debajo del score como botón de ancho completo con texto '↺ Reiniciar'
- Racha de aciertos movida entre el score y el botón reiniciar (antes estaba oculta arriba de la card)

---

## V.005.1 — (actual)
- **Pulido general de UI/UX**:
  - Card con bordes más redondeados y sombra más profunda
  - Tabs con mejor espaciado y letter-spacing
  - Input con glow sutil al hacer foco
  - Botones con feedback táctil (scale en :active) en toda la app
  - Score bar simplificada: ✓ / ✗ en lugar de texto largo, porcentaje más pequeño
  - Barra de progreso movida encima del score (orden más lógico: avance → puntaje)
  - Botón ↺ Reiniciar alineado a la derecha del score con margin-left:auto
  - Labels de opciones en negrita para mayor legibilidad
  - Error cards con feedback táctil al presionar
  - Botones Repaso/Limpiar en App 5 con hover state propio
  - Espaciado general más ajustado para pantallas pequeñas
  - Transición de progreso más suave (0.35s ease)

---

## V.005.0.4 — (actual)
- **Fix Limpiar errores (App 5)**: el botón no respondía porque usaba `confirm()`, bloqueado silenciosamente por Android en archivos locales. Eliminado, ahora limpia directo
- **Reiniciar limpia errores también**: el botón ↺ ahora resetea puntaje, cola Y lista de errores del modo actual

---

## V.005.0.3 — (actual)
- **Fix Reiniciar**: eliminado el `confirm()` que Android bloquea silenciosamente en archivos locales. El botón ahora reinicia directamente sin diálogo
- **Modo Flash rediseñado**:
  - Imagen visible 1 segundo (antes 1.5s), sin countdown encima — ocupa todo el espacio disponible (190px)
  - Al desaparecer la imagen, aparecen las 4 opciones en grilla 2×2 ocupando todo el ancho
  - Timer de 10 segundos para elegir (barra naranja → amarillo → rojo), con número al costado
  - Si el tiempo se agota, se muestra la correcta y se registra como error (igual que App 3)
  - Al elegir, la imagen vuelve a aparecer como confirmación con el nombre correcto

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
