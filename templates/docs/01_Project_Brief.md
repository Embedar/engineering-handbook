
# 01. Project Brief — [Nombre del Proyecto]

> **Propósito de este documento:** responder "¿qué problema resuelvo y por qué?" antes de tocar una sola línea de código o un solo componente. Si no puedes llenar la sección 2 con claridad, el proyecto todavía no está listo para pasar a `02_Requirements.md`.

**Autor:** [Tu nombre] · **Fecha de inicio:** [YYYY-MM-DD] · **Estado:** `Borrador / En progreso / Congelado`
**Repositorio del proyecto:** [link] · **Documento relacionado:** `07_Decisions.md` (ADR-001 en adelante)

---

## 1. Contexto y motivación

- ¿De dónde nace este proyecto? (materia, competencia, portafolio, necesidad personal, cliente ficticio/real)
- ¿Qué existe hoy que resuelve esto parcial o totalmente? (benchmark rápido de soluciones existentes)
- ¿Por qué vale la pena documentarlo/publicarlo en el portafolio?

## 2. Preguntas clave a responder

> Esta es la lista de preguntas que **debes poder responder** antes de diseñar. Bórralas a medida que las contestas (mueve la respuesta a la sección correspondiente) y añade las que sean específicas de tu dominio (electrónica, control, RF, etc.).

| # | Pregunta | Respondida en |
|---|----------|----------------|
| Q1 | ¿Cuál es el problema exacto que resuelve el sistema? | §3 |
| Q2 | ¿Quién lo usa y en qué condiciones (ambiente, usuario técnico/no técnico)? | §5 |
| Q3 | ¿Existen restricciones físicas/eléctricas de entrada (voltajes, alimentación, tamaño)? | §6 |
| Q4 | ¿El proyecto requiere hardware propio (PCB), o usa módulos/desarrollo boards? | `03_System_Architecture.md` |
| Q5 | ¿Involucra más de un microcontrolador/procesador? ¿Cómo se comunican? | `03_System_Architecture.md` |
| Q6 | ¿Necesita modelado físico (mecánico, térmico, cinemático) o simulación de circuitos? | `04_Design.md` |
| Q7 | ¿Es orientado a objetos (C++/Python) o procedural (C embebido)? Define qué tipo de diagrama de diseño aplica. | `04_Design.md` |
| Q8 | ¿Hay normativa o estándar que deba cumplir (seguridad, EMC, industrial)? | §6 |
| Q9 | ¿Cuál es el criterio objetivo de que el proyecto "funciona" (métrica medible)? | §7 |
| Q10 | ¿Qué parte es la más riesgosa/incierta del proyecto? | §8 |

## 3. Objetivo general

[Una frase. Debe ser verificable, no aspiracional. Ej: "Diseñar un sistema de adquisición de datos de 3 canales con muestreo ≥1kSPS transmitido por Wi-Fi a un dashboard local".]

### 3.1 Objetivos específicos

1. [Objetivo medible 1]
2. [Objetivo medible 2]
3. [Objetivo medible 3]

## 4. Alcance

**Dentro del alcance (in scope):**
- [ ] [Ítem]

**Fuera del alcance (out of scope, explícitamente):**
- [ ] [Ítem — decir "no" a tiempo evita crear carpetas/documentos que nunca vas a llenar]

## 5. Usuarios / Stakeholders

| Rol | Necesidad | Nivel técnico |
|-----|-----------|----------------|
| [Usuario final] | | |
| [Evaluador/profesor/cliente] | | |
| [Tú como mantenedor futuro] | Poder retomar el proyecto en 6 meses sin perder contexto | Alto |

## 6. Restricciones

- **Presupuesto:** [$ o "sin restricción definida"]
- **Tiempo:** [fecha límite / sprint]
- **Plataforma obligatoria:** [ESP32-IDF / STM32CubeIDE / CCS / ninguna aún]
- **Normativa aplicable:** [N/A o cuál]
- **Restricciones físicas:** [alimentación disponible, tamaño máximo, consumo máximo, etc.]

## 7. Criterios de éxito (medibles)

| Criterio | Métrica | Meta |
|----------|---------|------|
| [Ej: Latencia de control] | ms | ≤ [valor] |
| [Ej: Autonomía] | horas | ≥ [valor] |

## 8. Riesgos iniciales

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|--------------|---------|------------|
| [Ej: Componente con lead time largo] | Media | Alto | [Pedir con anticipación / alternativa] |

## 9. Clasificación del proyecto (define qué otras carpetas/documentos vas a necesitar)

Marca lo que aplica — esto determina la estructura del resto del repositorio:

- [ ] Requiere diseño de hardware propio (PCB) → carpeta `/hardware`
- [ ] Requiere firmware embebido → carpeta `/firmware`
- [ ] Involucra múltiples MCUs/procesadores → sección "Topología multi-nodo" en `03_System_Architecture.md`
- [ ] Requiere software de alto nivel (host, GUI, dashboard) → carpeta `/software`
- [ ] Requiere simulación de circuito (SPICE) → carpeta `/simulation/circuit`
- [ ] Requiere simulación física/mecánica/control → carpeta `/simulation/physics` o `/simulation/control`
- [ ] Requiere modelado 3D/mecánico (CAD, enclosure) → carpeta `/mechanical`
- [ ] Es orientado a objetos → diagrama de clases en `04_Design.md`
- [ ] Es procedural/bare-metal → diagramas de flujo/estado en `04_Design.md`

> **Regla práctica:** no crees la carpeta hasta que el primer archivo real vaya a vivir en ella. La checklist de arriba es la lista de "carpetas permitidas", no la lista de "carpetas obligatorias".
