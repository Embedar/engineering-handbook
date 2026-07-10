
# 07. Decisions — Registro de Decisiones de Arquitectura (ADR)

> Formato ADR (Architecture Decision Record) simplificado. Cada decisión técnica importante — que alguien podría preguntarte "¿por qué elegiste esto y no lo otro?" en una entrevista — merece una entrada aquí. Esto es lo que más impresiona en un portafolio: demuestra criterio de ingeniería, no solo que "funcionó".

**Cómo usar este archivo:** copia el bloque de plantilla por cada decisión nueva, numera secuencialmente (ADR-001, ADR-002...), y nunca borres una entrada — si una decisión se revierte, se marca como `Superseded` y se referencia la nueva.

---

## Plantilla de entrada

### ADR-XXX: [Título corto de la decisión]

- **Fecha:** [YYYY-MM-DD]
- **Estado:** `Propuesta / Aceptada / Rechazada / Superseded por ADR-YYY`
- **Contexto:** ¿Qué problema u opción estaba en juego? ¿Qué restricciones aplicaban (de `01_Project_Brief.md` §6)?
- **Opciones consideradas:**
  1. [Opción A] — pros / contras
  2. [Opción B] — pros / contras
- **Decisión:** [Qué se eligió, en una o dos frases]
- **Justificación:** [Por qué, con criterio técnico — costo, disponibilidad, rendimiento, curva de aprendizaje, etc.]
- **Consecuencias:** [Qué implica esta decisión a futuro — positivas y negativas]
- **Referencias:** [Documento/sección afectada, ej. `03_System_Architecture.md` §3]

---

## Ejemplo (bórralo al iniciar el proyecto real)

### ADR-001: Comunicación entre Nodo A (STM32) y Nodo B (ESP32)

- **Fecha:** 2026-01-15
- **Estado:** Aceptada
- **Contexto:** El sistema requiere transferir datos de control en tiempo real desde el STM32 (control determinístico) hacia el ESP32 (conectividad Wi-Fi), con baja latencia y sin necesidad de gran ancho de banda.
- **Opciones consideradas:**
  1. UART simple — bajo costo, fácil de depurar, suficiente para el volumen de datos esperado, pero sin verificación de errores nativa.
  2. CAN bus — robusto ante ruido y multi-nodo real, pero requiere transceptor adicional y es sobredimensionado para 2 nodos.
  3. SPI — más rápido, pero requiere líneas adicionales (CS, líneas dedicadas) y es más sensible a la distancia física entre placas.
- **Decisión:** UART a 115200 baudios con un framing simple (start byte + longitud + CRC8).
- **Justificación:** El volumen de datos y la distancia entre placas no justifican CAN; UART simplifica el hardware y el firmware, y el CRC8 cubre el riesgo de corrupción de datos sin la complejidad de un bus completo.
- **Consecuencias:** Si en el futuro se agregan más nodos, esta decisión deberá revisarse (candidato a ADR de superseding con CAN o RS-485).
- **Referencias:** `03_System_Architecture.md` §3, `04_Design.md` §6

---

## Índice de decisiones

| ID | Título | Estado | Fecha |
|----|--------|--------|-------|
| ADR-001 | | | |
