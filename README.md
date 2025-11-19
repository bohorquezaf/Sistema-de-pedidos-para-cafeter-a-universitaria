# Sistema-de-pedidos-para-cafeteria-universitaria

[![cafeteria.png](https://i.postimg.cc/xCpFLQG0/cafeteria.png)](https://postimg.cc/k68cdkhZ)

---

# 🌟 Introducción

Este proyecto desarrolla un Sistema de Pedidos para la Cafetería Universitaria, permitiendo a los usuarios realizar órdenes de manera rápida desde una plataforma web que permita a estudiantes, docentes y personal realizar pedidos desde cualquier dispositivo, mientras la cafetería los gestiona de manera organizada y sin estrés.

---

## 🎯 Objetivo del Proyecto

Desarrollar un sistema digital que optimice la gestión de pedidos en la cafetería universitaria, mejorando la rapidez de atención y la organización interna, mediante la aplicación de buenas prácticas de ingeniería de software y documentación clara en Markdown.

---

# 📝 Requerimientos 

## ✔ Requerimientos Funcionales
- Gestión de productos (CRUD).
- Registro de pedidos.
- Actualización del estado del pedido.
- Autenticación de usuarios (roles).
- Visualización del menú.
- Historial de pedidos.
- Reportes de ventas.

## ✔ Requerimientos No Funcionales
- Usabilidad (fácil de usar, completar pedidos en <2 min).
- Rendimiento (<2 segundos por acción).
- Escalabilidad (soportar duplicación de carga).
- Disponibilidad (95% uptime).
- Seguridad (cifrado y control de acceso).

---

#  Plan de Pruebas

| Requerimiento | Entrada | Resultado esperado | Resultado obtenido |
|---------------|---------|-------------------|--------------------|
| Funcional | Usuario “maria123” | Acceso exitoso | Correcto |
| Funcional | Solicitud | Lista completa | Correcto |
| Funcional | Café x2 + Sándwich | Pedido registrado | Correcto |
| no Funcional | 10 usuarios simultáneos | Fluido | Correcto |
| no Funcional | Varias operaciones | ≤ 2s | correcto|
- **Criterio de aceptación:** 
  - Sistema sin errores.  
  - Respuestas en menos de 2 segundos.  
  - Estados actualizados correctamente.

---

# 🛠 Propuesta de Mantenimiento 


| Tipo de Mantenimiento | Situaciones Detectadas | Acciones Propuestas |
|-----------------------|------------------------|----------------------|
| **Correctivo** | - Edición/cancelación de pedidos confirmados.<br>- Pérdida de datos.<br>- Validaciones insuficientes. | - Corregir lógica de estados.<br>- Implementar validaciones en cliente y servidor.<br>- Reparar errores transaccionales. |
| **Preventivo** | - Riesgos de concurrencia.<br>- Caídas bajo carga.<br>- Lentitud bajo picos de uso. | - Pruebas de carga y estrés (JMeter).<br>- Monitoreo continuo.<br>- Optimización temprana. |
| **Perfectivo** | - Interfaz poco clara.<br>- Consultas lentas.<br>- Flujo poco intuitivo. | - Optimización SQL.<br>- Mejoras visuales (alertas y estados).<br>- Máquina de estados (FSM) bien documentada. |

---

# Investigación sobre Markdown

Markdown es un lenguaje de marcado ligero diseñado para escribir texto con formato de manera simple y rápida. Su principal fortaleza es que permite crear documentos claros y estructurados usando solo texto plano, sin la complejidad de lenguajes como HTML.

## ¿Por qué se usa en proyectos de software?

- Facilita la documentación técnica.

- Es fácil de leer incluso sin procesar.

- Funciona en cualquier editor de texto.

- Se integra de forma nativa con plataformas como GitHub, GitLab y Bitbucket.

- Permite mantener documentación ordenada, ligera y versionable.

## Elementos más usados

- Encabezados: #, ##, ###

- Listas: - item o 1. item

- Tablas: sintaxis simple con pipes (|)

- Enlaces: [Cómo agregar un enlace](https://www.linkedin.com/pulse/github-readmemd-how-add-link-billour-ou)

- Imágenes:

[![cat.jpg](https://i.postimg.cc/90nGMNYJ/cat.jpg)](https://postimg.cc/bS1GVgMt)

---

# 🧠 Reflexión Personal sobre la Utilidad del Control de Versiones y Markdown en la Documentación Técnica

El uso de **control de versiones**, especialmente GitHub, transformó completamente la manera en que trabajo la documentación técnica. Algunas razones:

### ✔ Control de versiones
- Permite ver **cada cambio**, quién lo hizo y cuándo lo hizo.  
- Evita perder información o sobrescribir archivos.  
- Hace posible **volver a versiones anteriores** si algo sale mal.  
- Facilita el trabajo colaborativo sin conflictos.  
- Mantiene una **trazabilidad completa**, algo esencial en ingeniería de software.

Trabajar documentación sin control de versiones es como programar sin guardado automático: tarde o temprano algo se rompe.

### ✔ Markdown
Markdown es la herramienta perfecta para documentar porque:
- Es ligero, rápido y fácil de aprender.  
- No necesita herramientas complicadas (solo texto plano).  
- Se ve hermoso cuando GitHub lo renderiza.  
- Permite tablas, imágenes, listas, encabezados y más.  
- Mantiene la documentación ordenada, clara y profesional.

### ✔ Combinación Markdown + GitHub
Cuando ambos se juntan, pasa magia.  
La documentación se vuelve:

- Más portable  
- Más colaborativa  
- Más fácil de mantener  
- Más segura  
- Más profesional  
- Más trazable  

En conclusión, el control de versiones y Markdown no solo facilitan el trabajo: **elevan el estándar**.  
Son herramientas que todo ingeniero de software debería dominar porque garantizan orden, claridad y evolución constante en la documentación de cualquier proyecto.

---

# 📌 Autores
**Autor:** *[Bohórquez Flores Axel Darlyn]* Fecha: [18/11/2025]

**Proyecto:** *Sistema de pedidos para cafeteria universitaria*

**docente:** *[ING.Jorge Dumar Guevara]*

