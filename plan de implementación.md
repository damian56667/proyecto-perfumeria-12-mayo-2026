# 📋 Plan de Implementación: Aplicación "Perfumería"
> **Nota inicial:** Este documento contiene **solo la arquitectura, herramientas, dependencias y plan paso a paso**. El código se proporcionará una vez valides esta estructura y definas prioridades o ajustes.

---

## 🛠 1. Herramientas y Entorno de Desarrollo
| Herramienta | Propósito |
|-------------|-----------|
| **Flutter SDK** (`stable ≥ 3.24`) | Framework multiplataforma |
| **Dart SDK** (`≥ 3.5`) | Lenguaje de programación |
| **VS Code** + Extensiones | IDE principal. Extensiones: `Flutter`, `Dart`, `Firebase`, `GitLens`, `Error Lens` |
| **Firebase CLI** | Inicialización y despliegue de backend |
| **Android Studio / Xcode** | Emuladores, gestión de SDKs nativos y builds firmados |
| **Git + GitHub/GitLab** | Control de versiones y CI/CD básico |
| **Figma / Penpot** | Diseño UI/UX, prototipado y handoff a código |
| **Postman / Insomnia** (opcional) | Pruebas de endpoints si se integra API externa en el futuro |

---

## 🎨 2. Directrices UI/UX
| Aspecto | Recomendación |
|---------|---------------|
| **Estética** | Minimalista, premium, espacios amplios, paleta neutra con acentos dorados o pastel |
| **Tipografía** | Sans-serif limpia (`Inter`, `SF Pro`) + Serif elegante para títulos (`Playfair Display`, `Cormorant`) |
| **Navegación** | BottomNavigationBar (móvil), Sidebar/Drawer (desktop/tablet), transiciones suaves (`Hero`, `PageRouteBuilder`) |
| **Responsividad** | `LayoutBuilder`, `ResponsiveSizer`, grids adaptativos, soporte `hover` para web |
| **Accesibilidad** | Contraste ≥ 4.5:1, `Semantics`, soporte escalado de texto, navegación por teclado |
| **Feedback** | Shimmer loading, skeleton cards, snackbar/toasts para errores/éxito, validación en tiempo real |

---

## 📦 3. Dependencias (`pubspec.yaml`)
```yaml
dependencies:
  flutter:
    sdk: flutter

  # Firebase
  firebase_core: ^3.6.0
  firebase_auth: ^5.3.0
  cloud_firestore: ^5.4.0

  # Estado
  provider: ^6.1.2

  # Navegación
  go_router: ^14.2.0

  # Utilidades & UI
  intl: ^0.19.0
  cached_network_image: ^3.4.0
  flutter_svg: ^2.0.10
  flutter_staggered_grid_view: ^0.7.0
  shimmer: ^3.0.0
  responsive_framework: ^1.5.0

  # Almacenamiento local
  shared_preferences: ^2.3.0

  # Testing & Linting
  flutter_test:
    sdk: flutter
  flutter_lints: ^5.0.0

dev_dependencies:
  flutter_launcher_icons: ^0.14.0
  build_runner: ^2.4.12
```
> 🔹 *Versiones sujetas a compatibilidad con tu versión de Flutter. Ejecuta `flutter pub outdated` para verificar actualizaciones seguras.*

---

## 🏗 4. Arquitectura & Gestión de Estado
```
lib/
├── core/
│   ├── constants/          # Strings, rutas, temas, colores
│   ├── utils/              # Validadores, formatters, helpers
│   ├── theme/              # ThemeData, Typography, Dark/Light mode
│   └── router/             # GoRouter configuration
├── services/
│   ├── auth_service.dart   # Firebase Auth wrapper
│   └── db_service.dart     # Firestore CRUD abstracto
├── models/
│   ├── user_model.dart
│   └── product_model.dart
├── providers/
│   ├── auth_provider.dart
│   ├── product_provider.dart
│   └── ui_provider.dart    # Theme, loading, filtros
├── features/
│   ├── auth/               # Login, Register, Forgot Password
│   ├── home/               # Catálogo, destacados, búsqueda
│   ├── product/            # Detalle, reseñas, favoritos
│   └── profile/            # Datos usuario, historial, logout
└── main.dart
```
- **Patrón:** Capas + Repositorio + Provider (notificadores por dominio)
- **Estado asíncrono:** `FutureProvider` / `StreamProvider` para Firestore
- **Separación:** UI pura, lógica en providers/services, modelos inmutables

---

## 📅 5. Plan Paso a Paso de Implementación

### ✅ Fase 1: Configuración Inicial
1. Crear proyecto: `flutter create perfumeria --platforms=android,ios,web,windows,macos`
2. Configurar `pubspec.yaml` con dependencias base
3. Instalar extensiones VS Code y activar linting
4. Inicializar Git y rama `main`
5. Validar compilación multiplataforma en emulador/dispositivo

### 🔥 Fase 2: Firebase & Backend
1. Crear proyecto en Firebase Console
2. Registrar apps (Android, iOS, Web) y descargar configs:
   - `android/app/google-services.json`
   - `ios/Runner/GoogleService-Info.plist`
   - `web/firebase-config.js`
3. Instalar Firebase CLI y ejecutar `flutterfire configure`
4. Configurar **Authentication** → Email/Password habilitado
5. Crear **Firestore Database** (modo producción)
6. Definir reglas de seguridad básicas (`auth != null` para lectura/escritura)

### 🔐 Fase 3: Autenticación
1. Implementar `AuthService` (`signIn`, `signUp`, `signOut`, `resetPassword`)
2. Crear `AuthProvider` con `ChangeNotifier` o `ValueNotifier`
3. Diseñar pantallas: `LoginScreen`, `RegisterScreen`, `ForgotPasswordScreen`
4. Validaciones en tiempo real + manejo de errores Firebase (`FirebaseAuthException`)
5. Persistencia de sesión automática (`authStateChanges`)
6. Redirección condicional (guard de rutas)

### 🗄 Fase 4: Firestore & Modelos
1. Estructura de colecciones:
   ```
   users/{uid} → {name, email, role, createdAt}
   products/{id} → {name, brand, price, description, category, images[], stock, rating}
   categories/{id} → {name, icon, slug}
   favorites/{uid}/{productId} → {addedAt}
   ```
2. Crear modelos Dart con `fromJson`/`toJson` y validación
3. Implementar `DBService` con métodos paginados (`limit`, `startAfter`)
4. Índices compuestos para filtros (precio, categoría, rating)

### 🎨 Fase 5: UI/UX & Pantallas
1. Configurar `ThemeData` (light/dark, colores, tipografía)
2. Crear componentes reutilizables: `PrimaryButton`, `ProductCard`, `SearchBar`, `EmptyState`
3. Implementar pantallas:
   - `HomeScreen` (grid + búsqueda + filtros)
   - `ProductDetailScreen` (galería, descripción, stock, favoritos)
   - `ProfileScreen` (datos, historial, cerrar sesión)
4. Adaptar layouts para móvil, tablet y web (`ResponsiveBuilder`)
5. Optimizar imágenes (`cached_network_image`, `webp`, lazy loading)

### 🔄 Fase 6: State Management (Provider)
1. Envolver `MaterialApp` con `MultiProvider`
2. `AuthProvider` → escucha `authStateChanges`, expone `User?`, `isLoading`, `error`
3. `ProductProvider` → carga paginada, filtros, búsqueda, favoritos
4. `UIProvider` → tema, idioma, estado de carga global, diálogos
5. Implementar `Consumer` / `Selector` para renderizado eficiente
6. Manejo de errores y retry en streams

### 🧭 Fase 7: Navegación & Rutas
1. Configurar `GoRouter` con:
   - Rutas protegidas (`redirect` si `!user.isLoggedIn`)
   - Deep links (`/product/:id`)
   - Animaciones personalizadas
2. Navegación nativa + web URL sincronizada
3. Historial de back button manejado

### 🧪 Fase 8: Pruebas & Optimización
1. Unit tests: modelos, validadores, servicios mockeados
2. Widget tests: login form, product card, navegación
3. Integration test: flujo completo login → catálogo → detalle
4. Performance: `flutter run --profile`, evitar rebuilds innecesarios, usar `const`, `key`
5. Accesibilidad: `flutter analyze`, `dart fix`, contraste, semántica

### 🚀 Fase 9: Build & Despliegue
1. Generar assets (`flutter_launcher_icons`, iconos adaptativos)
2. Configurar firmas (Android keystore, iOS provisioning)
3. Builds:
   - `flutter build apk --release`
   - `flutter build ios --release`
   - `flutter build web --release --web-renderer canvaskit`
4. Despliegue Firebase Hosting (web), Play Console / App Store Connect
5. Monitoreo: Firebase Crashlytics, Analytics, Performance Monitoring

---

## ✅ Próximos Pasos
1. **Revisa este plan** y confirma si la arquitectura, dependencias y flujo coinciden con tu visión.
2. **Indica prioridades**: ¿Quieres empezar por Auth, Catálogo o ambos en paralelo?
3. **Aporta detalles adicionales** (si existen): logo, paleta de colores exacta, roles de usuario, pasarela de pago futura, etc.
4. Una vez validado, **proporcionaré el código modular por fases**, listo para copiar/pegar y ejecutar en VS Code.

¿Procedemos con la **Fase 1 + Fase 2** (configuración proyecto + Firebase) o prefieres ajustar algún punto del plan primero?
