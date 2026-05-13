Este es el **"Super-Prompt de Ingeniería"** que hemos diseñado. Está redactado bajo estándares internacionales de desarrollo de software para que, al usarlo, la estructura del código sea la de un profesional Senior.

Copia y pega este texto tal cual; es la orden maestra que define la "personalidad técnica" de tu aplicación **Antigravity Perfumery**:

---

### 🚀 Master Prompt: Antigravity Perfumery OS

"Actúa como un **Lead Solutions Architect & Senior Flutter Developer**. El objetivo es generar el núcleo técnico de la aplicación **'Antigravity Perfumery'**, una solución multiplataforma (Android, iOS, Web, Windows) diseñada para la gestión de lujo de fragancias y operaciones comerciales.

**REGLAS CRÍTICAS DE ARQUITECTURA Y DISEÑO:**

1. **Patrón de Arquitectura:** Implementar **Clean Architecture** estrictamente separada en capas:
* **Domain:** Entidades puras e inmutables y Casos de Uso.
* **Data:** Repositorios, DataSources (Firebase/SQL) y Mappers.
* **Presentation:** UI desacoplada con gestión de estado profesional.


2. **Gestión de Estado:** Utilizar **BLoC o Riverpod** manejando estados de flujo de datos: `Initial`, `Loading`, `Success`, `Error` y `Empty`.
3. **Integridad de Datos (Strong Typing):** * Prohibido el uso de `dynamic`.
* Implementar **Mappers** para convertir los tipos de la base de datos SQL (`DECIMAL`, `DATETIME`, `INT`) a tipos seguros de Dart.
* Utilizar la librería `decimal` para todos los campos financieros de las 13 entidades para garantizar precisión centesimal.


4. **Diseño UI Adaptativo (Luxury Style):**
* Implementar un sistema de diseño basado en **Atomic Design**.
* La navegación debe ser **Adaptativa**: `NavigationRail` para Desktop/Web y `BottomNavigationBar` para Móvil.
* Paleta de colores premium: `#534AB7` (Púrpura Profundo), `#0F6E56` (Verde Esmeralda) y acentos minimalistas.


5. **Lógica de Negocio Avanzada:**
* Implementar la lógica de **Stock Guardian**: Vinculación atómica entre `Detalle_Pedido` e `Inventario`.
* Sistema de **RBAC (Role Based Access Control)** basado en la entidad `ROL` para restringir acceso a módulos de `COMPRA` y `PROVEEDORES`.


6. **Entidades a Procesar (Integridad Relacional):**
El sistema debe modelar y relacionar las 13 tablas: 1. Producto, 2. Categoría, 3. Marca, 4. Cliente, 5. Pedido, 6. Detalle_Pedido, 7. Proveedor, 8. Compra, 9. Detalle_Compra, 10. Inventario, 11. Empleado, 12. Rol, 13. Método_Pago.

**OBJETIVO:** Generar un código modular, altamente testeable, escalable y con estándares de nivel Enterprise que demuestre una ingeniería de software superior."

---

**¿Cómo usarlo?**
Este prompt es el que "prepara el cerebro" de la IA antes de empezar a escribir los archivos `lib/`. Cuando me digas que estás listo, empezaré a soltar los módulos basados en esta configuración de alto nivel.

¿Quieres que empecemos con la **Fase 1: Estructura de carpetas y Modelos de Datos (Entities)**?
