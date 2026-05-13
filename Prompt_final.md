Este es el **Prompt Maestro Definitivo** y el **Plan de Ingeniería de Software** expandido bajo estándares de arquitectura de gran escala (Enterprise-Grade). Este documento está diseñado para ser presentado como la memoria técnica de tu proyecto, asegurando que cualquier profesor identifique inmediatamente un nivel de senioritiy superior.

---

## 🏗️ 1. El Ultra-Prompt: "Antigravity OS - Enterprise Architect"

Este prompt es la configuración de reglas que guiará la creación de cada archivo en Flutter. Úsalo para que el código generado sea impecable.

> **Prompt de Configuración:** "Actúa como un **Lead Solution Architect & Senior Flutter Engineer**. El objetivo es construir **'Antigravity Perfumery System'**, una solución de ecosistema unificado para Android, iOS, Windows y Web.
> **Restricciones de Ingeniería de Software:**
> 1. **Arquitectura:** Implementar **Clean Architecture** estricta dividida en `Core`, `Features`, `Domain`, `Data` y `Presentation`.
> 2. **Paradigma de Datos:** Utilizar el patrón **Repository** con **Data Sources** abstractos. Queda prohibido el uso de `dynamic`. Todo dato proveniente de SQL/Firebase debe ser mapeado a objetos inmutables mediante `Data Transfer Objects (DTOs)`.
> 3. **Precisión Monetaria:** Dado que el sistema maneja 10 entidades transaccionales, se debe integrar la librería `decimal` para todos los campos `precio_compra`, `precio_venta` y `total`. No se aceptarán tipos `double` en lógica financiera.
> 4. **Gestión de Estado Reactiva:** Implementar **Bloc (Business Logic Component)** con eventos y estados transformacionales. Se debe garantizar la persistencia de estado mediante `HydratedBloc` para que la app mantenga la sesión y el carrito incluso tras el cierre.
> 5. **UI/UX Framework:** Diseño basado en **Atomic Design**. Crear una librería de componentes `antigravity_ui` que incluya botones, inputs y cards con micro-animaciones de lujo (shimmers, transiciones Hero y feedback háptico).
> 6. **Multi-Platform Engine:** La UI debe ser **totalmente adaptativa**. En Desktop/Web se debe usar un `Navigation Rail` extendido con atajos de teclado (Hotkeys). En móvil, una interfaz de una sola mano (One-hand UI)."
> 
> 

---

## 📈 2. Plan de Implementación Maestro (Expandido)

Este plan detalla el "cómo" vamos a construir las 10 entidades de tu base de datos de forma profesional.

### Fase I: Fundamentos y Capa de Dominio (Semana 1)

* **Diseño de la Capa de Abstracción:** Creación de las `Entities` puras. Si tu tabla `producto` tiene 12 campos, nuestra entidad tendrá validaciones de dominio (ej. un producto no puede tener precio negativo).
* **Inyección de Dependencias (DI):** Implementar un contenedor de dependencias global (`GetIt` + `Injectable`) que permita intercambiar la base de datos de pruebas por la de producción sin tocar un solo widget.
* **Standardized Failures:** Crear un sistema de manejo de errores profesional (`ServerFailure`, `CacheFailure`, `InsufficientStockFailure`) para que el usuario reciba mensajes claros y no códigos de error extraños.

### Fase II: Infraestructura de Datos y Lógica Relacional (Semana 2)

* **Data Mapping Avanzado:** Implementar lógica para unir las tablas. Por ejemplo, al consultar un `Pedido`, el repositorio devolverá un objeto que contenga la lista de `DetallePedido` y la información del `Cliente` de forma automática.
* **Integridad de Inventario:** Programar el "Interceptor de Stock". Cada vez que se genera un `detalle_pedido`, un proceso asíncrono debe verificar en la tabla `inventario` si el `stock_actual` permite la venta, respetando el `stock_minimo`.
* **Persistencia Híbrida:** Configurar `Hive` (base de datos NoSQL ultra rápida) para caché local en móviles y `SQL/Firestore` para sincronización en la nube.

### Fase III: Presentación Adaptativa y Luxury UI (Semana 3)

* **Responsive Engine:** Creación de un `LayoutManager` que detecte el ancho de pantalla.
* *Móvil:* Pantallas de scroll vertical optimizadas para pulgares.
* *Windows/Mac:* Dashboard con paneles colapsables y tablas de datos avanzadas (DataGrids) con exportación a PDF/Excel.


* **Theming Enterprise:** Definición de un `CustomThemeExtension`. No solo usaremos `primaryColor`, definiremos colores para estados de inventario: `StockDanger`, `StockWarning`, `StockOptimal`.
* **Componentes de Lujo:** Implementación de imágenes con `CachedNetworkImage` y efectos de "vidrio esmerilado" (Glassmorphism) en los menús de navegación.

### Fase IV: Módulos Críticos y Reglas de Negocio (Semana 4)

* **RBAC (Control de Acceso Basado en Roles):** Implementar Guards de navegación. El sistema consultará la tabla `rol` y ocultará automáticamente los botones de "Compras" o "Proveedores" si el usuario logueado es un "Empleado" y no un "Administrador".
* **Módulo de Analítica:** Implementar cálculos de rentabilidad real: `(precio_venta - precio_compra) * cantidad`. Esto se presentará en gráficos de alto impacto en la versión Web/Windows.

---

## 💎 ¿Por qué esta propuesta impresionará al profesor?

1. **Enfoque en Clean Architecture:** La mayoría de los estudiantes mezclan la base de datos con la interfaz. Tú presentarás una estructura donde cada pieza de código tiene un lugar lógico y profesional.
2. **Tratamiento de Datos:** El uso de tipos de datos financieros específicos (`decimal`) demuestra que entiendes los problemas reales del desarrollo de software empresarial.
3. **Adaptabilidad Multiplataforma:** Presentar una app que se ve y se comporta como una app nativa de Windows y, al mismo tiempo, como una app móvil fluida, demuestra un dominio total del SDK de Flutter.
4. **Escalabilidad:** Podrás decirle al profesor: *"Si mañana la perfumería crece a 100 sucursales, el sistema solo requiere cambiar una línea de código en la capa de datos para escalar"*.

**¿Deseas que proceda a entregarte la estructura de carpetas `lib/` completa y el primer módulo de la capa de Dominio (Entities) para las 10 tablas?**
