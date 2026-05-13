## prompt 
Actúa como un Senior Flutter & Firebase Architect con experiencia comprobada en el despliegue de aplicaciones multiplataforma de alto rendimiento en entornos de producción reales.
Tu única tarea en esta respuesta es generar un Plan de Implementación profesional, exhaustivo y estructurado para la aplicación "Perfumería", destinada a la gestión avanzada, catálogo curado y experiencia de compra inmersiva de fragancias.
La aplicación debe ser 100% funcional, escalable y optimizada para Android, iOS, Web y Windows, manteniendo coherencia de marca, rendimiento nativo y cumplimiento de estándares modernos de desarrollo.
📋 INSTRUCCIONES DE FORMATO (OBLIGATORIO):
- Usa EXACTAMENTE la siguiente estructura en Markdown. NO modifiques, renombres, elimines ni añadas títulos de nivel 1 o 2 bajo ninguna circunstancia.
- ⛔ PROHIBIDO utilizar tablas en cualquier parte del documento. Convierte toda información comparativa, matricial o estructural en listas con viñetas, enumeraciones, negritas o bloques de texto plano.
- ⛔ PROHIBIDO generar código funcional de la aplicación en esta etapa. Únicamente se permite incluir el bloque pubspec.yaml y el árbol de directorios lib/ como referencia arquitectónica y de configuración.
- ✅ Adapta cada sección específicamente al dominio de una perfumería: familias olfativas, pirámide de notas, concentraciones, marcas de lujo y nicho, wishlists, comparadores de acordes, filtros premium y experiencia visual inmersiva.
- ✅ Mantén un tono técnico, riguroso y listo para desarrollo en VS Code con Flutter 3.24+ / Dart 3.5+, aplicando Clean Architecture, tipado estricto, null-safety, manejo de errores estructurado y prácticas modernas de CI/CD.
- ✅ Especifica claramente reglas de seguridad de Firestore, estrategias de paginación/caché, optimización de assets, adaptación responsiva por plataforma, validación de accesibilidad (WCAG 2.2) y métricas de rendimiento objetivo.
📐 ESTRUCTURA DE SALIDA REQUERIDA:
# 📋 Plan de Implementación: Aplicación "Perfumería"
> **Nota inicial:** [Contexto de negocio, alcance técnico multiplataforma, justificación del stack Flutter + Firebase + Provider, enfoque de calidad y arquitectura, límites del alcance actual, criterios de éxito para la fase de planificación y premisas técnicas inmutables.]
---
## 🛠 1. Herramientas y Entorno de Desarrollo
[Lista detallada y sin tablas que incluya: versiones exactas de Flutter y Dart, Firebase CLI, SDKs nativos (Xcode, Android SDK/NDK, Visual Studio + MSVC para Windows, Web tooling), extensiones esenciales de VS Code, configuración de emuladores/simuladores por plataforma, herramientas de análisis estático (dart analyze, flutter format, custom_lint), gestión de variables de entorno (flutter_dotenv, --dart-define), flujo Git con convenciones de commits, revisión de PRs y protección de ramas, emuladores locales de Firebase para desarrollo offline seguro, y scripts de automatización para linting y pre-build.]
---
## 🎨 2. Directrices UI/UX
[Guías profundas centradas en perfumería: sistema de diseño premium (paleta neutra cálida, acentos metálicos sutiles, modos claro/oscuro adaptativos con transiciones suaves), tipografía editorial con jerarquía clara, microinteracciones inspiradas en la difusión de aromas, estados de carga con shimmer contextual, manejo de errores visuales elegantes. Responsividad específica por plataforma: navegación gestual y bottom sheets en móvil, hover/focus/keyboard navigation en web, gestión de ventanas y atajos de teclado en desktop. Accesibilidad estricta: contraste ≥4.5:1, etiquetado semántico Semantics, navegación por voz, targets táctiles ≥44x44px. Flujos clave: onboarding sensorial personalizado, catálogo con cuadrículas adaptativas, ficha de fragancia con pirámide olfativa interactiva, filtros avanzados con chips persistentes y checkout simulado.]
---
## 📦 3. Dependencias (`pubspec.yaml`)
[Bloque YAML completo, actualizado y comentado línea por línea. Categorizado en: núcleo Flutter, Firebase (auth, firestore, storage, crashlytics), enrutamiento (GoRouter con navegación declarativa), gestión de estado (Provider/StreamProvider para reactividad granular), utilidades (intl, cached_network_image, shimmer, logging, equatable), UI/theme (google_fonts, flutter_svg, flutter_animate), y dev/testing (mockito, build_runner, flutter_lints). Versiones compatibles con Dart 3.5+ y null-safety estricta. Exclusión explícita de paquetes pesados o en mantenimiento dudoso. Notas sobre configuración de assets, fonts, metadatos multiplataforma y estrategias de tree-shaking.]
---
## 🏗 4. Arquitectura & Gestión de Estado
[Árbol de directorios lib/ completo con enfoque Feature-First + Clean Architecture. Estructura clara de core/ (error handling, constants, theme, routing, utils, di), features/ (auth, catalog, fragrance_detail, wishlist, filters, settings), shared/ (widgets reutilizables, validators, extensions, animations), y main.dart con bootstrap. Explicación detallada del flujo de datos: Data Layer (Firestore repos, mappers, caché local con hive/isar ligero, strategy pattern), Domain Layer (entities inmutables, use cases puras, repository interfaces), Presentation Layer (providers por feature, screens stateless con Consumer/Selector, widgets atómicos). Uso específico de Provider/StreamProvider: justificación técnica, anidamiento óptimo, gestión de ChangeNotifier, FutureProvider, StreamProvider, desacoplamiento de UI y prevención de rebuilds innecesarios. Modelado de Firestore: colecciones (perfumes, brands, categories, notes, users, favorites), índices compuestos, reglas de seguridad, paginación con DocumentSnapshot + limit(), denormalización controlada, y estrategia de sincronización offline. Manejo de errores globales con ErrorWidget personalizado, logging estructurado y placeholders para pruebas unitarias/widget.]
---
## 📅 5. Plan de Implementación en 20 Fases Detalladas
[Genera exactamente 20 fases numeradas, cada una con: objetivo técnico, pasos concretos, entregables verificables, criterios de aceptación y riesgos/mitigaciones. Las fases deben cubrir:]
Fase 1: Inicialización del proyecto, estructura base, configuración de pubspec y validación de entornos multiplataforma.
Fase 2: Integración de Firebase, generación de firebase_options.dart, configuración por plataforma y validación de conexión.
Fase 3: Setup de arquitectura core, inyección vía Provider, capa de errores global y router GoRouter con rutas protegidas/públicas.
Fase 4: Diseño del esquema de Firestore, reglas de seguridad iniciales, índices compuestos y emuladores locales para desarrollo seguro.
Fase 5: Implementación de la capa de datos, repositorios abstractos, mappers DTO/Entity y estrategia de caché local con fallback offline.
Fase 6: Construcción del sistema de tema premium, paleta adaptativa, tipografía, tokens de diseño y componente AppTheme con modo claro/oscuro.
Fase 7: Desarrollo del shell de navegación, Scaffold responsivo, bottom navigation (móvil), sidebar/rail (desktop/web) y gestión de estado global.
Fase 8: Implementación de autenticación Firebase (Google, email/password, anónima), persistencia de sesión y manejo seguro de tokens.
Fase 9: Creación del catálogo principal, grid/list adaptable, paginación infinita con Firestore y estados de carga/vacío/error.
Fase 10: Desarrollo de filtros avanzados por familia olfativa, notas, intensidad, marca, precio y disponibilidad, con chips persistentes.
Fase 11: Búsqueda optimizada con debounce, indexación de texto, sugerencias en tiempo real y fallback a filtros cuando no hay resultados.
Fase 12: Pantalla de detalle de fragancia, pirámide olfativa interactiva, galería de imágenes optimizada, metadatos técnicos y botón de favorito.
Fase 13: Gestión de wishlist con sincronización en tiempo real, resolución de conflictos offline/online y notificaciones visuales de estado.
Fase 14: Comparador de fragancias side-by-side, tabla de atributos convertida a lista de cards y exportación visual de diferencias.
Fase 15: Adaptación web avanzada: meta tags SEO, Open Graph, favicon, manejo de URL routing, scroll behavior y optimización de bundle.
Fase 16: Adaptación desktop Windows: gestión de ventanas, resize listeners, atajos de teclado, tooltips y rendimiento en alta densidad de píxeles.
Fase 17: Optimización de rendimiento: lazy loading de imágenes, RepaintBoundary, const constructors, profiling con DevTools y reducción de rebuilds.
Fase 18: Accesibilidad y QA interno: auditoría WCAG 2.2, navegación por teclado/voz, contraste dinámico, pruebas en 4 plataformas y reporte de bugs.
Fase 19: Preparación de builds: keystore/certificados, firmas multiplataforma, assets finales, flutter build configurado y validación de tamaños.
Fase 20: Pipeline CI/CD básico, automatización de pruebas, generación de changelog, documentación técnica final y checklist de release.
---
## ✅ Próximos Pasos
[Checklist de validación técnica pre-código: revisión de arquitectura, audit de dependencias, verificación de flujo de estado, validación de reglas Firestore, prueba de responsividad en 4 plataformas, benchmark de rendimiento inicial y alineación de criterios de aceptación. Pregunta clara y directa para confirmar inicio de la generación de código modular fase por fase, especificando que se entregará solo un archivo o conjunto lógico por iteración, con instrucciones de integración, validación y rollback antes de avanzar. Incluye recordatorio explícito de que no se generará código hasta recibir "APROBADO".]
- No uses lenguaje coloquial, marketing o especulaciones fuera del alcance técnico.
- Mantén la consistencia en la nomenclatura de directorios, clases y servicios a lo largo de todo el documento.
- Especifica cómo se manejarán las imágenes de alta resolución de frascos y notas olfativas sin afectar el rendimiento.
- Detalla la estrategia de fallback cuando la red esté inestable o Firebase falle temporalmente.
- Define claramente los límites entre la capa de presentación, dominio y datos en cada feature.
- Incluye métricas cuantitables de rendimiento esperadas (ej: <16ms por frame, carga inicial <2s en 4G, <500KB impacto por feature).
- Asegura que cada fase incluya al menos un criterio de aceptación verificable mediante pruebas o inspección de código.
- Prohíbe explícitamente el uso de setState() para lógica de negocio global; solo se permite en widgets aislados con estado puramente local.
- Especifica cómo se gestionarán los deep links para compartir fragancias directamente a la web o app.
- Detalla la configuración de analytics básicos para trackear conversiones y comportamiento de usuarios sin violar privacidad.
- Incluye un protocolo de rollback claro si una fase introduce breaking changes o degradación de rendimiento.
- Mantén el enfoque en la escalabilidad futura: preparación para integración de pagos reales, notificaciones push y multi-idioma.
- Asegura que el árbol de directorios refleje estrictamente la separación de responsabilidades y evite acoplamiento circular.
- Define cómo se validará la compatibilidad con versiones anteriores de Firebase y Flutter en el pipeline.
- Establece un estándar de documentación interna: comentarios DartDoc en funciones críticas y README por feature.
- Prohíbe el hardcoding de strings, colores o rutas; todo debe provenir de constantes centralizadas o temas.
- Especifica el manejo de caché de imágenes con invalidación inteligente y purga automática por tamaño.
- Detalla cómo se probará la accesibilidad en cada plataforma usando herramientas nativas y paquetes de Flutter.
- Asegura que la arquitectura permita la inyección de mocks para pruebas unitarias sin modificar la lógica de negocio.
Finaliza con una declaración explícita de que el plan es inmutable hasta recibir tu aprobación formal.
Entrega SOLO este plan. Respeta estrictamente la estructura, el dominio de perfumería, la prohibición de tablas y código funcional, y el enfoque técnico Flutter 3.24+ / Dart 3.5+ / VS Code. Espera mi respuesta con "APROBADO" para comenzar a generar el código modular, fase por fase, sin saltos, sin suposiciones y con validación explícita en cada iteración.









# 📋 Plan de Implementación: Aplicación "Perfumería"
> **Nota inicial:** Este documento establece la arquitectura técnica, las directrices de diseño, el stack tecnológico y la hoja de ruta completa para el desarrollo de "Perfumería", una aplicación multiplataforma orientada a la gestión comercial interna, la curación de un catálogo de fragancias premium y la experiencia de compra inmersiva. El stack seleccionado (Flutter 3.24+ / Dart 3.5+ con Firebase, Provider y GoRouter) garantiza rendimiento nativo, sincronización en tiempo real, escalabilidad horizontal y mantenimiento limpio a largo plazo. El alcance actual se limita a la funcionalidad core: autenticación, catálogo interactivo, gestión de inventario básica, wishlist, comparador de notas y flujo de pedido simulado. Quedan fuera de esta versión la integración de pasarelas de pago reales, notificaciones push nativas y multi-idioma completo (preparados como hooks de extensión). Los criterios de éxito se basan en estabilidad del 99.5%, cumplimiento de WCAG 2.2 AA, métricas de rendimiento estrictas y separación arquitectónica verificable. Las premisas técnicas son inmutables: Clean Architecture, tipado estricto, null-safety, gestión de estado reactiva sin acoplamiento, y generación de código controlada fase por fase con validación explícita antes de cada entrega.

---

## 🛠 1. Herramientas y Entorno de Desarrollo
- Flutter SDK versión 3.24.0 o superior (canal stable).
- Dart SDK versión 3.5.0 o superior, con null-safety estricto habilitado por defecto.
- Firebase CLI versión 13.x para gestión de proyecto, emuladores locales y despliegue de reglas.
- SDKs nativos requeridos: Xcode 15+ para iOS/macOS, Android SDK 34 con NDK 26 para Android, Visual Studio 2022 con carga de trabajo "Desarrollo de escritorio con C++" y MSVC 143 para Windows desktop, y Chrome/Edge actualizados para Web tooling.
- Entorno de desarrollo principal: VS Code con extensiones oficiales `Flutter`, `Dart`, `Firebase`, `Error Lens`, `GitLens`, `Pretty Errors` y `Dart Snippets`.
- Emuladores y simuladores configurados: Android Emulator (API 34), iOS Simulator (iPhone 15 Pro / iOS 17), Chrome (modo responsive y device emulation), Windows Desktop (1080p/1440p con escala 100-150%).
- Herramientas de análisis estático y calidad: `dart analyze`, `flutter format`, `custom_lint` para reglas de negocio personalizadas, y `flutter pub deps` para auditoría de dependencias.
- Gestión de configuración y secretos: paquete `flutter_dotenv` para desarrollo local y flags `--dart-define` para inyección segura de variables en CI/CD y builds de release.
- Flujo de control de versiones: Git con modelo `GitFlow` simplificado, convenciones de commits `Conventional Commits`, protección de rama `main` con revisión obligatoria de PR, y validación automática de linting en pre-commit via `husky` o `pre-commit` framework.
- Entorno de desarrollo local seguro: emuladores locales de Firebase (Auth, Firestore, Storage) ejecutados con `firebase emulators:start` para pruebas offline, aislamiento de datos de prueba y validación de reglas sin consumo de cuota en producción.
- Scripts de automatización integrados en `package.json` o `Makefile`: comandos para `flutter analyze --fatal-infos`, `flutter format .`, ejecución de emuladores, y generación de assets antes de cada build.

---

## 🎨 2. Directrices UI/UX
- Sistema de diseño premium centrado en la experiencia sensorial: paleta base neutra cálida (blancos hueso, grises perla, negros suaves) con acentos metálicos sutiles (dorado mate, cobre satinado) para estados interactivos y jerarquía visual.
- Modo claro y oscuro adaptativos con transiciones suaves de 300ms, respetando la configuración del sistema operativo y permitiendo override manual por usuario.
- Tipografía editorial con jerarquía estricta: serif de alto contraste (ej. Playfair Display o Cormorant) para títulos y familias olfativas, sans-serif geométrica (ej. Inter o SF Pro) para cuerpo, precios y metadatos técnicos. Escalas tipográficas fluidas basadas en `MediaQuery.textScaleFactor`.
- Microinteracciones inspiradas en la difusión aromática: fade-in progresivo, escala sutil al hover/tap, desenfoque de fondo en modales y animaciones de transición que evocan ligereza sin comprometer el rendimiento (<60ms por animación).
- Estados de carga y error visuales: shimmer contextual adaptado al layout destino (cards, grids, listas), skeletons estructurales que mantienen la relación de aspecto, y mensajes de error con acciones de reintento claras y accesibles.
- Responsividad multiplataforma específica: navegación gestual y bottom sheets en móvil con safe areas dinámicas, sidebar/rail fijo con hover states y focus rings visibles en web/desktop, gestión de ventanas redimensionables con breakpoints adaptativos (360px, 768px, 1024px, 1440px).
- Accesibilidad estricta alineada con WCAG 2.2 AA: contraste mínimo 4.5:1 para texto normal y 3:1 para grande, etiquetado semántico con widgets `Semantics` para lectores de pantalla, navegación completa por teclado (Tab, Shift+Tab, Enter, Escape) y por voz, targets táctiles y de cursor de al menos 44x44 píxeles independientes, y soporte para escalado de fuente hasta 200% sin truncamiento.
- Flujos clave de usuario: onboarding sensorial personalizado por preferencias olfativas, catálogo con cuadrículas adaptativas y scroll infinito optimizado, ficha de fragancia con pirámide olfativa interactiva (notas de salida, corazón y fondo), filtros avanzados con chips persistentes y estado conservado entre sesiones, y checkout simulado con resumen de pedido y validación de inventario en tiempo real.

---

## 📦 3. Dependencias (`pubspec.yaml`)
```yaml
name: perfumeria_app
description: Aplicación multiplataforma de catálogo y gestión de perfumería premium.
version: 1.0.0+1
publish_to: 'none'

environment:
  sdk: '>=3.5.0 <4.0.0'
  flutter: '>=3.24.0'

dependencies:
  flutter:
    sdk: flutter

  # Núcleo Firebase
  firebase_core: ^3.6.0
  firebase_auth: ^5.3.0
  cloud_firestore: ^5.4.0
  firebase_storage: ^12.3.0
  firebase_crashlytics: ^4.1.0

  # Enrutamiento declarativo
  go_router: ^14.2.0

  # Gestión de estado reactivo
  provider: ^6.1.2

  # Utilidades y UI
  intl: ^0.19.0
  cached_network_image: ^3.4.0
  flutter_svg: ^2.0.10
  shimmer: ^3.0.0
  flutter_animate: ^4.5.0
  google_fonts: ^6.2.0
  equatable: ^2.0.5
  uuid: ^4.4.0

  # Persistencia local ligera (offline fallback)
  isar: ^3.1.0+1
  isar_flutter_libs: ^3.1.0+1

  # Logging y métricas
  logger: ^2.4.0

  # Configuración de entorno
  flutter_dotenv: ^5.1.0

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^5.0.0
  build_runner: ^2.4.12
  mockito: ^5.4.4
  isar_generator: ^3.1.0+1
  custom_lint: ^0.6.8

flutter:
  uses-material-design: true
  assets:
    - assets/images/
    - assets/icons/
    - assets/fonts/
    - .env
  fonts:
    - family: PlayfairDisplay
      fonts:
        - asset: assets/fonts/PlayfairDisplay-Regular.ttf
        - asset: assets/fonts/PlayfairDisplay-Bold.ttf
          weight: 700
    - family: Inter
      fonts:
        - asset: assets/fonts/Inter-Regular.ttf
        - asset: assets/fonts/Inter-Medium.ttf
          weight: 500
```
- Notas de configuración: Se prioriza tree-shaking automático de Dart para eliminar código inalcanzado. Las fuentes se cargan localmente para evitar dependencias de red en inicio. Los assets se organizan por densidad y formato WebP para optimizar bundle size. Se excluyen paquetes de gestión de estado alternativos para mantener consistencia con Provider y evitar conflictos de ciclo de vida.

---

## 🏗 4. Arquitectura & Gestión de Estado
Árbol de directorios `lib/` (Feature-First + Clean Architecture):
```
lib/
├── core/
│   ├── errors/                 # Excepciones tipadas, Failures, Either pattern
│   ├── constants/              # Strings, rutas, colores, breakpoints, claves de analítica
│   ├── theme/                  # AppTheme, tokens, modo claro/oscuro, tipografía
│   ├── router/                 # Configuración GoRouter, guards, deep links
│   ├── utils/                  # Validadores, formatters, debouncer, logger
│   └── di/                     # Inicialización de servicios, inyección manual vía Provider
├── features/
│   ├── auth/
│   │   ├── data/               # Repos, mappers, DTOs
│   │   ├── domain/             # Entidades, use cases, interfaces
│   │   └── presentation/       # Provider, screens, widgets locales
│   ├── catalog/
│   ├── fragrance_detail/
│   ├── wishlist/
│   ├── filters/
│   ├── inventory_admin/        # Roles, empleados, compras, proveedores, stock
│   └── settings/
├── shared/
│   ├── widgets/                # Atomic components (buttons, cards, inputs, modals)
│   ├── validators/             # Reglas de negocio transversales
│   ├── extensions/             # Helpers para DateTime, String, List, BuildContext
│   └── animations/             # Curvas, transiciones, microinteracciones
└── main.dart
```
Flujo de datos estratificado:
- Capa de datos: Repositorios concretos que interactúan con `cloud_firestore` y `isar` para caché offline. Implementan mappers explícitos de DTO a Entity, strategy pattern para fallback de red, y validación de respuestas. La paginación se resuelve con `limit()` y `startAfterDocument()`, almacenando el último `DocumentSnapshot` para scroll infinito eficiente.
- Capa de dominio: Entidades inmutables (`Equatable` o records de Dart 3.5+), casos de uso puros sin dependencias de Flutter, e interfaces de repositorio que permiten inyección de mocks para pruebas unitarias. Los límites entre capas se respetan mediante imports direccionales (presentación nunca importa data, solo domain).
- Capa de presentación: Providers por feature que exponen `ChangeNotifier` o `ValueNotifier`. Las pantallas son `StatelessWidget` que consumen estado mediante `Selector` o `Consumer` con listeners granulares para evitar rebuilds innecesarios. Prohibido explícito de `setState()` para lógica de negocio global; solo permitido en componentes aislados con estado puramente visual (ej. toggle de animación local).
Modelado de Firestore (integración conceptual de módulos):
- Colecciones `roles` y `employees` gestionan control de permisos (Admin, Vendedor) y perfiles vinculados.
- `products` almacena concentración, volumen, género, pirámide olfativa, precios y estado. `categories` clasifica por tipo técnico (EDP, EDT, EDC) y `brands` registra casas de diseño y país de origen.
- `inventory` mantiene stock_actual y stock_minimo con triggers de alertas visuales. `suppliers` es el directorio de distribuidores. `purchases` y `purchase_details` registran órdenes de reposición cabecera e ítems recibidos.
- `customers` alimenta CRM básico, `orders` captura cabecera de venta (total, fecha, estado), y `order_details` desglosa productos vendidos por transacción.
Estrategia de índices y seguridad:
- Índices compuestos explícitos para búsquedas frecuentes: categoría + precio, marca + stock, familia olfativa + rating. Reglas de seguridad basadas en `request.auth != null` para operaciones de lectura y escritura, con validación de tipo y longitud de campos. Los datos administrativos (`inventory`, `purchases`, `roles`) requieren verificación de claims personalizados o documento de rol asociado al UID.
Gestión de fallos y rendimiento:
- Fallback offline: Isar almacena catálogo y wishlist localmente. Al reconectar, se ejecuta sincronización bidireccional con resolución de conflictos por timestamp.
- Imágenes de alta resolución: Se sirven desde Firebase Storage con transformaciones CDN, se cachean con `cached_network_image` usando `CacheManager` con invalidación inteligente por tamaño y TTL, y se renderizan con `FadeInImage` o placeholders vectoriales para evitar jank.
- Métricas objetivo: <16ms por frame en interacción, carga inicial <2s en red 4G, impacto por feature <500KB comprimido, rebuilds reducidos >70% mediante `Selector` y `const`.
- Analytics y privacidad: Eventos básicos trackeados con `logEvent` de Firebase (view_catalog, add_to_wishlist, start_checkout, filter_applied) sin PII, con consentimiento explícito y retención configurada.
- Deep links: Configuración de `go_router` con esquema `perfumeria://product/:id` y rutas web compatibles `/producto/:id` para compartir fragancias directamente.
- Documentación y pruebas: DartDoc obligatorio en funciones críticas y use cases. README por feature con diagramas de flujo y decisiones técnicas. Inyección de mocks vía constructores de providers para pruebas unitarias y widget sin tocar lógica de negocio.
- Protocolo de rollback: Cada fase incluye tag git `v1.x-phaseY`. Si se detecta degradación de rendimiento o breaking change, se revierte a la versión estable anterior, se documenta el fallo y se reestructura la implementación antes de continuar.

---

## 📅 5. Plan de Implementación en 20 Fases Detalladas

**Fase 1: Inicialización del proyecto, estructura base, configuración de pubspec y validación de entornos multiplataforma.**
- Objetivo: Establecer la base técnica limpia y verificable en las 4 plataformas.
- Pasos: Crear proyecto con flags de plataforma, aplicar estructura de directorios definida, configurar `pubspec.yaml` inicial, ejecutar `flutter pub get`, validar compilación vacía en Android, iOS, Web y Windows.
- Entregables: Repositorio inicializado, estructura de carpetas, `pubspec.yaml` base, logs de build exitosos por plataforma.
- Criterios de aceptación: `flutter run` sin errores en al menos 3 dispositivos/simuladores simultáneos, `flutter analyze` con 0 warnings.
- Riesgos/Mitigaciones: Conflictos de SDKs nativos; mitigar con actualización de toolchains y limpieza de caché (`flutter clean`).

**Fase 2: Integración de Firebase, generación de firebase_options.dart, configuración por plataforma y validación de conexión.**
- Objetivo: Vincular el proyecto con backend seguro y listo para desarrollo local.
- Pasos: Crear proyecto en Firebase Console, registrar apps por plataforma, ejecutar `flutterfire configure`, generar `firebase_options.dart`, verificar handshake de `FirebaseCore`.
- Entregables: Archivos de configuración nativos, `firebase_options.dart` tipado, logs de inicialización exitosa.
- Criterios de aceptación: App inicia sin crash de Firebase, `Firebase.apps` contiene al menos una instancia válida.
- Riesgos/Mitigaciones: Hash SHA-1 incorrecto en Android; mitigar con generación automática vía `keytool` y verificación en console.

**Fase 3: Setup de arquitectura core, inyección vía Provider, capa de errores global y router GoRouter con rutas protegidas/públicas.**
- Objetivo: Establecer infraestructura de navegación y gestión de fallos transversales.
- Pasos: Implementar `AppTheme`, configurar `MultiProvider` en `main.dart`, crear `ErrorWidget` global, definir rutas base y guards en `GoRouter`, separar rutas públicas (login) y privadas (home).
- Entregables: Router funcional, inyección de providers base, manejo de errores no capturados.
- Criterios de aceptación: Redirección automática a login si no hay sesión, navegación sin pérdida de estado, error boundary activo.
- Riesgos/Mitigaciones: Rebuilds masivos al montar providers; mitigar con `ProviderScope` granular y `listen: false` donde corresponda.

**Fase 4: Diseño del esquema de Firestore, reglas de seguridad iniciales, índices compuestos y emuladores locales para desarrollo seguro.**
- Objetivo: Preparar backend para desarrollo iterativo con datos aislados.
- Pasos: Definir estructuras de colecciones según módulos de negocio, escribir `firestore.rules` con validación de tipos y acceso por rol, crear índices compuestos en console, configurar `firebase emulators:start`.
- Entregables: Reglas de seguridad versiónadas, índices declarados, emuladores corriendo con seed data.
- Criterios de aceptación: Escritura no autorizada denegada, lecturas autenticadas permitidas, queries paginadas ejecutadas sin warning de índice.
- Riesgos/Mitigaciones: Reglas demasiado permisivas en staging; mitigar con auditoría automática de `rules` y pruebas de negación en emulador.

**Fase 5: Implementación de la capa de datos, repositorios abstractos, mappers DTO/Entity y estrategia de caché local con fallback offline.**
- Objetivo: Aislar lógica de acceso a datos y garantizar resiliencia.
- Pasos: Crear interfaces de repositorio, implementar concretos para Firestore, diseñar mappers explícitos, integrar Isar para caché local, definir estrategia de sincronización (pull on connect, conflict resolution por timestamp).
- Entregables: Repositorios tipados, mappers unit-tested, caché local funcional.
- Criterios de aceptación: Datos se persisten offline, se restauran al reconectar, mappers no pierden tipos ni valores nulos inesperados.
- Riesgos/Mitigaciones: Desincronización de timestamps; mitigar con uso de `FieldValue.serverTimestamp()` y validación de consistencia en domain layer.

**Fase 6: Construcción del sistema de tema premium, paleta adaptativa, tipografía, tokens de diseño y componente AppTheme con modo claro/oscuro.**
- Objetivo: Unificar identidad visual y garantizar accesibilidad desde el núcleo.
- Pasos: Definir tokens de color/spacing/typography en `core/constants`, crear `ThemeData` extendido, implementar switch de tema con persistencia local, validar contraste con herramienta automática.
- Entregables: Tema funcional, transiciones suaves, persistencia de preferencia.
- Criterios de aceptación: Modo oscuro/claro intercambia sin rebuilds globales, contraste ≥4.5:1 verificado, fuentes cargadas localmente.
- Riesgos/Mitigaciones: Assets oscuros no adaptables; mitigar con variantes SVG/temáticas y fallback programático.

**Fase 7: Desarrollo del shell de navegación, Scaffold responsivo, bottom navigation (móvil), sidebar/rail (desktop/web) y gestión de estado global.**
- Objetivo: Estructura visual principal adaptable a cada plataforma.
- Pasos: Crear `AppShell` con `LayoutBuilder`, condicionar navegación por breakpoint, integrar `GoRouter` state, conectar con `UIProvider`.
- Entregables: Navegación funcional en 4 plataformas, estado global sincronizado.
- Criterios de aceptación: Bottom nav en móvil, sidebar en desktop/web, back button manejado correctamente, sin memory leaks al cambiar plataforma.
- Riesgos/Mitigaciones: Overlap de elementos en resize; mitigar con `SafeArea` y listeners de `MediaQuery.size`.

**Fase 8: Implementación de autenticación Firebase (email/password, persistente), manejo seguro de tokens y flujos de recuperación.**
- Objetivo: Acceso seguro y estable a cuentas de usuario.
- Pasos: Implementar `AuthService` con signIn/signUp/signOut/reset, crear `AuthProvider`, manejar `FirebaseAuthException` tipadas, validar sesiones persistentes.
- Entregables: Flujos de auth completos, validaciones en tiempo real, manejo de errores claros.
- Criterios de aceptación: Login exitoso redirige a home, error de credenciales muestra feedback, sesión persiste tras reinicio.
- Riesgos/Mitigaciones: Rate limiting de Firebase; mitigar con debounce en botones y mensajes de espera explícitos.

**Fase 9: Construcción del catálogo principal, grid/list adaptable, paginación infinita con Firestore y estados de carga/vacío/error.**
- Objetivo: Visualización eficiente y escalable del inventario público.
- Pasos: Implementar `CatalogProvider` con stream paginado, diseñar `ProductCard` optimizado, integrar `Shimmer` y `EmptyState`, manejar scroll infinito con `DocumentSnapshot`.
- Entregables: Listado fluido, estados visuales claros, paginación funcional.
- Criterios de aceptación: Carga inicial <2s, scroll sin jank, transición de estados suave, límite de items configurado.
- Riesgos/Mitigaciones: Rebuilds al actualizar lista; mitigar con `SliverList` y `ListView.builder` con `key` estables.

**Fase 10: Desarrollo de filtros avanzados por familia olfativa, notas, intensidad, marca, precio y disponibilidad, con chips persistentes.**
- Objetivo: Refinar búsqueda con parámetros de dominio específicos.
- Pasos: Crear `FilterProvider` con estado de chips, implementar lógica de filtrado en repositorio, persistir selección en `SharedPreferences`, conectar UI con `Selector`.
- Entregables: Chips interactivos, filtrado en tiempo real, estado conservado.
- Criterios de aceptación: Filtros combinables, respuesta <300ms, estado no se pierde al navegar.
- Riesgos/Mitigaciones: Queries complejas saturan Firestore; mitigar con índices optimizados y filtrado local post-fetch para conjuntos pequeños.

**Fase 11: Búsqueda optimizada con debounce, indexación de texto, sugerencias en tiempo real y fallback a filtros cuando no hay resultados.**
- Objetivo: Encontrar fragancias rápidamente con experiencia fluida.
- Pasos: Implementar `DebounceTextController`, conectar con stream de búsqueda parcial, diseñar sugerencias dropdown, configurar fallback a filtros activos.
- Entregables: Barra de búsqueda reactiva, sugerencias, fallback visual.
- Criterios de aceptación: Debounce 400ms, sin queries redundantes, resultados precisos, fallback claro.
- Riesgos/Mitigaciones: Búsqueda no nativa en Firestore; mitigar con indexación de campos clave y filtrado en client con cache.

**Fase 12: Pantalla de detalle de fragancia, pirámide olfativa interactiva, galería de imágenes optimizada, metadatos técnicos y botón de favorito.**
- Objetivo: Inmersión completa en la ficha de producto.
- Pasos: Diseñar layout responsivo, implementar pirámide con acordeón animado, integrar galería con `PageView` + cache, conectar botón de favorito a `WishlistProvider`.
- Entregables: Detalle completo, galería fluida, favorito funcional.
- Criterios de aceptación: Imágenes cargan progresivamente, pirámide colapsable, favorito sincroniza con backend.
- Riesgos/Mitigaciones: Alto consumo de memoria en galería; mitigar con `ImageCache` limitado y preload controlado.

**Fase 13: Gestión de wishlist con sincronización en tiempo real, resolución de conflictos offline/online y notificaciones visuales de estado.**
- Objetivo: Permitir guardar y gestionar preferencias sin pérdida de datos.
- Pasos: Implementar colección `favorites/{uid}/{productId}`, sincronizar cambios con `StreamProvider`, manejar conflictos con `lastWriteWins`, mostrar toasts de confirmación.
- Entregables: Wishlist persistente, sync en tiempo real, feedback claro.
- Criterios de aceptación: Agregar/eliminar refleja instantáneamente, funciona offline con cola de sync, sin duplicados.
- Riesgos/Mitigaciones: Conflictos de escritura simultánea; mitigar con transacciones Firestore y validación de documento existente.

**Fase 14: Comparador de fragancias side-by-side, tabla de atributos convertida a lista de cards y exportación visual de diferencias.**
- Objetivo: Facilitar decisión de compra mediante comparación técnica.
- Pasos: Crear `CompareProvider`, seleccionar hasta 4 productos, diseñar vista comparativa con cards alineadas, resaltar diferencias de notas y precio.
- Entregables: Comparador funcional, resaltado visual, estado seleccionable.
- Criterios de aceptación: Máximo 4 items, scroll sincronizado, diferencias marcadas claramente, responsive.
- Riesgos/Mitigaciones: Layout complejo en móvil; mitigar con scroll horizontal + swipe y colapso de atributos secundarios.

**Fase 15: Adaptación web avanzada: meta tags SEO, Open Graph, favicon, manejo de URL routing, scroll behavior y optimización de bundle.**
- Objetivo: Garantizar descubribilidad y rendimiento en navegadores.
- Pasos: Configurar `index.html` con meta tags, ajustar `go_router` para URLs limpias, optimizar renderizador CanvasKit, reducir bundle size con tree-shaking.
- Entregables: Web pública indexable, URLs amigables, bundle <2MB inicial.
- Criterios de aceptación: Lighthouse score >85, deep links funcionales, scroll nativo suave.
- Riesgos/Mitigaciones: Overhead de CanvasKit; mitigar con lazy loading de módulos y preconnect a CDN.

**Fase 16: Adaptación desktop Windows: gestión de ventanas, resize listeners, atajos de teclado, tooltips y rendimiento en alta densidad de píxeles.**
- Objetivo: Experiencia nativa en entorno de escritorio.
- Pasos: Configurar tamaño mínimo de ventana, añadir listeners de resize, mapear atajos (Ctrl+F, Ctrl+W, Alt+1-4), habilitar tooltips accesibles.
- Entregables: Ventana responsive, atajos funcionales, rendimiento estable en 4K.
- Criterios de aceptación: UI no se superpone en resize, atajos ejecutan acciones, renderizado <16ms en alta densidad.
- Riesgos/Mitigaciones: DPI scaling inconsistente; mitigar con `MediaQuery.devicePixelRatio` y assets vectoriales.

**Fase 17: Optimización de rendimiento: lazy loading de imágenes, RepaintBoundary, const constructors, profiling con DevTools y reducción de rebuilds.**
- Objetivo: Alcanzar métricas de fluidez y eficiencia.
- Pasos: Aplicar `RepaintBoundary` a widgets pesados, forzar `const` donde sea posible, ejecutar `flutter run --profile`, identificar rebuilds con DevTools, refactorizar providers con `Selector`.
- Entregables: Perfil de rendimiento optimizado, rebuilds documentados y reducidos.
- Criterios de aceptación: <16ms/frame consistente, memoria estable tras 10 min de uso, 0 jank en scroll.
- Risks/Mitigaciones: Over-optimización prematura; mitigar con benchmarking antes/después y enfoque en cuellos de botella reales.

**Fase 18: Accesibilidad y QA interno: auditoría WCAG 2.2, navegación por teclado/voz, contraste dinámico, pruebas en 4 plataformas y reporte de bugs.**
- Objetivo: Cumplimiento normativo y calidad transversal.
- Pasos: Ejecutar auditoría con `AccessibilityScanner` y `flutter analyze`, probar con TalkBack/VoiceOver/Narrator, validar contraste dinámico, registrar y priorizar bugs.
- Entregables: Reporte de accesibilidad, bugs priorizados y corregidos.
- Criterios de aceptación: 100% de flujos críticos navegables por teclado/voz, 0 violaciones WCAG críticas, pruebas pasadas en 4 plataformas.
- Riesgos/Mitigaciones: Widgets personalizados sin semántica; mitigar con envoltura `Semantics` y pruebas automatizadas de accesibilidad.

**Fase 19: Preparación de builds: keystore/certificados, firmas multiplataforma, assets finales, flutter build configurado y validación de tamaños.**
- Objetivo: Generar binarios listos para distribución.
- Pasos: Generar keystore Android, provisioning iOS, certificados Windows, configurar `build.yaml`, ejecutar `flutter build` por plataforma, validar tamaños y estructura.
- Entregables: APK, IPA, EXE, Web folder firmados, reportes de tamaño.
- Criterios de aceptación: Builds exitosos sin warnings críticos, tamaño web <3MB, firmas válidas.
- Riesgos/Mitigaciones: Fallos de firma en iOS; mitigar con verificación de provisioning profile y team ID actualizado.

**Fase 20: Pipeline CI/CD básico, automatización de pruebas, generación de changelog, documentación técnica final y checklist de release.**
- Objetivo: Automatizar entrega y garantizar trazabilidad.
- Pasos: Configurar GitHub Actions para lint/test/build, generar changelog automático con `conventional-changelog`, escribir docs técnicas por feature, ejecutar checklist final de QA.
- Entregables: Pipeline activo, changelog, documentación completa, checklist firmado.
- Criterios de aceptación: CI pasa en cada push, documentación accesible, checklist 100% cumplido.
- Riesgos/Mitigaciones: Flaky tests en CI; mitigar con emuladores headless estables y retries configurados.

---

## ✅ Próximos Pasos
- Revisión exhaustiva de la arquitectura propuesta y validación de límites entre capas (presentación, dominio, datos).
- Auditoría de dependencias en `pubspec.yaml` para confirmar compatibilidad con Dart 3.5+ y ausencia de conflictos transitivos.
- Verificación del flujo de estado con Provider: granularidad de `Consumer`/`Selector`, prevención de rebuilds globales, y desacoplamiento estricto de lógica de negocio.
- Validación de reglas de seguridad de Firestore y estrategia de paginación/caché contra escenarios de alta concurrencia y red inestable.
- Prueba de responsividad y accesibilidad en las 4 plataformas objetivo usando emuladores y herramientas nativas de auditoría.
- Benchmark inicial de rendimiento para confirmar que se mantienen las métricas objetivo (<16ms/frame, carga <2s, impacto por feature controlado).
- Alineación final de criterios de aceptación por fase y confirmación de que no se utilizará `setState()` para lógica global, que todo string/color/ruta provendrá de constantes centralizadas, y que se mantendrá la estrategia de caché de imágenes con invalidación por TTL y tamaño.
- Definición explícita del protocolo de rollback: si una fase introduce degradación medible o breaking change, se revertirá al tag estable anterior, se documentará el fallo, y se reestructurará la implementación antes de avanzar.
- Pregunta directa para iniciar generación de código: ¿Confirma que desea comenzar con la Fase 1? Se entregará exclusivamente el conjunto de archivos de configuración y estructura base, con instrucciones precisas de integración, validación en VS Code, y criterio de aprobación antes de continuar. No se generará código adicional ni se avanzará a la Fase 2 sin recibir su confirmación explícita "APROBADO".

Este plan es inmutable en su estructura, alcance técnico y directrices arquitectónicas hasta recibir su aprobación formal. Una vez emitida, el desarrollo procederá fase por fase, con validación explícita, entregables verificables y cero suposiciones implícitas.
