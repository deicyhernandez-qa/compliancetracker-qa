# VendorShield QA — Reporte de Correcciones

<p align="center">
  <img src="https://img.shields.io/badge/Producto-VendorShield-1B9E91?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Empresa-CyberProtect_Solutions-2471A3?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Hallazgos-69-E67E22?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Secciones-5-2980B9?style=flat-square&labelColor=333333" />
  <img src="https://img.shields.io/badge/Estado-Resuelto-27AE60?style=flat-square&labelColor=333333" />
</p>

---

## Contexto del proyecto

**VendorShield** es el producto SaaS de **CyberProtect Solutions** para la gestión de cumplimiento y validación de proveedores. Esta ronda de QA cubrió la revisión del sitio web de producto (página de marketing, tarjetas de planes y botón de prueba gratuita) y el portal interno de soluciones.

A diferencia de otros proyectos del portafolio, los hallazgos de esta revisión **no se registraron en Jira**: se trabajaron directamente con el equipo de desarrollo en sesiones presenciales. Este repositorio incluye un **documento Excel equivalente a Jira** con los mismos campos utilizados en los reportes formales de otros proyectos, generado para garantizar la trazabilidad y documentación de los hallazgos.

> **Empresa:** CyberProtect Solutions  
> **Producto:** VendorShield (SaaS de gestión de cumplimiento de proveedores)  
> **Período de revisión:** Septiembre – Noviembre 2026  
> **Metodología:** Revisión directa con desarrollador · Sesiones de trabajo presencial

---

## Cobertura de la revisión

| Código | Sección revisada | Hallazgos | Prioridad máx. | Estado |
|--------|-----------------|-----------|----------------|--------|
| VS001 | Tarjeta de Producto en Página Web | 6 | Media | ✅ Resuelto |
| VS002 | Contenido de Producto en Página Web | 8 | Media | ✅ Resuelto |
| VS003 | Tarjetas de Planes (Core / Pro) | 11 | Media | ⚠️ Parcial |
| VS004 | Botón "Probar 10 días gratis" | 2 | **Crítica** | ✅ Resuelto |
| VS005 | Portal de Soluciones | 42 | Media / Alta | ✅ Resuelto |
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
| Defecto funcional crítico | El flujo de registro de prueba gratuita permite correos personales y no redirige correctamente al producto |
| Defecto de seguridad | 2FA desmontable después de cerrar sesión; re-validación de identidad no requerida si el flujo no se completa |
| Defecto visual / UI | Inconsistencias de tamaño, colores, bordes y alineación en tarjetas y secciones del portal |
| Mejora de contenido | Textos desactualizados, párrafos que no reflejan el diferenciador de IA, formatos de precio incompletos |
| Mejora de UX | Elementos duplicados en menú y portal, flujos de verificación de correo y 2FA fragmentados |
| Nueva funcionalidad | Sección de Soporte técnico con formulario de contacto integrado en el portal |

---

## Hallazgos críticos destacados

### VS-026 — Registro con correo personal y flujo post-registro incorrecto (VS004)

| Campo | Detalle |
|-------|---------|
| **Resultado actual** | El botón "Prueba 10 días gratis" permite registros con correos personales (Gmail, Hotmail, etc.) y, al verificar, redirige a la pantalla de inicio con todos los planes en lugar de al producto VendorShield. |
| **Resultado esperado** | Solo correos corporativos. Al verificar, el usuario debe ir directamente a VendorShield en versión Core. |
| **Prioridad** | 🔴 Crítica |
| **Evidencia** | Video: REGISTRO CORREO PERSONAL |

### VS-036 / VS-037 — Defectos en flujo de autenticación de dos factores (VS005)

| Campo | Detalle |
|-------|---------|
| **Defecto 1** | El 2FA puede desconfiguarse tras cerrar sesión, perdiendo la protección establecida. |
| **Defecto 2** | Si el usuario valida su identidad para el 2FA pero no completa el proceso, en la siguiente sesión no se solicita re-validar la identidad. |
| **Prioridad** | Media / Alta |
| **Referencia** | Audio grupo app web, 28/09/2026 |

---

## Documento de hallazgos (equivalente Jira)

Dado que estos hallazgos no se registraron en Jira, se elaboró un documento Excel con los mismos campos de los tickets formales:

📄 [`VendorShield_QA_Hallazgos_Jira.xlsx`](./VendorShield_QA_Hallazgos_Jira.xlsx)

**Campos incluidos por hallazgo:**

| Campo | Descripción |
|-------|-------------|
| ID | Identificador único (VS-001 a VS-040+) |
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

```
vendorshield-qa/
├── README.md
└── VendorShield_QA_Hallazgos_Jira.xlsx   # Registro completo equivalente a Jira
```

---

## Stack utilizado

<p>
  <img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white" />
  <img src="https://img.shields.io/badge/Revisión_con_Desarrollador-1B9E91?style=for-the-badge" />
</p>
