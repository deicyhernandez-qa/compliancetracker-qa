# ComplianceTracker QA — Reporte de Correcciones

<p align="center">
  <img src="https://img.shields.io/badge/Producto-ComplianceTracker-1B9E91?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Empresa-CyberProtect_Solutions-2471A3?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Hallazgos-69-E67E22?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Secciones-5-2980B9?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Estado-Resuelto-27AE60?style=flat-square&labelColor=333333" />
</p>

---

## Contexto del proyecto

**ComplianceTracker** es una plataforma SaaS de **CyberProtect Solutions** para la gestión de cumplimiento y validación de proveedores. Esta ronda de QA cubrió la revisión del sitio web de producto (página de marketing, tarjetas de planes y botón de prueba gratuita) y el portal interno de soluciones.

A diferencia de otros proyectos del portafolio, los hallazgos de esta revisión **no se registraron en Jira**: se trabajaron directamente con el equipo de desarrollo en sesiones presenciales. Este repositorio incluye un **documento Excel equivalente a Jira** con los mismos campos utilizados en los reportes formales de otros proyectos, generado para garantizar la trazabilidad y documentación de los hallazgos.

> **Empresa:** CyberProtect Solutions
> **Producto:** ComplianceTracker (SaaS de gestión de cumplimiento de proveedores)
> **Período de revisión:** Septiembre – Noviembre 2026
> **Metodología:** Revisión directa con desarrollador · Sesiones de trabajo presencial

---

## Cobertura de la revisión

| Código | Sección revisada | Hallazgos | Prioridad máx. | Estado |
|--------|-----------------|-----------|----------------|--------|
| CT001 | Tarjeta de Producto en Página Web | 6 | Media | ✅ Resuelto |
| CT002 | Contenido de Producto en Página Web | 8 | Media | ✅ Resuelto |
| CT003 | Tarjetas de Planes (Core / Pro) | 11 | Media | ⚠️ Parcial |
| CT004 | Botón "Probar 10 días gratis" | 2 | **Crítica** | ✅ Resuelto |
| CT005 | Portal de Soluciones | 42 | Media / Alta | ✅ Resuelto |
| **TOTAL** | | **69** | | |

---

## Hallazgos por prioridad

| Prioridad | Hallazgos | % |
|-----------|-----------|---|
| 🔴 Crítica | 2 | 2.9% |
| 🟡 Media / Alta | 51 | 73.9% |
| 🟢 Baja | 16 | 23.2% |
| **Total** | **69** | **100%** |

---

## Tipos de hallazgos

| Tipo | Descripción |
|------|-------------|
| Defecto funcional crítico | El flujo de registro de prueba gratuita no valida el tipo de correo y no redirige correctamente al producto tras la verificación |
| Defecto de autenticación | Defectos en el flujo de configuración del segundo factor de autenticación, ya resueltos |
| Defecto visual / UI | Inconsistencias de tamaño, colores, bordes y alineación en tarjetas y secciones del portal |
| Mejora de contenido | Textos desactualizados, párrafos que no reflejan el diferenciador de IA, formatos de precio incompletos |
| Mejora de UX | Elementos duplicados en menú y portal, flujos de verificación de correo fragmentados |
| Nueva funcionalidad | Sección de Soporte técnico con formulario de contacto integrado en el portal |

---

## Hallazgo crítico destacado

### CT-026 — Validación de correo y redirección post-registro incorrectas (CT004)

| Campo | Detalle |
|-------|---------|
| **Resultado actual** | El botón "Prueba 10 días gratis" no valida el tipo de correo ingresado y, al verificar, redirige a la pantalla de inicio en lugar de al producto en versión de prueba. |
| **Resultado esperado** | Solo correos corporativos. Al verificar, el usuario debe acceder directamente a la versión de prueba del producto. |
| **Prioridad** | 🔴 Crítica |
| **Estado** | ✅ Resuelto |

### CT-036 / CT-037 — Defectos en flujo de segundo factor de autenticación (CT005)

| Campo | Detalle |
|-------|---------|
| **Descripción** | Defectos en el flujo de configuración del segundo factor de autenticación que afectaban la consistencia del proceso entre sesiones. |
| **Prioridad** | Media / Alta |
| **Estado** | ✅ Resuelto |

---

## Documento de hallazgos (equivalente Jira)

Dado que estos hallazgos no se registraron en Jira, se elaboró un documento Excel con los mismos campos de los tickets formales.

> **Nota sobre los IDs:** El documento Excel contiene **40 hallazgos documentados en detalle** (CT-001 a CT-040), seleccionados como muestra representativa de los 69 hallazgos totales identificados durante la revisión.

📄 [`ComplianceTracker_QA_Hallazgos_Jira.xlsx`](./ComplianceTracker_QA_Hallazgos_Jira.xlsx)

**Campos incluidos por hallazgo:**

| Campo | Descripción |
|-------|-------------|
| ID | Identificador único (CT-001 a CT-040) |
| Sección | Código y nombre de la sección revisada |
| Título del hallazgo | Descripción concisa del problema |
| Descripción | Contexto completo del hallazgo |
| Pasos para reproducir | Secuencia de acciones para reproducir el hallazgo |
| Resultado actual | Comportamiento observado |
| Resultado esperado | Comportamiento correcto definido |
| Prioridad | Crítica / Media / Alta / Baja |
| Severidad | Crítica / Alta / Moderada / Menor |
| Tipo | Categoría del hallazgo |
| Ambiente | Contexto de prueba (Producción - Sitio Web / Portal Web) |
| Herramienta | Revisión directa con desarrollador + evidencias si aplica |
| Estado | Resuelto / Pendiente |
| Fecha | Fecha de detección |
| Asignado a | Responsable de corrección |

---

## Estructura del repositorio

\`\`\`
compliancetracker-qa/
├── README.md
└── ComplianceTracker_QA_Hallazgos_Jira.xlsx   # 40 hallazgos documentados en detalle (de 69 totales)
\`\`\`

---

## Stack utilizado

<p>
  <img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white" />
  <img src="https://img.shields.io/badge/Chrome_DevTools-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white" />
  <img src="https://img.shields.io/badge/Revisión_con_Desarrollador-1B9E91?style=for-the-badge" />
</p>
