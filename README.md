# 📱 PROYECTO: MyComunidad App UTNG
# MiComunidad-App-UTNG  
> Aplicación Android para reportes comunitarios — UTNG  

---

## Tabla de contenido  

1. [Descripción del proyecto](#descripción-del-proyecto)  
2. [Características principales](#características-principales)  
3. [Tecnologías usadas](#tecnologías-usadas)  
4. [Instalación / Cómo ejecutar](#instalación--cómo-ejecutar)  
5. [Estructura del proyecto](#estructura-del-proyecto)  
6. [Uso / Flujo de la aplicación](#uso--flujo-de-la-aplicación)  
7. [Guía para contribuidores](#guía-para-contribuidores)  
8. [Screenshots](#screenshots)  
9. [Licencia](#licencia)  
10. [Autores / Mantenedores](#autores--mantenedores)  

---

## Descripción del proyecto  

MiComunidad-App-UTNG es una aplicación móvil desarrollada en Kotlin / Android destinada a que miembros de la comunidad de la UTNG puedan reportar incidencias, sugerencias o situaciones comunitarias de forma sencilla desde su dispositivo. El objetivo es facilitar la comunicación entre estudiantes / comunidad y autoridades, registrando reportes estructurados con datos relevantes.  

---

## Características principales  

- Creación de reportes comunitarios desde la app (incidencias, sugerencias, etc.).  
- Formulario para completar datos del reporte (título, descripción, categoría, ubicación, imagen, etc.).  
- Persistencia / almacenamiento de reportes (local / remoto — según implementación).  
- Interfaz amigable y fácil de usar.  
- Posibilidad de configurar datos de usuario / sesión (si aplica).  
- ... *(añadir las funcionalidades reales de tu app)*  

---

## Tecnologías usadas  

- Kotlin / Android (Android Studio, Gradle)  
- Android SDK / Jetpack (o libraries que uses)  
- *(añadir librerías externas, dependencias, versiones, etc.)*  

---

## Instalación / Cómo ejecutar  

```bash
git clone https://github.com/1224100827mrs-gif/-MiComunidad-App-UTNG.git
cd -MiComunidad-App-UTNG
# Abrir el proyecto con Android Studio
```

### 🔧 Sincronizar dependencias con Gradle  
### ▶️ Ejecutar la app en un emulador o dispositivo Android
---

## 📁 Estructura de Paquetes
### **1. Capa de Datos (`datos/`)**
```kotlin
app/src/main/java/mx/edu/utng/mrs/mycomunidad/
datos/
├── fuente_datos/     # Conexiones a Firebase/Firestore
├── modelo/           # Entidades de datos
└── repositorio/      # Implementación de repositorios

Inyección de Dependencias (di/)
kotlin
di/
├── ModuloAplicacion.kt    # Módulo principal de Hilt/Dagger
└── ModuloUbicacion.kt     # Módulo para servicios de ubicación

Capa de Dominio (dominio/)
kotlin
dominio/casos_uso/
├── CasoUsoAutenticacion.kt    # Lógica de login/registro
├── CasoUsoReportes.kt         # Operaciones con reportes
└── CasoUsoUsuario.kt          # Gestión de perfiles

Capa de Presentación (presentacion/)
kotlin
presentacion/
├── componentes/          # Componentes UI reutilizables
├── navegacion/          # Navegación entre pantallas
├── pantallas/           # Todas las pantallas de la app
│   ├── administrador/   # Pantallas para administradores
│   └── visitante/       # Pantallas para usuarios
├── tema/                # Temas, colores y tipografía
├── viewmodel/           # ViewModels para cada pantalla
├── servicios/           # Servicios en segundo plano
└── utilidades/          # Utilidades y helpers


# 🏫 MyComunidad - Aplicación Móvil para la UTNG

[![Kotlin](https://img.shields.io/badge/Kotlin-1.9.0-blue.svg)](https://kotlinlang.org)
[![Android](https://img.shields.io/badge/Android-API_24+-green.svg)](https://developer.android.com)
[![License](https://img.shields.io/badge/Licencia-MIT-yellow.svg)](LICENSE)
[![Estado](https://img.shields.io/badge/Estado-En%20Producción-success.svg)]()

## 📱 Descripción

**MyComunidad** 
Es una aplicación móvil desarrollada para la comunidad estudiantil de la Universidad Tecnológica del Norte de Guanajuato (UTNG). 
La aplicación facilita la gestión de reportes, comunicación entre estudiantes y administración de incidencias dentro del campus.

## ✨ Características Principales

### 👤 Para Estudiantes
- 📝 **Creación de reportes** con fotos y ubicación
- 🗺️ **Mapa interactivo** de incidencias del campus
- 🔔 **Notificaciones en tiempo real**
- 📊 **Estadísticas** de reportes por categoría
- 👥 **Comentarios** en reportes públicos

### 👨‍💼 Para Administradores
- ✅ **Validación de reportes** pendientes
- 👥 **Gestión de usuarios** y permisos
- 📈 **Panel de administración** con métricas
- 🔧 **Aprobación/Rechazo** de reportes
