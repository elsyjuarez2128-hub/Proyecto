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
### Estructura del proyecto
MyComunidad-App-UTNG/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/mx/edu/utng/mrs/mycomunidad/
│   │   │   │   ├── datos/
│   │   │   │   │   ├── fuente_datos/
│   │   │   │   │   ├── modelo/
│   │   │   │   │   └── repositorio/
│   │   │   │   ├── di/
│   │   │   │   │   ├── ModuloAplicacion.kt
│   │   │   │   │   └── ModuloUbicacion.kt
│   │   │   │   ├── dominio/
│   │   │   │   │   └── casos_uso/
│   │   │   │   │       ├── CasoUsoAutenticacion.kt
│   │   │   │   │       ├── CasoUsoReportes.kt
│   │   │   │   │       └── CasoUsoUsuario.kt
│   │   │   │   ├── presentacion/
│   │   │   │   │   ├── componentes/
│   │   │   │   │   │   ├── BotonCarga.kt
│   │   │   │   │   │   ├── CampoTextoPersonalizado.kt
│   │   │   │   │   │   ├── ComponentesEstadisticas.kt
│   │   │   │   │   │   ├── DialogoComentario.kt
│   │   │   │   │   │   ├── DialogoError.kt
│   │   │   │   │   │   ├── FiltrosEstadisticas.kt
│   │   │   │   │   │   ├── FondoConDegradado.kt
│   │   │   │   │   │   ├── SeccionComentarios.kt
│   │   │   │   │   │   ├── SelectorImagenes.kt
│   │   │   │   │   │   └── TarjetaReporte.kt
│   │   │   │   │   ├── navegacion/
│   │   │   │   │   │   ├── NavegacionPrincipal.kt
│   │   │   │   │   │   └── Rutas.kt
│   │   │   │   │   ├── pantallas/
│   │   │   │   │   │   ├── administrador/
│   │   │   │   │   │   │   ├── PantallaGestionUsuario.kt
│   │   │   │   │   │   │   ├── PantallaPanelAdministrador.kt
│   │   │   │   │   │   │   ├── PantallaPerfilAdministrador.kt
│   │   │   │   │   │   │   ├── PantallaReportesAprobados.kt
│   │   │   │   │   │   │   └── PantallaValidacionReportes.kt
│   │   │   │   │   │   └── visitante/
│   │   │   │   │   │       ├── MapaSeleccionUbicacion.kt
│   │   │   │   │   │       ├── MisReportes.kt
│   │   │   │   │   │       ├── PantallaBienvenida.kt
│   │   │   │   │   │       ├── PantallaCrearReporte.kt
│   │   │   │   │   │       ├── PantallaDetalleReporte.kt
│   │   │   │   │   │       ├── PantallaEditarReporte.kt
│   │   │   │   │   │       ├── PantallaEliminarCuenta.kt
│   │   │   │   │   │       ├── PantallaEstadisticas.kt
│   │   │   │   │   │       ├── PantallaInicioSesion.kt
│   │   │   │   │   │       ├── PantallaInputCoordenadas.kt
│   │   │   │   │   │       ├── PantallaListaReportes.kt
│   │   │   │   │   │       ├── PantallaMapa.kt
│   │   │   │   │   │       ├── PantallaMapaPublico.kt
│   │   │   │   │   │       ├── PantallaNotificaciones.kt
│   │   │   │   │   │       ├── PantallaPrincipal.kt
│   │   │   │   │   │       ├── PantallaRegistro.kt
│   │   │   │   │   │       └── PantallaReportesPublicos.kt
│   │   │   │   │   ├── tema/
│   │   │   │   │   │   ├── Colores.kt
│   │   │   │   │   │   ├── Tema.kt
│   │   │   │   │   │   └── Tipografia.kt
│   │   │   │   │   ├── viewmodel/
│   │   │   │   │   │   ├── EditarReporteViewModel.kt
│   │   │   │   │   │   ├── EstadosUI.kt
│   │   │   │   │   │   ├── MisReportesViewModel.kt
│   │   │   │   │   │   ├── ViewModelAdministrador.kt
│   │   │   │   │   │   ├── ViewModelAutenticacion.kt
│   │   │   │   │   │   ├── ViewModelComentarios.kt
│   │   │   │   │   │   ├── ViewModelCrearReporte.kt
│   │   │   │   │   │   ├── ViewModelDetalleReporte.kt
│   │   │   │   │   │   ├── ViewModelEstadisticas.kt
│   │   │   │   │   │   ├── ViewModelGestionUsuarios.kt
│   │   │   │   │   │   ├── ViewModelMapa.kt
│   │   │   │   │   │   ├── ViewModelMapaPublico.kt
│   │   │   │   │   │   ├── ViewModelNotificaciones.kt
│   │   │   │   │   │   ├── ViewModelPerfil.kt
│   │   │   │   │   │   ├── ViewModelReportes.kt
│   │   │   │   │   │   ├── ViewModelReportesPublicos.kt
│   │   │   │   │   │   └── ViewModelSeleccionUbicacion.kt
│   │   │   │   │   ├── servicios/
│   │   │   │   │   │   ├── AdministradorNotificaciones.kt
│   │   │   │   │   │   ├── ServicioNotificaciones.kt
│   │   │   │   │   │   ├── ServicioNotificacionesFirestore.kt
│   │   │   │   │   │   ├── ServicioUbicacion.kt
│   │   │   │   │   │   └── UbicacionManager.kt
│   │   │   │   │   ├── utilidades/
│   │   │   │   │   │   ├── AlmacenamientoSeguro.kt
│   │   │   │   │   │   ├── FormateadorTiempo.kt
│   │   │   │   │   │   ├── GradientUtils.kt
│   │   │   │   │   │   ├── ManejadorCamara.kt
│   │   │   │   │   │   └── ManejadorMapas.kt
│   │   │   │   │   ├── MainActivity.kt
│   │   │   │   │   └── MyComunidadApplication.kt
│   │   │   ├── res/
│   │   │   └── AndroidManifest.xml
│   │   └── build.gradle.kts
├── docs/
│   ├── screenshots/
│   └── pruebas-usuarios/
├── .gitignore
└── README.md
