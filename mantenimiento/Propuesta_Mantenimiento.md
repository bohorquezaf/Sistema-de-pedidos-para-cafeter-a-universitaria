FACULTAD DE CIENCIAS E INGENIERÍA 
CARRERA DE INGENIERÍA DE SOFTWARE 

TEMA: 
Mantenimineto para el Desarrollo de un Sistema de Pedidos para 
Cafetería Universitaria 

AUTORES: 
 Diaz Matias Wilmer Jostin 
Andrade Perez Emilia Thais 
Granda Vacacela Andres Said 
Bohorquez Flores Axel Darlyn 

ASIGNATURA: 
Introducción a la Ingeniería de Software 

DOCENTE: 
Guevara Serrano Jorge Dumar 

FECHA DE ENTREGA: 
3 de noviembre del 2025 

PERIODO: 
Agosto - Diciembre 2025 

MILAGRO-ECUADOR

---

Caso 6: Sistema de Pedidos para Cafetería Universitaria  

# 1. Descripción del sistema 

El Sistema de Pedidos para Cafetería Universitaria es una aplicación web diseñada para 
registrar y gestionar pedidos del menú, accesible desde equipos y dispositivos móviles en el 
campus. Opera sobre una arquitectura cliente-servidor con base de datos relacional que 
persiste usuarios, productos y pedidos. Actualmente presenta limitaciones críticas para la 
mantenibilidad: validaciones insuficientes (manejo de datos inválidos), deficiencias en el 
control de concurrencia y problemas de rendimiento bajo carga simultánea. Estas 
condiciones justifican el análisis y la propuesta de acciones de mantenimiento (correctivo, 
preventivo y perfectivo) contenidos en este informe. 

# 2. Análisis del problema 

## Situación 1: Registro incorrecto o fallas al guardar pedidos  

### Descripción del problema: 
 El sistema presenta lentitud o pérdida de información al registrar pedidos cuando múltiples 
usuarios interactúan simultáneamente, debido a la ausencia de control de concurrencia y 
validación de transacciones. Además, permite el ingreso de datos inválidos (por ejemplo, 
texto en campos numéricos o cantidades negativas) por ausencia de validaciones en cliente 
y servidor. Finalmente, ante desconexiones momentáneas no existe un mecanismo de 
reintento o persistencia transaccional, lo que ocasiona pérdida de pedidos y afecta la 
fiabilidad del servicio. 

### Causas técnicas: 
Falta de validaciones en la capa cliente/servidor, mala optimización de 
las consultas a la base de datos, ausencia de mecanismos de recuperación o reintento. 

### Impacto: 
Pedidos duplicados o no guardados, experiencia de usuario negativa, 
desconfianza en el sistema por pérdida de información, pérdida de pedidos o cobros 
erróneos. 

### Área de mejora: 
Validación de datos, control de transacciones, pruebas de carga, 
mecanismos de tolerancia a fallos. 

---

## Situación 2: Edición o cancelación incorrecta de pedidos confirmados  

### Descripción del sistema: 
El sistema permite editar o cancelar pedidos que ya fueron confirmados, generando 
inconsistencias entre el estado lógico del pedido y la información persistida en la base de 
datos. Además, si dos usuarios intentan modificar simultáneamente un mismo pedido, 
pueden producirse conflictos de datos por ausencia de control de concurrencia 
transaccional. 

### Causas técnicas: 
- Lógica de negocio débil sin control de estados  
- Falta de control de concurrencia y auditoría  
- Ausencia de límites temporales para cancelaciones  

### Impacto: 
Pedidos preparados erróneamente o cancelados tarde, pérdida de fiabilidad en el 
sistema, posibles pérdidas económicas y confusión del personal. 

### Área de mejora: 
Control de estados, validaciones, concurrencia y reglas de negocio más 
estrictas. 

---

# 3. Tipos de mantenimiento aplicables y justificación 

## Situación 1: Registro incorrecto o lentitud al guardar pedidos 

### Correctivo:
Se deben corregir errores en validaciones y fallos que causan pérdida de datos. 

### Preventivo:
Implementar pruebas de carga y monitoreo para prevenir fallos futuros. 

### Perfectivo:
Optimizar consultas SQL, mejorar el tiempo de respuesta y aumentar la eficiencia.

### Justificación teórica:
El mantenimiento correctivo consiste en modificar el software para corregir defectos 
detectados durante su uso que afectan su funcionamiento, mientras que el 
mantenimiento perfectivo busca optimizar el rendimiento y la usabilidad del sistema 
sin que exista un fallo crítico. De acuerdo con Sommerville (2011), el mantenimiento 
preventivo busca anticiparse a posibles fallos mediante mejoras que preservan la 
calidad interna y la confiabilidad del sistema. 

En el caso analizado, la pérdida de datos y la lentitud en el registro de pedidos evidencian 
deficiencias estructurales en la gestión de concurrencia y validación de entradas. Por ello 
se justifica aplicar mantenimiento correctivo, perfectivo y preventivo.  

### Justificación técnica  
La aplicación de mantenimiento es viable dentro de la infraestructura existente, mediante:  
- Refactorización de módulos de pedido  
- Transacciones atómicas  
- Índices y caché  
- Pruebas de carga con JMeter  
- Cumplimiento del RNF01  
- Alineación con ISO/IEC 25010  

Estas medidas aseguran integridad de datos, mejor rendimiento y mayor confiabilidad.

---

## Situación 2: Edición o cancelación incorrecta de pedidos confirmados 

### Correctivo: 
Corregir errores que permiten modificar pedidos confirmados. 

### Preventivo: 
Implementar control de estados y concurrencia para evitar inconsistencias futuras. 

### Perfectivo: 
Mejorar la interfaz con advertencias y validación visual del estado del pedido. 

### Justificación teórica: 
Basada en Pressman (errores operativos → mantenimiento correctivo) y Sommerville 
(prevención de inconsistencias → mantenimiento preventivo).  
La mejora de interfaz corresponde al mantenimiento perfectivo según ISO/IEC 25010.  

### Justificación técnica 
Viable gracias a diseño modular del sistema. Se propone:  
- FSM (máquina de estados)  
- UML para documentar ciclos  
- Cancelación solo antes de confirmación  
- Concurrencia optimista  
- Registro de auditoría  

Esto fortalece confiabilidad, mantenibilidad y seguridad.

---

# 4. Cambio funcional propuesto 

## Nombre del cambio funcional 
Implementación de un Módulo de Control de Estados y Concurrencia (FSM) para la gestión 
segura de pedidos. 

## Descripción del cambio 
FSM regula transiciones del ciclo de vida del pedido:  
**En selección → Confirmado → En preparación → Listo para recoger → Entregado**

Una vez Confirmado, no se permite cancelar o editar.

Incluye:  
- Concurrencia optimista  
- Auditoría  
- Mejoras visuales  

## Qué mejora o corrige 
- Falla lógica en validación de estados  
- Manipulación inconsistente de datos  
- Problemas de concurrencia  
- Mejora de usabilidad y transparencia  

## Cómo se implementaría 
1. Diseño técnico: FSM + UML + auditoría  
2. Desarrollo: Integración FSM + concurrencia + refactor SQL  
3. Pruebas: unitarias, regresión, concurrencia, carga (JMeter)  
4. Despliegue con monitoreo  

## Impacto en mantenibilidad y calidad 
- Reduce errores de actualización  
- Disminuye MTTR  
- Aumenta trazabilidad  
- Código modular  
- Interfaz más clara  
- Mayor integridad del sistema  

---

# 5. Reflexión final 

El mantenimiento es una fase crítica que requiere mayor inversión y planificación.  
En este caso, aplicar los tres tipos de mantenimiento optimiza confiabilidad y mantenibilidad.  

La FSM y los controles de concurrencia fortalecen integridad y calidad, alineados con:  
- Sommerville (2011)  
- Pressman (2010)  
- ISO/IEC 25010  

Un mantenimiento proactivo mantiene sistemas competitivos y estables.

---

# 7. Evidencia del Cambio Funcional Propuesto (Diagrama de Estados Modificado) 

Título: Diagrama de Estados UML del ciclo de vida del pedido  

**Regla del negocio:**  
Un pedido puede cancelarse únicamente antes de ser confirmado.  

**Flujo:**  
En selección → Confirmado → En preparación → Listo para recoger → Entregado

---

Situación 1: Registro incorrecto o fallas al guardar pedidos  
Nombre del cambio funcional  
Descripción del cambio  
Qué mejora o corrige  
Cómo se implementaría  
Impacto en la mantenibilidad y la calidad


[![flujo.jpg](https://i.postimg.cc/WbNyDWPB/flujo.jpg)](https://postimg.cc/XXPLmgqL)
