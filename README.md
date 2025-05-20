# Tarea App - Angular + Ionic

## Descripción

Aplicación móvil desarrollada con Angular e Ionic, que implementa navegación híbrida, lazy loading, guardas de autenticación, animaciones y pruebas unitarias.

---

## Decisiones tomadas

### 1. Lazy Loading de Módulos

- Se crearon módulos lazy para `auth`, `tabs` y `settings` usando `loadChildren` en las rutas principales.
- Cada módulo tiene su propio archivo de rutas internas (`*-routing.module.ts`).

### 2. Navegación Híbrida

- Se utiliza **Angular Router** para la navegación principal (por ejemplo, después de login).
- Se utiliza **NavController** de Ionic para acciones como logout (`navigateRoot`) y volver atrás (`back()`).

### 3. AuthGuard

- Se implementó un guard (`authGuard`) que revisa la existencia de un token simulado en `localStorage`.
- Si no hay token, redirige al login.

### 4. Animaciones

- Se aplicaron animaciones de transición usando `@angular/animations` en las páginas principales (`fadeIn`, `zoomIn`, `slideIn`).

### 5. Logout

- El método `logout()` elimina el token y navega al login usando `navigateRoot()` para limpiar el historial.

### 6. Pruebas Unitarias

- Se escribieron pruebas unitarias para el guard, navegación y componentes principales.
- Se agregó `provideAnimations()` en los archivos de prueba para soportar animaciones.

---

## Estructura de carpetas

```
src/app/
  ├── pages/
  │     ├── auth/
  │     │     └── login/
  │     ├── tabs/
  │     │     ├── home/
  │     └── settings/
  │           └── settings/
  ├── guards/
  └── app.routes.ts
```

---

## Notas

- El token de autenticación es simulado y se guarda en `localStorage`.
- El guard protege las rutas de `tabs` y `settings`.
- Las animaciones requieren que `provideAnimations()` esté configurado en el bootstrap y en los tests.

---

## Autor

Mateo Lituma
