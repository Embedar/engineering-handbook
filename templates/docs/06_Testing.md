
# 06. Testing & Validation — [Nombre del Proyecto]

> Cada caso de prueba debe trazar a un requisito de `02_Requirements.md`. Si escribiste un requisito que no puedes probar aquí, vuelve y corrígelo.

---

## 1. Estrategia de pruebas

| Nivel | Qué se prueba | Herramienta/método |
|-------|-----------------|------------------------|
| Unitaria (firmware) | Funciones/módulos individuales | [Unity/Ceedling/GoogleTest] |
| Unitaria (software host) | Funciones Python | `pytest` |
| Integración | Comunicación entre nodos/módulos | Banco de pruebas + logs |
| Hardware-in-the-loop (HIL) | Firmware real contra señales reales/simuladas | [osciloscopio, fuente programable, etc.] |
| Validación de sistema | Cumplimiento de requisitos completos | Checklist contra `02_Requirements.md` |
| Circuito (si aplica) | Comportamiento real vs. simulado | Multímetro/osciloscopio vs. `/simulation/circuit` |

## 2. Casos de prueba

| Test ID | Requisito (ID) | Descripción | Procedimiento | Resultado esperado | Resultado obtenido | Estado |
|---------|-------------------|--------------|-----------------|-------------------------|--------------------------|--------|
| TC-01 | RF-01 | | | | | ⬜ |
| TC-02 | RH-01 | | | | | ⬜ |

> Estados sugeridos: ⬜ Pendiente · 🟡 En progreso · ✅ Passed · ❌ Failed · ⚠️ Passed con observaciones

## 3. Validación de hardware/circuito *(si aplica)*

| Medición | Valor simulado (`04_Design.md` §5) | Valor medido en banco | Desviación | ¿Dentro de tolerancia? |
|----------|----------------------------------------|---------------------------|--------------|---------------------------|
| | | | | |

## 4. Registro de bugs / no conformidades

> Idealmente esto vive como GitHub Issues con la etiqueta `bug`, enlazados aquí solo como resumen.

| ID Issue | Descripción corta | Severidad | Estado |
|----------|----------------------|-------------|--------|
| #12 | | | |

## 5. Resumen de cobertura de requisitos

| Total Must | Passed | Failed | Pendientes | % Cumplimiento |
|------------|--------|--------|-------------|-------------------|
| | | | | |

## 6. Lecciones aprendidas de la fase de pruebas

- [Qué falló y por qué — esto alimenta futuros ADR en `07_Decisions.md`]
