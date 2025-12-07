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

## 🛠️ Tecnologías Usadas
- Kotlin
- Android Studio
- Firebase Realtime Database / Firestore
- Firebase Storage
- Google Maps API
- Material Design 3


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
```

# Uso / Flujo de la aplicación

El usuario ingresa a la app.

Selecciona "Reportar problema".

Agrega: Foto

Descripción

Tipo de problema

Ubicación en el mapa

El reporte se almacena en la base de datos.

El usuario puede visualizar todos los reportes en Google Maps.

Puede revisar su historial y estado de cada reporte.

# 🤝 Guía para contribuidores
# Haz un fork del proyecto.

Crea una rama nueva:
```
git checkout -b feature-nueva-funcion
```
Realiza los cambios.

Haz commit con mensaje claro:
```
git commit -m "Agrega función de reporte con foto"
```
Sube los cambios:
```
git push origin feature-nueva-funcion
```
# Screenshots de la Aplicación
# 🏠 Pantalla Principal
--
<img src="https://github.com/user-attachments/assets/d12866d8-e2da-4216-adc4-56b1ca16097d" alt="Pantalla principal" width="120">
--
# 🗺️ Mapa de Reportes
--<img src="https://github.com/user-attachments/assets/3c461b6e-e4fd-4c0b-8cc8-8ce0d38afa5b" alt="Mapa de reportes" width="120">
--
# Comentarios Fuente con KDoc/JSDoc

# 🟦 1. MyComunidadApplication.kt (KDoc para App)
```
package mx.edu.utng.mrs.mycomunidad

import android.app.Application
import dagger.hilt.android.HiltAndroidApp

/**
 * Clase principal de la aplicación Mi Comunidad.
 * Se ejecuta antes que cualquier Activity y configura los módulos de dependencias,
 * servicios globales y componentes compartidos por toda la app.
 */
@HiltAndroidApp
class MyComunidadApplication : Application()

/**
 * Se ejecuta al iniciar la aplicación.
 * Ideal para inicializar Koin/Hilt, Firebase o servicios globales.
 */
override fun onCreate() {
    super.onCreate()
}
}
```
# 🟦 2. MainActivity.kt (KDoc para pantalla principal)
```
package mx.edu.utng.mrs.mycomunidad

import android.Manifest
import android.content.Intent
import android.content.pm.PackageManager
import android.os.Build
import android.os.Bundle
import android.util.Log
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.result.contract.ActivityResultContracts
import androidx.activity.viewModels
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.material3.Surface
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.rememberCoroutineScope
import androidx.compose.ui.Modifier
import androidx.core.content.ContextCompat
import androidx.navigation.compose.rememberNavController
import com.google.firebase.firestore.FirebaseFirestore
import dagger.hilt.android.AndroidEntryPoint
import kotlinx.coroutines.launch
import mx.edu.utng.mrs.mycomunidad.datos.fuente_datos.ServicioFirebase
import mx.edu.utng.mrs.mycomunidad.presentacion.navegacion.NavegacionPrincipal
import mx.edu.utng.mrs.mycomunidad.presentacion.tema.MyComunidadTheme
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelAutenticacion
import mx.edu.utng.mrs.mycomunidad.servicios.AdministradorNotificaciones
import javax.inject.Inject


/**
 * Pantalla principal de la aplicación.
 * Aquí se muestra el menú y las opciones principales para el usuario.
 */
@AndroidEntryPoint
class MainActivity : ComponentActivity() {

    private val viewModelAutenticacion: ViewModelAutenticacion by viewModels()

    @Inject
    lateinit var servicioFirebase: ServicioFirebase

    @Inject
    lateinit var administradorNotificaciones: AdministradorNotificaciones

    companion object {
        private const val TAG = "MainActivity"
        const val PERMISO_UBICACION_OTORGADO = "permiso_ubicacion_otorgado"
        const val PERMISO_NOTIFICACION_OTORGADO = "permiso_notificacion_otorgado"
    }

    // Permisos de ubicación
    private val permisosUbicacion = if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.Q) {
        arrayOf(
            Manifest.permission.ACCESS_FINE_LOCATION,
            Manifest.permission.ACCESS_COARSE_LOCATION,
            Manifest.permission.ACCESS_BACKGROUND_LOCATION
        )
    } else {
        arrayOf(
            Manifest.permission.ACCESS_FINE_LOCATION,
            Manifest.permission.ACCESS_COARSE_LOCATION
        )
    }

    // Permisos de notificaciones (Android 13+)
    private val permisoNotificacion = if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.TIRAMISU) {
        Manifest.permission.POST_NOTIFICATIONS
    } else {
        null
    }

    // Launcher para permisos de ubicación
    private val requestLocationPermissionLauncher = registerForActivityResult(
        ActivityResultContracts.RequestMultiplePermissions()
    ) { permisos ->
        val todosConcedidos = permisos.values.all { it }
        if (todosConcedidos) {
            Log.d(TAG, "✅ Todos los permisos de ubicación concedidos")
            // Guardar en preferencias que los permisos fueron otorgados
            getSharedPreferences("permisos", MODE_PRIVATE)
                .edit()
                .putBoolean(PERMISO_UBICACION_OTORGADO, true)
                .apply()

            // Inicializar servicios que requieren ubicación
            inicializarServiciosUbicacion()
        } else {
            Log.w(TAG, "⚠️ Algunos permisos de ubicación fueron denegados: $permisos")
            mostrarDialogoPermisosUbicacion()
        }
    }

    // Launcher para permisos de notificaciones
    private val requestNotificationPermissionLauncher = registerForActivityResult(
        ActivityResultContracts.RequestPermission()
    ) { isGranted ->
        if (isGranted) {
            Log.d(TAG, "✅ Permiso de notificaciones concedido")
            getSharedPreferences("permisos", MODE_PRIVATE)
                .edit()
                .putBoolean(PERMISO_NOTIFICACION_OTORGADO, true)
                .apply()

            // Inicializar notificaciones ahora que tenemos permisos
            inicializarSistemaNotificacionesCompleto()
        } else {
            Log.w(TAG, "⚠️ Permiso de notificaciones denegado")
        }
    }

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        configurarFirebaseLogs()

        setContent {
            MyComunidadTheme {
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = androidx.compose.material3.MaterialTheme.colorScheme.background
                ) {
                    val navController = rememberNavController()
                    val coroutineScope = rememberCoroutineScope()

                    LaunchedEffect(Unit) {
                        // Inicializar servicios
                        servicioFirebase.probarConexionFirebase()
                        servicioFirebase.logEstadoFirebase()
                        viewModelAutenticacion.cargarUsuarioActual()
                        manejarNotificacionAlAbrir(intent)

                        // Verificar y solicitar permisos
                        coroutineScope.launch {
                            verificarYSolicitarPermisos()
                        }
                    }

                    NavegacionPrincipal(
                        navController = navController,
                        viewModelAutenticacion = viewModelAutenticacion
                    )
                }
            }
        }
    }

    private fun verificarYSolicitarPermisos() {
        Log.d(TAG, "🔍 Verificando permisos...")

        // 1. Verificar y solicitar permisos de notificaciones primero
        if (permisoNotificacion != null && !tienePermisoNotificaciones()) {
            Log.d(TAG, "📱 Permisos de notificación necesarios")
            solicitarPermisosNotificaciones()
        } else {
            Log.d(TAG, "📱 Permisos de notificación ya concedidos o no requeridos")
            // Inicializar notificaciones si ya tenemos permisos
            inicializarSistemaNotificacionesCompleto()
        }

        // 2. Verificar permisos de ubicación
        if (necesitaPermisosUbicacion()) {
            Log.d(TAG, "📍 Permisos de ubicación necesarios")
            solicitarPermisosUbicacion()
        } else {
            Log.d(TAG, "✅ Permisos de ubicación ya concedidos")
            inicializarServiciosUbicacion()
        }
    }

    private fun necesitaPermisosUbicacion(): Boolean {
        return permisosUbicacion.any { permiso ->
            ContextCompat.checkSelfPermission(this, permiso) != PackageManager.PERMISSION_GRANTED
        }
    }

    private fun tienePermisoNotificaciones(): Boolean {
        return permisoNotificacion?.let { permiso ->
            ContextCompat.checkSelfPermission(this, permiso) == PackageManager.PERMISSION_GRANTED
        } ?: true // Para Android <13, siempre retorna true
    }

    private fun solicitarPermisosUbicacion() {
        Log.d(TAG, "📍 Solicitando permisos de ubicación...")

        // Verificar si debemos mostrar una explicación
        val deberiaMostrarExplicacion = permisosUbicacion.any { permiso ->
            shouldShowRequestPermissionRationale(permiso)
        }

        if (deberiaMostrarExplicacion) {
            Log.d(TAG, "ℹ️ Mostrando explicación de permisos de ubicación")
            mostrarDialogoExplicacionUbicacion()
        } else {
            // Solicitar permisos directamente
            requestLocationPermissionLauncher.launch(permisosUbicacion)
        }
    }

    private fun solicitarPermisosNotificaciones() {
        Log.d(TAG, "🔔 Solicitando permisos de notificación...")

        if (permisoNotificacion != null) {
            val deberiaMostrarExplicacion = shouldShowRequestPermissionRationale(permisoNotificacion!!)

            if (deberiaMostrarExplicacion) {
                Log.d(TAG, "ℹ️ Mostrando explicación de permisos de notificación")
                mostrarDialogoExplicacionNotificacion()
            } else {
                requestNotificationPermissionLauncher.launch(permisoNotificacion!!)
            }
        }
    }

    private fun inicializarServiciosUbicacion() {
        Log.d(TAG, "🚀 Inicializando servicios de ubicación...")
        // Aquí puedes inicializar servicios que requieren ubicación
        // Por ejemplo: ServicioUbicacion.iniciarServicio(this)

        // Puedes agregar más servicios de ubicación aquí
        // Ejemplo: Geocoder inicialization, Location services, etc.
    }

    private fun inicializarSistemaNotificacionesCompleto() {
        Log.d(TAG, "🔔 Iniciando sistema de notificaciones")

        // Llamar al método existente en AdministradorNotificaciones
        administradorNotificaciones.inicializarSistemaNotificaciones(this)

        // Mostrar mensaje de éxito
        Log.d(TAG, "✅ Sistema de notificaciones inicializado correctamente")
    }

    private fun configurarFirebaseLogs() {
        try {
            FirebaseFirestore.setLoggingEnabled(true)
            val db = FirebaseFirestore.getInstance()
            db.collection("usuarios").limit(1).get()
                .addOnCompleteListener { task ->
                    if (task.isSuccessful) {
                        Log.d("FIREBASE_DEBUG", "Conexión Firestore exitosa")
                        Log.d("FIREBASE_DEBUG", "Documentos en 'usuarios': ${task.result?.size()}")
                    } else {
                        Log.e("FIREBASE_DEBUG", "Error Firestore: ${task.exception?.message}")
                    }
                }
            Log.d("FIREBASE_DEBUG", "Logs de Firestore habilitados")
        } catch (e: Exception) {
            Log.e("FIREBASE_DEBUG", "Error configurando Firebase: ${e.message}")
        }
    }

    private fun mostrarDialogoExplicacionUbicacion() {
        // Aquí puedes mostrar un diálogo o snackbar explicando por qué necesitas ubicación
        androidx.appcompat.app.AlertDialog.Builder(this)
            .setTitle("Permisos de Ubicación Necesarios")
            .setMessage("La aplicación necesita acceso a tu ubicación para:\n\n• Mostrar reportes cercanos\n• Permitirte crear reportes en tu ubicación actual\n• Filtrar reportes por proximidad\n• Mejorar la precisión de los reportes")
            .setPositiveButton("Entendido") { _, _ ->
                requestLocationPermissionLauncher.launch(permisosUbicacion)
            }
            .setNegativeButton("Cancelar") { dialog, _ ->
                dialog.dismiss()
            }
            .show()
    }

    private fun mostrarDialogoExplicacionNotificacion() {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.TIRAMISU) {
            androidx.appcompat.app.AlertDialog.Builder(this)
                .setTitle("Permisos de Notificación")
                .setMessage("Permite las notificaciones para recibir:\n\n• Actualizaciones sobre tus reportes\n• Alertas importantes de la comunidad\n• Notificaciones de nuevos comentarios\n• Estado de tus reportes enviados")
                .setPositiveButton("Permitir") { _, _ ->
                    requestNotificationPermissionLauncher.launch(permisoNotificacion!!)
                }
                .setNegativeButton("Ahora no") { dialog, _ ->
                    dialog.dismiss()
                }
                .show()
        }
    }

    private fun mostrarDialogoPermisosUbicacion() {
        androidx.appcompat.app.AlertDialog.Builder(this)
            .setTitle("Permisos de Ubicación Requeridos")
            .setMessage("Para usar todas las funciones de la app, necesitas conceder permisos de ubicación.\n\nPuedes activarlos en:\nConfiguración > Aplicaciones > MyComunidad > Permisos > Ubicación")
            .setPositiveButton("Ir a Configuración") { _, _ ->
                val intent = Intent(android.provider.Settings.ACTION_APPLICATION_DETAILS_SETTINGS)
                intent.data = android.net.Uri.fromParts("package", packageName, null)
                startActivity(intent)
            }
            .setNegativeButton("Cancelar") { dialog, _ ->
                dialog.dismiss()
            }
            .setNeutralButton("Usar sin ubicación") { dialog, _ ->
                dialog.dismiss()
                // El usuario puede continuar sin permisos de ubicación
                Log.d(TAG, "Usuario eligió continuar sin permisos de ubicación")
            }
            .show()
    }

    private fun manejarNotificacionAlAbrir(intent: Intent) {
        val desdeNotificacion = intent.getBooleanExtra("desde_notificacion", false)
        val tipoNotificacion = intent.getStringExtra("tipo_notificacion")
        val reporteId = intent.getStringExtra("reporte_id")
        val titulo = intent.getStringExtra("titulo")
        val mensaje = intent.getStringExtra("mensaje")

        if (desdeNotificacion) {
            Log.d(TAG, "📱 App abierta desde notificación: tipo=$tipoNotificacion, reporteId=$reporteId, titulo=$titulo, mensaje=$mensaje")
            if (!reporteId.isNullOrEmpty()) {
                Log.d(TAG, "🚀 Intentando navegar al reporte: $reporteId")
                // Aquí puedes navegar a la pantalla de detalles del reporte
                // navController.navigate("detalle_reporte/$reporteId")
            }
        } else {
            intent.extras?.let { extras ->
                if (extras.containsKey("google.message_id") || extras.containsKey("gcm.message_id")) {
                    val tipo = extras.getString("tipo")
                    val tituloFcm = extras.getString("titulo")
                    val mensajeFcm = extras.getString("mensaje")
                    val reporteIdFcm = extras.getString("reporteId")
                    Log.d(TAG, "📨 Datos FCM: tipo=$tipo, titulo=$tituloFcm, mensaje=$mensajeFcm, reporteId=$reporteIdFcm")
                }
            }
        }

        intent.action?.let { action -> Log.d(TAG, "Action del intent: $action") }
    }

    // Métodos públicos para uso desde otras partes de la app
    fun probarNotificacionManual() {
        administradorNotificaciones.probarNotificacionLocal(this)
    }

    fun verificarPermisosUbicacionEnTiempoReal(): Boolean {
        return !necesitaPermisosUbicacion()
    }

    fun solicitarPermisosUbicacionManual() {
        solicitarPermisosUbicacion()
    }

    fun verificarPermisosNotificacionesEnTiempoReal(): Boolean {
        return tienePermisoNotificaciones()
    }

    fun solicitarPermisosNotificacionesManual() {
        solicitarPermisosNotificaciones()
    }

    override fun onNewIntent(intent: Intent?) {
        super.onNewIntent(intent)
        intent?.let { manejarNotificacionAlAbrir(it) }
    }

    override fun onResume() {
        super.onResume()
        servicioFirebase.verificarEstadoFirebase()

        // Re-verificar permisos cuando la app vuelve al frente
        if (necesitaPermisosUbicacion()) {
            Log.d(TAG, "📍 Re-verificando permisos de ubicación en onResume")
        }
    }

    override fun onStart() {
        super.onStart()
        Log.d(TAG, "🚀 MainActivity iniciada")
    }

    override fun onStop() {
        super.onStop()
        Log.d(TAG, "⏸️ MainActivity en segundo plano")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d(TAG, "❌ MainActivity destruida")
    }

    // Función para mostrar notificación desde cualquier lugar
    fun mostrarNotificacion(
        titulo: String,
        mensaje: String,
        tipo: String = "general",
        reporteId: String = ""
    ) {
        administradorNotificaciones.mostrarNotificacion(
            context = this,
            titulo = titulo,
            mensaje = mensaje,
            tipo = tipo,
            reporteId = reporteId
        )
    }
}
```
# Datos - Fuente de Datos
# ServiceFirebase.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.fuente_datos

import android.content.Context
import android.util.Log
import com.google.firebase.Firebase
import com.google.firebase.firestore.FirebaseFirestore
import com.google.firebase.firestore.firestore
import com.google.firebase.storage.FirebaseStorage
import dagger.hilt.android.qualifiers.ApplicationContext
import kotlinx.coroutines.CoroutineScope
import kotlinx.coroutines.Dispatchers
import kotlinx.coroutines.launch
import kotlinx.coroutines.tasks.await
import javax.inject.Inject
import javax.inject.Singleton

/**
 * Servicio principal de Firebase que maneja la conexión con Firestore y Authentication
 *
 * @property firestore Instancia de Firebase Firestore para operaciones de base de datos
 * @property auth Instancia de Firebase Authentication para manejo de usuarios
 */
@Singleton
class ServicioFirebase @Inject constructor(
    @ApplicationContext private val context: Context
) {
    // Firestore normal
    val firestore: FirebaseFirestore by lazy { FirebaseFirestore.getInstance() }

    // Storage CORREGIDO - Usando el bucket correcto del google-services.json
    val storage: FirebaseStorage by lazy {
        FirebaseStorage.getInstance()
        // Esto usará automáticamente: gs://mi-comunidad-utng.firebasestorage.app
    }

    // ✅ CORREGIDO: Función para probar la conexión con Firebase
    fun probarConexionFirebase() {
        try {
            // Probar Firestore
            val db = Firebase.firestore
            Log.d("FirebaseTest", "✅ Firestore conectado correctamente")

            // Probar Storage
            val storageRef = storage.reference
            Log.d("FirebaseTest", "✅ Storage conectado correctamente")
            Log.d("FirebaseTest", "📦 Bucket: ${storage.app.options.storageBucket}")

            // ✅ CORREGIDO: Usar tipos explícitos en el mapOf
            val testData = hashMapOf<String, Any>(
                "timestamp" to System.currentTimeMillis(),
                "test_type" to "connection_test",
                "app_name" to "MiComunidad"
            )

            // Intentar una operación simple de Firestore
            db.collection("test").document("connection")
                .set(testData)
                .addOnSuccessListener {
                    Log.d("FirebaseTest", "✅ Escritura en Firestore exitosa")
                }
                .addOnFailureListener { e ->
                    Log.w("FirebaseTest", "⚠️ Escritura en Firestore falló: ${e.message}")
                }

        } catch (e: Exception) {
            Log.e("FirebaseTest", "❌ Error conectando Firebase: ${e.message}")
        }
    }

    // ✅ CORREGIDO: Función para verificar si Firebase está inicializado
    fun verificarEstadoFirebase(): Boolean {
        return try {
            // Intentar acceder a Firestore
            Firebase.firestore
            Log.d("FirebaseTest", "✅ Firebase está inicializado correctamente")
            true
        } catch (e: Exception) {
            Log.e("FirebaseTest", "❌ Firebase NO está inicializado: ${e.message}")
            false
        }
    }

    // ✅ CORREGIDO: Función para obtener información del proyecto
    fun obtenerInfoProyecto(): Map<String, String> {
        return try {
            // ✅ CORREGIDO: Especificar explícitamente los tipos Pair<String, String>
            mapOf<String, String>(
                "firestore_initialized" to firestore.app.name,
                "storage_initialized" to storage.app.name,
                "project_id" to (firestore.app.options.projectId ?: "No disponible"),
                "storage_bucket" to (storage.app.options.storageBucket ?: "No configurado")
            )
        } catch (e: Exception) {
            mapOf("error" to (e.message ?: "Error desconocido"))
        }
    }

    // ✅ AGREGADO: Función más simple para debugging
    fun logEstadoFirebase() {
        val estado = verificarEstadoFirebase()
        if (estado) {
            Log.i("FirebaseStatus", "🔥 Firebase CONECTADO - Proyecto: ${firestore.app.options.projectId}")
            Log.i("FirebaseStatus", "📦 Storage Bucket: ${storage.app.options.storageBucket}")
        } else {
            Log.e("FirebaseStatus", "💥 Firebase DESCONECTADO")
        }
    }

    // ✅ NUEVO: Función específica para diagnosticar Storage
    fun diagnosticarStorage(): Map<String, String> {
        return try {
            val bucket = storage.app.options.storageBucket
            if (bucket.isNullOrEmpty()) {
                // ✅ CORREGIDO: Especificar tipo explícito
                mapOf<String, String>(
                    "status" to "ERROR",
                    "message" to "Bucket de Storage NO CONFIGURADO",
                    "solution" to "Ve a Firebase Console > Storage > Comenzar"
                )
            } else {
                // ✅ CORREGIDO: Especificar tipo explícito
                mapOf<String, String>(
                    "status" to "OK",
                    "bucket" to bucket,
                    "project_id" to (storage.app.options.projectId ?: "No disponible")
                )
            }
        } catch (e: Exception) {
            // ✅ CORREGIDO: Especificar tipo explícito
            mapOf<String, String>(
                "status" to "ERROR",
                "message" to (e.message ?: "Error desconocido"),
                "exception" to e.javaClass.simpleName
            )
        }
    }

    // ✅ NUEVO: Función para probar subida a Storage
    fun probarSubidaStorage(onSuccess: (String) -> Unit, onError: (String) -> Unit) {
        CoroutineScope(Dispatchers.IO).launch {
            try {
                Log.d("StorageTest", "🧪 Iniciando prueba de Storage...")

                val bucket = storage.app.options.storageBucket
                if (bucket.isNullOrEmpty()) {
                    onError("Bucket de Storage no configurado")
                    return@launch
                }

                Log.d("StorageTest", "📦 Bucket detectado: $bucket")

                // Crear archivo de prueba
                val testFileName = "test_conexion_${System.currentTimeMillis()}.txt"
                val testRef = storage.reference.child(testFileName)
                val testData = "Prueba de conexión Firebase Storage - ${java.util.Date()}"

                // Subir archivo
                testRef.putBytes(testData.toByteArray()).await()
                Log.d("StorageTest", "✅ Archivo subido exitosamente")

                // Obtener URL
                val url = testRef.downloadUrl.await()
                Log.d("StorageTest", "🔗 URL obtenida: $url")

                onSuccess("✅ Storage funciona\nBucket: $bucket\nURL: $url")

            } catch (e: Exception) {
                Log.e("StorageTest", "❌ Error en prueba Storage: ${e.message}")

                val errorMessage = when {
                    e.message?.contains("404") == true -> "❌ ERROR 404: El bucket no existe\n💡 Ve a Firebase Console > Storage > Comenzar"
                    e.message?.contains("permission") == true -> "❌ ERROR Permisos: Revisa las reglas de Storage\n💡 Configura reglas temporales en Firebase Console"
                    e.message?.contains("network") == true -> "❌ ERROR Red: Verifica tu conexión a internet"
                    else -> "❌ Error: ${e.message}"
                }

                onError(errorMessage)
            }
        }
    }
}
```
# Cometarios.kt 
```
package mx.edu.utng.mrs.mycomunidad.datos.fuente_datos

import android.content.Context
import android.util.Log
import com.google.firebase.Firebase
import com.google.firebase.firestore.FirebaseFirestore
import com.google.firebase.firestore.firestore
import com.google.firebase.storage.FirebaseStorage
import dagger.hilt.android.qualifiers.ApplicationContext
import kotlinx.coroutines.CoroutineScope
import kotlinx.coroutines.Dispatchers
import kotlinx.coroutines.launch
import kotlinx.coroutines.tasks.await
import javax.inject.Inject
import javax.inject.Singleton

/**
 * Modelo de datos para representar un comentario en el sistema
 *
 * @property id Identificador único del comentario
 * @property contenido Texto del comentario
 * @property idUsuario ID del usuario que realizó el comentario
 * @property idReporte ID del reporte al que pertenece el comentario (opcional)
 * @property fechaHora Fecha y hora de creación del comentario
 */
@Singleton
class ServicioFirebase @Inject constructor(
    @ApplicationContext private val context: Context
) {
    // Firestore normal
    val firestore: FirebaseFirestore by lazy { FirebaseFirestore.getInstance() }

    // Storage CORREGIDO - Usando el bucket correcto del google-services.json
    val storage: FirebaseStorage by lazy {
        FirebaseStorage.getInstance()
        // Esto usará automáticamente: gs://mi-comunidad-utng.firebasestorage.app
    }

    // ✅ CORREGIDO: Función para probar la conexión con Firebase
    fun probarConexionFirebase() {
        try {
            // Probar Firestore
            val db = Firebase.firestore
            Log.d("FirebaseTest", "✅ Firestore conectado correctamente")

            // Probar Storage
            val storageRef = storage.reference
            Log.d("FirebaseTest", "✅ Storage conectado correctamente")
            Log.d("FirebaseTest", "📦 Bucket: ${storage.app.options.storageBucket}")

            // ✅ CORREGIDO: Usar tipos explícitos en el mapOf
            val testData = hashMapOf<String, Any>(
                "timestamp" to System.currentTimeMillis(),
                "test_type" to "connection_test",
                "app_name" to "MiComunidad"
            )

            // Intentar una operación simple de Firestore
            db.collection("test").document("connection")
                .set(testData)
                .addOnSuccessListener {
                    Log.d("FirebaseTest", "✅ Escritura en Firestore exitosa")
                }
                .addOnFailureListener { e ->
                    Log.w("FirebaseTest", "⚠️ Escritura en Firestore falló: ${e.message}")
                }

        } catch (e: Exception) {
            Log.e("FirebaseTest", "❌ Error conectando Firebase: ${e.message}")
        }
    }

    // ✅ CORREGIDO: Función para verificar si Firebase está inicializado
    fun verificarEstadoFirebase(): Boolean {
        return try {
            // Intentar acceder a Firestore
            Firebase.firestore
            Log.d("FirebaseTest", "✅ Firebase está inicializado correctamente")
            true
        } catch (e: Exception) {
            Log.e("FirebaseTest", "❌ Firebase NO está inicializado: ${e.message}")
            false
        }
    }

    // ✅ CORREGIDO: Función para obtener información del proyecto
    fun obtenerInfoProyecto(): Map<String, String> {
        return try {
            // ✅ CORREGIDO: Especificar explícitamente los tipos Pair<String, String>
            mapOf<String, String>(
                "firestore_initialized" to firestore.app.name,
                "storage_initialized" to storage.app.name,
                "project_id" to (firestore.app.options.projectId ?: "No disponible"),
                "storage_bucket" to (storage.app.options.storageBucket ?: "No configurado")
            )
        } catch (e: Exception) {
            mapOf("error" to (e.message ?: "Error desconocido"))
        }
    }

    // ✅ AGREGADO: Función más simple para debugging
    fun logEstadoFirebase() {
        val estado = verificarEstadoFirebase()
        if (estado) {
            Log.i("FirebaseStatus", "🔥 Firebase CONECTADO - Proyecto: ${firestore.app.options.projectId}")
            Log.i("FirebaseStatus", "📦 Storage Bucket: ${storage.app.options.storageBucket}")
        } else {
            Log.e("FirebaseStatus", "💥 Firebase DESCONECTADO")
        }
    }

    // ✅ NUEVO: Función específica para diagnosticar Storage
    fun diagnosticarStorage(): Map<String, String> {
        return try {
            val bucket = storage.app.options.storageBucket
            if (bucket.isNullOrEmpty()) {
                // ✅ CORREGIDO: Especificar tipo explícito
                mapOf<String, String>(
                    "status" to "ERROR",
                    "message" to "Bucket de Storage NO CONFIGURADO",
                    "solution" to "Ve a Firebase Console > Storage > Comenzar"
                )
            } else {
                // ✅ CORREGIDO: Especificar tipo explícito
                mapOf<String, String>(
                    "status" to "OK",
                    "bucket" to bucket,
                    "project_id" to (storage.app.options.projectId ?: "No disponible")
                )
            }
        } catch (e: Exception) {
            // ✅ CORREGIDO: Especificar tipo explícito
            mapOf<String, String>(
                "status" to "ERROR",
                "message" to (e.message ?: "Error desconocido"),
                "exception" to e.javaClass.simpleName
            )
        }
    }

    // ✅ NUEVO: Función para probar subida a Storage
    fun probarSubidaStorage(onSuccess: (String) -> Unit, onError: (String) -> Unit) {
        CoroutineScope(Dispatchers.IO).launch {
            try {
                Log.d("StorageTest", "🧪 Iniciando prueba de Storage...")

                val bucket = storage.app.options.storageBucket
                if (bucket.isNullOrEmpty()) {
                    onError("Bucket de Storage no configurado")
                    return@launch
                }

                Log.d("StorageTest", "📦 Bucket detectado: $bucket")

                // Crear archivo de prueba
                val testFileName = "test_conexion_${System.currentTimeMillis()}.txt"
                val testRef = storage.reference.child(testFileName)
                val testData = "Prueba de conexión Firebase Storage - ${java.util.Date()}"

                // Subir archivo
                testRef.putBytes(testData.toByteArray()).await()
                Log.d("StorageTest", "✅ Archivo subido exitosamente")

                // Obtener URL
                val url = testRef.downloadUrl.await()
                Log.d("StorageTest", "🔗 URL obtenida: $url")

                onSuccess("✅ Storage funciona\nBucket: $bucket\nURL: $url")

            } catch (e: Exception) {
                Log.e("StorageTest", "❌ Error en prueba Storage: ${e.message}")

                val errorMessage = when {
                    e.message?.contains("404") == true -> "❌ ERROR 404: El bucket no existe\n💡 Ve a Firebase Console > Storage > Comenzar"
                    e.message?.contains("permission") == true -> "❌ ERROR Permisos: Revisa las reglas de Storage\n💡 Configura reglas temporales en Firebase Console"
                    e.message?.contains("network") == true -> "❌ ERROR Red: Verifica tu conexión a internet"
                    else -> "❌ Error: ${e.message}"
                }

                onError(errorMessage)
            }
        }
    }
}
```
# Notificaciones.kt
```

package mx.edu.utng.mrs.mycomunidad.datos.modelo

import android.os.Parcelable
import kotlinx.parcelize.Parcelize
/**
 * Modelo de datos para representar una notificación en el sistema
 *
 * @property id Identificador único de la notificación
 * @property titulo Título de la notificación
 * @property mensaje Contenido detallado de la notificación
 * @property idUsuarioDestino ID del usuario destinatario de la notificación
 * @property idRemitente ID del usuario que envía la notificación (opcional)
 * @property tipo Tipo de notificación (ej: "reporte", "comentario", "sistema")
 * @property leida Indica si la notificación ha sido leída
 * @property fechaHora Fecha y hora de creación de la notificación
 */
@Parcelize
data class Notificacion(
    val id: String = "",
    val titulo: String = "",
    val mensaje: String = "",
    val tipo: String = "general", // "nuevo_reporte", "actualizacion_reporte", "nuevo_comentario", "reporte_resuelto"
    val usuarioId: String = "", // Usuario destinatario
    val datosExtra: Map<String, String> = emptyMap(),
    val fecha: Long = System.currentTimeMillis(),
    val leida: Boolean = false
) : Parcelable {

    fun toMap(): Map<String, Any> {
        return mapOf(
            "id" to id,
            "titulo" to titulo,
            "mensaje" to mensaje,
            "tipo" to tipo,
            "usuarioId" to usuarioId,
            "datosExtra" to datosExtra,
            "fecha" to fecha,
            "leida" to leida
        )
    }
}
```
# Reportes
```
package mx.edu.utng.mrs.mycomunidad.datos.modelo

import android.os.Parcelable
import kotlinx.parcelize.Parcelize
/**
 * Modelo de datos para representar un reporte en el sistema
 *
 * @property id Identificador único del reporte
 * @property titulo Título del reporte
 * @property descripcion Descripción detallada del problema
 * @property idUsuario ID del usuario que creó el reporte
 * @property estado Estado actual del reporte (ej: "pendiente", "en_proceso", "resuelto")
 * @property prioridad Nivel de prioridad (ej: "baja", "media", "alta")
 * @property fechaCreacion Fecha y hora de creación del reporte
 * @property fechaActualizacion Fecha y hora de última actualización
 * @property ubicacion Ubicación asociada al reporte (opcional)
 */
@Parcelize
data class Reporte(
    val id: String = "",
    val titulo: String = "",
    val descripcion: String = "",
    val tipo: TipoReporte = TipoReporte.OTRO,
    val gravedad: String = "Media",
    val latitud: Double = 0.0,
    val longitud: Double = 0.0,
    val usuarioId: String = "",
    val usuarioNombre: String = "",
    val usuarioEmail: String = "",
    val fechaCreacion: Long = System.currentTimeMillis(),
    val fechaActualizacion: Long = System.currentTimeMillis(),
    val estado: EstadoReporte = EstadoReporte.PENDIENTE,
    val imagenUrls: List<String> = emptyList(),
    val comentarios: List<Comentario> = emptyList(),
    val meGustas: List<String> = emptyList() // Lista de user IDs que dieron like
) : Parcelable {

    fun toMap(): Map<String, Any> {
        return mapOf(
            "id" to id,
            "titulo" to titulo,
            "descripcion" to descripcion,
            "tipo" to tipo.name,
            "gravedad" to gravedad,
            "latitud" to latitud,
            "longitud" to longitud,
            "usuarioId" to usuarioId,
            "usuarioNombre" to usuarioNombre,
            "usuarioEmail" to usuarioEmail,
            "fechaCreacion" to fechaCreacion,
            "fechaActualizacion" to fechaActualizacion,
            "estado" to estado.name,
            "imagenUrls" to imagenUrls,
            "comentarios" to comentarios.map { it.toMap() },
            "meGustas" to meGustas
        )
    }
}

enum class TipoReporte {
    BACHE, ALUMBRADO, BASURA, AGUA, OTRO
}

enum class EstadoReporte {
    PENDIENTE, APROBADO, RECHAZADO, RESUELTO
}
```
# Ubicacion.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.modelo

import android.os.Parcelable
import kotlinx.parcelize.Parcelize // ✅ CORRECTO
/**
 * Modelo de datos para representar una ubicación geográfica
 *
 * @property latitud Coordenada de latitud
 * @property longitud Coordenada de longitud
 * @property direccion Descripción textual de la dirección (opcional)
 */
@Parcelize
data class Ubicacion(
    val latitud: Double = 0.0,
    val longitud: Double = 0.0,
    val direccion: String = ""
) : Parcelable
```
# Usuario.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.modelo

import android.os.Parcelable
import kotlinx.parcelize.Parcelize
/**
 * Modelo de datos para representar un usuario en el sistema
 *
 * @property id Identificador único del usuario
 * @property nombre Nombre completo del usuario
 * @property email Dirección de correo electrónico
 * @property telefono Número de teléfono (opcional)
 * @property rol Rol del usuario en el sistema (ej: "usuario", "admin", "tecnico")
 * @property fechaRegistro Fecha de registro del usuario
 * @property activo Indica si la cuenta está activa
 */
@Parcelize
data class Usuario(
    val id: String = "",
    val email: String = "",
    val nombre: String = "",
    val rol: RolUsuario = RolUsuario.USUARIO,
    val imagenPerfil: String? = null,
    val fechaCreacion: Long = System.currentTimeMillis(),
    val estaActivo: Boolean = true,
    val tokenFCM: String? = null
) : Parcelable {

    fun toMap(): Map<String, Any> {
        return mapOf(
            "id" to id,
            "email" to email,
            "nombre" to nombre,
            "rol" to rol.name,
            "imagenPerfil" to (imagenPerfil ?: ""),
            "fechaCreacion" to fechaCreacion,
            "estaActivo" to estaActivo,
            "tokenFCM" to (tokenFCM ?: "")
        )
    }
}

enum class RolUsuario {
    USUARIO, ADMINISTRADOR
}
```
# RepositoryAutoAuthentication.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.repositorio

import com.google.firebase.auth.FirebaseAuth
import com.google.firebase.firestore.FirebaseFirestore
import kotlinx.coroutines.tasks.await
import mx.edu.utng.mrs.mycomunidad.datos.modelo.RolUsuario
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Usuario
import javax.inject.Inject

/**
 * Repositorio encargado de centralizar el acceso a los datos.
 * Combina datos de fuentes locales, remotas o servicios externos.
 */
class RepositorioAutenticacion @Inject constructor() {


    /**
     * Verifica si hay un usuario autenticado automáticamente
     * @return Usuario de Firebase si está autenticado, null en caso contrario
     */
    private val auth = FirebaseAuth.getInstance()
    private val db = FirebaseFirestore.getInstance()

    /**
     * Obtiene la información del usuario autenticado desde Firestore
     * @param userId ID del usuario
     * @return Objeto Usuario si existe, null en caso contrario
     * @throws Exception si ocurre un error en la consulta
     */
    suspend fun registrarUsuario(nombre: String, email: String, contrasena: String): Result<Usuario> {
        return try {
            val resultado = auth.createUserWithEmailAndPassword(email, contrasena).await()

            resultado.user?.let { usuarioFirebase ->
                val usuario = Usuario(
                    id = usuarioFirebase.uid,
                    email = email,
                    nombre = nombre,
                    rol = RolUsuario.USUARIO,
                    fechaCreacion = System.currentTimeMillis(),
                    estaActivo = true
                )

                db.collection("usuarios")
                    .document(usuarioFirebase.uid)
                    .set(usuario.toMap())
                    .await()

                Result.success(usuario)
            } ?: Result.failure(Exception("No se pudo crear el usuario en Firebase Auth"))

        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun iniciarSesion(email: String, contrasena: String): Result<Usuario> {
        return try {
            val resultado = auth.signInWithEmailAndPassword(email, contrasena).await()
            val usuarioFirebase = resultado.user
            if (usuarioFirebase != null) {
                val usuario = obtenerUsuarioDesdeFirestore(usuarioFirebase.uid)
                Result.success(usuario)
            } else {
                Result.failure(Exception("Error al iniciar sesión"))
            }
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun cerrarSesion(): Result<Boolean> {
        return try {
            auth.signOut()
            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    private suspend fun obtenerUsuarioDesdeFirestore(usuarioId: String): Usuario {
        return try {
            val documento = db.collection("usuarios")
                .document(usuarioId)
                .get()
                .await()

            if (documento.exists()) {
                Usuario(
                    id = documento.getString("id") ?: usuarioId,
                    email = documento.getString("email") ?: "",
                    nombre = documento.getString("nombre") ?: "Usuario",
                    rol = documento.getString("rol")?.let {
                        try { RolUsuario.valueOf(it) } catch (e: Exception) { RolUsuario.USUARIO }
                    } ?: RolUsuario.USUARIO,
                    imagenPerfil = documento.getString("imagenPerfil"),
                    fechaCreacion = documento.getLong("fechaCreacion") ?: System.currentTimeMillis(),
                    estaActivo = documento.getBoolean("estaActivo") ?: true
                )
            } else {
                Usuario(
                    id = usuarioId,
                    email = auth.currentUser?.email ?: "",
                    nombre = auth.currentUser?.displayName ?: "Usuario",
                    fechaCreacion = System.currentTimeMillis()
                )
            }
        } catch (e: Exception) {
            Usuario(
                id = usuarioId,
                email = auth.currentUser?.email ?: "",
                nombre = auth.currentUser?.displayName ?: "Usuario",
                fechaCreacion = System.currentTimeMillis()
            )
        }
    }

    fun obtenerUsuarioActual(): Usuario? {
        val usuarioFirebase = auth.currentUser
        println("🔄 [RepositorioAutenticacion] Verificando usuario actual...")
        println("   🔥 UID: ${usuarioFirebase?.uid ?: "NULL"}")
        println("   📧 Email: ${usuarioFirebase?.email ?: "NULL"}")
        println("   👤 Nombre: ${usuarioFirebase?.displayName ?: "NULL"}")

        return if (usuarioFirebase != null) {
            Usuario(
                id = usuarioFirebase.uid,
                email = usuarioFirebase.email ?: "",
                nombre = usuarioFirebase.displayName ?: "Usuario"
            ).also {
                println("✅ [RepositorioAutenticacion] Usuario básico creado: ${it.id}")
            }
        } else {
            println("❌ [RepositorioAutenticacion] No hay usuario autenticado")
            null
        }
    }
}
```
# RepositoryComentarios.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.repositorio

import com.google.firebase.auth.FirebaseAuth
import com.google.firebase.firestore.FieldValue
import com.google.firebase.firestore.FirebaseFirestore
import com.google.firebase.firestore.Query
import kotlinx.coroutines.channels.awaitClose
import kotlinx.coroutines.flow.Flow
import kotlinx.coroutines.flow.callbackFlow
import kotlinx.coroutines.tasks.await
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Comentario
import java.util.*
import javax.inject.Inject

/**
 * Repositorio para manejar operaciones CRUD de comentarios
 */
class RepositorioComentarios @Inject constructor() {
    /**
     * Crea un nuevo comentario en Firestore
     * @param comentario Objeto Comentario a crear
     * @return ID del comentario creado
     * @throws Exception si ocurre un error en la creación
     */
    private val auth = FirebaseAuth.getInstance()
    private val db = FirebaseFirestore.getInstance()
    /**
     * Obtiene comentarios por ID de reporte
     * @param idReporte ID del reporte
     * @return Lista de comentarios asociados al reporte
     * @throws Exception si ocurre un error en la consulta
     */
    suspend fun agregarComentario(
        reporteId: String,
        texto: String
    ): Result<Comentario> {
        return try {
            val usuario = auth.currentUser
            if (usuario == null) {
                return Result.failure(Exception("Usuario no autenticado"))
            }

            val comentario = Comentario(
                id = UUID.randomUUID().toString(),
                texto = texto.trim(),
                usuarioId = usuario.uid,
                usuarioNombre = usuario.displayName ?: "Usuario",
                fecha = System.currentTimeMillis()
            )

            db.collection("reportes")
                .document(reporteId)
                .update("comentarios", FieldValue.arrayUnion(comentario.toMap()))
                .await()

            Result.success(comentario)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    fun obtenerComentariosPorReporte(reporteId: String): Flow<List<Comentario>> = callbackFlow {
        val listener = db.collection("reportes")
            .document(reporteId)
            .addSnapshotListener { snapshot, error ->
                if (error != null) {
                    trySend(emptyList())
                    return@addSnapshotListener
                }

                val comentarios = if (snapshot != null && snapshot.exists()) {
                    val comentariosFirestore = snapshot.get("comentarios") as? List<Map<String, Any>> ?: emptyList()
                    comentariosFirestore.map { mapaComentario ->
                        Comentario(
                            id = mapaComentario["id"] as? String ?: "",
                            texto = mapaComentario["texto"] as? String ?: "",
                            usuarioId = mapaComentario["usuarioId"] as? String ?: "",
                            usuarioNombre = mapaComentario["usuarioNombre"] as? String ?: "Usuario",
                            fecha = mapaComentario["fecha"] as? Long ?: System.currentTimeMillis(),
                            editado = mapaComentario["editado"] as? Boolean ?: false,
                            fechaEdicion = mapaComentario["fechaEdicion"] as? Long
                        )
                    }.sortedByDescending { it.fecha }
                } else {
                    emptyList()
                }

                trySend(comentarios)
            }

        awaitClose { listener.remove() }
    }

    /**
     * Elimina un comentario por su ID
     * @param idComentario ID del comentario a eliminar
     * @throws Exception si ocurre un error en la eliminación
     */
    suspend fun eliminarComentario(
        reporteId: String,
        comentarioId: String,
        usuarioId: String,
        esAdmin: Boolean = false
    ): Result<Boolean> {
        return try {
            val reporte = db.collection("reportes")
                .document(reporteId)
                .get()
                .await()

            if (!reporte.exists()) {
                return Result.failure(Exception("Reporte no encontrado"))
            }

            val comentariosFirestore = reporte.get("comentarios") as? List<Map<String, Any>> ?: emptyList()
            val comentarioAEliminar = comentariosFirestore.find { it["id"] == comentarioId }

            if (comentarioAEliminar == null) {
                return Result.failure(Exception("Comentario no encontrado"))
            }

            val comentarioUsuarioId = comentarioAEliminar["usuarioId"] as? String ?: ""

            if (comentarioUsuarioId != usuarioId && !esAdmin) {
                return Result.failure(Exception("No tienes permisos para eliminar este comentario"))
            }

            db.collection("reportes")
                .document(reporteId)
                .update("comentarios", FieldValue.arrayRemove(comentarioAEliminar))
                .await()

            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun editarComentario(
        reporteId: String,
        comentarioId: String,
        nuevoTexto: String,
        usuarioId: String
    ): Result<Boolean> {
        return try {
            val reporte = db.collection("reportes")
                .document(reporteId)
                .get()
                .await()

            if (!reporte.exists()) {
                return Result.failure(Exception("Reporte no encontrado"))
            }

            val comentariosFirestore = reporte.get("comentarios") as? List<Map<String, Any>> ?: emptyList()
            val comentarioIndex = comentariosFirestore.indexOfFirst { it["id"] == comentarioId }

            if (comentarioIndex == -1) {
                return Result.failure(Exception("Comentario no encontrado"))
            }

            val comentario = comentariosFirestore[comentarioIndex]
            val comentarioUsuarioId = comentario["usuarioId"] as? String ?: ""
            if (comentarioUsuarioId != usuarioId) {
                return Result.failure(Exception("No tienes permisos para editar este comentario"))
            }

            val comentarioEditado = comentario.toMutableMap().apply {
                put("texto", nuevoTexto.trim())
                put("editado", true)
                put("fechaEdicion", System.currentTimeMillis())
            }

            val nuevosComentarios = comentariosFirestore.toMutableList().apply {
                set(comentarioIndex, comentarioEditado)
            }

            db.collection("reportes")
                .document(reporteId)
                .update("comentarios", nuevosComentarios)
                .await()

            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun obtenerCantidadComentarios(reporteId: String): Int {
        return try {
            val reporte = db.collection("reportes")
                .document(reporteId)
                .get()
                .await()

            if (reporte.exists()) {
                val comentarios = reporte.get("comentarios") as? List<Map<String, Any>> ?: emptyList()
                comentarios.size
            } else {
                0
            }
        } catch (e: Exception) {
            0
        }
    }
}
```
# RepositoryNotificaciones.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.repositorio

import android.util.Log
import com.google.firebase.auth.FirebaseAuth
import com.google.firebase.firestore.FieldValue
import com.google.firebase.firestore.FirebaseFirestore
import com.google.firebase.messaging.FirebaseMessaging
import kotlinx.coroutines.tasks.await
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Notificacion
import javax.inject.Inject
import javax.inject.Singleton
/**
 * Repositorio para manejar operaciones CRUD de notificaciones
 */
@Singleton
class RepositorioNotificaciones @Inject constructor() {
    /**
     * Crea una nueva notificación en Firestore
     * @param notificacion Objeto Notificacion a crear
     * @return ID de la notificación creada
     * @throws Exception si ocurre un error en la creación
     */
    private val auth = FirebaseAuth.getInstance()
    private val db = FirebaseFirestore.getInstance()
    private val messaging = FirebaseMessaging.getInstance()

    companion object {
        private const val TAG = "RepositorioNotificaciones"
    }

    /**
     * Obtiene notificaciones por ID de usuario destinatario
     * @param idUsuario ID del usuario destinatario
     * @return Lista de notificaciones del usuario
     * @throws Exception si ocurre un error en la consulta
     */
    suspend fun guardarTokenUsuario(token: String): Result<Boolean> {
        return try {
            val usuarioId = auth.currentUser?.uid ?: return Result.failure(Exception("Usuario no autenticado"))

            db.collection("usuarios")
                .document(usuarioId)
                .update("tokenFCM", token)
                .await()

            Log.d(TAG, "✅ Token FCM guardado para usuario: $usuarioId")
            Result.success(true)
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error guardando token FCM: ${e.message}")
            Result.failure(e)
        }
    }
    /**
     * Marca una notificación como leída
     * @param idNotificacion ID de la notificación
     * @throws Exception si ocurre un error en la actualización
     */
    suspend fun obtenerTokenUsuario(): String? {
        return try {
            val usuarioId = auth.currentUser?.uid ?: return null
            val documento = db.collection("usuarios")
                .document(usuarioId)
                .get()
                .await()
            val token = documento.getString("tokenFCM")
            Log.d(TAG, "📱 Token FCM obtenido: ${token?.take(10)}...")
            token
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo token FCM: ${e.message}")
            null
        }
    }

    suspend fun obtenerTokensAdministradores(): List<String> {
        return try {
            val snapshot = db.collection("usuarios")
                .whereEqualTo("rol", "ADMINISTRADOR")
                .whereEqualTo("estaActivo", true)
                .get()
                .await()

            val tokens = snapshot.documents.mapNotNull { documento ->
                documento.getString("tokenFCM")
            }.filter { it.isNotBlank() }

            Log.d(TAG, "👥 Tokens de administradores encontrados: ${tokens.size}")
            tokens
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo tokens de administradores: ${e.message}")
            emptyList()
        }
    }

    suspend fun obtenerTokenUsuarioPorId(usuarioId: String): String? {
        return try {
            val documento = db.collection("usuarios")
                .document(usuarioId)
                .get()
                .await()
            val token = documento.getString("tokenFCM")
            Log.d(TAG, "🔍 Token FCM para usuario $usuarioId: ${token?.take(10)}...")
            token
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo token FCM para usuario $usuarioId: ${e.message}")
            null
        }
    }

    fun suscribirATemas(esAdministrador: Boolean = false) {
        try {
            messaging.subscribeToTopic("todos")
                .addOnCompleteListener { task ->
                    if (task.isSuccessful) {
                        Log.d(TAG, "✅ Suscrito al tema 'todos'")
                    } else {
                        Log.e(TAG, "❌ Error suscribiendo al tema 'todos': ${task.exception}")
                    }
                }

            if (esAdministrador) {
                messaging.subscribeToTopic("administradores")
                    .addOnCompleteListener { task ->
                        if (task.isSuccessful) {
                            Log.d(TAG, "✅ Suscrito al tema 'administradores'")
                        } else {
                            Log.e(TAG, "❌ Error suscribiendo al tema 'administradores': ${task.exception}")
                        }
                    }
            }

            messaging.subscribeToTopic("usuarios")
                .addOnCompleteListener { task ->
                    if (task.isSuccessful) {
                        Log.d(TAG, "✅ Suscrito al tema 'usuarios'")
                    } else {
                        Log.e(TAG, "❌ Error suscribiendo al tema 'usuarios': ${task.exception}")
                    }
                }
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error en suscripción a temas: ${e.message}")
        }
    }

    suspend fun guardarNotificacionEnHistorial(notificacion: Notificacion): Result<Boolean> {
        return try {
            db.collection("notificaciones")
                .document(notificacion.id)
                .set(notificacion.toMap())
                .await()
            Log.d(TAG, "📝 Notificación guardada en historial: ${notificacion.id}")
            Result.success(true)
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error guardando notificación en historial: ${e.message}")
            Result.failure(e)
        }
    }

    suspend fun obtenerHistorialNotificaciones(usuarioId: String): List<Notificacion> {
        return try {
            val snapshot = db.collection("notificaciones")
                .whereEqualTo("usuarioId", usuarioId)
                .orderBy("fecha", com.google.firebase.firestore.Query.Direction.DESCENDING)
                .limit(50)
                .get()
                .await()

            val notificaciones = snapshot.documents.map { documento ->
                Notificacion(
                    id = documento.id,
                    titulo = documento.getString("titulo") ?: "",
                    mensaje = documento.getString("mensaje") ?: "",
                    tipo = documento.getString("tipo") ?: "general",
                    usuarioId = documento.getString("usuarioId") ?: "",
                    datosExtra = (documento.get("datosExtra") as? Map<String, String>) ?: emptyMap(),
                    fecha = documento.getLong("fecha") ?: System.currentTimeMillis(),
                    leida = documento.getBoolean("leida") ?: false
                )
            }

            Log.d(TAG, "📋 Historial de notificaciones obtenido: ${notificaciones.size}")
            notificaciones
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo historial de notificaciones: ${e.message}")
            emptyList()
        }
    }

    suspend fun marcarNotificacionLeida(notificacionId: String): Result<Boolean> {
        return try {
            db.collection("notificaciones")
                .document(notificacionId)
                .update("leida", true)
                .await()
            Log.d(TAG, "✅ Notificación marcada como leída: $notificacionId")
            Result.success(true)
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error marcando notificación como leída: ${e.message}")
            Result.failure(e)
        }
    }

    suspend fun obtenerCantidadNoLeidas(usuarioId: String): Int {
        return try {
            val snapshot = db.collection("notificaciones")
                .whereEqualTo("usuarioId", usuarioId)
                .whereEqualTo("leida", false)
                .get()
                .await()
            val cantidad = snapshot.size()
            Log.d(TAG, "🔔 Notificaciones no leídas: $cantidad")
            cantidad
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo notificaciones no leídas: ${e.message}")
            0
        }
    }
}
```
# RepositoryReportes.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.repositorio

import android.net.Uri
import android.util.Log
import com.google.firebase.auth.FirebaseAuth
import com.google.firebase.firestore.FieldValue
import com.google.firebase.firestore.FirebaseFirestore
import com.google.firebase.firestore.Query
import com.google.firebase.storage.FirebaseStorage
import kotlinx.coroutines.tasks.await
import mx.edu.utng.mrs.mycomunidad.datos.fuente_datos.ServicioFirebase
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Comentario
import mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import java.util.*
import javax.inject.Inject
/**
 * Repositorio para manejar operaciones CRUD de reportes
 */
class RepositorioReportes @Inject constructor(
    /**
     * Crea un nuevo reporte en Firestore
     * @param reporte Objeto Reporte a crear
     * @return ID del reporte creado
     * @throws Exception si ocurre un error en la creación
     */
    private val servicioFirebase: ServicioFirebase
) {

    private val auth = FirebaseAuth.getInstance()
    private val db = FirebaseFirestore.getInstance()
    private val storage: FirebaseStorage get() = servicioFirebase.storage

    companion object {
        private const val TAG = "RepositorioReportes"
    }
    /**
     * Obtiene reportes por ID de usuario
     * @param idUsuario ID del usuario
     * @return Lista de reportes del usuario
     * @throws Exception si ocurre un error en la consulta
     */

    suspend fun crearReporte(
        titulo: String,
        descripcion: String,
        tipo: TipoReporte,
        gravedad: String,
        latitud: Double,
        longitud: Double,
        imagenes: List<Uri> = emptyList()
    ): Result<Reporte> {
        return try {
            Log.d(TAG, "🔄 Iniciando creación de reporte...")

            val usuario = auth.currentUser
            if (usuario == null) {
                Log.e(TAG, "❌ Usuario no autenticado")
                return Result.failure(Exception("Usuario no autenticado"))
            }

            // ✅ CORREGIDO: Obtener información COMPLETA del usuario
            Log.d(TAG, "👤 Información del usuario Firebase:")
            Log.d(TAG, "   ID: ${usuario.uid}")
            Log.d(TAG, "   DisplayName: ${usuario.displayName ?: "NULO"}")
            Log.d(TAG, "   Email: ${usuario.email ?: "NULO"}")

            // ✅ CORREGIDO: Obtener información REAL del usuario desde Firestore
            var nombreUsuario = usuario.displayName
            var emailUsuario = usuario.email

            try {
                // Buscar información adicional en la colección "usuarios"
                val usuarioDoc = db.collection("usuarios")
                    .whereEqualTo("userId", usuario.uid)
                    .limit(1)
                    .get()
                    .await()

                if (!usuarioDoc.isEmpty && usuarioDoc.documents.isNotEmpty()) {
                    val doc = usuarioDoc.documents[0]
                    val nombreFirestore = doc.getString("nombre") ?: doc.getString("nombreCompleto")
                    val emailFirestore = doc.getString("email")

                    if (!nombreFirestore.isNullOrBlank()) {
                        nombreUsuario = nombreFirestore
                        Log.d(TAG, "✅ Nombre obtenido de Firestore: $nombreUsuario")
                    }

                    if (!emailFirestore.isNullOrBlank()) {
                        emailUsuario = emailFirestore
                        Log.d(TAG, "✅ Email obtenido de Firestore: $emailUsuario")
                    }
                } else {
                    Log.w(TAG, "⚠️ No se encontró documento de usuario en Firestore para ID: ${usuario.uid}")
                    Log.w(TAG, "🔍 Intentando con documento directo...")

                    // Intentar con documento directo
                    try {
                        val directDoc = db.collection("usuarios")
                            .document(usuario.uid)
                            .get()
                            .await()

                        if (directDoc.exists()) {
                            val nombreDirecto = directDoc.getString("nombre") ?: directDoc.getString("nombreCompleto")
                            val emailDirecto = directDoc.getString("email")

                            if (!nombreDirecto.isNullOrBlank()) {
                                nombreUsuario = nombreDirecto
                                Log.d(TAG, "✅ Nombre obtenido de documento directo: $nombreUsuario")
                            }

                            if (!emailDirecto.isNullOrBlank()) {
                                emailUsuario = emailDirecto
                                Log.d(TAG, "✅ Email obtenido de documento directo: $emailUsuario")
                            }
                        }
                    } catch (e: Exception) {
                        Log.w(TAG, "⚠️ Error obteniendo usuario por documento directo: ${e.message}")
                    }
                }
            } catch (e: Exception) {
                Log.w(TAG, "⚠️ Error obteniendo usuario de Firestore: ${e.message}")
            }

            // ✅ Usar valores REALES o por defecto si no se encontró información
            val nombreFinal = if (nombreUsuario.isNullOrBlank()) {
                "Usuario ${usuario.uid.take(8)}..."
            } else {
                nombreUsuario
            }

            val emailFinal = if (emailUsuario.isNullOrBlank()) {
                "usuario@example.com"
            } else {
                emailUsuario
            }

            Log.d(TAG, "👤 Información FINAL para reporte:")
            Log.d(TAG, "   Nombre: $nombreFinal")
            Log.d(TAG, "   Email: $emailFinal")

            // Subir imágenes
            val urlsImagenes = mutableListOf<String>()
            if (imagenes.isNotEmpty()) {
                Log.d(TAG, "📤 Subiendo ${imagenes.size} imagen(es)...")
                for ((index, uri) in imagenes.withIndex()) {
                    try {
                        val url = subirImagen(uri)
                        if (url.startsWith("http")) {
                            urlsImagenes.add(url)
                            Log.d(TAG, "✅ Imagen $index subida: $url")
                        }
                    } catch (e: Exception) {
                        Log.e(TAG, "❌ Error subiendo imagen $index: ${e.message}")
                    }
                }
            }

            // ✅ CORREGIDO: Crear el reporte con información REAL del usuario
            val reporte = Reporte(
                id = UUID.randomUUID().toString(),
                titulo = titulo,
                descripcion = descripcion,
                tipo = tipo,
                gravedad = gravedad,
                latitud = latitud,
                longitud = longitud,
                usuarioId = usuario.uid,
                usuarioNombre = nombreFinal,  // ✅ Nombre real
                usuarioEmail = emailFinal,    // ✅ Email real
                fechaCreacion = System.currentTimeMillis(),
                fechaActualizacion = System.currentTimeMillis(),
                estado = EstadoReporte.PENDIENTE,
                imagenUrls = urlsImagenes,
                comentarios = emptyList(),
                meGustas = emptyList()
            )

            Log.d(TAG, "💾 Guardando reporte en Firestore:")
            Log.d(TAG, "   ID: ${reporte.id}")
            Log.d(TAG, "   Título: ${reporte.titulo}")
            Log.d(TAG, "   Usuario Nombre: ${reporte.usuarioNombre}")
            Log.d(TAG, "   Usuario Email: ${reporte.usuarioEmail}")
            Log.d(TAG, "   Usuario ID: ${reporte.usuarioId}")

            // ✅ CORREGIDO: Verificar datos antes de guardar
            val datosParaGuardar = reporte.toMap()
            Log.d(TAG, "📝 DATOS A GUARDAR (VERIFICACIÓN):")
            Log.d(TAG, "   usuarioNombre: ${datosParaGuardar["usuarioNombre"]}")
            Log.d(TAG, "   usuarioEmail: ${datosParaGuardar["usuarioEmail"]}")
            Log.d(TAG, "   usuarioId: ${datosParaGuardar["usuarioId"]}")

            // Guardar en Firestore
            db.collection("reportes")
                .document(reporte.id)
                .set(datosParaGuardar)
                .await()

            Log.d(TAG, "✅ Reporte creado exitosamente: ${reporte.id}")
            Result.success(reporte)
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error creando reporte: ${e.message}")
            Log.e(TAG, "📝 Stack trace completo:", e)
            Result.failure(e)
        }
    }

    private suspend fun subirImagen(uri: Uri): String {
        return try {
            val extension = when {
                uri.toString().contains(".png") -> "png"
                uri.toString().contains(".jpeg") -> "jpeg"
                else -> "jpg"
            }
            val nombreArchivo = "reportes/${UUID.randomUUID()}.$extension"

            val referencia = storage.reference.child(nombreArchivo)
            val uploadTask = referencia.putFile(uri)
            uploadTask.await()

            val url = referencia.downloadUrl.await()
            url.toString()
        } catch (e: Exception) {
            throw Exception("Error al subir imagen: ${e.message}")
        }
    }

    /**
     * Actualiza el estado de un reporte
     * @param idReporte ID del reporte
     * @param nuevoEstado Nuevo estado del reporte
     * @throws Exception si ocurre un error en la actualización
     */
    suspend fun obtenerReportePorId(reporteId: String): Reporte? {
        return try {
            Log.d(TAG, "🔍 Obteniendo reporte por ID: $reporteId")

            val documento = db.collection("reportes")
                .document(reporteId)
                .get()
                .await()

            if (documento.exists()) {
                // ✅ Convertir a Reporte
                val reporte = documento.toReporte()

                // ✅ DIAGNÓSTICO: Verificar información del usuario
                Log.d(TAG, "✅ Reporte obtenido por ID:")
                Log.d(TAG, "   Título: ${reporte.titulo}")
                Log.d(TAG, "   Usuario Nombre: ${reporte.usuarioNombre}")
                Log.d(TAG, "   Usuario Email: ${reporte.usuarioEmail}")
                Log.d(TAG, "   Usuario ID: ${reporte.usuarioId}")
                Log.d(TAG, "   ¿Nombre vacío?: ${reporte.usuarioNombre.isBlank()}")

                // ✅ Si el nombre está vacío, intentar obtenerlo desde otra fuente
                if (reporte.usuarioNombre.isBlank() || reporte.usuarioNombre == "Usuario") {
                    Log.w(TAG, "⚠️ Nombre de usuario está vacío o es 'Usuario'")
                    Log.w(TAG, "🔄 Intentando obtener información adicional...")

                    // Intentar obtener nombre desde la colección "usuarios"
                    try {
                        val usuarioDoc = db.collection("usuarios")
                            .document(reporte.usuarioId)
                            .get()
                            .await()

                        if (usuarioDoc.exists()) {
                            val nombreCompleto = usuarioDoc.getString("nombre") ?:
                            usuarioDoc.getString("nombreCompleto") ?:
                            usuarioDoc.getString("displayName")

                            if (!nombreCompleto.isNullOrBlank()) {
                                // Actualizar el nombre en el reporte
                                Log.d(TAG, "✅ Nombre obtenido de colección usuarios: $nombreCompleto")
                                // Crear nuevo reporte con nombre actualizado
                                return reporte.copy(usuarioNombre = nombreCompleto)
                            }
                        }
                    } catch (e: Exception) {
                        Log.w(TAG, "⚠️ No se pudo obtener nombre adicional: ${e.message}")
                    }
                }

                reporte
            } else {
                Log.w(TAG, "❌ Reporte no encontrado: $reporteId")
                null
            }
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo reporte por ID: ${e.message}")
            null
        }
    }

    suspend fun obtenerReportesPorUsuario(usuarioId: String): List<Reporte> {
        return try {
            Log.d(TAG, "🔍 Obteniendo reportes para usuario: $usuarioId")

            val snapshot = db.collection("reportes")
                .whereEqualTo("usuarioId", usuarioId)
                .orderBy("fechaCreacion", Query.Direction.DESCENDING)
                .get()
                .await()

            val reportes = snapshot.documents.mapNotNull { documento ->
                try {
                    val reporte = documento.toReporte()

                    // ✅ DIAGNÓSTICO para cada reporte
                    Log.d(TAG, "   📋 Reporte: ${reporte.titulo}")
                    Log.d(TAG, "      👤 Usuario: ${reporte.usuarioNombre}")
                    Log.d(TAG, "      📧 Email: ${reporte.usuarioEmail}")

                    reporte
                } catch (e: Exception) {
                    Log.e(TAG, "❌ Error convirtiendo documento: ${e.message}")
                    null
                }
            }

            Log.d(TAG, "✅ Total reportes encontrados: ${reportes.size}")
            reportes
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo reportes por usuario: ${e.message}")
            emptyList()
        }
    }

    suspend fun obtenerTodosLosReportes(): List<Reporte> {
        return try {
            Log.d(TAG, "🔍 Obteniendo TODOS los reportes...")

            val snapshot = db.collection("reportes")
                .orderBy("fechaCreacion", Query.Direction.DESCENDING)
                .get()
                .await()

            val reportes = snapshot.documents.map { documento ->
                documento.toReporte()
            }

            // ✅ DIAGNÓSTICO: Mostrar información de usuarios
            Log.d(TAG, "📊 RESUMEN DE REPORTES (${reportes.size}):")
            reportes.take(5).forEachIndexed { index, reporte ->
                Log.d(TAG, "   #${index + 1}: '${reporte.titulo}'")
                Log.d(TAG, "      👤 Por: ${reporte.usuarioNombre}")
                Log.d(TAG, "      📧 Email: ${reporte.usuarioEmail}")
            }

            reportes
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error obteniendo todos los reportes: ${e.message}")
            emptyList()
        }
    }

    suspend fun obtenerReportesPublicos(): List<Reporte> {
        return try {
            val snapshot = db.collection("reportes")
                .whereIn("estado", listOf(EstadoReporte.APROBADO.name, EstadoReporte.RESUELTO.name))
                .orderBy("fechaCreacion", Query.Direction.DESCENDING)
                .get()
                .await()

            snapshot.documents.map { documento ->
                documento.toReporte()
            }
        } catch (e: Exception) {
            emptyList()
        }
    }

    suspend fun obtenerReportesPorEstado(estado: EstadoReporte): List<Reporte> {
        return try {
            val snapshot = db.collection("reportes")
                .whereEqualTo("estado", estado.name)
                .orderBy("fechaCreacion", Query.Direction.DESCENDING)
                .get()
                .await()
            snapshot.documents.map { documento ->
                documento.toReporte()
            }
        } catch (e: Exception) {
            emptyList()
        }
    }

    suspend fun editarReporte(
        reporteId: String,
        titulo: String,
        descripcion: String,
        tipo: TipoReporte,
        gravedad: String,
        latitud: Double,
        longitud: Double
    ): Result<Boolean> {
        return try {
            val usuarioId = auth.currentUser?.uid ?: return Result.failure(Exception("Usuario no autenticado"))
            val reporte = obtenerReportePorId(reporteId)

            if (reporte != null && reporte.usuarioId == usuarioId) {
                val updates = hashMapOf<String, Any>(
                    "titulo" to titulo,
                    "descripcion" to descripcion,
                    "tipo" to tipo.name,
                    "gravedad" to gravedad,
                    "latitud" to latitud,
                    "longitud" to longitud,
                    "fechaActualizacion" to System.currentTimeMillis()
                )

                db.collection("reportes")
                    .document(reporteId)
                    .update(updates)
                    .await()

                Result.success(true)
            } else {
                Result.failure(Exception("No tienes permisos para editar este reporte"))
            }
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun actualizarEstadoReporte(reporteId: String, estado: EstadoReporte): Result<Boolean> {
        return try {
            db.collection("reportes")
                .document(reporteId)
                .update("estado", estado.name)
                .await()

            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun alternarMeGusta(reporteId: String): Result<Boolean> {
        return try {
            val usuarioId = auth.currentUser?.uid ?: return Result.failure(Exception("Usuario no autenticado"))
            val reporte = obtenerReportePorId(reporteId)

            reporte?.let {
                val meGustas = it.meGustas.toMutableList()
                if (meGustas.contains(usuarioId)) {
                    meGustas.remove(usuarioId)
                } else {
                    meGustas.add(usuarioId)
                }

                db.collection("reportes")
                    .document(reporteId)
                    .update("meGustas", meGustas)
                    .await()

                Result.success(true)
            } ?: Result.failure(Exception("Reporte no encontrado"))
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun eliminarReporte(reporteId: String): Result<Boolean> {
        return try {
            val usuarioId = auth.currentUser?.uid ?: return Result.failure(Exception("Usuario no autenticado"))
            val reporte = obtenerReportePorId(reporteId)

            if (reporte != null && reporte.usuarioId == usuarioId) {
                // Eliminar imágenes del Storage
                reporte.imagenUrls.forEach { url ->
                    try {
                        storage.getReferenceFromUrl(url).delete().await()
                    } catch (e: Exception) {
                        // Ignorar errores al eliminar imágenes
                    }
                }

                // Eliminar documento de Firestore
                db.collection("reportes")
                    .document(reporteId)
                    .delete()
                    .await()

                Result.success(true)
            } else {
                Result.failure(Exception("No tienes permisos para eliminar este reporte"))
            }
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun agregarComentario(
        reporteId: String,
        comentario: String,
        usuarioId: String,
        usuarioNombre: String
    ): Result<Boolean> {
        return try {
            val comentarioData = mapOf(
                "id" to UUID.randomUUID().toString(),
                "texto" to comentario,
                "usuarioId" to usuarioId,
                "usuarioNombre" to usuarioNombre,
                "fecha" to System.currentTimeMillis(),
                "editado" to false
            )

            db.collection("reportes")
                .document(reporteId)
                .update("comentarios", FieldValue.arrayUnion(comentarioData))
                .await()

            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun actualizarReporte(
        reporteId: String,
        titulo: String,
        descripcion: String,
        tipo: TipoReporte
    ): Result<Boolean> {
        return try {
            val updates = hashMapOf<String, Any>(
                "titulo" to titulo,
                "descripcion" to descripcion,
                "tipo" to tipo.name
            )

            db.collection("reportes")
                .document(reporteId)
                .update(updates)
                .await()

            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun probarStorage(): Result<String> {
        return try {
            val testRef = storage.reference.child("test/${System.currentTimeMillis()}.txt")
            val testData = "Prueba de conexión Firebase Storage ${System.currentTimeMillis()}"

            testRef.putBytes(testData.toByteArray()).await()
            val url = testRef.downloadUrl.await()

            Result.success("Storage funciona correctamente. URL: $url")
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    // ✅ FUNCIÓN MEJORADA para convertir DocumentSnapshot a Reporte
    private fun com.google.firebase.firestore.DocumentSnapshot.toReporte(): Reporte {
        return try {
            // ✅ 1. Obtener datos básicos
            val id = getString("id") ?: this.id
            val titulo = getString("titulo") ?: "Sin título"
            val descripcion = getString("descripcion") ?: "Sin descripción"

            // ✅ 2. Tipo
            val tipo = try {
                TipoReporte.valueOf(getString("tipo") ?: "OTRO")
            } catch (e: Exception) {
                TipoReporte.OTRO
            }

            // ✅ 3. Datos de ubicación
            val gravedad = getString("gravedad") ?: "Media"
            val latitud = getDouble("latitud") ?: 0.0
            val longitud = getDouble("longitud") ?: 0.0

            // ✅ 4. DATOS DEL USUARIO (CORREGIDO)
            val usuarioId = getString("usuarioId") ?: ""

            // ✅ Intentar obtener nombre de usuario de diferentes campos
            val usuarioNombre = when {
                !getString("usuarioNombre").isNullOrBlank() -> getString("usuarioNombre")!!
                !getString("nombreUsuario").isNullOrBlank() -> getString("nombreUsuario")!!
                !getString("userName").isNullOrBlank() -> getString("userName")!!
                !getString("displayName").isNullOrBlank() -> getString("displayName")!!
                !getString("authorName").isNullOrBlank() -> getString("authorName")!!
                else -> "Usuario ${usuarioId.take(8)}..."
            }

            // ✅ Intentar obtener email de usuario de diferentes campos
            val usuarioEmail = when {
                !getString("usuarioEmail").isNullOrBlank() -> getString("usuarioEmail")!!
                !getString("email").isNullOrBlank() -> getString("email")!!
                !getString("userEmail").isNullOrBlank() -> getString("userEmail")!!
                else -> "usuario@example.com"
            }

            // ✅ 5. Fechas
            val fechaCreacion = getLong("fechaCreacion") ?: System.currentTimeMillis()
            val fechaActualizacion = getLong("fechaActualizacion") ?: System.currentTimeMillis()

            // ✅ 6. Estado
            val estado = try {
                EstadoReporte.valueOf(getString("estado") ?: "PENDIENTE")
            } catch (e: Exception) {
                EstadoReporte.PENDIENTE
            }

            // ✅ 7. Imágenes
            val imagenUrls = mutableListOf<String>()
            val imagenesData = get("imagenUrls")

            when (imagenesData) {
                is List<*> -> {
                    imagenesData.forEach { item ->
                        when (item) {
                            is String -> imagenUrls.add(item)
                            is Map<*, *> -> {
                                val url = item["url"] as? String
                                url?.let { imagenUrls.add(it) }
                            }
                        }
                    }
                }
                is ArrayList<*> -> {
                    imagenesData.forEach { item ->
                        if (item is String) {
                            imagenUrls.add(item)
                        }
                    }
                }
            }

            // ✅ 8. Comentarios
            val comentariosFirestore = get("comentarios") as? List<Map<String, Any>> ?: emptyList()
            val comentarios = comentariosFirestore.mapNotNull { mapaComentario ->
                try {
                    Comentario(
                        id = mapaComentario["id"] as? String ?: "",
                        texto = mapaComentario["texto"] as? String ?: "",
                        usuarioId = mapaComentario["usuarioId"] as? String ?: "",
                        usuarioNombre = mapaComentario["usuarioNombre"] as? String ?: "Usuario",
                        fecha = mapaComentario["fecha"] as? Long ?: System.currentTimeMillis(),
                        editado = mapaComentario["editado"] as? Boolean ?: false
                    )
                } catch (e: Exception) {
                    null
                }
            }

            // ✅ 9. Me gustas
            val meGustas = (get("meGustas") as? List<String>) ?: emptyList()

            // ✅ 10. Crear Reporte
            Reporte(
                id = id,
                titulo = titulo,
                descripcion = descripcion,
                tipo = tipo,
                gravedad = gravedad,
                latitud = latitud,
                longitud = longitud,
                usuarioId = usuarioId,
                usuarioNombre = usuarioNombre,
                usuarioEmail = usuarioEmail,
                fechaCreacion = fechaCreacion,
                fechaActualizacion = fechaActualizacion,
                estado = estado,
                imagenUrls = imagenUrls,
                comentarios = comentarios,
                meGustas = meGustas
            )

        } catch (e: Exception) {
            Log.e(TAG, "❌ ERROR en toReporte: ${e.message}")

            // Retornar un reporte mínimo en caso de error
            Reporte(
                id = this.id,
                titulo = "Error al cargar",
                descripcion = "No se pudo cargar la información del reporte",
                tipo = TipoReporte.OTRO,
                gravedad = "Media",
                latitud = 0.0,
                longitud = 0.0,
                usuarioId = "",
                usuarioNombre = "Usuario",
                usuarioEmail = "",
                fechaCreacion = System.currentTimeMillis(),
                fechaActualizacion = System.currentTimeMillis(),
                estado = EstadoReporte.PENDIENTE,
                imagenUrls = emptyList(),
                comentarios = emptyList(),
                meGustas = emptyList()
            )
        }
    }
}
```
# RepositoryUsuario.kt
```
package mx.edu.utng.mrs.mycomunidad.datos.repositorio

import com.google.firebase.firestore.FieldValue
import com.google.firebase.firestore.FirebaseFirestore
import com.google.firebase.firestore.Query
import kotlinx.coroutines.channels.awaitClose
import kotlinx.coroutines.flow.Flow
import kotlinx.coroutines.flow.callbackFlow
import kotlinx.coroutines.tasks.await
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Usuario
import mx.edu.utng.mrs.mycomunidad.datos.modelo.RolUsuario
import javax.inject.Inject
import android.util.Log

/**
 * Repositorio para manejar operaciones CRUD de usuarios
 */
class RepositorioUsuarios @Inject constructor(
    /**
     * Crea un nuevo usuario en Firestore
     * @param usuario Objeto Usuario a crear
     * @return ID del usuario creado
     * @throws Exception si ocurre un error en la creación
     */
    private val firestore: FirebaseFirestore
) {

    init {
        Log.d("FIREBASE_DEBUG", "✅ RepositorioUsuarios inicializado")
    }

    fun obtenerTodosLosUsuarios(): Flow<List<Usuario>> = callbackFlow {
        Log.d("FIREBASE_DEBUG", "🔥 INICIANDO CONSULTA: collection('usuarios')")

        val listener = firestore.collection("usuarios")
            .addSnapshotListener { snapshot, error ->
                Log.d("FIREBASE_DEBUG", "📡 SNAPSHOT LISTENER ACTIVADO")

                if (error != null) {
                    Log.e("FIREBASE_DEBUG", "❌ ERROR Firestore: ${error.message}")
                    Log.e("FIREBASE_DEBUG", "❌ ERROR Code: ${error.code}")
                    trySend(emptyList())
                    return@addSnapshotListener
                }

                Log.d("FIREBASE_DEBUG", "📄 Snapshot recibido, documentos: ${snapshot?.documents?.size}")

                val usuarios = snapshot?.documents?.mapNotNull { documento ->
                    Log.d("FIREBASE_DEBUG", "📋 Procesando documento: ${documento.id}")
                    val usuario = documento.toUsuario()
                    if (usuario == null) {
                        Log.e("FIREBASE_DEBUG", "❌ Documento ${documento.id} no pudo convertirse a Usuario")
                    } else {
                        Log.d("FIREBASE_DEBUG", "👤 Usuario convertido: ${usuario.nombre} (${usuario.email})")
                    }
                    usuario
                } ?: emptyList()

                Log.d("FIREBASE_DEBUG", "👥 TOTAL usuarios finales: ${usuarios.size}")
                trySend(usuarios)
            }

        Log.d("FIREBASE_DEBUG", "🎯 Listener de Firestore registrado")

        awaitClose {
            Log.d("FIREBASE_DEBUG", "🔚 Listener removido")
            listener.remove()
        }
    }

    /**
     * Obtiene un usuario por su ID
     * @param userId ID del usuario
     * @return Objeto Usuario si existe, null en caso contrario
     * @throws Exception si ocurre un error en la consulta
     */
    suspend fun obtenerUsuariosDebug(): List<Usuario> {
        return try {
            Log.d("FIREBASE_DEBUG", "🔍 EJECUTANDO CONSULTA DIRECTA A FIRESTORE")
            val snapshot = firestore.collection("usuarios").get().await()
            Log.d("FIREBASE_DEBUG", "📊 Documentos obtenidos: ${snapshot.documents.size}")

            val usuarios = snapshot.documents.mapNotNull { documento ->
                val usuario = documento.toUsuario()
                if (usuario == null) {
                    Log.e("FIREBASE_DEBUG", "❌ Falló conversión del documento: ${documento.id}")
                    Log.e("FIREBASE_DEBUG", "📝 Datos del documento: ${documento.data}")
                }
                usuario
            }

            Log.d("FIREBASE_DEBUG", "✅ Usuarios convertidos: ${usuarios.size}")
            usuarios
        } catch (e: Exception) {
            Log.e("FIREBASE_DEBUG", "❌ Error en obtenerUsuariosDebug: ${e.message}")
            emptyList()
        }
    }

    /**
     * Actualiza la información de un usuario
     * @param userId ID del usuario a actualizar
     * @param usuario Objeto Usuario con los datos actualizados
     * @throws Exception si ocurre un error en la actualización
     */
    suspend fun obtenerUsuarioPorId(usuarioId: String): Usuario? {
        return try {
            val documento = firestore.collection("usuarios")
                .document(usuarioId)
                .get()
                .await()
            documento.toUsuario()
        } catch (e: Exception) {
            null
        }
    }


    /**
     * Desactiva la cuenta de un usuario
     * @param userId ID del usuario a desactivar
     * @throws Exception si ocurre un error en la actualización
     */ 
    suspend fun actualizarRolUsuario(usuarioId: String, nuevoRol: RolUsuario): Result<Boolean> {
        return try {
            firestore.collection("usuarios")
                .document(usuarioId)
                .update("rol", nuevoRol.name)
                .await()
            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun desactivarUsuario(usuarioId: String): Result<Boolean> {
        return try {
            firestore.collection("usuarios")
                .document(usuarioId)
                .update("estaActivo", false)
                .await()
            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun eliminarUsuario(usuarioId: String): Result<Boolean> {
        return try {
            firestore.collection("usuarios")
                .document(usuarioId)
                .delete()
                .await()
            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    fun buscarUsuariosPorNombre(nombre: String): Flow<List<Usuario>> = callbackFlow {
        val listener = firestore.collection("usuarios")
            .whereGreaterThanOrEqualTo("nombre", nombre)
            .whereLessThanOrEqualTo("nombre", nombre + "\uf8ff")
            .addSnapshotListener { snapshot, error ->
                if (error != null) {
                    trySend(emptyList())
                    return@addSnapshotListener
                }

                val usuarios = snapshot?.documents?.mapNotNull { documento ->
                    documento.toUsuario()
                } ?: emptyList()
                trySend(usuarios)
            }

        awaitClose { listener.remove() }
    }

    suspend fun actualizarPerfilUsuario(usuarioId: String, nombre: String, imagenUrl: String?): Result<Boolean> {
        return try {
            val updates = mutableMapOf<String, Any>()
            updates["nombre"] = nombre
            if (imagenUrl != null) {
                updates["imagenPerfil"] = imagenUrl
            }

            firestore.collection("usuarios")
                .document(usuarioId)
                .update(updates)
                .await()
            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    fun obtenerUsuariosPorRol(rol: RolUsuario): Flow<List<Usuario>> = callbackFlow {
        val listener = firestore.collection("usuarios")
            .whereEqualTo("rol", rol.name)
            .whereEqualTo("estaActivo", true)
            .addSnapshotListener { snapshot, error ->
                if (error != null) {
                    trySend(emptyList())
                    return@addSnapshotListener
                }

                val usuarios = snapshot?.documents?.mapNotNull { documento ->
                    documento.toUsuario()
                } ?: emptyList()
                trySend(usuarios)
            }

        awaitClose { listener.remove() }
    }

    suspend fun obtenerEstadisticasUsuarios(): Map<String, Int> {
        return try {
            val todosUsuarios = firestore.collection("usuarios").get().await()

            val total = todosUsuarios.size()
            val activos = todosUsuarios.count { it.getBoolean("estaActivo") ?: true }
            val administradores = todosUsuarios.count {
                it.getString("rol") == RolUsuario.ADMINISTRADOR.name
            }

            mapOf(
                "total" to total,
                "activos" to activos,
                "administradores" to administradores
            )
        } catch (e: Exception) {
            emptyMap()
        }
    }

    suspend fun activarUsuario(usuarioId: String): Result<Boolean> {
        return try {
            firestore.collection("usuarios")
                .document(usuarioId)
                .update("estaActivo", true)
                .await()
            Result.success(true)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun verificarEmailExistente(email: String): Boolean {
        return try {
            val snapshot = firestore.collection("usuarios")
                .whereEqualTo("email", email)
                .get()
                .await()
            !snapshot.isEmpty
        } catch (e: Exception) {
            false
        }
    }

    suspend fun actualizarUsuario(usuarioId: String, nombre: String, email: String): Result<Unit> {
        return try {
            val usuariosConEmail = firestore.collection("usuarios")
                .whereEqualTo("email", email)
                .get()
                .await()

            val emailExisteEnOtroUsuario = usuariosConEmail.documents.any { doc ->
                doc.id != usuarioId && doc.getString("email") == email
            }

            if (emailExisteEnOtroUsuario) {
                return Result.failure(Exception("El email ya está en uso por otro usuario"))
            }

            firestore.collection("usuarios")
                .document(usuarioId)
                .update(
                    mapOf(
                        "nombre" to nombre,
                        "email" to email
                    )
                )
                .await()

            Result.success(Unit)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun actualizarNombreUsuario(usuarioId: String, nuevoNombre: String): Result<Unit> {
        return try {
            firestore.collection("usuarios")
                .document(usuarioId)
                .update("nombre", nuevoNombre)
                .await()
            Result.success(Unit)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun actualizarEmailUsuario(usuarioId: String, nuevoEmail: String): Result<Unit> {
        return try {
            if (verificarEmailExistente(nuevoEmail)) {
                return Result.failure(Exception("El email ya está en uso"))
            }

            firestore.collection("usuarios")
                .document(usuarioId)
                .update("email", nuevoEmail)
                .await()
            Result.success(Unit)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun actualizarImagenPerfil(usuarioId: String, imagenUrl: String): Result<Unit> {
        return try {
            firestore.collection("usuarios")
                .document(usuarioId)
                .update("imagenPerfil", imagenUrl)
                .await()
            Result.success(Unit)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun obtenerEstadisticasUsuario(usuarioId: String): Map<String, Int> {
        return try {
            val reportesUsuario = firestore.collection("reportes")
                .whereEqualTo("usuarioId", usuarioId)
                .get()
                .await()

            val todosReportes = firestore.collection("reportes").get().await()
            var totalComentarios = 0

            todosReportes.documents.forEach { reporteDoc ->
                val comentarios = reporteDoc.get("comentarios") as? List<Map<String, Any>> ?: emptyList()
                totalComentarios += comentarios.count { comentario ->
                    comentario["usuarioId"] == usuarioId
                }
            }

            mapOf(
                "totalReportes" to reportesUsuario.size(),
                "totalComentarios" to totalComentarios,
                "reportesResueltos" to reportesUsuario.count {
                    it.getString("estado") == "RESUELTO"
                }
            )
        } catch (e: Exception) {
            mapOf(
                "totalReportes" to 0,
                "totalComentarios" to 0,
                "reportesResueltos" to 0
            )
        }
    }

    suspend fun cambiarContrasena(usuarioId: String, nuevaContrasena: String): Result<Unit> {
        return try {
            Result.success(Unit)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    suspend fun crearUsuario(usuario: Usuario): Result<Unit> {
        return try {
            if (verificarEmailExistente(usuario.email)) {
                return Result.failure(Exception("El email ya está registrado"))
            }

            firestore.collection("usuarios")
                .document(usuario.id)
                .set(
                    mapOf(
                        "id" to usuario.id,
                        "email" to usuario.email,
                        "nombre" to usuario.nombre,
                        "rol" to usuario.rol.name,
                        "imagenPerfil" to (usuario.imagenPerfil ?: ""),
                        "fechaCreacion" to usuario.fechaCreacion,
                        "estaActivo" to usuario.estaActivo
                    )
                )
                .await()

            Result.success(Unit)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    // ============== FUNCIÓN PARA OBTENER EMAIL (ELIMINACIÓN POR EMAIL) ==============

    suspend fun obtenerEmailParaEliminacion(usuarioId: String): Result<String> {
        return try {
            val documento = firestore.collection("usuarios")
                .document(usuarioId)
                .get()
                .await()

            if (!documento.exists()) {
                return Result.failure(Exception("Usuario no encontrado"))
            }

            val email = documento.getString("email")
            if (email.isNullOrEmpty()) {
                return Result.failure(Exception("No se encontró email del usuario"))
            }

            Result.success(email)
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    // ============== FUNCIÓN ELIMINACIÓN DIRECTA (OPCIONAL) ==============

    suspend fun eliminarCuentaUsuario(usuarioId: String): Result<Unit> {
        return try {
            Log.d("ELIMINAR_CUENTA", "Iniciando eliminación para usuario: $usuarioId")

            // 1. Obtener el usuario primero
            val usuarioDoc = firestore.collection("usuarios")
                .document(usuarioId)
                .get()
                .await()

            if (!usuarioDoc.exists()) {
                return Result.failure(Exception("Usuario no encontrado"))
            }

            val emailUsuario = usuarioDoc.getString("email") ?: ""

            // 2. Eliminar reportes del usuario (opcional pero recomendado)
            try {
                val reportesSnapshot = firestore.collection("reportes")
                    .whereEqualTo("usuarioId", usuarioId)
                    .get()
                    .await()

                val batch = firestore.batch()
                reportesSnapshot.documents.forEach { documento ->
                    batch.delete(documento.reference)
                    Log.d("ELIMINAR_CUENTA", "Marcado para eliminar reporte: ${documento.id}")
                }
                batch.commit().await()
                Log.d("ELIMINAR_CUENTA", "Reportes del usuario eliminados")
            } catch (e: Exception) {
                Log.w("ELIMINAR_CUENTA", "No se pudieron eliminar reportes: ${e.message}")
                // Continuamos aunque falle
            }

            // 3. Eliminar notificaciones del usuario
            try {
                val notificacionesSnapshot = firestore.collection("notificaciones")
                    .whereEqualTo("usuarioId", usuarioId)
                    .get()
                    .await()

                val batch = firestore.batch()
                notificacionesSnapshot.documents.forEach { documento ->
                    batch.delete(documento.reference)
                }
                batch.commit().await()
                Log.d("ELIMINAR_CUENTA", "Notificaciones del usuario eliminadas")
            } catch (e: Exception) {
                Log.w("ELIMINAR_CUENTA", "No se pudieron eliminar notificaciones: ${e.message}")
            }

            // 4. Eliminar el usuario
            firestore.collection("usuarios")
                .document(usuarioId)
                .delete()
                .await()

            Log.d("ELIMINAR_CUENTA", "Usuario eliminado exitosamente")
            Result.success(Unit)
        } catch (e: Exception) {
            Log.e("ELIMINAR_CUENTA", "Error al eliminar cuenta: ${e.message}")
            Result.failure(e)
        }
    }

    private fun com.google.firebase.firestore.DocumentSnapshot.toUsuario(): Usuario? {
        return try {
            val id = getString("id") ?: this.id
            val email = getString("email") ?: ""
            val nombre = getString("nombre") ?: ""
            val rolString = getString("rol") ?: RolUsuario.USUARIO.name
            val rol = try {
                RolUsuario.valueOf(rolString)
            } catch (e: Exception) {
                RolUsuario.USUARIO
            }
            val imagenPerfil = getString("imagenPerfil")
            val fechaCreacion = getLong("fechaCreacion") ?: System.currentTimeMillis()
            val estaActivo = getBoolean("estaActivo") ?: true

            Log.d("FIREBASE_DEBUG", "🔄 Convirtiendo documento: $id")
            Log.d("FIREBASE_DEBUG", "   📧 Email: $email")
            Log.d("FIREBASE_DEBUG", "   👤 Nombre: $nombre")
            Log.d("FIREBASE_DEBUG", "   🎯 Rol: $rol")
            Log.d("FIREBASE_DEBUG", "   📅 Fecha: $fechaCreacion")
            Log.d("FIREBASE_DEBUG", "   ✅ Activo: $estaActivo")

            Usuario(
                id = id,
                email = email,
                nombre = nombre,
                rol = rol,
                imagenPerfil = imagenPerfil,
                fechaCreacion = fechaCreacion,
                estaActivo = estaActivo
            )
        } catch (e: Exception) {
            Log.e("FIREBASE_DEBUG", "❌ ERROR en toUsuario(): ${e.message}")
            Log.e("FIREBASE_DEBUG", "📝 Datos del documento: ${this.data}")
            null
        }
    }
}
```
# App Module
# Module ubicacion.kt
```
package mx.edu.utng.mrs.mycomunidad.di

/**
 * Módulo de ubicación que proporciona dependencias relacionadas con la geolocalización
 *
 * @property context Contexto de la aplicación para inicializar servicios de ubicación
 */
import android.content.Context
import dagger.Module
import dagger.Provides
import dagger.hilt.InstallIn
import dagger.hilt.android.qualifiers.ApplicationContext
import dagger.hilt.components.SingletonComponent
import mx.edu.utng.mrs.mycomunidad.servicios.ServicioUbicacionManager
import javax.inject.Singleton

@Module
@InstallIn(SingletonComponent::class)
object ModuloUbicacion {



    /**
     * Inicializa el módulo de ubicación con el contexto de la aplicación
     * @param context Contexto de la aplicación
     */
    @Provides
    @Singleton
    fun proporcionarServicioUbicacionManager(
        @ApplicationContext context: Context
    ): ServicioUbicacionManager {
        return ServicioUbicacionManager(context)
    }
}
```
# ModuleApplication.kt
```
package mx.edu.utng.mrs.mycomunidad.di

import android.app.Application
import android.content.Context
import com.google.firebase.firestore.FirebaseFirestore
import dagger.Module
import dagger.Provides
import dagger.hilt.InstallIn
import dagger.hilt.android.qualifiers.ApplicationContext
import dagger.hilt.components.SingletonComponent
import mx.edu.utng.mrs.mycomunidad.datos.fuente_datos.ServicioFirebase
import mx.edu.utng.mrs.mycomunidad.datos.repositorio.RepositorioComentarios
import mx.edu.utng.mrs.mycomunidad.datos.repositorio.RepositorioNotificaciones
import mx.edu.utng.mrs.mycomunidad.datos.repositorio.RepositorioReportes
import mx.edu.utng.mrs.mycomunidad.servicios.AdministradorNotificaciones
import javax.inject.Singleton
/**
 * Clase principal de la aplicación que maneja la inicialización global
 *
 * @property applicationContext Contexto de la aplicación
 */
@Module
@InstallIn(SingletonComponent::class)
object ModuloAplicacion {

    /**
     * Se llama cuando la aplicación es creada por primera vez
     * Inicializa componentes globales como Firebase y módulos de la aplicación
     */
    @Provides
    @Singleton
    fun proporcionarContext(application: Application): Context {
        return application.applicationContext
    }

    @Provides
    @Singleton
    fun proporcionarFirebaseFirestore(): FirebaseFirestore {
        return FirebaseFirestore.getInstance()
    }

    @Provides
    @Singleton
    fun proporcionarServicioFirebase(
        @ApplicationContext context: Context
    ): ServicioFirebase {
        return ServicioFirebase(context)
    }

    @Provides
    @Singleton
    fun proporcionarRepositorioComentarios(): RepositorioComentarios {
        return RepositorioComentarios()
    }

    @Provides
    @Singleton
    fun proporcionarRepositorioNotificaciones(): RepositorioNotificaciones {
        return RepositorioNotificaciones()
    }

    @Provides
    @Singleton
    fun proporcionarAdministradorNotificaciones(): AdministradorNotificaciones {
        return AdministradorNotificaciones()
    }

    @Provides
    @Singleton
    fun proporcionarRepositorioReportes(
        servicioFirebase: ServicioFirebase
    ): RepositorioReportes {
        return RepositorioReportes(servicioFirebase)
    }
}
```
 # Dominio - Casos de Uso
 # CasoUsoAutenticacion.kt
```
package mx.edu.utng.mrs.mycomunidad.dominio.casos_uso

import mx.edu.utng.mrs.mycomunidad.datos.modelo.Usuario
import mx.edu.utng.mrs.mycomunidad.datos.repositorio.RepositorioAutenticacion
import javax.inject.Inject
/**
 * Caso de uso para manejar la lógica de autenticación de usuarios
 *
 * @property repository Repositorio de autenticación
 */
class CasoUsoAutenticacion @Inject constructor(
    private val repositorioAutenticacion: RepositorioAutenticacion
) {

    /**
     * Verifica si hay un usuario autenticado en el sistema
     * @return true si hay un usuario autenticado, false en caso contrario
     */
    suspend fun iniciarSesion(email: String, contrasena: String): Result<Usuario> {
        // ✅ Validaciones de negocio
        if (email.isBlank() || contrasena.isBlank()) {
            return Result.failure(Exception("Email y contraseña son requeridos"))
        }

        return repositorioAutenticacion.iniciarSesion(email, contrasena)
    }
    /**
     * Obtiene el usuario autenticado actualmente
     * @return Objeto Usuario si está autenticado, null en caso contrario
     * @throws Exception si ocurre un error al obtener el usuario
     */
    suspend fun registrarUsuario(nombre: String, email: String, contrasena: String): Result<Usuario> {
        // ✅ Validaciones de negocio
        if (nombre.length < 3) {
            return Result.failure(Exception("El nombre debe tener al menos 3 caracteres"))
        }
        if (contrasena.length < 6) {
            return Result.failure(Exception("La contraseña debe tener al menos 6 caracteres"))
        }
        if (!email.contains("@")) {
            return Result.failure(Exception("Email no válido"))
        }

        // ✅ CORREGIDO: Los parámetros en el orden correcto
        return repositorioAutenticacion.registrarUsuario(nombre, email, contrasena)
    }
    /**
     * Obtiene el ID del usuario autenticado actualmente
     * @return ID del usuario si está autenticado, null en caso contrario
     */
    suspend fun cerrarSesion(): Result<Boolean> {
        return repositorioAutenticacion.cerrarSesion()
    }
    /**
     * Cierra la sesión del usuario actual
     * @throws Exception si ocurre un error al cerrar sesión
     */
    fun obtenerUsuarioActual(): Usuario? {
        return repositorioAutenticacion.obtenerUsuarioActual()
    }

}
```
# CasoUsoReportes.kt
```
package mx.edu.utng.mrs.mycomunidad.dominio.casos_uso
/*
import android.net.Uri
import mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import mx.edu.utng.mrs.mycomunidad.datos.repositorio.RepositorioReportes
import javax.inject.Inject
/**
 * Caso de uso para manejar la lógica de negocio de reportes
 *
 * @property reportesRepository Repositorio de reportes
 */
class CasoUsoReportes @Inject constructor(
    private val repositorioReportes: RepositorioReportes
) {
 /**
     * Crea un nuevo reporte en el sistema
     * @param titulo Título del reporte
     * @param descripcion Descripción detallada del problema
     * @param idUsuario ID del usuario que crea el reporte
     * @param ubicacion Ubicación asociada al reporte (opcional)
     * @return ID del reporte creado
     * @throws Exception si ocurre un error en la creación
     */
    suspend fun crearReporte(
        titulo: String,
        descripcion: String,
        tipo: TipoReporte,
        gravedad: String,
        latitud: Double,
        longitud: Double,
        imagenes: List<Uri> = emptyList()
    ): Result<Reporte> {
        // Validaciones de negocio
        if (titulo.length < 5) {
            return Result.failure(Exception("El título debe tener al menos 5 caracteres"))
        }
        if (descripcion.length < 10) {
            return Result.failure(Exception("La descripción debe tener al menos 10 caracteres"))
        }
        /**
     * Obtiene los reportes de un usuario específico
     * @param idUsuario ID del usuario
     * @return Lista de reportes del usuario
     * @throws Exception si ocurre un error en la consulta
     */


        return repositorioReportes.crearReporte(
            titulo = titulo,
            descripcion = descripcion,
            tipo = tipo,
            gravedad = gravedad,
            latitud = latitud,
            longitud = longitud,
            imagenes = imagenes
        )
    }
    
 /**
     * Actualiza el estado de un reporte
     * @param idReporte ID del reporte a actualizar
     * @param nuevoEstado Nuevo estado del reporte
     * @throws Exception si ocurre un error en la actualización
     */

    // ✅ CORREGIDO: SUSPEND - Lista directa
    suspend fun obtenerTodosLosReportes(): List<Reporte> {
        return repositorioReportes.obtenerTodosLosReportes()
    }

    // ✅ CORREGIDO: SUSPEND - Lista directa
    suspend fun obtenerReportesPendientes(): List<Reporte> {
        return repositorioReportes.obtenerReportesPendientes()
    }

    // ✅ CORREGIDO: SUSPEND - Lista directa
    suspend fun obtenerReportesAprobados(): List<Reporte> {
        return repositorioReportes.obtenerReportesAprobados()
    }

    suspend fun obtenerReportePorId(reporteId: String): Reporte? {
        return repositorioReportes.obtenerReportePorId(reporteId)
    }

    suspend fun agregarComentario(
        reporteId: String,
        texto: String,
        usuarioId: String,
        usuarioNombre: String
    ): Result<Boolean> {
        if (texto.isBlank()) {
            return Result.failure(Exception("El comentario no puede estar vacío"))
        }

        return repositorioReportes.agregarComentario(
            reporteId = reporteId,
            comentario = texto,
            usuarioId = usuarioId,
            usuarioNombre = usuarioNombre
        )
    }

    suspend fun actualizarEstadoReporte(reporteId: String, estado: EstadoReporte): Result<Boolean> {
        return repositorioReportes.actualizarEstadoReporte(reporteId, estado)
    }

    suspend fun eliminarReporte(reporteId: String, usuarioId: String, esAdmin: Boolean): Result<Boolean> {
        return repositorioReportes.eliminarReporte(reporteId, usuarioId, esAdmin)
    }

    // ✅ CORREGIDO: SUSPEND - Lista directa
    suspend fun obtenerReportesPorUsuario(usuarioId: String): List<Reporte> {
        return repositorioReportes.obtenerReportesPorUsuario(usuarioId)
    }

    // ✅ CORREGIDO: SUSPEND - Lista directa
    suspend fun obtenerReportesPorTipo(tipo: TipoReporte): List<Reporte> {
        return repositorioReportes.obtenerReportesPorTipo(tipo)
    }

    suspend fun obtenerEstadisticas(): Map<String, Any> {
        return repositorioReportes.obtenerEstadisticas()
    }

    suspend fun actualizarReporte(
        reporteId: String,
        titulo: String,
        descripcion: String,
        tipo: TipoReporte
    ): Result<Boolean> {
        // Validaciones de negocio
        if (titulo.length < 5) {
            return Result.failure(Exception("El título debe tener al menos 5 caracteres"))
        }
        if (descripcion.length < 10) {
            return Result.failure(Exception("La descripción debe tener al menos 10 caracteres"))
        }

        return repositorioReportes.actualizarReporte(
            reporteId = reporteId,
            titulo = titulo,
            descripcion = descripcion,
            tipo = tipo
        )
    }
}
```
# CasoUsoUsuario.kt
```
package mx.edu.utng.mrs.mycomunidad.dominio.casos_uso

import kotlinx.coroutines.flow.Flow
import mx.edu.utng.mrs.mycomunidad.datos.modelo.RolUsuario
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Usuario
import mx.edu.utng.mrs.mycomunidad.datos.repositorio.RepositorioUsuarios
import javax.inject.Inject
/**
 * Caso de uso para manejar la lógica de negocio de usuarios
 *
 * @property usuarioRepository Repositorio de usuarios
 */
class CasoUsoUsuarios @Inject constructor(
    /**
     * Registra un nuevo usuario en el sistema
     * @param nombre Nombre completo del usuario
     * @param email Correo electrónico del usuario
     * @param telefono Número de teléfono (opcional)
     * @param rol Rol del usuario (por defecto "usuario")
     * @return ID del usuario creado
     * @throws Exception si ocurre un error en el registro
     */
    private val repositorioUsuarios: RepositorioUsuarios
) {

    fun obtenerTodosLosUsuarios(): Flow<List<Usuario>> {
        return repositorioUsuarios.obtenerTodosLosUsuarios()
    }

    /**
     * Obtiene la información de un usuario por su ID
     * @param userId ID del usuario a consultar
     * @return Objeto Usuario si existe, null en caso contrario
     * @throws Exception si ocurre un error en la consulta
     */
    suspend fun obtenerUsuarioPorId(usuarioId: String): Usuario? {
        if (usuarioId.isBlank()) {
            return null
        }
        return repositorioUsuarios.obtenerUsuarioPorId(usuarioId)
    }
    /**
     * Actualiza la información de un usuario
     * @param userId ID del usuario a actualizar
     * @param nombre Nuevo nombre (opcional)
     * @param telefono Nuevo teléfono (opcional)
     * @throws Exception si ocurre un error en la actualización
     */
    suspend fun actualizarRolUsuario(usuarioId: String, nuevoRol: RolUsuario): Result<Boolean> {
        if (usuarioId.isBlank()) {
            return Result.failure(Exception("ID de usuario inválido"))
        }

        // Validación de negocio: No permitir cambiar rol a uno mismo (esto se haría en ViewModel con el usuario actual)
        return repositorioUsuarios.actualizarRolUsuario(usuarioId, nuevoRol)
    }

    /**
     * Desactiva la cuenta de un usuario
     * @param userId ID del usuario a desactivar
     * @throws Exception si ocurre un error en la desactivación
     */
    suspend fun desactivarUsuario(usuarioId: String): Result<Boolean> {
        if (usuarioId.isBlank()) {
            return Result.failure(Exception("ID de usuario inválido"))
        }

        // Validación de negocio: No permitir desactivarse a uno mismo (se validaría en ViewModel)
        return repositorioUsuarios.desactivarUsuario(usuarioId)
    }

    suspend fun eliminarUsuario(usuarioId: String): Result<Boolean> {
        if (usuarioId.isBlank()) {
            return Result.failure(Exception("ID de usuario inválido"))
        }

        // Validación de negocio: No permitir eliminarse a uno mismo
        return repositorioUsuarios.eliminarUsuario(usuarioId)
    }

    fun buscarUsuariosPorNombre(nombre: String): Flow<List<Usuario>> {
        return repositorioUsuarios.buscarUsuariosPorNombre(nombre)
    }

    suspend fun actualizarPerfilUsuario(usuarioId: String, nombre: String, imagenUrl: String?): Result<Boolean> {
        // Validaciones de negocio
        if (usuarioId.isBlank()) {
            return Result.failure(Exception("ID de usuario inválido"))
        }
        if (nombre.length < 3) {
            return Result.failure(Exception("El nombre debe tener al menos 3 caracteres"))
        }
        if (nombre.length > 50) {
            return Result.failure(Exception("El nombre no puede tener más de 50 caracteres"))
        }

        return repositorioUsuarios.actualizarPerfilUsuario(usuarioId, nombre, imagenUrl)
    }

    // ✅ NUEVOS MÉTODOS MEJORADOS:

    // 1. Obtener usuarios por rol
    fun obtenerUsuariosPorRol(rol: RolUsuario): Flow<List<Usuario>> {
        return repositorioUsuarios.obtenerUsuariosPorRol(rol)
    }

    // 2. Activar usuario (contrario a desactivar)
    suspend fun activarUsuario(usuarioId: String): Result<Boolean> {
        if (usuarioId.isBlank()) {
            return Result.failure(Exception("ID de usuario inválido"))
        }
        return repositorioUsuarios.activarUsuario(usuarioId)
    }

    // 3. Obtener estadísticas de usuarios
    suspend fun obtenerEstadisticasUsuarios(): Map<String, Int> {
        return repositorioUsuarios.obtenerEstadisticasUsuarios()
    }

    // 4. Verificar si el email ya existe (útil para registro)
    suspend fun verificarEmailExistente(email: String): Boolean {
        if (!email.contains("@") || !email.contains(".")) {
            return false
        }
        return repositorioUsuarios.verificarEmailExistente(email)
    }

    // 5. Obtener usuarios activos solamente
    fun obtenerUsuariosActivos(): Flow<List<Usuario>> {
        return repositorioUsuarios.obtenerTodosLosUsuarios()
        // El filtrado por activos se haría en el ViewModel o aquí si fuera suspend
    }

    // 6. Validar permisos para modificar usuario
    suspend fun puedeModificarUsuario(usuarioActualId: String, usuarioTargetId: String, esAdmin: Boolean): Boolean {
        // Un usuario solo puede modificarse a sí mismo a menos que sea admin
        return esAdmin || usuarioActualId == usuarioTargetId
    }
}
```
# Presentación - Servicios
# AdministradorNotificaciones.kt
```
package mx.edu.utng.mrs.mycomunidad.servicios

import android.app.NotificationChannel
import android.app.NotificationManager
import android.app.PendingIntent
import android.content.Context
import android.content.Intent
import android.os.Build
import android.util.Log
import androidx.core.app.NotificationCompat
import com.google.firebase.messaging.FirebaseMessaging
import mx.edu.utng.mrs.mycomunidad.MainActivity
import mx.edu.utng.mrs.mycomunidad.R
import javax.inject.Inject
import javax.inject.Singleton
/**
 * Administrador central de notificaciones que coordina diferentes servicios
 *
 * @property servicioNotificaciones Servicio de notificaciones locales
 * @property servicioNotificacionesFirestore Servicio de notificaciones en la nube
 * @property casoUsoAutenticacion Caso de uso para autenticación
 */
@Singleton
class AdministradorNotificaciones @Inject constructor() {

    companion object {
        private const val TAG = "AdminNotificaciones"
        const val CANAL_NOTIFICACIONES_ID = "canal_mi_comunidad"
    }
    /**
     * Inicializa el administrador de notificaciones
     * Configura listeners y sincronización entre servicios
     */
    fun inicializarSistemaNotificaciones(context: Context) {
        Log.d(TAG, "🚀 INICIALIZANDO SISTEMA DE NOTIFICACIONES")
        crearCanalNotificaciones(context)

        obtenerTokenFCM()

        suscribirATemasBasicos()

        android.os.Handler(context.mainLooper).postDelayed({
            probarNotificacionLocal(context)
        }, 5000)
    }

    private fun obtenerTokenFCM() {
        FirebaseMessaging.getInstance().token.addOnCompleteListener { task ->
            if (task.isSuccessful) {
                val token = task.result
                Log.d(TAG, "✅ TOKEN FCM OBTENIDO: ${token?.take(15)}...")
            } else {
                Log.e(TAG, "❌ ERROR OBTENIENDO TOKEN: ${task.exception}")
            }
        }
    }

    private fun suscribirATemasBasicos() {
        val temas = listOf("todos", "usuarios")

        temas.forEach { tema ->
            FirebaseMessaging.getInstance().subscribeToTopic(tema)
                .addOnCompleteListener { task ->
                    if (task.isSuccessful) {
                        Log.d(TAG, "✅ Suscrito al tema: $tema")
                    } else {
                        Log.e(TAG, "❌ Error suscribiendo a $tema: ${task.exception}")
                    }
                }
        }
    }

    /**
     * Envía una notificación tanto local como remota
     * @param titulo Título de la notificación
     * @param mensaje Contenido de la notificación
     * @param idUsuarioDestino ID del usuario destinatario
     * @throws Exception si ocurre un error en el envío
     */
    fun probarNotificacionLocal(context: Context) {
        Log.d(TAG, "🧪 ENVIANDO NOTIFICACIÓN DE PRUEBA...")

        mostrarNotificacion(
            context = context,
            titulo = "¡Notificaciones Funcionando! 🎉",
            mensaje = "El sistema de notificaciones push está configurado correctamente",
            tipo = "prueba",
            reporteId = "test-123"
        )
    }

    /**
     * Obtiene todas las notificaciones del usuario actual
     * @return Lista de notificaciones
     * @throws Exception si ocurre un error en la obtención
     */
    fun mostrarNotificacion(
        context: Context,
        titulo: String,
        mensaje: String,
        tipo: String = "general",
        reporteId: String = ""
    ) {
        crearCanalNotificaciones(context)

        val intent = Intent(context, MainActivity::class.java).apply {
            flags = Intent.FLAG_ACTIVITY_NEW_TASK or Intent.FLAG_ACTIVITY_CLEAR_TASK
            putExtra("desde_notificacion", true)
            putExtra("tipo_notificacion", tipo)
            putExtra("reporte_id", reporteId)
            putExtra("titulo", titulo)
            putExtra("mensaje", mensaje)
        }

        val pendingIntent = PendingIntent.getActivity(
            context,
            System.currentTimeMillis().toInt(),
            intent,
            PendingIntent.FLAG_UPDATE_CURRENT or PendingIntent.FLAG_IMMUTABLE
        )

        val notificationId = System.currentTimeMillis().toInt()

        val notificationBuilder = NotificationCompat.Builder(context, CANAL_NOTIFICACIONES_ID)
            .setSmallIcon(R.drawable.ic_launcher_foreground)
            .setContentTitle(titulo)
            .setContentText(mensaje)
            .setPriority(NotificationCompat.PRIORITY_HIGH)
            .setContentIntent(pendingIntent)
            .setAutoCancel(true)
            .setStyle(NotificationCompat.BigTextStyle().bigText(mensaje))

        when (tipo) {
            "nuevo_reporte" -> {
                notificationBuilder.setColor(context.getColor(android.R.color.holo_blue_light))
            }
            "reporte_aprobado" -> {
                notificationBuilder.setColor(context.getColor(android.R.color.holo_green_light))
            }
            "reporte_rechazado" -> {
                notificationBuilder.setColor(context.getColor(android.R.color.holo_red_light))
            }
            "nuevo_comentario" -> {
                notificationBuilder.setColor(context.getColor(android.R.color.holo_orange_light))
            }
            "prueba" -> {
                notificationBuilder.setColor(context.getColor(android.R.color.holo_purple))
            }
        }

        val notificationManager = context.getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
        notificationManager.notify(notificationId, notificationBuilder.build())

        Log.d(TAG, "📤 NOTIFICACIÓN MOSTRADA: $titulo")
    }

    private fun crearCanalNotificaciones(context: Context) {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
            val channel = NotificationChannel(
                CANAL_NOTIFICACIONES_ID,
                "Notificaciones Mi Comunidad",
                NotificationManager.IMPORTANCE_HIGH
            ).apply {
                description = "Notificaciones de reportes y actividades de la comunidad"
                enableLights(true)
                enableVibration(true)
                setShowBadge(true)
                lightColor = android.graphics.Color.BLUE
            }

            val notificationManager = context.getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
            notificationManager.createNotificationChannel(channel)
        }
    }
    /**
     * Marca una notificación como leída
     * @param idNotificacion ID de la notificación
     * @throws Exception si ocurre un error en la actualización
     */
    fun enviarNotificacionNuevoReporte(context: Context, tituloReporte: String, usuarioNombre: String) {
        mostrarNotificacion(
            context = context,
            titulo = "📋 Nuevo Reporte",
            mensaje = "$usuarioNombre reportó: $tituloReporte",
            tipo = "nuevo_reporte"
        )
    }

    fun enviarNotificacionReporteAprobado(context: Context, tituloReporte: String) {
        mostrarNotificacion(
            context = context,
            titulo = "✅ Reporte Aprobado",
            mensaje = "Tu reporte '$tituloReporte' ha sido aprobado",
            tipo = "reporte_aprobado"
        )
    }
}
```
# ServicioNotificaciones.kt
```
package mx.edu.utng.mrs.mycomunidad.servicios

import android.app.NotificationChannel
import android.app.NotificationManager
import android.app.PendingIntent
import android.content.Context
import android.content.Intent
import android.os.Build
import android.util.Log
import androidx.core.app.NotificationCompat
import com.google.firebase.messaging.FirebaseMessagingService
import com.google.firebase.messaging.RemoteMessage
import dagger.hilt.android.AndroidEntryPoint
import mx.edu.utng.mrs.mycomunidad.MainActivity
import mx.edu.utng.mrs.mycomunidad.R
import javax.inject.Inject

/**
 * Servicio para manejar notificaciones locales en el dispositivo
 *
 * @property context Contexto de la aplicación
 * @property notificationManager Gestor de notificaciones del sistema
 */
@AndroidEntryPoint
class ServicioNotificaciones : FirebaseMessagingService() {

    @Inject
    lateinit var administradorNotificaciones: AdministradorNotificaciones
    /**
     * Crea el canal de notificaciones para Android 8.0+
     * Este método debe ser llamado antes de mostrar cualquier notificación
     */
    companion object {
        private const val TAG = "ServicioNotificaciones"
        const val CANAL_NOTIFICACIONES_ID = "canal_mi_comunidad"
    }
    /**
     * Muestra una notificación local en el dispositivo
     * @param titulo Título de la notificación
     * @param mensaje Contenido de la notificación
     * @param id Identificador único de la notificación (opcional)
     */
    override fun onNewToken(token: String) {
        super.onNewToken(token)
        Log.d(TAG, "🔥 NUEVO TOKEN FCM: ${token.take(10)}...")

        // Guardar token en SharedPreferences como respaldo
        val sharedPref = getSharedPreferences("notificaciones", Context.MODE_PRIVATE)
        sharedPref.edit().putString("fcm_token", token).apply()

        Log.d(TAG, "✅ Token guardado en SharedPreferences")
    }

    override fun onMessageReceived(remoteMessage: RemoteMessage) {
        Log.d(TAG, "📨 MENSAJE RECIBIDO de: ${remoteMessage.from}")

        if (remoteMessage.data.isNotEmpty()) {
            Log.d(TAG, "📊 Datos del mensaje: ${remoteMessage.data}")
            manejarMensajeDeDatos(remoteMessage.data)
            return
        }

        remoteMessage.notification?.let { notificacion ->
            Log.d(TAG, "📢 Notificación directa")
            mostrarNotificacionSimple(
                titulo = notificacion.title ?: "Mi Comunidad",
                mensaje = notificacion.body ?: "Nueva notificación"
            )
        }
    }

    private fun manejarMensajeDeDatos(datos: Map<String, String>) {
        val tipo = datos["tipo"] ?: "general"
        val titulo = datos["titulo"] ?: "Mi Comunidad"
        val mensaje = datos["mensaje"] ?: "Nueva notificación"
        val reporteId = datos["reporteId"] ?: ""

        Log.d(TAG, "🎯 Tipo: $titulo - $mensaje")

        mostrarNotificacionCompleta(titulo, mensaje, tipo, reporteId)
    }

    private fun mostrarNotificacionSimple(titulo: String, mensaje: String) {
        crearCanalNotificaciones()

        val intent = Intent(this, MainActivity::class.java).apply {
            flags = Intent.FLAG_ACTIVITY_NEW_TASK or Intent.FLAG_ACTIVITY_CLEAR_TASK
        }

        val pendingIntent = PendingIntent.getActivity(
            this,
            System.currentTimeMillis().toInt(),
            intent,
            PendingIntent.FLAG_UPDATE_CURRENT or PendingIntent.FLAG_IMMUTABLE
        )

        val notificationId = System.currentTimeMillis().toInt()

        val notification = NotificationCompat.Builder(this, CANAL_NOTIFICACIONES_ID)
            .setSmallIcon(R.drawable.ic_launcher_foreground)
            .setContentTitle(titulo)
            .setContentText(mensaje)
            .setPriority(NotificationCompat.PRIORITY_HIGH)
            .setContentIntent(pendingIntent)
            .setAutoCancel(true)
            .build()

        val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
        notificationManager.notify(notificationId, notification)

        Log.d(TAG, "✅ Notificación simple mostrada")
    }

    private fun mostrarNotificacionCompleta(titulo: String, mensaje: String, tipo: String, reporteId: String) {
        crearCanalNotificaciones()

        val intent = Intent(this, MainActivity::class.java).apply {
            flags = Intent.FLAG_ACTIVITY_NEW_TASK or Intent.FLAG_ACTIVITY_CLEAR_TASK
            putExtra("desde_notificacion", true)
            putExtra("tipo_notificacion", tipo)
            putExtra("reporte_id", reporteId)
        }

        val pendingIntent = PendingIntent.getActivity(
            this,
            System.currentTimeMillis().toInt(),
            intent,
            PendingIntent.FLAG_UPDATE_CURRENT or PendingIntent.FLAG_IMMUTABLE
        )

        val notificationId = System.currentTimeMillis().toInt()

        val notificationBuilder = NotificationCompat.Builder(this, CANAL_NOTIFICACIONES_ID)
            .setSmallIcon(R.drawable.ic_launcher_foreground)
            .setContentTitle(titulo)
            .setContentText(mensaje)
            .setPriority(NotificationCompat.PRIORITY_HIGH)
            .setContentIntent(pendingIntent)
            .setAutoCancel(true)
            .setStyle(NotificationCompat.BigTextStyle().bigText(mensaje))

        when (tipo) {
            "nuevo_reporte" -> notificationBuilder.setColor(getColor(android.R.color.holo_blue_light))
            "reporte_aprobado" -> notificationBuilder.setColor(getColor(android.R.color.holo_green_light))
            "reporte_rechazado" -> notificationBuilder.setColor(getColor(android.R.color.holo_red_light))
            "nuevo_comentario" -> notificationBuilder.setColor(getColor(android.R.color.holo_orange_light))
        }

        val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
        notificationManager.notify(notificationId, notificationBuilder.build())

        Log.d(TAG, "✅ Notificación completa mostrada - ID: $notificationId")
    }

    /**
     * Elimina una notificación local específica
     * @param id Identificador de la notificación a eliminar
     */
    private fun crearCanalNotificaciones() {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
            val channel = NotificationChannel(
                CANAL_NOTIFICACIONES_ID,
                "Notificaciones Mi Comunidad",
                NotificationManager.IMPORTANCE_HIGH
            ).apply {
                description = "Notificaciones de reportes y actividades de la comunidad"
                enableLights(true)
                enableVibration(true)
                lightColor = android.graphics.Color.BLUE
            }

            val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
            notificationManager.createNotificationChannel(channel)
        }
    }
}
```
# ServicioNotificacionesFirestore.kt
```
package mx.edu.utng.mrs.mycomunidad.servicios

import android.util.Log
import com.google.firebase.firestore.FirebaseFirestore
import kotlinx.coroutines.tasks.await
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Notificacion
import java.util.UUID
import javax.inject.Inject
import javax.inject.Singleton
/**
 * Servicio para manejar notificaciones en Firestore (en la nube)
 *
 * @property repository Repositorio de notificaciones
 */
@Singleton
/**
 * Envía una notificación a Firestore
 * @param titulo Título de la notificación
 * @param mensaje Contenido de la notificación
 * @param idUsuarioDestino ID del usuario destinatario
 * @param tipo Tipo de notificación (por defecto "general")
 * @return ID de la notificación creada
 * @throws Exception si ocurre un error en el envío
 */
class ServicioNotificacionesFirestore @Inject constructor() {

    private val db = FirebaseFirestore.getInstance()
    private val TAG = "NotificacionesFirestore"
    suspend fun enviarNotificacionReporteRechazado(
        usuarioId: String,
        tituloReporte: String,
        motivo: String = ""
    ): Boolean {
        return try {
            Log.d(TAG, "🚀 INICIANDO ENVÍO DE NOTIFICACIÓN DE RECHAZO")
            Log.d(TAG, "👤 Destinatario: $usuarioId")
            Log.d(TAG, "📋 Reporte: $tituloReporte")

            val notificacion = Notificacion(
                id = UUID.randomUUID().toString(),
                titulo = "❌ Reporte Rechazado",
                mensaje = "Tu reporte '$tituloReporte' ha sido rechazado${if (motivo.isNotEmpty()) ". Motivo: $motivo" else ""}",
                tipo = "reporte_rechazado",
                usuarioId = usuarioId,
                datosExtra = mapOf(
                    "reporteTitulo" to tituloReporte,
                    "motivo" to motivo
                ),
                fecha = System.currentTimeMillis(),
                leida = false
            )

            Log.d(TAG, "💾 GUARDANDO NOTIFICACIÓN EN FIRESTORE...")
            // 1. Guardar en Firestore
            val resultado = guardarNotificacionEnFirestore(notificacion)

            if (resultado) {
                Log.d(TAG, "✅ NOTIFICACIÓN DE RECHAZO GUARDADA EN FIRESTORE")
                true
            } else {
                Log.e(TAG, "❌ FALLÓ AL GUARDAR NOTIFICACIÓN DE RECHAZO")
                false
            }

        } catch (e: Exception) {
            Log.e(TAG, "❌ ERROR enviando notificación de rechazo: ${e.message}")
            false
        }
    }
    
    suspend fun enviarNotificacionReporteAprobado(
        usuarioId: String,
        tituloReporte: String
    ): Boolean {
        return try {
            Log.d(TAG, "🚀 INICIANDO ENVÍO DE NOTIFICACIÓN DE APROBACIÓN")
            Log.d(TAG, "👤 Destinatario: $usuarioId")
            Log.d(TAG, "📋 Reporte: $tituloReporte")

            val notificacion = Notificacion(
                id = UUID.randomUUID().toString(),
                titulo = "✅ Reporte Aprobado",
                mensaje = "¡Felicidades! Tu reporte '$tituloReporte' ha sido aprobado y ahora es visible para la comunidad",
                tipo = "reporte_aprobado",
                usuarioId = usuarioId,
                datosExtra = mapOf(
                    "reporteTitulo" to tituloReporte
                ),
                fecha = System.currentTimeMillis(),
                leida = false
            )

            Log.d(TAG, "💾 GUARDANDO NOTIFICACIÓN EN FIRESTORE...")
            val resultado = guardarNotificacionEnFirestore(notificacion)

            if (resultado) {
                Log.d(TAG, "✅ NOTIFICACIÓN DE APROBACIÓN GUARDADA EN FIRESTORE")
                true
            } else {
                Log.e(TAG, "❌ FALLÓ AL GUARDAR NOTIFICACIÓN DE APROBACIÓN")
                false
            }

        } catch (e: Exception) {
            Log.e(TAG, "❌ ERROR enviando notificación de aprobación: ${e.message}")
            false
        }
    }
    private suspend fun guardarNotificacionEnFirestore(notificacion: Notificacion): Boolean {
        return try {
            Log.d(TAG, "💾 INTENTANDO GUARDAR NOTIFICACIÓN EN FIRESTORE...")
            Log.d(TAG, "   🆔 ID: ${notificacion.id}")
            Log.d(TAG, "   👤 usuarioId: ${notificacion.usuarioId}")
            Log.d(TAG, "   📝 título: ${notificacion.titulo}")

            db.collection("notificaciones")
                .document(notificacion.id)
                .set(notificacion.toMap())
                .await()

            Log.d(TAG, "✅ NOTIFICACIÓN GUARDADA EXITOSAMENTE EN FIRESTORE")
            true

        } catch (e: Exception) {
            Log.e(TAG, "❌ ERROR GUARDANDO NOTIFICACIÓN EN FIRESTORE: ${e.message}")
            false
        }
    }
    /**
     * Obtiene las notificaciones de un usuario específico
     * @param userId ID del usuario
     * @return Lista de notificaciones del usuario
     * @throws Exception si ocurre un error en la obtención
     */
    suspend fun obtenerNotificacionesUsuario(usuarioId: String): List<Notificacion> {
        return try {
            Log.d(TAG, "🔍 OBTENIENDO NOTIFICACIONES PARA USUARIO: $usuarioId")

            val snapshot = db.collection("notificaciones")
                .whereEqualTo("usuarioId", usuarioId)
                .orderBy("fecha", com.google.firebase.firestore.Query.Direction.DESCENDING)
                .get()
                .await()

            val notificaciones = snapshot.documents.mapNotNull { doc ->
                try {
                    Notificacion(
                        id = doc.id,
                        titulo = doc.getString("titulo") ?: "",
                        mensaje = doc.getString("mensaje") ?: "",
                        tipo = doc.getString("tipo") ?: "general",
                        usuarioId = doc.getString("usuarioId") ?: "",
                        datosExtra = (doc.get("datosExtra") as? Map<String, String>) ?: emptyMap(),
                        fecha = doc.getLong("fecha") ?: System.currentTimeMillis(),
                        leida = doc.getBoolean("leida") ?: false
                    )
                } catch (e: Exception) {
                    Log.e(TAG, "❌ Error parseando notificación ${doc.id}: ${e.message}")
                    null
                }
            }

            Log.d(TAG, "📋 NOTIFICACIONES OBTENIDAS: ${notificaciones.size} para usuario: $usuarioId")
            notificaciones

        } catch (e: Exception) {
            Log.e(TAG, "❌ ERROR OBTENIENDO NOTIFICACIONES: ${e.message}")
            emptyList()
        }
    }
    /**
     * Marca una notificación como leída
     * @param idNotificacion ID de la notificación
     * @throws Exception si ocurre un error en la actualización
     */
    suspend fun marcarNotificacionLeida(notificacionId: String): Boolean {
        return try {
            db.collection("notificaciones")
                .document(notificacionId)
                .update("leida", true)
                .await()

            Log.d(TAG, "✅ Notificación marcada como leída: $notificacionId")
            true
        } catch (e: Exception) {
            Log.e(TAG, "❌ Error marcando notificación como leída: ${e.message}")
            false
        }
    }
    /**
     * Marca una notificación como leída
     * @param idNotificacion ID de la notificación
     * @throws Exception si ocurre un error en la actualización
     */
    suspend fun diagnosticoNotificaciones(usuarioId: String) {
        try {
            Log.d(TAG, "🎯 ===========================================")
            Log.d(TAG, "🔍 DIAGNÓSTICO DE NOTIFICACIONES")
            Log.d(TAG, "👤 USUARIO: $usuarioId")
            Log.d(TAG, "🎯 ===========================================")

            val snapshot = db.collection("notificaciones")
                .whereEqualTo("usuarioId", usuarioId)
                .get()
                .await()

            Log.d(TAG, "📊 NOTIFICACIONES ENCONTRADAS: ${snapshot.documents.size}")

            if (snapshot.documents.isEmpty()) {
                Log.d(TAG, "📭 NO HAY NOTIFICACIONES PARA ESTE USUARIO")
            } else {
                snapshot.documents.forEachIndexed { index, doc ->
                    Log.d(TAG, "   ${index + 1}. ${doc.getString("titulo")} - ${doc.getString("tipo")} - Leída: ${doc.getBoolean("leida") ?: false}")
                }
            }

            Log.d(TAG, "✅ DIAGNÓSTICO COMPLETADO")
            Log.d(TAG, "🎯 ===========================================")

        } catch (e: Exception) {
            Log.e(TAG, "❌ ERROR en diagnóstico: ${e.message}")
        }
    }

    /**
     * Obtiene un flujo de notificaciones no leídas para un usuario
     * @param userId ID del usuario
     * @return Flow de lista de notificaciones no leídas
     */
    suspend fun enviarNotificacionNuevoReporte(
        tituloReporte: String,
        tipoReporte: String,
        usuarioNombre: String
    ): Boolean {
        return try {
            Log.d(TAG, "🚀 ENVIANDO NOTIFICACIÓN DE NUEVO REPORTE")

            val notificacion = Notificacion(
                id = UUID.randomUUID().toString(),
                titulo = "📢 Nuevo Reporte",
                mensaje = "$usuarioNombre ha creado un nuevo reporte: $tituloReporte ($tipoReporte)",
                tipo = "nuevo_reporte",
                usuarioId = "administradores", // Para que todos los admins lo vean
                datosExtra = mapOf(
                    "reporteTitulo" to tituloReporte,
                    "tipoReporte" to tipoReporte,
                    "usuarioNombre" to usuarioNombre
                ),
                fecha = System.currentTimeMillis(),
                leida = false
            )

            val resultado = guardarNotificacionEnFirestore(notificacion)

            if (resultado) {
                Log.d(TAG, "✅ NOTIFICACIÓN DE NUEVO REPORTE ENVIADA")
            } else {
                Log.e(TAG, "❌ FALLÓ AL ENVIAR NOTIFICACIÓN DE NUEVO REPORTE")
            }

            resultado

        } catch (e: Exception) {
            Log.e(TAG, "❌ ERROR enviando notificación de nuevo reporte: ${e.message}")
            false
        }
    }
}
```
# ServicioUbicacion.kt
```
package mx.edu.utng.mrs.mycomunidad.servicios

import android.Manifest
import android.annotation.SuppressLint
import android.app.Notification
import android.app.NotificationChannel
import android.app.NotificationManager
import android.app.Service
import android.content.Context
import android.content.Intent
import android.content.pm.PackageManager
import android.location.Location
import android.os.Binder
import android.os.Build
import android.os.IBinder
import android.os.Looper
import androidx.core.app.NotificationCompat
import androidx.core.content.ContextCompat
import com.google.android.gms.location.*
import com.google.android.gms.tasks.Task
import com.google.android.gms.tasks.Tasks
import dagger.hilt.android.AndroidEntryPoint
import kotlinx.coroutines.flow.MutableStateFlow
import kotlinx.coroutines.flow.StateFlow
import mx.edu.utng.mrs.mycomunidad.R
import javax.inject.Inject
/**
 * Servicio para manejar la obtención de ubicación del dispositivo
 *
 * @property context Contexto de la aplicación
 * @property fusedLocationClient Cliente de ubicación fusionada de Google Play Services
 */
@AndroidEntryPoint
class ServicioUbicacion : Service() {
    /**
     * Verifica si la aplicación tiene permisos de ubicación
     * @return true si tiene permisos, false en caso contrario
     */
    @Inject
    lateinit var administradorNotificaciones: AdministradorNotificaciones

    private val binder = LocalBinder()
    private lateinit var clienteUbicacion: FusedLocationProviderClient
    private lateinit var solicitudUbicacion: LocationRequest
    private lateinit var callbackUbicacion: LocationCallback

    private val _ubicacionActual = MutableStateFlow<Location?>(null)
    val ubicacionActual: StateFlow<Location?> = _ubicacionActual

    private val _estaMonitoreando = MutableStateFlow(false)
    val estaMonitoreando: StateFlow<Boolean> = _estaMonitoreando

    private val _error = MutableStateFlow<String?>(null)
    val error: StateFlow<String?> = _error

    inner class LocalBinder : Binder() {
        fun getService(): ServicioUbicacion = this@ServicioUbicacion
    }

    override fun onBind(intent: Intent?): IBinder = binder

    override fun onCreate() {
        super.onCreate()
        inicializarServicioUbicacion()
    }
    /**
     * Obtiene la última ubicación conocida del dispositivo
     * @return Objeto Location con la última ubicación conocida, null si no está disponible
     * @throws SecurityException si no hay permisos de ubicación
     * @throws Exception si ocurre un error al obtener la ubicación
     */

    override fun onStartCommand(intent: Intent?, flags: Int, startId: Int): Int {
        when (intent?.action) {
            ACCION_INICIAR -> iniciarMonitoreoUbicacion()
            ACCION_DETENER -> detenerMonitoreoUbicacion()
        }
        return START_STICKY
    }

    /**
     * Inicia la actualización continua de ubicación
     * @param intervalo Intervalo de actualización en milisegundos
     * @param callback Función a ejecutar cuando se obtiene una nueva ubicación
     * @throws SecurityException si no hay permisos de ubicación
     */


    private fun inicializarServicioUbicacion() {
        clienteUbicacion = LocationServices.getFusedLocationProviderClient(this)

        solicitudUbicacion = if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.S) {
            LocationRequest.Builder(
                Priority.PRIORITY_HIGH_ACCURACY,
                10000L // Intervalo de 10 segundos
            ).apply {
                setMinUpdateIntervalMillis(5000L) // Intervalo mínimo de 5 segundos
                setMaxUpdateDelayMillis(15000L) // Máximo retraso de 15 segundos
                setWaitForAccurateLocation(true)
            }.build()
        } else {
            LocationRequest.create().apply {
                priority = LocationRequest.PRIORITY_HIGH_ACCURACY
                interval = 10000L
                fastestInterval = 5000L
                maxWaitTime = 15000L
            }
        }

        callbackUbicacion = object : LocationCallback() {
            override fun onLocationResult(resultadoUbicacion: LocationResult) {
                super.onLocationResult(resultadoUbicacion)
                resultadoUbicacion.lastLocation?.let { ubicacion ->
                    _ubicacionActual.value = ubicacion
                    // Aquí puedes guardar la ubicación o enviarla a tu backend
                    manejarNuevaUbicacion(ubicacion)
                }
            }

            override fun onLocationAvailability(disponibilidadUbicacion: LocationAvailability) {
                super.onLocationAvailability(disponibilidadUbicacion)
                if (!disponibilidadUbicacion.isLocationAvailable) {
                    _error.value = "La ubicación no está disponible"
                } else {
                    _error.value = null
                }
            }
        }
    }

    @SuppressLint("MissingPermission")
    fun iniciarMonitoreoUbicacion() {
        if (tienePermisosUbicacion()) {
            try {
                clienteUbicacion.requestLocationUpdates(
                    solicitudUbicacion,
                    callbackUbicacion,
                    Looper.getMainLooper()
                )
                _estaMonitoreando.value = true
                _error.value = null
                iniciarNotificacionPrimerPlano()
            } catch (e: SecurityException) {
                _error.value = "Error de permisos: ${e.message}"
            } catch (e: Exception) {
                _error.value = "Error al iniciar monitoreo: ${e.message}"
            }
        } else {
            _error.value = "Permisos de ubicación no concedidos"
        }
    }

    fun detenerMonitoreoUbicacion() {
        try {
            clienteUbicacion.removeLocationUpdates(callbackUbicacion)
            _estaMonitoreando.value = false
            _ubicacionActual.value = null
            _error.value = null
            detenerNotificacionPrimerPlano()
            stopSelf()
        } catch (e: Exception) {
            _error.value = "Error al detener monitoreo: ${e.message}"
        }
    }

    private fun tienePermisosUbicacion(): Boolean {
        return ContextCompat.checkSelfPermission(
            this,
            Manifest.permission.ACCESS_FINE_LOCATION
        ) == PackageManager.PERMISSION_GRANTED ||
                ContextCompat.checkSelfPermission(
                    this,
                    Manifest.permission.ACCESS_COARSE_LOCATION
                ) == PackageManager.PERMISSION_GRANTED
    }

    @SuppressLint("MissingPermission")
    fun obtenerUbicacionActualUnaVez(): Task<Location> {
        return if (tienePermisosUbicacion()) {
            clienteUbicacion.lastLocation
        } else {
            Tasks.forException(SecurityException("Permisos de ubicación no concedidos"))
        }
    }

    private fun manejarNuevaUbicacion(ubicacion: Location) {
        // Aquí puedes implementar la lógica para:
        // - Guardar la ubicación en local
        // - Enviar a tu backend
        // - Actualizar la UI si es necesario
        // - Verificar geocercas, etc.

        // Ejemplo: Guardar última ubicación conocida
        // sharedPreferences.edit().putString("ultima_ubicacion", "${ubicacion.latitude},${ubicacion.longitude}").apply()
    }

    @SuppressLint("ForegroundServiceType")
    private fun iniciarNotificacionPrimerPlano() {
        crearCanalNotificacionServicio()

        val notification = NotificationCompat.Builder(this, CANAL_SERVICIO_UBICACION_ID)
            .setContentTitle("Mi Comunidad")
            .setContentText("Monitoreando ubicación para reportes...")
            .setSmallIcon(R.drawable.ic_launcher_foreground)
            .setPriority(NotificationCompat.PRIORITY_LOW)
            .setOngoing(true)
            .setSilent(true)
            .build()
        // Configurar actualización de ubicación
        // En implementación real se usaría requestLocationUpdates

        startForeground(NOTIFICACION_UBICACION_ID, notification)
    }
    /**
     * Detiene las actualizaciones de ubicación
     */

    private fun crearCanalNotificacionServicio() {
        // Remover listeners de ubicación
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
            val canal = NotificationChannel(
                CANAL_SERVICIO_UBICACION_ID,
                CANAL_SERVICIO_UBICACION_NOMBRE,
                NotificationManager.IMPORTANCE_LOW
            ).apply {
                description = "Notificación del servicio de ubicación en primer plano"
                setShowBadge(false)
                lockscreenVisibility = Notification.VISIBILITY_PRIVATE
            }

            val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
            notificationManager.createNotificationChannel(canal)
        }
    }

    private fun detenerNotificacionPrimerPlano() {
        stopForeground(STOP_FOREGROUND_REMOVE)
    }

    override fun onDestroy() {
        super.onDestroy()
        detenerMonitoreoUbicacion()
    }

    companion object {
        const val ACCION_INICIAR = "ACCION_INICIAR_MONITOREO"
        const val ACCION_DETENER = "ACCION_DETENER_MONITOREO"
        const val NOTIFICACION_UBICACION_ID = 1001
        const val CANAL_SERVICIO_UBICACION_ID = "canal_servicio_ubicacion"
        const val CANAL_SERVICIO_UBICACION_NOMBRE = "Servicio de Ubicación"

        fun iniciarServicio(context: Context) {
            if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
                context.startForegroundService(
                    Intent(context, ServicioUbicacion::class.java).apply {
                        action = ACCION_INICIAR
                    }
                )
            } else {
                context.startService(
                    Intent(context, ServicioUbicacion::class.java).apply {
                        action = ACCION_INICIAR
                    }
                )
            }
        }

        fun detenerServicio(context: Context) {
            val intent = Intent(context, ServicioUbicacion::class.java).apply {
                action = ACCION_DETENER
            }
            context.startService(intent)
        }
    }
}
```
# UbicacionManager.kt
```

package mx.edu.utng.mrs.mycomunidad.servicios

import android.Manifest
import android.annotation.SuppressLint
import android.content.Context
import android.content.pm.PackageManager
import android.location.Location
import android.os.Looper
import androidx.core.content.ContextCompat
import com.google.android.gms.location.*
import com.google.android.gms.tasks.CancellationToken
import com.google.android.gms.tasks.CancellationTokenSource
import com.google.android.gms.tasks.OnTokenCanceledListener
import kotlinx.coroutines.channels.awaitClose
import kotlinx.coroutines.flow.Flow
import kotlinx.coroutines.flow.callbackFlow
import kotlinx.coroutines.tasks.await
import javax.inject.Inject
import javax.inject.Singleton
/**
 * Gestor de ubicación que coordina los servicios de geolocalización
 *
 * @property servicioUbicacion Servicio para obtener ubicación del dispositivo
 */
@Singleton
class ServicioUbicacionManager @Inject constructor(
    private val context: Context
) {
    /**
     * Verifica y solicita los permisos de ubicación necesarios
     * @return true si ya tiene permisos, false si necesita solicitarlos
     */
    private val clienteUbicacion: FusedLocationProviderClient by lazy {
        LocationServices.getFusedLocationProviderClient(context)
    }

    /**
     * Obtiene la ubicación actual del dispositivo
     * @param onSuccess Callback ejecutado cuando se obtiene la ubicación exitosamente
     * @param onError Callback ejecutado cuando ocurre un error
     */
    private val solicitudUbicacion = LocationRequest.Builder(
        Priority.PRIORITY_HIGH_ACCURACY,
        10000L
    ).apply {
        setMinUpdateIntervalMillis(5000L)
        setWaitForAccurateLocation(true)
    }.build()

    @SuppressLint("MissingPermission")

            /**
             * Obtiene la dirección a partir de coordenadas
             * @param latitud Coordenada de latitud
             * @param longitud Coordenada de longitud
             * @return Dirección formateada o null si no se puede obtener
             */fun obtenerUbicacionActualUnaVez(): Flow<Location> = callbackFlow {
        // Implementación usando Geocoder
        // Por simplicidad, se devuelve una dirección ficticia
                 if (!tienePermisosUbicacion()) {
            close(Exception("Permisos de ubicación no concedidos"))
            return@callbackFlow
        }

        /**
         * Calcula la distancia entre dos ubicaciones
         * @param ubicacion1 Primera ubicación
         * @param ubicacion2 Segunda ubicación
         * @return Distancia en metros
         */
        val cancellationTokenSource = CancellationTokenSource()

        clienteUbicacion.getCurrentLocation(
            Priority.PRIORITY_HIGH_ACCURACY,
            cancellationTokenSource.token
        ).addOnSuccessListener { location ->
            if (location != null) {
                trySend(location)
                close()
            } else {
                close(Exception("No se pudo obtener la ubicación"))
            }
        }.addOnFailureListener { exception ->
            close(exception)
        }

        awaitClose {
            cancellationTokenSource.cancel()
        }
    }

    @SuppressLint("MissingPermission")
    fun monitorearUbicacionEnTiempoReal(): Flow<Location> = callbackFlow {
        if (!tienePermisosUbicacion()) {
            close(Exception("Permisos de ubicación no concedidos"))
            return@callbackFlow
        }

        val callback = object : LocationCallback() {
            override fun onLocationResult(resultado: LocationResult) {
                resultado.locations.lastOrNull()?.let { ubicacion ->
                    trySend(ubicacion)
                }
            }
        }

        clienteUbicacion.requestLocationUpdates(
            solicitudUbicacion,
            callback,
            Looper.getMainLooper()
        ).addOnFailureListener { exception ->
            close(exception)
        }

        awaitClose {
            clienteUbicacion.removeLocationUpdates(callback)
        }
    }

    private fun tienePermisosUbicacion(): Boolean {
        return ContextCompat.checkSelfPermission(
            context,
            Manifest.permission.ACCESS_FINE_LOCATION
        ) == PackageManager.PERMISSION_GRANTED ||
                ContextCompat.checkSelfPermission(
                    context,
                    Manifest.permission.ACCESS_COARSE_LOCATION
                ) == PackageManager.PERMISSION_GRANTED
    }

    suspend fun obtenerUltimaUbicacionConocida(): Location? {
        return if (tienePermisosUbicacion()) {
            try {
                clienteUbicacion.lastLocation.await()
            } catch (e: Exception) {
                null
            }
        } else {
            null
        }
    }
}
```
# Utilidades
# AlmacenamientoSeguro.kt
```
package mx.edu.utng.mrs.mycomunidad.utilidades

import android.content.Context
import android.content.SharedPreferences
import com.google.gson.Gson
import dagger.hilt.android.qualifiers.ApplicationContext
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Usuario
import javax.inject.Inject
import javax.inject.Singleton
/**
 * Utilidad para manejar almacenamiento seguro de datos sensibles usando EncriptedSharedPreferences
 *
 * @property context Contexto de la aplicación
 * @property masterKey Clave maestra para encriptación
 * @property encryptedPrefs Preferencias encriptadas
 */
@Singleton
class AlmacenamientoSeguro @Inject constructor(
    @ApplicationContext private val context: Context
) {

    /**
     * Guarda un valor de forma segura en las preferencias encriptadas
     * @param key Clave del valor a guardar
     * @param value Valor a guardar (puede ser String, Int, Boolean, Long, Float)
     * @throws IllegalArgumentException si el tipo de valor no es soportado
     */  private val sharedPreferences: SharedPreferences by lazy {
        context.getSharedPreferences("mi_comunidad_prefs", Context.MODE_PRIVATE)
    }
    private val gson = Gson()

    companion object {
        private const val KEY_USUARIO_ACTUAL = "usuario_actual"
        private const val KEY_SESION_ACTIVA = "sesion_activa"
        private const val KEY_TOKEN_NOTIFICACIONES = "token_notificaciones"
    }

    fun guardarSesionUsuario(usuario: Usuario) {
        val usuarioJson = gson.toJson(usuario)
        sharedPreferences.edit()
            .putString(KEY_USUARIO_ACTUAL, usuarioJson)
            .putBoolean(KEY_SESION_ACTIVA, true)
            .apply()
    }

    fun obtenerUsuarioActual(): Usuario? {
        val usuarioJson = sharedPreferences.getString(KEY_USUARIO_ACTUAL, null)
        return try {
            gson.fromJson(usuarioJson, Usuario::class.java)
        } catch (e: Exception) {
            null
        }
    }
    /**
     * Obtiene un valor de forma segura de las preferencias encriptadas
     * @param key Clave del valor a obtener
     * @param defaultValue Valor por defecto si la clave no existe
     * @return Valor almacenado o el valor por defecto
     */
    fun limpiarSesion() {
        sharedPreferences.edit()
            .remove(KEY_USUARIO_ACTUAL)
            .putBoolean(KEY_SESION_ACTIVA, false)
            .apply()
    }

    fun haySesionActiva(): Boolean {
        return sharedPreferences.getBoolean(KEY_SESION_ACTIVA, false)
    }
    /**
     * Elimina un valor de forma segura de las preferencias encriptadas
     * @param key Clave del valor a eliminar
     */
    fun guardarTokenNotificaciones(token: String) {
        sharedPreferences.edit()
            .putString(KEY_TOKEN_NOTIFICACIONES, token)
            .apply()
    }
    /**
     * Verifica si existe una clave en las preferencias encriptadas
     * @param key Clave a verificar
     * @return true si la clave existe, false en caso contrario
     */
    fun obtenerTokenNotificaciones(): String? {
        return sharedPreferences.getString(KEY_TOKEN_NOTIFICACIONES, null)
    }
}
```
# FormatearTiempo.kt
```
package mx.edu.utng.mrs.mycomunidad.utilidades

import java.util.concurrent.TimeUnit
/**
 * Utilidad para formatear fechas y tiempos de manera consistente en la aplicación
 *
 * @property locale Configuración regional para el formateo (por defecto español de México)
 */
object FormateadorTiempo {
    /**
     * Formatea una fecha en un patrón específico
     * @param fecha Fecha a formatear
     * @param patron Patrón de formato (ej: "dd/MM/yyyy", "yyyy-MM-dd HH:mm:ss")
     * @return String formateado según el patrón
     */
    fun obtenerTiempoTranscurrido(tiempoMillis: Long): String {
        val ahora = System.currentTimeMillis()
        val diferencia = ahora - tiempoMillis
        /**
         * Convierte una fecha a un formato amigable para el usuario (ej: "Hace 2 horas")
         * @param fecha Fecha a convertir
         * @return String con formato amigable para el usuario
         */
        return when {
            diferencia < TimeUnit.MINUTES.toMillis(1) -> "Hace un momento"
            diferencia < TimeUnit.HOURS.toMillis(1) -> {
                val minutos = TimeUnit.MILLISECONDS.toMinutes(diferencia)
                "Hace $minutos minuto${if (minutos > 1) "s" else ""}"
            }
            diferencia < TimeUnit.DAYS.toMillis(1) -> {
                val horas = TimeUnit.MILLISECONDS.toHours(diferencia)
                "Hace $horas hora${if (horas > 1) "s" else ""}"
            }
            diferencia < TimeUnit.DAYS.toMillis(7) -> {
                val dias = TimeUnit.MILLISECONDS.toDays(diferencia)
                "Hace $dias día${if (dias > 1) "s" else ""}"
            }
            else -> "Hace más de una semana"
        }
    }
}
```
# GradientUtils
```
package mx.edu.utng.mrs.mycomunidad.utilidades

import androidx.compose.runtime.Composable
import androidx.compose.ui.graphics.Brush
import androidx.compose.ui.graphics.Color
import androidx.compose.material3.MaterialTheme
/**
 * Utilidad para aplicar gradientes a elementos de la UI, especialmente TextViews
 *
 * @property direcciones Map de direcciones de gradiente
 */
object GradientUtils {
    /**
     * Aplica un gradiente lineal a un TextView
     * @param textView TextView al que se aplicará el gradiente
     * @param colores Array de colores para el gradiente
     * @param direccion Dirección del gradiente (por defecto izquierda a derecha)
     */
    @Composable
    fun getPrimaryGradient(): Brush {
        return Brush.linearGradient(
            colors = listOf(
                MaterialTheme.colorScheme.primary,
                MaterialTheme.colorScheme.primaryContainer
            )
        )
    }
    /**
     * Crea un gradiente de dos colores
     * @param colorInicio Color inicial del gradiente
     * @param colorFin Color final del gradiente
     * @return IntArray con los dos colores
     */
    @Composable
    fun getSecondaryGradient(): Brush {
        return Brush.linearGradient(
            colors = listOf(
                MaterialTheme.colorScheme.secondary,
                MaterialTheme.colorScheme.secondaryContainer
            )
        )
    }
    /**
     * Crea un gradiente de múltiples colores
     * @param colores Lista de colores para el gradiente
     * @return IntArray con todos los colores
     */
    @Composable
    fun getSurfaceGradient(): Brush {
        return Brush.verticalGradient(
            colors = listOf(
                MaterialTheme.colorScheme.surface,
                MaterialTheme.colorScheme.surfaceVariant
            )
        )
    }

    /**
     * Aplica un gradiente predefinido (azul a morado) a un TextView
     * @param textView TextView al que se aplicará el gradiente
     */

    @Composable
    fun getBackgroundGradient(): Brush {
        return Brush.verticalGradient(
            colors = listOf(
                MaterialTheme.colorScheme.background,
                MaterialTheme.colorScheme.surface
            )
        )
    }

    // Estos no necesitan @Composable porque no usan MaterialTheme
    fun getSuccessGradient(): Brush {
        return Brush.linearGradient(
            colors = listOf(
                Color(0xFF10B981),
                Color(0xFF059669)
            )
        )
    }

    /**
     * Aplica un gradiente de éxito (verde) a un TextView
     * @param textView TextView al que se aplicará el gradiente
     */
    fun getWarningGradient(): Brush {
        return Brush.linearGradient(
            colors = listOf(
                Color(0xFFF59E0B),
                Color(0xFFD97706)
            )
        )
    }


    /**
     * Aplica un gradiente de error (rojo) a un TextView
     * @param textView TextView al que se aplicará el gradiente
     */
    fun getErrorGradient(): Brush {
        return Brush.linearGradient(
            colors = listOf(
                Color(0xFFEF4444),
                Color(0xFFDC2626)
            )
        )
    }
}
```
# ManejadorCamaras.kt
```
package mx.edu.utng.mrs.mycomunidad.utilidades

import android.app.Activity
import android.content.ContentValues
import android.content.Context
import android.content.Intent
import android.net.Uri
import android.provider.MediaStore
import androidx.activity.ComponentActivity
import androidx.activity.compose.rememberLauncherForActivityResult
import androidx.activity.result.contract.ActivityResultContracts
import androidx.compose.runtime.Composable
import androidx.compose.runtime.remember
import androidx.compose.ui.platform.LocalContext
import androidx.core.content.FileProvider
import java.io.ByteArrayOutputStream
import java.io.File
import java.io.InputStream
import java.text.SimpleDateFormat
import java.util.Date
import java.util.Locale

/**
 * Utilidad para manejar operaciones de cámara y galería de fotos
 *
 * @property activity Actividad que utiliza el manejador
 * @property fotoActualPath Ruta de la foto actual tomada
 */

class ManejadorCamara(private val context: Context) {
    /**
     * Verifica si la aplicación tiene permisos de cámara
     * @return true si tiene permisos, false en caso contrario
     */    private var uriFotoTemporal: Uri? = null

    @Composable
    fun recordatorioTomarFoto(
        onFotoTomada: (ByteArray) -> Unit,
        onError: (String) -> Unit
    ): TomarFotoLauncher {
        val actividad = LocalContext.current as ComponentActivity

        val launcherCamara = rememberLauncherForActivityResult(
            contract = ActivityResultContracts.TakePicture(),
            onResult = { exito ->
                if (exito) {
                    uriFotoTemporal?.let { uri ->
                        try {
                            val inputStream = context.contentResolver.openInputStream(uri)
                            val bytesFoto = inputStream?.leerBytes()
                            if (bytesFoto != null) {
                                onFotoTomada(bytesFoto)
                            } else {
                                onError("No se pudo leer la foto")
                            }
                        } catch (e: Exception) {
                            onError("Error al procesar la foto: ${e.message}")
                        } finally {
                            eliminarFotoTemporal()
                        }
                    }
                } else {
                    onError("No se pudo tomar la foto")
                }
            }
        )

        val launcherGaleria = rememberLauncherForActivityResult(
            contract = ActivityResultContracts.GetContent(),
            onResult = { uri ->
                if (uri != null) {
                    try {
                        val inputStream = context.contentResolver.openInputStream(uri)
                        val bytesFoto = inputStream?.leerBytes()
                        if (bytesFoto != null) {
                            onFotoTomada(bytesFoto)
                        } else {
                            onError("No se pudo leer la imagen")
                        }
                    } catch (e: Exception) {
                        onError("Error al procesar la imagen: ${e.message}")
                    }
                }
            }
        )

        return remember {
            TomarFotoLauncher(
                onAbrirCamara = {
                    try {
                        uriFotoTemporal = crearArchivoFotoTemporal()
                        launcherCamara.launch(uriFotoTemporal)
                    } catch (e: Exception) {
                        onError("Error al abrir la cámara: ${e.message}")
                    }
                },
                onAbrirGaleria = {
                    launcherGaleria.launch("image/*")
                }
            )
        }
    }

    private fun crearArchivoFotoTemporal(): Uri {
        val tiempo = SimpleDateFormat("yyyyMMdd_HHmmss", Locale.getDefault()).format(Date())
        val nombreArchivo = "JPEG_${tiempo}_"
        val directorio = context.externalCacheDir ?: context.cacheDir
        val archivo = File.createTempFile(nombreArchivo, ".jpg", directorio)

        return FileProvider.getUriForFile(
            context,
            "${context.packageName}.provider",
            archivo
        )
    }


    /**
     * Abre la cámara para tomar una foto
     * @param launcher ActivityResultLauncher para manejar el resultado
     * @return true si se pudo abrir la cámara, false en caso contrario
     */private fun InputStream.leerBytes(): ByteArray {
        return use { inputStream ->
            ByteArrayOutputStream().use { outputStream ->
                val buffer = ByteArray(1024)
                var longitud: Int
                while (inputStream.read(buffer).also { longitud = it } != -1) {
                    outputStream.write(buffer, 0, longitud)
                }
                outputStream.toByteArray()
            }
        }
    }

    private fun eliminarFotoTemporal() {
        uriFotoTemporal?.let { uri ->
            try {
                context.contentResolver.delete(uri, null, null)
            } catch (e: Exception) {
                // Ignorar error al eliminar archivo temporal
            }
        }
        uriFotoTemporal = null
    }
}
/**
 * Guarda la foto en la galería del dispositivo
 * @param rutaFoto Ruta del archivo de la foto
 * @param descripcion Descripción de la foto para guardar en MediaStore
 * @return Uri de la foto guardada en la galería o null si falló
 */
data class TomarFotoLauncher(
    val onAbrirCamara: () -> Unit,
    val onAbrirGaleria: () -> Unit
)

// Extensión para comprimir imagen si es muy grande
fun ByteArray.comprimirImagen(maxSizeKB: Int = 500): ByteArray {
    if (this.size <= maxSizeKB * 1024) {
        return this
    }

    // Aquí podrías implementar compresión de imagen
    // Por simplicidad, retornamos los bytes originales
    // En una implementación real, usarías BitmapFactory para comprimir
    return this
}
```
# ManejadorMapas
```
package mx.edu.utng.mrs.mycomunidad.utilidades

import android.content.Context
import android.location.Geocoder
import com.google.android.gms.maps.model.LatLng
import kotlinx.coroutines.Dispatchers
import kotlinx.coroutines.withContext
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Ubicacion
import java.util.Locale
/**
 * Utilidad para manejar operaciones con mapas y navegación
 *
 * @property context Contexto de la aplicación
 */
class ManejadorMapas(private val context: Context) {

    private val geocoder = Geocoder(context, Locale.getDefault())
    /**
     * Abre Google Maps con una ubicación específica
     * @param latitud Coordenada de latitud
     * @param longitud Coordenada de longitud
     * @param etiqueta Etiqueta para mostrar en el marcador
     * @return true si se pudo abrir Google Maps, false en caso contrario
     */
    suspend fun obtenerDireccionDesdeCoordenadas(latitud: Double, longitud: Double): String {
        return withContext(Dispatchers.IO) {
            try {
                val direcciones = geocoder.getFromLocation(latitud, longitud, 1)
                if (!direcciones.isNullOrEmpty()) {
                    val direccion = direcciones[0]
                    val calle = direccion.thoroughfare ?: ""
                    val numero = direccion.subThoroughfare ?: ""
                    val colonia = direccion.subLocality ?: ""
                    val ciudad = direccion.locality ?: ""

                    buildString {
                        if (calle.isNotBlank()) append(calle)
                        if (numero.isNotBlank()) append(" #$numero")
                        if (colonia.isNotBlank()) append(", $colonia")
                        if (ciudad.isNotBlank()) append(", $ciudad")
                    }.ifBlank { "Ubicación seleccionada" }
                } else {
                    "Ubicación no encontrada"
                }
                /**
                 * Abre cualquier aplicación de mapas disponible
                 * @param latitud Coordenada de latitud
                 * @param longitud Coordenada de longitud
                 * @param etiqueta Etiqueta para mostrar
                 * @return true si se pudo abrir alguna aplicación de mapas, false en caso contrario
                 */
            } catch (e: Exception) {
                "Error obteniendo dirección: ${e.message}"
            }
        }
    }
    /**
     * Abre Google Maps con direcciones desde la ubicación actual
     * @param latitudDestino Latitud del destino
     * @param longitudDestino Longitud del destino
     * @param etiquetaDestino Etiqueta del destino
     * @param modoTransporte Modo de transporte (driving, walking, bicycling, transit)
     * @return true si se pudo abrir, false en caso contrario
     */
    suspend fun obtenerCoordenadasDesdeDireccion(direccion: String): LatLng? {
        return withContext(Dispatchers.IO) {
            try {
                val direcciones = geocoder.getFromLocationName(direccion, 1)
                if (!direcciones.isNullOrEmpty()) {
                    val ubicacion = direcciones[0]
                    LatLng(ubicacion.latitude, ubicacion.longitude)
                } else {
                    null
                }
            } catch (e: Exception) {
                null
            }
        }
    }

    /**
     * Calcula la distancia entre dos ubicaciones usando la fórmula del haversine
     * @param ubicacion1 Primera ubicación
     * @param ubicacion2 Segunda ubicación
     * @return Distancia en kilómetros
     */
    fun calcularDistancia(
        lat1: Double,
        lon1: Double,
        lat2: Double,
        lon2: Double
    ): Double {
        val radioTierra = 6371 // Radio de la Tierra en kilómetros

        val dLat = Math.toRadians(lat2 - lat1)
        val dLon = Math.toRadians(lon2 - lon1)

        val a = Math.sin(dLat / 2) * Math.sin(dLat / 2) +
                Math.cos(Math.toRadians(lat1)) * Math.cos(Math.toRadians(lat2)) *
                Math.sin(dLon / 2) * Math.sin(dLon / 2)

        val c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a))

        return radioTierra * c
    }
    /**
     * Formatea una distancia para mostrar de manera amigable
     * @param distanciaKm Distancia en kilómetros
     * @return String formateado (ej: "1.5 km" o "500 m")
     */
    fun crearUbicacion(latLng: LatLng, direccion: String): Ubicacion {
        return Ubicacion(
            latitud = latLng.latitude,
            longitud = latLng.longitude,
            direccion = direccion
        )
    }
}
```








