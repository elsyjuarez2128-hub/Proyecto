# 📱 PROYECTO: MyComunidad App UTNG
# MiComunidad-App-UTNG  
Aplicación Android para reportes comunitarios — UTNG  



# 📑 Índice

Descripción del proyecto

Características principales

Tecnologías usadas

Instalación / Cómo ejecutar

Estructura del proyecto

Uso / Flujo de la aplicación

Guía para contribuidores

Screenshots

Licencia

Autores / Mantenedores

## Descripción del proyecto  

MiComunidad-App-UTNG es una aplicación móvil desarrollada en Kotlin / Android destinada a que miembros de la comunidad de la UTNG puedan reportar incidencias, sugerencias o situaciones comunitarias de forma sencilla desde su dispositivo. El objetivo es facilitar la comunicación entre estudiantes / comunidad y autoridades, registrando reportes estructurados con datos relevantes.  

---

## Características principales  
Características principales

📍 Reportar problemas mediante formulario con descripción, fotografía y ubicación.

🗺️ Visualización de reportes en mapa mediante Google Maps.

📸 Subida de imágenes desde galería o cámara.

🔐 Autenticación de usuario (según versión del proyecto).

📨 Notificación de reportes enviados.

🗂️ Historial de reportes realizados por el usuario.
---

# 🛠️ Tecnologías usadas
Frontend / App

Android Studio (Java/Kotlin según tu proyecto)

XML para interfaces

Google Maps API

Firebase Storage (si lo usas para imágenes)

Firebase Authentication / Firestore (si aplica)

Backend

API REST (si existiera en el proyecto)

Firebase Realtime Database o Firestore (según integración)


# 🚀 Instalación / Cómo ejecutar
1. Clonar repositorio
   git clone https://github.com/1224100827mrs-gif/-MiComunidad-App-UTNG.git
2. Abrir el proyecto

Abrir Android Studio

Seleccionar Open an existing project

Elegir la carpeta del repositorio

3. Configurar APIs (si aplica)

Crear archivo google-services.json

Activar APIs de Google Maps

Configurar Firebase (Authentication, Firestore, Storage)

4. Ejecutar

Conectar un dispositivo físico o usar un emulador

Presionar ▶️ Run

## 📁 Estructura de Paquetes
### **1. Capa de Datos (`datos/`)**
```kotlin
app/src/main/java/mx/edu/utng/mrs/mycomunidad/
datos/
├── fuente_datos/
                      # Conexiones a Firebase/Firestore
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



FASE 1: Configuración Inicial del Proyecto
Paso 1: Estructura Base y Archivos Esenciales
Modelos de Datos

├── datos
├── fuente_datos
│   └── ServicioFirebase
├── Modelo
│   ├── Comentario.kt
│   ├── Notificasiones.kt
│   ├── Reportes.kt
│   ├── Ubicasion.kt
│   └── Usuario.kt
├── Respositorio
│   ├── RepositorioAutenticacion.kt
│   ├── ResopitorioCompentario.kt
│   ├── RespositorioNotificasiones.kt
│   ├── RepositorioReportes.kt
│   └── RepositorioUsuaio.kt
├── Crear di
│   ├── ModuloUbicacion.kt
│   └── ModuloApplicacion.kt
├── Crear Dominio
├── Caso_uso
│   ├── CasoUsoAutenticasion.kt
│   ├── CasoUsoReportes.kt
│   └── CasoUsoUsuario.kt
├── Crear presentacion
├── Componentes
│   ├── BotonCarga.kt
│   ├── CampoTextoPerzonalizado.kt
│   ├── ComponentesEstadisticas.kt
│   ├── DialogoComentario.kt
│   ├── DialogoError.kt
│   ├── Filtros.Estadisticas.kt
│   ├── FondoconDegradado.kt
│   ├── SeccionComentario.kt
│   ├── SelectorImagenes.kt
│   └── TarjetaReportes.kt
├── navegacion
│   ├── NavegacionPrincipal.kt
│   └── Rutas.kt
├── pantallas
├── administrador
│   ├── PantallaGestionUsuaio.kt
│   ├── PantallaPanelAdministrador.kt
│   ├── PantallaPerfilAdminitrador.kt
│   ├── PantallaReportesAprobado.kt
│   └── PantallaValidacionReportes.kt
├── visitante
│   ├── MapaSeleccionUbicacion.kt
│   ├── MisReportes.kt
│   ├── PantallaBienvenida.kt
│   ├── PantallaCraerReportes.kt
│   ├── PantallaDetalleReportes.kt
│   ├── PantllaEditarReportes.kt
│   ├── PantallaEliminarCuenta.kt
│   ├── PantallaEstadisticas.kt
│   ├── PantallaInicioSesion.kt
│   ├── PantllaInpotCoordenas.kt
│   ├── PantallaListasReportes.kt
│   ├── PantallaMapa.kt
│   ├── PantallaMapaPublico.kt
│   ├── PantallaNotificasiones.kt
│   ├── PantallaPrincipal.kt
│   ├── PantallaRegistro.kt
│   └── PantallaReportesPublicos.kt
├── tema
│   ├── Colores.kt
│   ├── Tema.kt
│   └── Tipografia.kt
├── viewmodel
│   ├── EditarReporte.kt
│   ├── EstadosUi.kt
│   ├── MisReportes.kt
│   ├── ViewModelAdministrador.kt
│   ├── ViewModelAutenticacion.kt
│   ├── ViewModelComentarios.kt
│   ├── ViewModelCrearReporetes.kt
│   ├── ViewModelDetalleReaporte.kt
│   ├── ViewModelEstadisticas.kt
│   ├── ViewModelGestionUsuaios.kt
│   ├── ViewModelMapa.kt
│   ├── ViewModelMapaPublico.kt
│   ├── ViewModelNotificasiones.kt
│   ├── ViewModelPerfil.kt
│   ├── ViewModelReportes.kt
│   ├── ViewModelReportesPublicos.kt
│   └── ViewModelSeleccionesUbicasion.kt
├── servicios
│   ├── AdminitradorNotificasiones.kt
│   ├── ServiciosNotificasiones.kt
│   ├── ServiciosNotofocasionesFirestore.kt
│   ├── ServicioUbicasion.kt
│   └── UbicasionManager.kt
├── utilidades
│   ├── AlmacenamientoSeguro.kt
│   ├── FormateadorTiempo.kt
│   ├── GradientUtils.kt
│   ├── ManejadorCamara.kt
│   ├── ManejadorMapas.kt
│   ├── MainActivity.kt
│   └── MyCominidadApplication.kt

### Uso / Flujo de la aplicación

El usuario ingresa a la app.

Selecciona "Reportar problema".

Agrega:

Foto

Descripción

Tipo de problema

Ubicación en el mapa

El reporte se almacena en la base de datos.

El usuario puede visualizar todos los reportes en Google Maps.

Puede revisar su historial y estado de cada reporte.
