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
# Administrador 
#PantallaGestionUsuario.kt 
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas.administrador

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Delete
import androidx.compose.material.icons.filled.Person
import androidx.compose.material.icons.filled.Search
import androidx.compose.material.icons.filled.Security
import androidx.compose.material.icons.filled.Visibility
import androidx.compose.material3.AlertDialog
import androidx.compose.material3.Button
import androidx.compose.material3.ButtonDefaults
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.CircularProgressIndicator
import androidx.compose.material3.ExperimentalMaterial3Api
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.material3.TopAppBar
import androidx.compose.material3.TopAppBarDefaults
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.hilt.navigation.compose.hiltViewModel
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.input.TextFieldValue
import androidx.compose.ui.unit.dp
import mx.edu.utng.mrs.mycomunidad.datos.modelo.RolUsuario
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Usuario
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelAdministrador
import java.text.SimpleDateFormat
import java.util.Date
import java.util.Locale
/**
 * Pantalla para la gestión de usuarios por parte del administrador
 * Permite ver, buscar, filtrar y gestionar usuarios del sistema
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja la lógica de gestión de usuarios
 * @param onNavigateBack Callback para regresar a la pantalla anterior
 * @param onNavigateToUserDetail Callback para navegar al detalle de un usuario
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaGestionUsuarios(
    onNavegarAtras: () -> Unit,
    viewModel: ViewModelAdministrador = hiltViewModel()
) {
    val usuarios by viewModel.usuarios.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()
    val mensajeError by viewModel.mensajeError.collectAsState()
    var textoBusqueda by remember { mutableStateOf(TextFieldValue()) }
    var usuarioAEliminar by remember { mutableStateOf<Usuario?>(null) }
    var mostrarDialogoEliminar by remember { mutableStateOf(false) }

    LaunchedEffect(Unit) {
        viewModel.cargarUsuarios()
    }

    /**
     * Componente de la lista de usuarios para administrador
     *
     * @param users Lista de usuarios a mostrar
     * @param onUserClick Callback cuando se hace clic en un usuario
     * @param onToggleUserStatus Callback para activar/desactivar usuario
     */

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Gestión de Usuarios") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primary,
                    titleContentColor = MaterialTheme.colorScheme.onPrimary
                )
            )
        }
    ) { paddingValores ->
        Column(
            modifier = Modifier
                .fillMaxSize()
                .padding(paddingValores)
                .padding(16.dp)
        ) {
            if (!mensajeError.isNullOrEmpty()) {
                Card(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(bottom = 16.dp),
                    colors = CardDefaults.cardColors(
                        containerColor = Color.Red.copy(alpha = 0.1f)
                    )
                ) {
                    Text(
                        text = "ERROR: $mensajeError",
                        color = Color.Red,
                        modifier = Modifier.padding(16.dp)
                    )
                }
            }

            OutlinedTextField(
                value = textoBusqueda,
                onValueChange = { textoBusqueda = it },
                label = { Text("Buscar usuarios...") },
                leadingIcon = {
                    Icon(Icons.Default.Search, contentDescription = "Buscar")
                },
                modifier = Modifier.fillMaxWidth(),
                singleLine = true
            )

            Spacer(modifier = Modifier.height(16.dp))

            Card(
                modifier = Modifier.fillMaxWidth(),
                colors = CardDefaults.cardColors(
                    containerColor = MaterialTheme.colorScheme.surfaceVariant
                )
            ) {
                Row(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(16.dp),
                    horizontalArrangement = Arrangement.SpaceAround
                ) {
                    EstadisticaUsuario(
                        titulo = "Total",
                        valor = usuarios.size.toString(),
                        color = MaterialTheme.colorScheme.primary
                    )
                    EstadisticaUsuario(
                        titulo = "Administradores",
                        valor = usuarios.count { it.rol == RolUsuario.ADMINISTRADOR }.toString(),
                        color = Color(0xFF2196F3)
                    )
                    EstadisticaUsuario(
                        titulo = "Usuarios",
                        valor = usuarios.count { it.rol == RolUsuario.USUARIO }.toString(),
                        color = Color(0xFF4CAF50)
                    )
                }
            }

            Spacer(modifier = Modifier.height(16.dp))

            Card(
                modifier = Modifier.fillMaxWidth(),
                colors = CardDefaults.cardColors(
                    containerColor = Color(0xFFFFF3CD)
                )
            ) {
                Column(
                    modifier = Modifier.padding(12.dp)
                ) {
                    Text(
                        "🔍 INFORMACIÓN DE DEBUG:",
                        style = MaterialTheme.typography.labelSmall,
                        fontWeight = FontWeight.Bold,
                        color = Color(0xFF856404)
                    )
                    Text(
                        "Usuarios cargados: ${usuarios.size}",
                        style = MaterialTheme.typography.labelSmall,
                        color = Color(0xFF856404)
                    )
                    Text(
                        "Estado carga: ${if (estaCargando) "CARGANDO..." else "COMPLETADO"}",
                        style = MaterialTheme.typography.labelSmall,
                        color = Color(0xFF856404)
                    )
                }
            }

            Spacer(modifier = Modifier.height(16.dp))

            if (estaCargando && usuarios.isEmpty()) {
                Box(
                    modifier = Modifier
                        .fillMaxWidth()
                        .weight(1f),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        CircularProgressIndicator()
                        Spacer(modifier = Modifier.height(16.dp))
                        Text("Cargando usuarios...")
                        Text(
                            "Revisa Logcat para ver el progreso",
                            style = MaterialTheme.typography.labelSmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            } else if (usuarios.isEmpty()) {
                Box(
                    modifier = Modifier
                        .fillMaxWidth()
                        .weight(1f),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        Icon(
                            imageVector = Icons.Default.Person,
                            contentDescription = "Sin usuarios",
                            modifier = Modifier.size(64.dp),
                            tint = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Spacer(modifier = Modifier.height(16.dp))
                        Text(
                            "No hay usuarios registrados",
                            style = MaterialTheme.typography.bodyLarge
                        )
                        Text(
                            "Verifica Firestore Console",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            } else {
                val usuariosFiltrados = if (textoBusqueda.text.isBlank()) {
                    usuarios
                } else {
                    usuarios.filter { usuario ->
                        usuario.nombre.contains(textoBusqueda.text, ignoreCase = true) ||
                                usuario.email.contains(textoBusqueda.text, ignoreCase = true)
                    }
                }

                LazyColumn(
                    modifier = Modifier.weight(1f),
                    verticalArrangement = Arrangement.spacedBy(12.dp)
                ) {
                    items(usuariosFiltrados) { usuario ->
                        TarjetaUsuario(
                            usuario = usuario,
                            onEliminar = {
                                usuarioAEliminar = usuario
                                mostrarDialogoEliminar = true
                            },
                            onCambiarRol = { nuevoRol ->
                                viewModel.actualizarRolUsuario(usuario.id, nuevoRol)
                            }
                        )
                    }
                }
            }
        }
    }

    if (mostrarDialogoEliminar && usuarioAEliminar != null) {
        AlertDialog(
            onDismissRequest = {
                mostrarDialogoEliminar = false
                usuarioAEliminar = null
            },
            title = { Text("Eliminar Usuario") },
            text = {
                Text("¿Estás seguro de que deseas eliminar al usuario ${usuarioAEliminar?.nombre}? Esta acción no se puede deshacer.")
            },
            confirmButton = {
                TextButton(
                    onClick = {
                        usuarioAEliminar?.let { usuario ->
                            viewModel.eliminarUsuario(usuario.id)
                        }
                        mostrarDialogoEliminar = false
                        usuarioAEliminar = null
                    }
                ) {
                    Text("Eliminar", color = Color.Red)
                }
            },
            dismissButton = {
                TextButton(
                    onClick = {
                        mostrarDialogoEliminar = false
                        usuarioAEliminar = null
                    }
                ) {
                    Text("Cancelar")
                }
            }
        )
    }
}

@Composable
fun EstadisticaUsuario(
    titulo: String,
    valor: String,
    color: Color
) {
    Column(
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Text(
            valor,
            style = MaterialTheme.typography.headlineSmall,
            fontWeight = FontWeight.Bold,
            color = color
        )
        Text(
            titulo,
            style = MaterialTheme.typography.labelSmall,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )
    }
}

@Composable
fun TarjetaUsuario(
    usuario: Usuario,
    onEliminar: () -> Unit,
    onCambiarRol: (RolUsuario) -> Unit
) {
    Card(
        modifier = Modifier.fillMaxWidth(),
        shape = RoundedCornerShape(12.dp),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Column(
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp)
        ) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                verticalAlignment = Alignment.CenterVertically
            ) {
                Box(
                    modifier = Modifier
                        .size(50.dp)
                        .clip(RoundedCornerShape(25.dp))
                        .background(
                            color = MaterialTheme.colorScheme.primary.copy(alpha = 0.1f)
                        ),
                    contentAlignment = Alignment.Center
                ) {
                    Icon(
                        imageVector = Icons.Default.Person,
                        contentDescription = "Usuario",
                        tint = MaterialTheme.colorScheme.primary
                    )
                }

                Spacer(modifier = Modifier.width(12.dp))

                Column(
                    modifier = Modifier.weight(1f)
                ) {
                    Text(
                        usuario.nombre,
                        style = MaterialTheme.typography.titleMedium,
                        fontWeight = FontWeight.SemiBold
                    )
                    Text(
                        usuario.email,
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Spacer(modifier = Modifier.height(4.dp))

                    Text(
                        text = usuario.rol.name,
                        style = MaterialTheme.typography.labelSmall,
                        color = when (usuario.rol) {
                            RolUsuario.ADMINISTRADOR -> Color(0xFF2196F3)
                            RolUsuario.USUARIO -> Color(0xFF4CAF50)
                        },
                        modifier = Modifier
                            .clip(RoundedCornerShape(4.dp))
                            .background(
                                color = when (usuario.rol) {
                                    RolUsuario.ADMINISTRADOR -> Color(0xFF2196F3).copy(alpha = 0.1f)
                                    RolUsuario.USUARIO -> Color(0xFF4CAF50).copy(alpha = 0.1f)
                                }
                            )
                            .padding(horizontal = 8.dp, vertical = 2.dp)
                    )
                }

                IconButton(
                    onClick = onEliminar,
                    modifier = Modifier.size(24.dp)
                ) {
                    Icon(
                        imageVector = Icons.Default.Delete,
                        contentDescription = "Eliminar usuario",
                        tint = Color.Red
                    )
                }
            }

            Spacer(modifier = Modifier.height(12.dp))

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                if (usuario.rol == RolUsuario.USUARIO) {
                    Button(
                        onClick = { onCambiarRol(RolUsuario.ADMINISTRADOR) },
                        modifier = Modifier.weight(1f),
                        colors = ButtonDefaults.buttonColors(
                            containerColor = Color(0xFF2196F3)
                        )
                    ) {
                        Row(
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Icon(
                                Icons.Default.Security,
                                contentDescription = "Hacer admin",
                                modifier = Modifier.size(16.dp)
                            )
                            Spacer(modifier = Modifier.width(4.dp))
                            Text("Hacer Admin")
                        }
                    }
                } else {
                    Button(
                        onClick = { onCambiarRol(RolUsuario.USUARIO) },
                        modifier = Modifier.weight(1f),
                        colors = ButtonDefaults.buttonColors(
                            containerColor = Color(0xFF4CAF50)
                        )
                    ) {
                        Row(
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Icon(
                                Icons.Default.Person,
                                contentDescription = "Hacer usuario",
                                modifier = Modifier.size(16.dp)
                            )
                            Spacer(modifier = Modifier.width(4.dp))
                            Text("Hacer Usuario")
                        }
                    }
                }

                Button(
                    onClick = { },
                    modifier = Modifier.weight(1f),
                    colors = ButtonDefaults.buttonColors(
                        containerColor = MaterialTheme.colorScheme.surfaceVariant,
                        contentColor = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                ) {
                    Row(
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Icon(
                            Icons.Default.Visibility,
                            contentDescription = "Ver reportes",
                            modifier = Modifier.size(16.dp)
                        )
                        Spacer(modifier = Modifier.width(4.dp))
                        Text("Reportes")
                    }
                }
            }

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Text(
                    "Registrado: ${formatearFecha(usuario.fechaCreacion)}",
                    style = MaterialTheme.typography.labelSmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
                Text(
                    if (usuario.estaActivo) "Activo" else "Inactivo",
                    style = MaterialTheme.typography.labelSmall,
                    color = if (usuario.estaActivo) Color(0xFF4CAF50) else Color(0xFFF44336)
                )
            }
        }
    }
}

private fun formatearFecha(tiempoMillis: Long): String {
    val fecha = Date(tiempoMillis)
    val formateador = SimpleDateFormat("dd/MM/yyyy HH:mm", Locale.getDefault())
    return formateador.format(fecha)
}
```
# PantallaPanelAdministrador.kt
```package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas.administrador

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.PaddingValues
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.AccountCircle
import androidx.compose.material.icons.filled.ArrowForward
import androidx.compose.material.icons.filled.ExitToApp
import androidx.compose.material.icons.filled.PendingActions
import androidx.compose.material.icons.filled.Report
import androidx.compose.material.icons.filled.Verified
import androidx.compose.material.icons.filled.People
import androidx.compose.material.icons.filled.Warning
import androidx.compose.material.icons.filled.BarChart
import androidx.compose.material3.Card
import androidx.compose.material3.CardDefaults
import androidx.compose.material3.CircularProgressIndicator
import androidx.compose.material3.ExperimentalMaterial3Api
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.material3.TopAppBar
import androidx.compose.material3.TopAppBarDefaults
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelAdministrador
/**
 * Panel principal de administrador con métricas y acceso rápido a funciones
 * Muestra estadísticas generales del sistema y enlaces a diferentes módulos
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja los datos del panel
 * @param onNavigateToUsers Callback para navegar a gestión de usuarios
 * @param onNavigateToReports Callback para navegar a validación de reportes
 * @param onNavigateToStatistics Callback para navegar a estadísticas detalladas
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaPanelAdministrador(

    /**
     * Componente de métricas del sistema
     *
     * @param metrics Datos de métricas a mostrar
     */
    onNavegarAValidacion: () -> Unit,
    onNavegarAGestionUsuarios: () -> Unit,
    onNavegarAReportesAprobados: () -> Unit,
    onNavegarAEstadisticas: () -> Unit,
    onNavegarAPerfil: () -> Unit,
    onCerrarSesion: () -> Unit,
    viewModel: ViewModelAdministrador = hiltViewModel()
) {
    // Implementación del panel de administrador
    // Incluiría: métricas, gráficos rápidos, accesos directos
    val reportesPendientes by viewModel.reportesPendientes.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()
    val totalUsuarios by viewModel.totalUsuarios.collectAsState()
    val reportesResueltos by viewModel.reportesResueltos.collectAsState()
    val reportesUrgentes by viewModel.reportesUrgentes.collectAsState()
    val conteoPorPrioridad by viewModel.conteoPorPrioridad.collectAsState()
    val usuarioAdministrador by viewModel.usuarioAdministrador.collectAsState()

    LaunchedEffect(Unit) {
        viewModel.cargarDatosCompletos()
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = {
                    Column {
                        Text("Panel de Administración")
                        usuarioAdministrador?.let { usuario ->
                            Text(
                                "Hola, ${usuario.nombre}",
                                style = MaterialTheme.typography.labelSmall,
                                color = MaterialTheme.colorScheme.onPrimary.copy(alpha = 0.8f)
                            )
                        }
                    }
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primary,
                    titleContentColor = MaterialTheme.colorScheme.onPrimary
                ),
                actions = {
                    // Botón para ir al perfil
                    IconButton(onClick = onNavegarAPerfil) {
                        Icon(
                            imageVector = Icons.Default.AccountCircle,
                            contentDescription = "Mi Perfil",
                            tint = MaterialTheme.colorScheme.onPrimary
                        )
                    }
                    IconButton(onClick = onCerrarSesion) {
                        Icon(
                            imageVector = Icons.Default.ExitToApp,
                            contentDescription = "Cerrar Sesión",
                            tint = MaterialTheme.colorScheme.onPrimary
                        )
                    }
                }
            )
        }
    ) { paddingValores ->
        Column(
            modifier = Modifier
                .fillMaxSize()
                .padding(paddingValores)
                .padding(16.dp)
        ) {
            // Tarjetas de Estadísticas
            Text(
                "Resumen del Sistema",
                style = MaterialTheme.typography.headlineSmall,
                modifier = Modifier.padding(bottom = 16.dp)
            )

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(12.dp)
            ) {
                // Tarjeta Reportes Pendientes
                TarjetaEstadistica(
                    titulo = "Pendientes",
                    valor = reportesPendientes.size.toString(),
                    icono = Icons.Default.PendingActions,
                    color = Color(0xFFFF9800),
                    modifier = Modifier.weight(1f)
                )

                // Tarjeta Total Usuarios
                TarjetaEstadistica(
                    titulo = "Usuarios",
                    valor = totalUsuarios.toString(),
                    icono = Icons.Default.People,
                    color = Color(0xFF2196F3),
                    modifier = Modifier.weight(1f)
                )
            }

            Spacer(modifier = Modifier.height(16.dp))

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(12.dp)
            ) {
                // Tarjeta Reportes Resueltos
                TarjetaEstadistica(
                    titulo = "Resueltos",
                    valor = reportesResueltos.toString(),
                    icono = Icons.Default.Verified,
                    color = Color(0xFF4CAF50),
                    modifier = Modifier.weight(1f)
                )

                // Tarjeta Reportes Urgentes
                TarjetaEstadistica(
                    titulo = "Urgentes",
                    valor = reportesUrgentes.toString(),
                    icono = Icons.Default.Warning,
                    color = Color(0xFFF44336),
                    modifier = Modifier.weight(1f)
                )
            }

            Spacer(modifier = Modifier.height(16.dp))

            // Conteo por Prioridad
            Text(
                "Reportes por Prioridad",
                style = MaterialTheme.typography.titleMedium,
                fontWeight = FontWeight.SemiBold,
                modifier = Modifier.padding(bottom = 8.dp)
            )

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                val prioridades = listOf("Baja", "Media", "Alta", "Urgente")
                prioridades.forEach { prioridad ->
                    ChipPrioridad(
                        prioridad = prioridad,
                        cantidad = conteoPorPrioridad[prioridad] ?: 0,
                        modifier = Modifier.weight(1f)
                    )
                }
            }

            Spacer(modifier = Modifier.height(24.dp))

            // Sección de Acciones Rápidas
            Text(
                "Acciones Rápidas",
                style = MaterialTheme.typography.headlineSmall,
                modifier = Modifier.padding(bottom = 16.dp)
            )

            Column(
                verticalArrangement = Arrangement.spacedBy(12.dp)
            ) {
                // Botón Validar Reportes
                BotonAccionAdministrador(
                    titulo = "Validar Reportes Pendientes",
                    subtitulo = "${reportesPendientes.size} reportes esperando aprobación",
                    icono = Icons.Default.Report,
                    onClick = onNavegarAValidacion
                )

                // Botón Gestión de Usuarios
                BotonAccionAdministrador(
                    titulo = "Gestión de Usuarios",
                    subtitulo = "Administrar usuarios del sistema",
                    icono = Icons.Default.People,
                    onClick = onNavegarAGestionUsuarios
                )

                // Botón Estadísticas Detalladas
                BotonAccionAdministrador(
                    titulo = "Estadísticas Detalladas",
                    subtitulo = "Ver reportes y métricas avanzadas",
                    icono = Icons.Default.BarChart,
                    onClick = onNavegarAEstadisticas
                )

                // Botón Reportes Aprobados
                BotonAccionAdministrador(
                    titulo = "Reportes Aprobados",
                    subtitulo = "Ver reportes aprobados recientemente",
                    icono = Icons.Default.Verified,
                    onClick = onNavegarAReportesAprobados
                )
            }

            Spacer(modifier = Modifier.height(24.dp))

            // Lista de Reportes Pendientes Recientes
            Text(
                "Reportes Pendientes Recientes",
                style = MaterialTheme.typography.headlineSmall,
                modifier = Modifier.padding(bottom = 16.dp)
            )

            if (estaCargando) {
                Box(
                    modifier = Modifier
                        .fillMaxWidth()
                        .height(100.dp),
                    contentAlignment = Alignment.Center
                ) {
                    CircularProgressIndicator()
                }
            } else if (reportesPendientes.isEmpty()) {
                Card(
                    modifier = Modifier.fillMaxWidth(),
                    colors = CardDefaults.cardColors(
                        containerColor = MaterialTheme.colorScheme.surfaceVariant
                    )
                ) {
                    Column(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(24.dp),
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        Icon(
                            imageVector = Icons.Default.Verified,
                            contentDescription = "Sin reportes",
                            modifier = Modifier.size(48.dp),
                            tint = MaterialTheme.colorScheme.primary
                        )
                        Spacer(modifier = Modifier.height(8.dp))
                        Text(
                            "No hay reportes pendientes",
                            style = MaterialTheme.typography.bodyLarge,
                            textAlign = TextAlign.Center
                        )
                        Text(
                            "Todos los reportes han sido revisados",
                            style = MaterialTheme.typography.bodyMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant,
                            textAlign = TextAlign.Center
                        )
                    }
                }
            } else {
                LazyColumn(
                    verticalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    items(reportesPendientes.take(5)) { reporte ->
                        TarjetaReportePendiente(
                            reporte = reporte,
                            onClick = { onNavegarAValidacion() }
                        )
                    }
                }
            }
        }
    }
}

@Composable
fun TarjetaEstadistica(
    titulo: String,
    valor: String,
    icono: androidx.compose.ui.graphics.vector.ImageVector,
    color: Color,
    modifier: Modifier = Modifier
) {
    Card(
        modifier = modifier,
        shape = RoundedCornerShape(12.dp),
        colors = CardDefaults.cardColors(
            containerColor = MaterialTheme.colorScheme.surface
        ),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Column(
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp),
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            Icon(
                imageVector = icono,
                contentDescription = titulo,
                modifier = Modifier.size(32.dp),
                tint = color
            )
            Spacer(modifier = Modifier.height(8.dp))
            Text(
                valor,
                style = MaterialTheme.typography.headlineMedium,
                fontWeight = FontWeight.Bold,
                color = color
            )
            Text(
                titulo,
                style = MaterialTheme.typography.bodySmall,
                color = MaterialTheme.colorScheme.onSurfaceVariant,
                textAlign = TextAlign.Center
            )
        }
    }
}

@Composable
fun ChipPrioridad(
    prioridad: String,
    cantidad: Int,
    modifier: Modifier = Modifier
) {
    val color = when (prioridad) {
        "Urgente" -> Color(0xFFF44336)
        "Alta" -> Color(0xFFFF9800)
        "Media" -> Color(0xFF2196F3)
        "Baja" -> Color(0xFF4CAF50)
        else -> MaterialTheme.colorScheme.primary
    }

    Card(
        modifier = modifier,
        shape = RoundedCornerShape(8.dp),
        colors = CardDefaults.cardColors(
            containerColor = color.copy(alpha = 0.1f)
        )
    ) {
        Column(
            modifier = Modifier
                .fillMaxWidth()
                .padding(12.dp),
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            Text(
                prioridad,
                style = MaterialTheme.typography.labelSmall,
                fontWeight = FontWeight.Bold,
                color = color
            )
            Spacer(modifier = Modifier.height(4.dp))
            Text(
                cantidad.toString(),
                style = MaterialTheme.typography.titleMedium,
                fontWeight = FontWeight.Bold,
                color = color
            )
        }
    }
}

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun BotonAccionAdministrador(
    titulo: String,
    subtitulo: String,
    icono: androidx.compose.ui.graphics.vector.ImageVector,
    onClick: () -> Unit,
    modifier: Modifier = Modifier
) {
    Card(
        onClick = onClick,
        modifier = modifier.fillMaxWidth(),
        shape = RoundedCornerShape(12.dp),
        colors = CardDefaults.cardColors(
            containerColor = MaterialTheme.colorScheme.surface
        ),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp),
            verticalAlignment = Alignment.CenterVertically
        ) {
            Icon(
                imageVector = icono,
                contentDescription = titulo,
                modifier = Modifier.size(40.dp),
                tint = MaterialTheme.colorScheme.primary
            )
            Spacer(modifier = Modifier.width(16.dp))
            Column(
                modifier = Modifier.weight(1f)
            ) {
                Text(
                    titulo,
                    style = MaterialTheme.typography.titleMedium,
                    fontWeight = FontWeight.SemiBold
                )
                Text(
                    subtitulo,
                    style = MaterialTheme.typography.bodyMedium,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
            Icon(
                imageVector = Icons.Default.ArrowForward,
                contentDescription = "Ir",
                tint = MaterialTheme.colorScheme.onSurfaceVariant
            )
        }
    }
}

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun TarjetaReportePendiente(
    reporte: Reporte,
    onClick: () -> Unit
) {
    Card(
        onClick = onClick,
        modifier = Modifier.fillMaxWidth(),
        shape = RoundedCornerShape(8.dp),
        colors = CardDefaults.cardColors(
            containerColor = MaterialTheme.colorScheme.surfaceVariant
        )
    ) {
        Column(
            modifier = Modifier
                .fillMaxWidth()
                .padding(12.dp)
        ) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Text(
                    reporte.titulo,
                    style = MaterialTheme.typography.titleSmall,
                    fontWeight = FontWeight.SemiBold,
                    maxLines = 1,
                    modifier = Modifier.weight(1f)
                )
                Text(
                    reporte.gravedad,
                    style = MaterialTheme.typography.labelSmall,
                    color = when (reporte.gravedad) {
                        "Urgente" -> Color(0xFFF44336)
                        "Alta" -> Color(0xFFFF9800)
                        "Media" -> Color(0xFF2196F3)
                        "Baja" -> Color(0xFF4CAF50)
                        else -> MaterialTheme.colorScheme.onSurfaceVariant
                    },
                    modifier = Modifier
                        .clip(RoundedCornerShape(4.dp))
                        .background(
                            color = when (reporte.gravedad) {
                                "Urgente" -> Color(0xFFF44336).copy(alpha = 0.1f)
                                "Alta" -> Color(0xFFFF9800).copy(alpha = 0.1f)
                                "Media" -> Color(0xFF2196F3).copy(alpha = 0.1f)
                                "Baja" -> Color(0xFF4CAF50).copy(alpha = 0.1f)
                                else -> MaterialTheme.colorScheme.surfaceVariant
                            }
                        )
                        .padding(horizontal = 6.dp, vertical = 2.dp)
                )
            }
            Spacer(modifier = Modifier.height(4.dp))
            Text(
                reporte.descripcion,
                style = MaterialTheme.typography.bodySmall,
                maxLines = 2,
                color = MaterialTheme.colorScheme.onSurfaceVariant
            )
            Spacer(modifier = Modifier.height(8.dp))
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Text(
                    "Por: ${reporte.usuarioNombre}",
                    style = MaterialTheme.typography.labelSmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
                Text(
                    "Hace: ${obtenerTiempoTranscurrido(reporte.fechaCreacion)}",
                    style = MaterialTheme.typography.labelSmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        }
    }
}

// Función auxiliar para formatear tiempo
private fun obtenerTiempoTranscurrido(tiempoMillis: Long): String {
    val diferencia = System.currentTimeMillis() - tiempoMillis
    val minutos = diferencia / (1000 * 60)
    val horas = minutos / 60
    val dias = horas / 24

    return when {
        minutos < 1 -> "Hace un momento"
        minutos < 60 -> "Hace $minutos min"
        horas < 24 -> "Hace $horas h"
        else -> "Hace $dias d"
    }
}
```
# PantallaPerfilAdministrador.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas.administrador

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Edit
import androidx.compose.material.icons.filled.Email
import androidx.compose.material.icons.filled.Person
import androidx.compose.material.icons.filled.AdminPanelSettings
import androidx.compose.material.icons.filled.CalendarToday
import androidx.compose.material.icons.filled.Security
import androidx.compose.material.icons.filled.Refresh
import androidx.compose.material.icons.filled.AccessTime
import androidx.compose.material.icons.filled.Fingerprint
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelAdministrador
import java.text.SimpleDateFormat
import java.util.*
/**
 * Pantalla de perfil específica para administradores
 * Incluye funciones adicionales y configuración del sistema
 *
 * @param modifier Modificador para personalizar el layout
 * @param adminUser Datos del usuario administrador
 * @param onEditProfile Callback para editar perfil
 * @param onSystemSettings Callback para configuraciones del sistema
 * @param onLogout Callback para cerrar sesión
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaPerfilAdministrador(
    onVolver: () -> Unit,
    viewModel: ViewModelAdministrador = hiltViewModel()
) {
    // Implementación del perfil de administrador
    // Incluiría: información del admin, funciones especiales, configuración
    val usuario by viewModel.usuarioAdministrador.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()
    val mensajeError by viewModel.mensajeError.collectAsState()
    val mensajeExito by viewModel.mensajeExito.collectAsState()

    var mostrarDialogoEditar by remember { mutableStateOf(false) }
    var nombreTemp by remember { mutableStateOf("") }
    var emailTemp by remember { mutableStateOf("") }

    // Obtener fecha y hora de creación de la cuenta
    val fechaCreacionCuenta = remember(usuario?.fechaCreacion) {
        obtenerFechaHoraCreacion(usuario?.fechaCreacion)
    }
    /**
     * Componente de acciones de administrador en el perfil
     *
     * @param onSystemSettings Callback para configuraciones del sistema
     * @param onBackup Callback para crear backup
     * @param onAuditLog Callback para ver registros de auditoría
     */

    // Hora actual para "Último acceso"
    val horaActual = remember { obtenerHoraActualFormateada() }

    LaunchedEffect(Unit) {
        viewModel.cargarPerfilAdministrador()
    }

    DisposableEffect(Unit) {
        onDispose {
            viewModel.limpiarError()
            viewModel.limpiarMensajeExito()
        }
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Mi Perfil - Administrador") },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primary,
                    titleContentColor = MaterialTheme.colorScheme.onPrimary
                ),
                navigationIcon = {
                    IconButton(onClick = onVolver) {
                        Icon(
                            imageVector = Icons.Default.ArrowBack,
                            contentDescription = "Volver",
                            tint = MaterialTheme.colorScheme.onPrimary
                        )
                    }
                },
                actions = {
                    IconButton(onClick = {
                        usuario?.let {
                            nombreTemp = it.nombre
                            emailTemp = it.email
                            mostrarDialogoEditar = true
                        }
                    }) {
                        Icon(
                            imageVector = Icons.Default.Edit,
                            contentDescription = "Editar Perfil",
                            tint = MaterialTheme.colorScheme.onPrimary
                        )
                    }
                }
            )
        }
    ) { paddingValues ->
        Column(
            modifier = Modifier
                .fillMaxSize()
                .padding(paddingValues)
                .verticalScroll(rememberScrollState())
        ) {
            mensajeExito?.let { exito ->
                if (exito.isNotBlank()) {
                    Card(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(16.dp),
                        colors = CardDefaults.cardColors(
                            containerColor = MaterialTheme.colorScheme.primaryContainer
                        )
                    ) {
                        Text(
                            text = exito,
                            modifier = Modifier.padding(16.dp),
                            color = MaterialTheme.colorScheme.onPrimaryContainer,
                            textAlign = TextAlign.Center
                        )
                    }
                }
            }

            mensajeError?.let { error ->
                if (error.isNotBlank()) {
                    Card(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(16.dp),
                        colors = CardDefaults.cardColors(
                            containerColor = MaterialTheme.colorScheme.errorContainer
                        )
                    ) {
                        Text(
                            text = error,
                            modifier = Modifier.padding(16.dp),
                            color = MaterialTheme.colorScheme.onErrorContainer,
                            textAlign = TextAlign.Center
                        )
                    }
                }
            }

            if (estaCargando) {
                Box(
                    modifier = Modifier
                        .fillMaxSize()
                        .weight(1f),
                    contentAlignment = Alignment.Center
                ) {
                    CircularProgressIndicator()
                }
            } else {
                Card(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(16.dp),
                    elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
                ) {
                    Column(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(20.dp),
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        Icon(
                            imageVector = Icons.Default.AdminPanelSettings,
                            contentDescription = "Administrador",
                            modifier = Modifier.size(80.dp),
                            tint = MaterialTheme.colorScheme.primary
                        )
                        Spacer(modifier = Modifier.height(16.dp))
                        Text(
                            usuario?.nombre ?: "Administrador",
                            style = MaterialTheme.typography.headlineSmall,
                            fontWeight = FontWeight.Bold
                        )
                        Spacer(modifier = Modifier.height(8.dp))
                        Row(
                            verticalAlignment = Alignment.CenterVertically
                        ) {
                            Icon(
                                imageVector = Icons.Default.Email,
                                contentDescription = "Email",
                                modifier = Modifier.size(16.dp),
                                tint = MaterialTheme.colorScheme.onSurfaceVariant
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Text(
                                usuario?.email ?: "email@ejemplo.com",
                                style = MaterialTheme.typography.bodyMedium,
                                color = MaterialTheme.colorScheme.onSurfaceVariant
                            )
                        }
                        Spacer(modifier = Modifier.height(8.dp))
                        Card(
                            modifier = Modifier
                                .clip(MaterialTheme.shapes.small)
                                .background(MaterialTheme.colorScheme.primary.copy(alpha = 0.1f)),
                            colors = CardDefaults.cardColors(
                                containerColor = MaterialTheme.colorScheme.primary.copy(alpha = 0.1f)
                            )
                        ) {
                            Row(
                                modifier = Modifier.padding(horizontal = 12.dp, vertical = 6.dp),
                                verticalAlignment = Alignment.CenterVertically
                            ) {
                                Icon(
                                    imageVector = Icons.Default.Security,
                                    contentDescription = "Rol",
                                    modifier = Modifier.size(16.dp),
                                    tint = MaterialTheme.colorScheme.primary
                                )
                                Spacer(modifier = Modifier.width(4.dp))
                                Text(
                                    "ADMINISTRADOR",
                                    style = MaterialTheme.typography.labelSmall,
                                    fontWeight = FontWeight.Bold,
                                    color = MaterialTheme.colorScheme.primary
                                )
                            }
                        }
                    }
                }

                Card(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(16.dp),
                    elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
                ) {
                    Column(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(16.dp)
                    ) {
                        Text(
                            "Información de la Cuenta",
                            style = MaterialTheme.typography.titleLarge,
                            fontWeight = FontWeight.Bold,
                            modifier = Modifier.padding(bottom = 16.dp)
                        )

                        InfoCuentaItem(
                            titulo = "ID de Usuario",
                            valor = usuario?.id?.take(12) ?: "N/A",
                            icono = Icons.Default.Fingerprint,
                            modifier = Modifier.fillMaxWidth()
                        )

                        Divider(modifier = Modifier.padding(vertical = 8.dp))

                        InfoCuentaItem(
                            titulo = "Cuenta creada el",
                            valor = fechaCreacionCuenta ?: "Fecha no disponible",
                            icono = Icons.Default.CalendarToday,
                            modifier = Modifier.fillMaxWidth()
                        )

                        Divider(modifier = Modifier.padding(vertical = 8.dp))

                        InfoCuentaItem(
                            titulo = "Último acceso",
                            valor = "Hoy, $horaActual",
                            icono = Icons.Default.AccessTime,
                            modifier = Modifier.fillMaxWidth()
                        )
                    }
                }

                Card(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(16.dp),
                    elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
                ) {
                    Column(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(16.dp)
                    ) {
                        Text(
                            "Acciones de Administrador",
                            style = MaterialTheme.typography.titleLarge,
                            fontWeight = FontWeight.Bold,
                            modifier = Modifier.padding(bottom = 16.dp)
                        )

                        Button(
                            onClick = { viewModel.cargarDatosCompletos() },
                            modifier = Modifier.fillMaxWidth(),
                            colors = ButtonDefaults.buttonColors(
                                containerColor = MaterialTheme.colorScheme.primaryContainer,
                                contentColor = MaterialTheme.colorScheme.onPrimaryContainer
                            )
                        ) {
                            Icon(
                                imageVector = Icons.Default.Refresh,
                                contentDescription = "Recargar",
                                modifier = Modifier.size(20.dp)
                            )
                            Spacer(modifier = Modifier.width(8.dp))
                            Text("Recargar Datos del Sistema")
                        }
                    }
                }
            }
        }

        if (mostrarDialogoEditar) {
            DialogoEditarPerfil(
                nombre = nombreTemp,
                email = emailTemp,
                onNombreChange = { nombreTemp = it },
                onEmailChange = { emailTemp = it },
                onConfirmar = {
                    viewModel.actualizarPerfilAdministrador(nombreTemp, emailTemp)
                    mostrarDialogoEditar = false
                },
                onCancelar = {
                    mostrarDialogoEditar = false
                    viewModel.limpiarError()
                }
            )
        }
    }
}

@Composable
fun InfoCuentaItem(
    titulo: String,
    valor: String,
    icono: androidx.compose.ui.graphics.vector.ImageVector,
    modifier: Modifier = Modifier
) {
    Row(
        modifier = modifier,
        horizontalArrangement = Arrangement.SpaceBetween,
        verticalAlignment = Alignment.CenterVertically
    ) {
        Row(
            verticalAlignment = Alignment.CenterVertically
        ) {
            Icon(
                imageVector = icono,
                contentDescription = titulo,
                modifier = Modifier.size(20.dp),
                tint = MaterialTheme.colorScheme.onSurfaceVariant
            )
            Spacer(modifier = Modifier.width(12.dp))
            Text(
                titulo,
                style = MaterialTheme.typography.bodyMedium,
                fontWeight = FontWeight.Medium
            )
        }
        Text(
            valor,
            style = MaterialTheme.typography.bodyMedium,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )
    }
}

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun DialogoEditarPerfil(
    nombre: String,
    email: String,
    onNombreChange: (String) -> Unit,
    onEmailChange: (String) -> Unit,
    onConfirmar: () -> Unit,
    onCancelar: () -> Unit
) {
    AlertDialog(
        onDismissRequest = onCancelar,
        title = { Text("Editar Perfil") },
        text = {
            Column {
                OutlinedTextField(
                    value = nombre,
                    onValueChange = onNombreChange,
                    label = { Text("Nombre") },
                    modifier = Modifier.fillMaxWidth(),
                    singleLine = true
                )
                Spacer(modifier = Modifier.height(16.dp))
                OutlinedTextField(
                    value = email,
                    onValueChange = onEmailChange,
                    label = { Text("Email") },
                    modifier = Modifier.fillMaxWidth(),
                    singleLine = true
                )
            }
        },
        confirmButton = {
            TextButton(onClick = onConfirmar) {
                Text("Guardar")
            }
        },
        dismissButton = {
            TextButton(onClick = onCancelar) {
                Text("Cancelar")
            }
        }
    )
}

// Funciones de utilidad para formatear fechas y horas
private fun obtenerFechaHoraCreacion(timestamp: Long?): String? {
    return if (timestamp != null && timestamp > 0) {
        try {
            val date = Date(timestamp)
            val dateFormat = SimpleDateFormat("d 'de' MMMM 'de' yyyy 'a las' hh:mm a", Locale("es", "ES"))
            dateFormat.format(date)
        } catch (e: Exception) {
            "Fecha no disponible"
        }
    } else {
        null
    }
}

private fun obtenerHoraActualFormateada(): String {
    return try {
        val dateFormat = SimpleDateFormat("hh:mm a", Locale("es", "ES"))
        dateFormat.format(Date())
    } catch (e: Exception) {
        "hora no disponible"
    }
}
```
# PantallaReportesAprobados.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas.administrador

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.PaddingValues
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.CheckCircle
import androidx.compose.material.icons.filled.Verified
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelReportes
import java.text.SimpleDateFormat
import java.util.*
/**
 * Pantalla que muestra los reportes aprobados por el administrador
 * Permite revisar y filtrar reportes ya validados
 *
 * @param modifier Modificador para personalizar el layout
 * @param approvedReports Lista de reportes aprobados
 * @param onReportClick Callback cuando se hace clic en un reporte
 * @param onFilterChange Callback para cambiar filtros
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaReportesAprobados(
    onNavegarAtras: () -> Unit,
    onNavegarADetalleReporte: (String) -> Unit,
    viewModel: ViewModelReportes = hiltViewModel()
) {
    // Implementación de la pantalla de reportes aprobados
    // Incluiría: lista de reportes, filtros, estadísticas de aprobación
    /**
     * Componente de estadísticas de aprobación
     *
     * @param stats Estadísticas de reportes aprobados
     */
    val reportes by viewModel.reportes.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()

    LaunchedEffect(Unit) {
        viewModel.cargarReportes()
    }

    val reportesFiltrados = reportes.filter { reporte ->
        reporte.estado == EstadoReporte.APROBADO
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Reportes Aprobados") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primary,
                    titleContentColor = MaterialTheme.colorScheme.onPrimary
                )
            )
        }
    ) { paddingValores ->
        if (estaCargando) {
            Box(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(paddingValores),
                contentAlignment = Alignment.Center
            ) {
                Column(
                    horizontalAlignment = Alignment.CenterHorizontally
                ) {
                    CircularProgressIndicator()
                    Spacer(modifier = Modifier.height(16.dp))
                    Text("Cargando reportes...")
                }
            }
        } else if (reportesFiltrados.isEmpty()) {
            Box(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(paddingValores),
                contentAlignment = Alignment.Center
            ) {
                Column(
                    horizontalAlignment = Alignment.CenterHorizontally
                ) {
                    Icon(
                        imageVector = Icons.Default.Verified,
                        contentDescription = "Sin reportes",
                        modifier = Modifier.size(64.dp),
                        tint = MaterialTheme.colorScheme.primary
                    )
                    Spacer(modifier = Modifier.height(16.dp))
                    Text(
                        "No hay reportes aprobados",
                        style = MaterialTheme.typography.headlineSmall,
                        textAlign = TextAlign.Center
                    )
                    Text(
                        "Los reportes aprobados aparecerán aquí",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant,
                        textAlign = TextAlign.Center,
                        modifier = Modifier.padding(horizontal = 32.dp)
                    )
                }
            }
        } else {
            Column(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(paddingValores)
            ) {
                Card(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(16.dp),
                    colors = CardDefaults.cardColors(
                        containerColor = MaterialTheme.colorScheme.surfaceVariant
                    )
                ) {
                    Row(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(16.dp),
                        horizontalArrangement = Arrangement.SpaceAround
                    ) {
                        EstadisticaReporte(
                            titulo = "Total Aprobados",
                            valor = reportesFiltrados.size.toString(),
                            color = Color(0xFF4CAF50)
                        )
                        EstadisticaReporte(
                            titulo = "Este Mes",
                            valor = reportesFiltrados.count { reporte ->
                                esEsteMes(reporte.fechaCreacion)
                            }.toString(),
                            color = Color(0xFF2196F3)
                        )
                    }
                }

                LazyColumn(
                    modifier = Modifier.weight(1f),
                    contentPadding = PaddingValues(16.dp),
                    verticalArrangement = Arrangement.spacedBy(12.dp)
                ) {
                    items(
                        items = reportesFiltrados,
                        key = { reporte -> reporte.id }
                    ) { reporte ->
                        TarjetaReporteAprobado(
                            reporte = reporte,
                            onClick = { onNavegarADetalleReporte(reporte.id) }
                        )
                    }
                }
            }
        }
    }
}

@Composable
fun EstadisticaReporte(
    titulo: String,
    valor: String,
    color: Color
) {
    Column(
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Text(
            valor,
            style = MaterialTheme.typography.headlineSmall,
            fontWeight = FontWeight.Bold,
            color = color
        )
        Text(
            titulo,
            style = MaterialTheme.typography.labelSmall,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )
    }
}

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun TarjetaReporteAprobado(
    reporte: mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte,
    onClick: () -> Unit
) {
    Card(
        onClick = onClick,
        modifier = Modifier.fillMaxWidth(),
        shape = RoundedCornerShape(12.dp),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Column(
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp)
        ) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Text(
                    reporte.titulo,
                    style = MaterialTheme.typography.titleMedium,
                    fontWeight = FontWeight.SemiBold,
                    modifier = Modifier.weight(1f)
                )

                Row(
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Icon(
                        imageVector = Icons.Default.CheckCircle,
                        contentDescription = "Aprobado",
                        modifier = Modifier.size(16.dp),
                        tint = Color(0xFF4CAF50)
                    )
                    Spacer(modifier = Modifier.width(4.dp))
                    Text(
                        "APROBADO",
                        style = MaterialTheme.typography.labelSmall,
                        color = Color(0xFF4CAF50),
                        fontWeight = FontWeight.Bold
                    )
                }
            }

            Spacer(modifier = Modifier.height(8.dp))

            Text(
                reporte.descripcion,
                style = MaterialTheme.typography.bodyMedium,
                maxLines = 2,
                color = MaterialTheme.colorScheme.onSurfaceVariant
            )

            Spacer(modifier = Modifier.height(12.dp))

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Column {
                    // ✅ PARA ADMINISTRADOR: Mostrar nombre y email
                    Text(
                        "Por: ${reporte.usuarioNombre}",
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Text(
                        "Email: ${reporte.usuarioEmail}",
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant,
                        fontSize = 10.sp
                    )
                }
                Text(
                    text = "Aprobado: ${obtenerTiempoTranscurrido(reporte.fechaCreacion)}",
                    style = MaterialTheme.typography.labelSmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }

            Spacer(modifier = Modifier.height(8.dp))

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Column {
                    Text(
                        if (reporte.latitud != 0.0 && reporte.longitud != 0.0) {
                            "Lat: ${"%.4f".format(reporte.latitud)}, Lng: ${"%.4f".format(reporte.longitud)}"
                        } else {
                            "Ubicación no especificada"
                        },
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant,
                        maxLines = 1
                    )
                    Text(
                        "${reporte.meGustas.size} 👍 • ${reporte.comentarios.size} 💬",
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }

                Text(
                    when (reporte.tipo) {
                        TipoReporte.BACHE -> "Bache"
                        TipoReporte.ALUMBRADO -> "Alumbrado"
                        TipoReporte.BASURA -> "Basura"
                        TipoReporte.AGUA -> "Agua"
                        TipoReporte.OTRO -> "Otro"
                    },
                    style = MaterialTheme.typography.labelSmall,
                    color = MaterialTheme.colorScheme.primary,
                    modifier = Modifier
                        .clip(RoundedCornerShape(4.dp))
                        .background(
                            color = MaterialTheme.colorScheme.primary.copy(alpha = 0.1f)
                        )
                        .padding(horizontal = 8.dp, vertical = 2.dp)
                )
            }
        }
    }
}

private fun obtenerTiempoTranscurrido(tiempoMillis: Long): String {
    val diferencia = System.currentTimeMillis() - tiempoMillis
    val minutos = diferencia / (1000 * 60)
    val horas = minutos / 60
    val dias = horas / 24

    return when {
        minutos < 1 -> "Hace un momento"
        minutos < 60 -> "Hace $minutos min"
        horas < 24 -> "Hace $horas h"
        else -> "Hace $dias d"
    }
}

private fun esEsteMes(tiempoMillis: Long): Boolean {
    val calendarioReporte = Calendar.getInstance().apply {
        timeInMillis = tiempoMillis
    }
    val calendarioActual = Calendar.getInstance()

    return calendarioReporte.get(Calendar.YEAR) == calendarioActual.get(Calendar.YEAR) &&
            calendarioReporte.get(Calendar.MONTH) == calendarioActual.get(Calendar.MONTH)
}
```
# PantallaValidacionReportes.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas.administrador

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.BugReport
import androidx.compose.material.icons.filled.Check
import androidx.compose.material.icons.filled.Close
import androidx.compose.material.icons.filled.Visibility
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelAdministrador
import java.text.SimpleDateFormat
import java.util.*

/**
 * Pantalla para validar reportes pendientes de aprobación
 * Permite aprobar, rechazar o solicitar modificaciones a reportes
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja la validación de reportes
 * @param onApproveReport Callback para aprobar un reporte
 * @param onRejectReport Callback para rechazar un reporte
 * @param onRequestChanges Callback para solicitar cambios
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaValidacionReportes(
    onNavegarAtras: () -> Unit,
    onNavegarADetalleReporte: (String) -> Unit,
    viewModel: ViewModelAdministrador = hiltViewModel()
) {
    // Implementación de la pantalla de validación de reportes
    // Incluiría: lista de reportes pendientes, detalles, acciones de validación
    /**
     * Componente de acciones de validación para un reporte
     *
     * @param reportId ID del reporte
     * @param onApprove Callback para aprobar
     * @param onReject Callback para rechazar
     * @param onRequestChanges Callback para solicitar cambios
     */
    val reportesPendientes by viewModel.reportesPendientes.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()
    val mensajeError by viewModel.mensajeError.collectAsState()
    val mensajeExito by viewModel.mensajeExito.collectAsState()

    LaunchedEffect(Unit) { viewModel.cargarReportesPendientes() }
    LaunchedEffect(Unit) {
        viewModel.limpiarError()
        viewModel.limpiarMensajeExito()
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Validar Reportes") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primary,
                    titleContentColor = MaterialTheme.colorScheme.onPrimary
                )
            )
        }
    ) { paddingValores ->
        Column(modifier = Modifier.fillMaxSize().padding(paddingValores)) {
            if (!mensajeExito.isNullOrEmpty()) {
                Card(
                    modifier = Modifier.fillMaxWidth().padding(16.dp),
                    colors = CardDefaults.cardColors(containerColor = Color(0xFF4CAF50).copy(alpha = 0.1f))
                ) {
                    Row(modifier = Modifier.padding(16.dp), verticalAlignment = Alignment.CenterVertically) {
                        Text(text = "✅ $mensajeExito", color = Color(0xFF2E7D32), modifier = Modifier.weight(1f))
                        IconButton(onClick = { viewModel.limpiarMensajeExito() }, modifier = Modifier.size(24.dp)) {
                            Icon(Icons.Default.Close, contentDescription = "Cerrar", tint = Color(0xFF2E7D32))
                        }
                    }
                }
            }

            if (!mensajeError.isNullOrEmpty()) {
                Card(
                    modifier = Modifier.fillMaxWidth().padding(16.dp),
                    colors = CardDefaults.cardColors(containerColor = Color.Red.copy(alpha = 0.1f))
                ) {
                    Row(modifier = Modifier.padding(16.dp), verticalAlignment = Alignment.CenterVertically) {
                        Text(text = "❌ $mensajeError", color = Color.Red, modifier = Modifier.weight(1f))
                        IconButton(onClick = { viewModel.limpiarError() }, modifier = Modifier.size(24.dp)) {
                            Icon(Icons.Default.Close, contentDescription = "Cerrar", tint = Color.Red)
                        }
                    }
                }
            }

            if (estaCargando && reportesPendientes.isEmpty()) {
                Box(modifier = Modifier.fillMaxSize().weight(1f), contentAlignment = Alignment.Center) {
                    Column(horizontalAlignment = Alignment.CenterHorizontally) {
                        CircularProgressIndicator()
                        Spacer(modifier = Modifier.height(16.dp))
                        Text("Cargando reportes...")
                    }
                }
            } else if (reportesPendientes.isEmpty()) {
                Box(modifier = Modifier.fillMaxSize().weight(1f), contentAlignment = Alignment.Center) {
                    Column(horizontalAlignment = Alignment.CenterHorizontally) {
                        Icon(Icons.Default.Check, contentDescription = "Sin reportes", modifier = Modifier.size(64.dp), tint = MaterialTheme.colorScheme.primary)
                        Spacer(modifier = Modifier.height(16.dp))
                        Text("No hay reportes pendientes", style = MaterialTheme.typography.headlineSmall, textAlign = TextAlign.Center)
                        Text(
                            "Todos los reportes han sido revisados y aprobados",
                            style = MaterialTheme.typography.bodyMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant,
                            textAlign = TextAlign.Center,
                            modifier = Modifier.padding(horizontal = 32.dp)
                        )
                    }
                }
            } else {
                LazyColumn(
                    modifier = Modifier.weight(1f),
                    contentPadding = PaddingValues(16.dp),
                    verticalArrangement = Arrangement.spacedBy(12.dp)
                ) {
                    items(reportesPendientes) { reporte ->
                        TarjetaValidacionReporte(reporte, { onNavegarADetalleReporte(reporte.id) }, viewModel)
                    }
                }
            }
        }
    }
}

@Composable
fun TarjetaValidacionReporte(
    reporte: mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte,
    onVerDetalles: () -> Unit,
    viewModel: ViewModelAdministrador
) {
    var estaProcesandoAprobar by remember { mutableStateOf(false) }
    var estaProcesandoRechazar by remember { mutableStateOf(false) }

    if (estaProcesandoAprobar) {
        LaunchedEffect(Unit) {
            try { viewModel.aprobarReporte(reporte.id) } finally { estaProcesandoAprobar = false }
        }
    }

    if (estaProcesandoRechazar) {
        LaunchedEffect(Unit) {
            try { viewModel.rechazarReporte(reporte.id) } finally { estaProcesandoRechazar = false }
        }
    }

    Card(
        modifier = Modifier.fillMaxWidth(),
        shape = RoundedCornerShape(12.dp),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Column(modifier = Modifier.fillMaxWidth().padding(16.dp)) {
            Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceBetween, verticalAlignment = Alignment.CenterVertically) {
                Text(reporte.titulo, style = MaterialTheme.typography.titleLarge, fontWeight = FontWeight.Bold, modifier = Modifier.weight(1f))
                Text(
                    text = when (reporte.tipo) {
                        TipoReporte.BACHE -> "Bache"
                        TipoReporte.ALUMBRADO -> "Alumbrado"
                        TipoReporte.BASURA -> "Basura"
                        TipoReporte.AGUA -> "Agua"
                        TipoReporte.OTRO -> "Otro"
                    },
                    style = MaterialTheme.typography.labelSmall,
                    color = MaterialTheme.colorScheme.primary,
                    modifier = Modifier.clip(RoundedCornerShape(4.dp))
                        .background(color = MaterialTheme.colorScheme.primary.copy(alpha = 0.1f))
                        .padding(horizontal = 8.dp, vertical = 2.dp)
                )
            }

            Spacer(modifier = Modifier.height(8.dp))
            Text(reporte.descripcion, style = MaterialTheme.typography.bodyMedium, maxLines = 3)
            Spacer(modifier = Modifier.height(12.dp))

            // ✅ PARA ADMINISTRADOR: Mostrar toda la información
            Column {
                InfoItem("Usuario:", reporte.usuarioNombre)
                InfoItem("Email:", reporte.usuarioEmail)
                InfoItem("ID Usuario:", reporte.usuarioId.take(8) + "...")
                InfoItem(
                    "Ubicación:",
                    if (reporte.latitud != 0.0 && reporte.longitud != 0.0) {
                        "Lat: ${"%.4f".format(reporte.latitud)}, Lng: ${"%.4f".format(reporte.longitud)}"
                    } else { "No especificada" }
                )
                InfoItem("Fecha:", formatearFecha(reporte.fechaCreacion))
                InfoItem("Gravedad:", reporte.gravedad)
                InfoItem("Imágenes:", "${reporte.imagenUrls.size} imagen(es)")
            }

            Spacer(modifier = Modifier.height(16.dp))
            Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.spacedBy(12.dp)) {
                Button(
                    onClick = onVerDetalles,
                    modifier = Modifier.weight(1f),
                    enabled = !estaProcesandoAprobar && !estaProcesandoRechazar,
                    colors = ButtonDefaults.buttonColors(
                        containerColor = MaterialTheme.colorScheme.surfaceVariant,
                        contentColor = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                ) {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        Icon(Icons.Default.Visibility, contentDescription = "Ver detalles", modifier = Modifier.size(16.dp))
                        Spacer(modifier = Modifier.width(4.dp))
                        Text("Detalles")
                    }
                }

                Button(
                    onClick = { estaProcesandoRechazar = true },
                    modifier = Modifier.weight(1f),
                    enabled = !estaProcesandoAprobar && !estaProcesandoRechazar,
                    colors = ButtonDefaults.buttonColors(containerColor = Color(0xFFF44336))
                ) {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        if (estaProcesandoRechazar) {
                            CircularProgressIndicator(modifier = Modifier.size(16.dp), color = Color.White, strokeWidth = 2.dp)
                        } else {
                            Icon(Icons.Default.Close, contentDescription = "Rechazar", modifier = Modifier.size(16.dp))
                        }
                        Spacer(modifier = Modifier.width(4.dp))
                        Text("Rechazar")
                    }
                }

                Button(
                    onClick = { estaProcesandoAprobar = true },
                    modifier = Modifier.weight(1f),
                    enabled = !estaProcesandoAprobar && !estaProcesandoRechazar
                ) {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        if (estaProcesandoAprobar) {
                            CircularProgressIndicator(modifier = Modifier.size(16.dp), color = Color.White, strokeWidth = 2.dp)
                        } else {
                            Icon(Icons.Default.Check, contentDescription = "Aprobar", modifier = Modifier.size(16.dp))
                        }
                        Spacer(modifier = Modifier.width(4.dp))
                        Text("Aprobar")
                    }
                }
            }
        }
    }
}

@Composable
private fun InfoItem(etiqueta: String, valor: String) {
    Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceBetween) {
        Text(etiqueta, style = MaterialTheme.typography.labelMedium, fontWeight = FontWeight.Medium, color = MaterialTheme.colorScheme.onSurfaceVariant)
        Text(valor, style = MaterialTheme.typography.labelMedium, textAlign = TextAlign.End, modifier = Modifier.weight(1f))
    }
}

private fun formatearFecha(tiempoMillis: Long): String {
    val fecha = Date(tiempoMillis)
    val formateador = SimpleDateFormat("dd/MM/yyyy HH:mm", Locale.getDefault())
    return formateador.format(fecha)
}
```
# Visitante
# MapaSeleccionUbicaion.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.*
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import androidx.navigation.NavController
import com.google.android.gms.maps.model.BitmapDescriptorFactory
import com.google.android.gms.maps.model.CameraPosition
import com.google.android.gms.maps.model.LatLng
import com.google.maps.android.compose.*
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelSeleccionUbicacion

/**
 * Pantalla para seleccionar ubicación en un mapa interactivo
 * Permite al usuario elegir una ubicación específica para reportes u otras funciones
 *
 * @param modifier Modificador para personalizar el layout
 * @param initialLocation Ubicación inicial del mapa (opcional)
 * @param onLocationSelected Callback cuando se selecciona una ubicación
 * @param onCancel Callback para cancelar la selección
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaSeleccionUbicacionCompleta(
    navController: NavController,
    onUbicacionSeleccionada: (LatLng) -> Unit,
    onCancelar: () -> Unit,
    viewModel: ViewModelSeleccionUbicacion = hiltViewModel()
) {
    // Implementación del mapa para selección de ubicación
    // Incluiría: mapa interactivo, marcador arrastrable, botones de acción
    /**
     * Componente del mapa interactivo para selección de ubicación
     *
     * @param currentLocation Ubicación actual del marcador
     * @param onLocationChanged Callback cuando cambia la ubicación del marcador
     */
    val ubicacionSeleccionada by viewModel.ubicacionSeleccionada.collectAsState()
    val ubicacionActual by viewModel.ubicacionActual.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()
    val error by viewModel.error.collectAsState()
    val context = LocalContext.current

    // ¡¡¡¡¡CAMBIÉ ESTO!!!!! Usar Dolores Hidalgo en lugar de Ciudad de México
    val doloresHidalgo = LatLng(21.156100, -100.934200)

    // Inicializar el ViewModel
    LaunchedEffect(Unit) {
        viewModel.inicializarUbicacion(context)
    }

    // Usar Dolores Hidalgo como ubicación predeterminada si no hay nada seleccionado
    LaunchedEffect(Unit) {
        if (ubicacionSeleccionada == null) {
            viewModel.seleccionarUbicacion(doloresHidalgo)
        }
    }

    val cameraPositionState = rememberCameraPositionState {
        position = CameraPosition.fromLatLngZoom(
            ubicacionSeleccionada ?: doloresHidalgo, // Usar Dolores Hidalgo si no hay selección
            15f
        )
    }

    // Variable para el marcador seleccionado - usar Dolores Hidalgo como predeterminado
    var marcadorSeleccionado by remember {
        mutableStateOf(ubicacionSeleccionada ?: doloresHidalgo)
    }

    // Actualizar marcador cuando cambia la ubicación seleccionada
    LaunchedEffect(ubicacionSeleccionada) {
        ubicacionSeleccionada?.let {
            marcadorSeleccionado = it
            cameraPositionState.position = CameraPosition.fromLatLngZoom(it, 15f)
        }
    }

    // Mover cámara a ubicación actual cuando se obtiene
    LaunchedEffect(ubicacionActual) {
        ubicacionActual?.let { location ->
            val nuevaUbicacion = LatLng(location.latitude, location.longitude)
            marcadorSeleccionado = nuevaUbicacion
            viewModel.seleccionarUbicacion(nuevaUbicacion)
            cameraPositionState.position = CameraPosition.fromLatLngZoom(nuevaUbicacion, 17f)
        }
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Seleccionar Ubicación del Reporte") },
                navigationIcon = {
                    IconButton(onClick = onCancelar) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Cancelar")
                    }
                },
                actions = {
                    IconButton(
                        onClick = {
                            ubicacionSeleccionada?.let { onUbicacionSeleccionada(it) }
                        },
                        enabled = ubicacionSeleccionada != null
                    ) {
                        Icon(Icons.Default.Check, contentDescription = "Confirmar")
                    }
                }
            )
        },
        floatingActionButton = {
            Column(
                verticalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                // Botón para usar ubicación actual del dispositivo
                FloatingActionButton(
                    onClick = { viewModel.obtenerUbicacionActual(context) },
                    containerColor = MaterialTheme.colorScheme.primary,
                    modifier = Modifier.size(56.dp)
                ) {
                    if (estaCargando) {
                        CircularProgressIndicator(
                            modifier = Modifier.size(24.dp),
                            color = Color.White,
                            strokeWidth = 2.dp
                        )
                    } else {
                        Icon(Icons.Default.MyLocation, contentDescription = "Mi ubicación actual")
                    }
                }

                // Botón para input manual
                FloatingActionButton(
                    onClick = {
                        // Navegar a pantalla de input de coordenadas
                        navController.navigate("input_coordenadas") {
                            launchSingleTop = true
                        }
                    },
                    containerColor = MaterialTheme.colorScheme.secondary,
                    modifier = Modifier.size(56.dp)
                ) {
                    Icon(Icons.Default.Edit, contentDescription = "Ingresar coordenadas manualmente")
                }

                // Botón para centrar en Dolores Hidalgo
                FloatingActionButton(
                    onClick = {
                        marcadorSeleccionado = doloresHidalgo
                        viewModel.seleccionarUbicacion(doloresHidalgo)
                        cameraPositionState.position = CameraPosition.fromLatLngZoom(doloresHidalgo, 15f)
                    },
                    containerColor = MaterialTheme.colorScheme.tertiary,
                    modifier = Modifier.size(56.dp)
                ) {
                    Icon(Icons.Default.Home, contentDescription = "Centrar en Dolores Hidalgo")
                }
            }
        }
    ) { paddingValues ->
        Box(
            modifier = Modifier
                .fillMaxSize()
                .padding(paddingValues)
        ) {
            GoogleMap(
                modifier = Modifier.fillMaxSize(),
                cameraPositionState = cameraPositionState,
                onMapClick = { nuevaUbicacion ->
                    // Cuando el usuario toca el mapa, guardar esa ubicación
                    marcadorSeleccionado = nuevaUbicacion
                    viewModel.seleccionarUbicacion(nuevaUbicacion)
                },
                properties = MapProperties(
                    mapType = MapType.NORMAL,
                    isMyLocationEnabled = true // Mostrar ubicación del dispositivo
                ),
                uiSettings = MapUiSettings(
                    zoomControlsEnabled = true,
                    compassEnabled = true,
                    mapToolbarEnabled = true,
                    myLocationButtonEnabled = true
                )
            ) {
                // Marcador de ubicación seleccionada
                Marker(
                    state = MarkerState(position = marcadorSeleccionado),
                    title = "Ubicación del reporte",
                    snippet = "Lat: ${"%.6f".format(marcadorSeleccionado.latitude)}, Lng: ${"%.6f".format(marcadorSeleccionado.longitude)}",
                    draggable = true // Permitir arrastrar el marcador
                )

                // Marcador de Dolores Hidalgo (referencia)
                Marker(
                    state = MarkerState(position = doloresHidalgo),
                    title = "Dolores Hidalgo, Gto.",
                    snippet = "Cuna de la Independencia Nacional",
                    icon = BitmapDescriptorFactory.defaultMarker(BitmapDescriptorFactory.HUE_VIOLET)
                )
            }

            // Panel inferior con información de ubicación
            Card(
                modifier = Modifier
                    .align(Alignment.BottomCenter)
                    .padding(16.dp)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        text = "Ubicación seleccionada:",
                        style = MaterialTheme.typography.labelLarge,
                        fontWeight = FontWeight.Bold
                    )
                    Spacer(modifier = Modifier.height(8.dp))

                    Text(
                        text = "Latitud: ${"%.6f".format(marcadorSeleccionado.latitude)}",
                        style = MaterialTheme.typography.bodyMedium
                    )
                    Text(
                        text = "Longitud: ${"%.6f".format(marcadorSeleccionado.longitude)}",
                        style = MaterialTheme.typography.bodyMedium
                    )
                    Spacer(modifier = Modifier.height(12.dp))
                    Text(
                        text = "Instrucciones:",
                        style = MaterialTheme.typography.labelSmall,
                        fontWeight = FontWeight.Medium
                    )
                    Text(
                        text = "• Toca el mapa para seleccionar ubicación",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Text(
                        text = "• Arrastra el marcador rojo para ajustar",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Text(
                        text = "• Botón azul: tu ubicación actual",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Text(
                        text = "• Botón morado: centrar en Dolores Hidalgo",
                        style = MaterialTheme.typography.bodySmall
                    )
                }
            }

            // Mostrar errores
            error?.let { mensajeError ->
                Card(
                    modifier = Modifier
                        .align(Alignment.TopCenter)
                        .padding(16.dp),
                    colors = CardDefaults.cardColors(
                        containerColor = MaterialTheme.colorScheme.errorContainer
                    )
                ) {
                    Row(
                        modifier = Modifier.padding(16.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Icon(
                            Icons.Default.Warning,
                            contentDescription = "Error",
                            tint = MaterialTheme.colorScheme.onErrorContainer
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text(
                            text = mensajeError,
                            color = MaterialTheme.colorScheme.onErrorContainer,
                            modifier = Modifier.weight(1f)
                        )
                        IconButton(
                            onClick = { viewModel.limpiarError() }
                        ) {
                            Icon(
                                Icons.Default.Close,
                                contentDescription = "Cerrar",
                                tint = MaterialTheme.colorScheme.onErrorContainer
                            )
                        }
                    }
                }
            }
        }
    }
}
```
# MisReportes
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Close
import androidx.compose.material.icons.filled.Person
import androidx.compose.material.icons.filled.Refresh
import androidx.compose.material.icons.filled.Warning
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.presentacion.componentes.TarjetaReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelMisReportes

/**
 * Pantalla que muestra los reportes creados por el usuario actual
 * Permite ver, filtrar y gestionar los propios reportes
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja los reportes del usuario
 * @param onReportClick Callback cuando se hace clic en un reporte
 * @param onCreateReport Callback para crear un nuevo reporte
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaMisReportes(
    onNavegarAtras: () -> Unit,
    onNavegarACrearReporte: () -> Unit,
    onNavegarADetalleReporte: (String) -> Unit,
    onNavegarAEditarReporte: (String) -> Unit,
    viewModel: ViewModelMisReportes = hiltViewModel()
) {
    // Implementación de la pantalla "Mis Reportes"
    // Incluiría: lista de reportes propios, filtros por estado, estadísticas persona


    /**
     * Componente de filtros para reportes del usuario
     *
     * @param currentFilter Filtro actual aplicado
     * @param onFilterChange Callback cuando cambia el filtro
     */
    val misReportes by viewModel.misReportes.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()
    val error by viewModel.error.collectAsState()

    LaunchedEffect(Unit) { viewModel.cargarMisReportes() }

    Scaffold(
        topBar = {
            TopAppBar(
                title = {
                    Text("Mis Reportes ${if (misReportes.isNotEmpty()) "(${misReportes.size})" else ""}")
                },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    IconButton(onClick = { viewModel.recargarReportes() }, enabled = !estaCargando) {
                        if (estaCargando) {
                            CircularProgressIndicator(modifier = Modifier.size(24.dp), strokeWidth = 2.dp)
                        } else {
                            Icon(Icons.Default.Refresh, contentDescription = "Recargar")
                        }
                    }
                }
            )
        },
        floatingActionButton = {
            FloatingActionButton(onClick = onNavegarACrearReporte) {
                Icon(Icons.Default.Add, contentDescription = "Nuevo Reporte")
            }
        }
    ) { paddingValues ->
        Column(modifier = Modifier.padding(paddingValues).fillMaxSize()) {
            error?.let { mensajeError ->
                Card(
                    modifier = Modifier.fillMaxWidth().padding(16.dp),
                    colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.errorContainer)
                ) {
                    Column(modifier = Modifier.padding(16.dp)) {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Icon(Icons.Default.Warning, contentDescription = "Error", tint = MaterialTheme.colorScheme.error)
                            Spacer(modifier = Modifier.width(8.dp))
                            Text(text = "Error", style = MaterialTheme.typography.titleSmall, fontWeight = FontWeight.Bold, color = MaterialTheme.colorScheme.error)
                        }
                        Spacer(modifier = Modifier.height(8.dp))
                        Text(text = mensajeError, color = MaterialTheme.colorScheme.onErrorContainer, modifier = Modifier.fillMaxWidth())
                        Spacer(modifier = Modifier.height(8.dp))
                        Row(horizontalArrangement = Arrangement.End, modifier = Modifier.fillMaxWidth()) {
                            TextButton(onClick = { viewModel.limpiarError() }) { Text("Cerrar") }
                            Spacer(modifier = Modifier.width(8.dp))
                            Button(onClick = { viewModel.recargarReportes() }) { Text("Reintentar") }
                        }
                    }
                }
            }

            when {
                estaCargando -> {
                    Box(modifier = Modifier.fillMaxSize(), contentAlignment = Alignment.Center) {
                        Column(horizontalAlignment = Alignment.CenterHorizontally, verticalArrangement = Arrangement.spacedBy(16.dp)) {
                            CircularProgressIndicator()
                            Text("Cargando mis reportes...")
                            Text("Buscando reportes para el usuario...", style = MaterialTheme.typography.bodySmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
                        }
                    }
                }
                misReportes.isEmpty() -> {
                    Box(modifier = Modifier.fillMaxSize(), contentAlignment = Alignment.Center) {
                        Column(horizontalAlignment = Alignment.CenterHorizontally, verticalArrangement = Arrangement.spacedBy(16.dp)) {
                            Icon(Icons.Default.Person, contentDescription = "Sin reportes", modifier = Modifier.size(64.dp), tint = MaterialTheme.colorScheme.onSurfaceVariant)
                            Text("No has creado reportes aún", style = MaterialTheme.typography.titleMedium)
                            Text("Presiona el botón + para crear tu primer reporte", style = MaterialTheme.typography.bodyMedium, color = MaterialTheme.colorScheme.onSurfaceVariant)
                            Button(onClick = onNavegarACrearReporte) { Text("Crear Primer Reporte") }
                            Spacer(modifier = Modifier.height(8.dp))
                            Text("O presiona el botón ↻ para recargar", style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
                        }
                    }
                }
                else -> {
                    val reportesPendientes = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.PENDIENTE }
                    val reportesAprobados = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.APROBADO }
                    val reportesRechazados = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.RECHAZADO }
                    val reportesResueltos = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.RESUELTO }

                    Column {
                        Card(modifier = Modifier.fillMaxWidth().padding(16.dp), colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surfaceVariant)) {
                            Column(modifier = Modifier.padding(16.dp)) {
                                Text("Resumen de mis reportes", style = MaterialTheme.typography.titleSmall, fontWeight = FontWeight.Bold)
                                Spacer(modifier = Modifier.height(12.dp))
                                Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceBetween) {
                                    InfoChip("Total", misReportes.size.toString())
                                    InfoChip("Pendientes", reportesPendientes.toString())
                                    InfoChip("Aprobados", reportesAprobados.toString())
                                    InfoChip("Resueltos", reportesResueltos.toString())
                                }
                                if (reportesRechazados > 0) {
                                    Spacer(modifier = Modifier.height(8.dp))
                                    InfoChip("Rechazados", reportesRechazados.toString(), isError = true)
                                }
                            }
                        }

                        LazyColumn(modifier = Modifier.fillMaxSize(), contentPadding = PaddingValues(16.dp), verticalArrangement = Arrangement.spacedBy(12.dp)) {
                            items(misReportes, key = { it.id }) { reporte ->
                                TarjetaReporte(
                                    reporte = reporte,
                                    onClic = { onNavegarADetalleReporte(reporte.id) },
                                    onMeGusta = { viewModel.alternarMeGusta(reporte.id) },
                                    onComentar = { onNavegarADetalleReporte(reporte.id) },
                                    estaLiked = reporte.meGustas.contains(viewModel.obtenerUsuarioActualId()),
                                    puedeEditar = reporte.usuarioId == viewModel.obtenerUsuarioActualId(),
                                    onEditar = { onNavegarAEditarReporte(reporte.id) },
                                    onEliminar = { viewModel.eliminarReporte(reporte.id) },
                                    usuarioActualId = viewModel.obtenerUsuarioActualId()
                                )
                            }
                        }
                    }
                }
            }
        }
    }
}

@Composable
fun InfoChip(texto: String, valor: String, isError: Boolean = false) {
    Column(horizontalAlignment = Alignment.CenterHorizontally, verticalArrangement = Arrangement.spacedBy(4.dp)) {
        Text(texto, style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
        Text(valor, style = MaterialTheme.typography.titleSmall, fontWeight = FontWeight.Bold, color = if (isError) MaterialTheme.colorScheme.error else MaterialTheme.colorScheme.primary)
    }
}
```
# PantallaBienvenida
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Close
import androidx.compose.material.icons.filled.Person
import androidx.compose.material.icons.filled.Refresh
import androidx.compose.material.icons.filled.Warning
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.presentacion.componentes.TarjetaReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelMisReportes


/**
 * Pantalla de bienvenida que se muestra al abrir la aplicación por primera vez
 * Presenta información sobre la aplicación y opciones para continuar
 *
 * @param modifier Modificador para personalizar el layout
 * @param onNavigateToLogin Callback para navegar al login
 * @param onNavigateToRegister Callback para navegar al registro
 * @param onContinueAsGuest Callback para continuar como invitado
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaMisReportes(
    onNavegarAtras: () -> Unit,
    onNavegarACrearReporte: () -> Unit,
    onNavegarADetalleReporte: (String) -> Unit,
    onNavegarAEditarReporte: (String) -> Unit,
    viewModel: ViewModelMisReportes = hiltViewModel()
) {
    // Implementación de la pantalla "Mis Reportes"
    // Incluiría: lista de reportes propios, filtros por estado, estadísticas persona


    /**
     * Componente de filtros para reportes del usuario
     *
     * @param currentFilter Filtro actual aplicado
     * @param onFilterChange Callback cuando cambia el filtro
     */
    val misReportes by viewModel.misReportes.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()
    val error by viewModel.error.collectAsState()

    LaunchedEffect(Unit) { viewModel.cargarMisReportes() }

    Scaffold(
        topBar = {
            TopAppBar(
                title = {
                    Text("Mis Reportes ${if (misReportes.isNotEmpty()) "(${misReportes.size})" else ""}")
                },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    IconButton(onClick = { viewModel.recargarReportes() }, enabled = !estaCargando) {
                        if (estaCargando) {
                            CircularProgressIndicator(modifier = Modifier.size(24.dp), strokeWidth = 2.dp)
                        } else {
                            Icon(Icons.Default.Refresh, contentDescription = "Recargar")
                        }
                    }
                }
            )
        },
        floatingActionButton = {
            FloatingActionButton(onClick = onNavegarACrearReporte) {
                Icon(Icons.Default.Add, contentDescription = "Nuevo Reporte")
            }
        }
    ) { paddingValues ->
        Column(modifier = Modifier.padding(paddingValues).fillMaxSize()) {
            error?.let { mensajeError ->
                Card(
                    modifier = Modifier.fillMaxWidth().padding(16.dp),
                    colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.errorContainer)
                ) {
                    Column(modifier = Modifier.padding(16.dp)) {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Icon(Icons.Default.Warning, contentDescription = "Error", tint = MaterialTheme.colorScheme.error)
                            Spacer(modifier = Modifier.width(8.dp))
                            Text(text = "Error", style = MaterialTheme.typography.titleSmall, fontWeight = FontWeight.Bold, color = MaterialTheme.colorScheme.error)
                        }
                        Spacer(modifier = Modifier.height(8.dp))
                        Text(text = mensajeError, color = MaterialTheme.colorScheme.onErrorContainer, modifier = Modifier.fillMaxWidth())
                        Spacer(modifier = Modifier.height(8.dp))
                        Row(horizontalArrangement = Arrangement.End, modifier = Modifier.fillMaxWidth()) {
                            TextButton(onClick = { viewModel.limpiarError() }) { Text("Cerrar") }
                            Spacer(modifier = Modifier.width(8.dp))
                            Button(onClick = { viewModel.recargarReportes() }) { Text("Reintentar") }
                        }
                    }
                }
            }

            when {
                estaCargando -> {
                    Box(modifier = Modifier.fillMaxSize(), contentAlignment = Alignment.Center) {
                        Column(horizontalAlignment = Alignment.CenterHorizontally, verticalArrangement = Arrangement.spacedBy(16.dp)) {
                            CircularProgressIndicator()
                            Text("Cargando mis reportes...")
                            Text("Buscando reportes para el usuario...", style = MaterialTheme.typography.bodySmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
                        }
                    }
                }
                misReportes.isEmpty() -> {
                    Box(modifier = Modifier.fillMaxSize(), contentAlignment = Alignment.Center) {
                        Column(horizontalAlignment = Alignment.CenterHorizontally, verticalArrangement = Arrangement.spacedBy(16.dp)) {
                            Icon(Icons.Default.Person, contentDescription = "Sin reportes", modifier = Modifier.size(64.dp), tint = MaterialTheme.colorScheme.onSurfaceVariant)
                            Text("No has creado reportes aún", style = MaterialTheme.typography.titleMedium)
                            Text("Presiona el botón + para crear tu primer reporte", style = MaterialTheme.typography.bodyMedium, color = MaterialTheme.colorScheme.onSurfaceVariant)
                            Button(onClick = onNavegarACrearReporte) { Text("Crear Primer Reporte") }
                            Spacer(modifier = Modifier.height(8.dp))
                            Text("O presiona el botón ↻ para recargar", style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
                        }
                    }
                }
                else -> {
                    val reportesPendientes = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.PENDIENTE }
                    val reportesAprobados = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.APROBADO }
                    val reportesRechazados = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.RECHAZADO }
                    val reportesResueltos = misReportes.count { it.estado == mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte.RESUELTO }

                    Column {
                        Card(modifier = Modifier.fillMaxWidth().padding(16.dp), colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surfaceVariant)) {
                            Column(modifier = Modifier.padding(16.dp)) {
                                Text("Resumen de mis reportes", style = MaterialTheme.typography.titleSmall, fontWeight = FontWeight.Bold)
                                Spacer(modifier = Modifier.height(12.dp))
                                Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceBetween) {
                                    InfoChip("Total", misReportes.size.toString())
                                    InfoChip("Pendientes", reportesPendientes.toString())
                                    InfoChip("Aprobados", reportesAprobados.toString())
                                    InfoChip("Resueltos", reportesResueltos.toString())
                                }
                                if (reportesRechazados > 0) {
                                    Spacer(modifier = Modifier.height(8.dp))
                                    InfoChip("Rechazados", reportesRechazados.toString(), isError = true)
                                }
                            }
                        }

                        LazyColumn(modifier = Modifier.fillMaxSize(), contentPadding = PaddingValues(16.dp), verticalArrangement = Arrangement.spacedBy(12.dp)) {
                            items(misReportes, key = { it.id }) { reporte ->
                                TarjetaReporte(
                                    reporte = reporte,
                                    onClic = { onNavegarADetalleReporte(reporte.id) },
                                    onMeGusta = { viewModel.alternarMeGusta(reporte.id) },
                                    onComentar = { onNavegarADetalleReporte(reporte.id) },
                                    estaLiked = reporte.meGustas.contains(viewModel.obtenerUsuarioActualId()),
                                    puedeEditar = reporte.usuarioId == viewModel.obtenerUsuarioActualId(),
                                    onEditar = { onNavegarAEditarReporte(reporte.id) },
                                    onEliminar = { viewModel.eliminarReporte(reporte.id) },
                                    usuarioActualId = viewModel.obtenerUsuarioActualId()
                                )
                            }
                        }
                    }
                }
            }
        }
    }
}

@Composable
fun InfoChip(texto: String, valor: String, isError: Boolean = false) {
    Column(horizontalAlignment = Alignment.CenterHorizontally, verticalArrangement = Arrangement.spacedBy(4.dp)) {
        Text(texto, style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
        Text(valor, style = MaterialTheme.typography.titleSmall, fontWeight = FontWeight.Bold, color = if (isError) MaterialTheme.colorScheme.error else MaterialTheme.colorScheme.primary)
    }
}
```
# PantallaCrearReportes
```package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.activity.compose.rememberLauncherForActivityResult
import androidx.activity.result.PickVisualMediaRequest
import androidx.activity.result.contract.ActivityResultContracts
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyRow
import androidx.compose.foundation.lazy.itemsIndexed
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.selection.selectable
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.*
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import androidx.lifecycle.compose.collectAsStateWithLifecycle
import androidx.navigation.NavController
import coil.compose.AsyncImage
import com.google.android.gms.maps.model.LatLng
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelCrearReporte

/**
 * Pantalla para crear nuevos reportes de incidencias
 * Permite al usuario reportar problemas con detalles y ubicación
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja la creación de reportes
 * @param onReportCreated Callback cuando se crea exitosamente un reporte
 * @param onCancel Callback para cancelar la creación
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaCrearReporte(
    navController: NavController,
    onReporteCreado: () -> Unit,
    onNavegarAtras: () -> Unit,
    viewModel: ViewModelCrearReporte = hiltViewModel()
) {
    // Implementación de la pantalla de creación de reportes
    // Incluiría: formulario, selector de ubicación, adjuntar fotos, categorías
    /**
     * Componente del formulario de creación de reporte
     *
     * @param onTitleChange Callback cuando cambia el título
     * @param onDescriptionChange Callback cuando cambia la descripción
     * @param onCategoryChange Callback cuando cambia la categoría
     * @param onPriorityChange Callback cuando cambia la prioridad
     */
    val contexto = LocalContext.current
    val estadoUI by viewModel.estadoUI.collectAsStateWithLifecycle()
    val ubicacion by viewModel.ubicacionActual.collectAsStateWithLifecycle()
    val estaObteniendoUbicacion by viewModel.estaObteniendoUbicacion.collectAsStateWithLifecycle()
    val errorUbicacion by viewModel.errorUbicacion.collectAsStateWithLifecycle()

    // Estados locales para la selección de ubicación
    var mostrarSelectorUbicacion by remember { mutableStateOf(false) }
    var ubicacionReporte by remember { mutableStateOf<LatLng?>(null) }

    // Si hay ubicación actual, usarla como predeterminada
    LaunchedEffect(ubicacion) {
        ubicacion?.let { location ->
            if (ubicacionReporte == null) {
                ubicacionReporte = LatLng(location.latitude, location.longitude)
            }
        }
    }

    val seleccionarImagenLauncher = rememberLauncherForActivityResult(
        contract = ActivityResultContracts.PickVisualMedia()
    ) { uri ->
        uri?.let { viewModel.agregarImagen(it) }
    }

    LaunchedEffect(estadoUI) {
        if (estadoUI is ViewModelCrearReporte.EstadoUI.Exito) {
            onReporteCreado()
        }
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Crear Reporte") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    if (viewModel.tieneDatos()) {
                        IconButton(onClick = { viewModel.limpiarFormulario() }) {
                            Icon(Icons.Default.Clear, contentDescription = "Limpiar formulario")
                        }
                    }
                }
            )
        },
        floatingActionButton = {
            ExtendedFloatingActionButton(
                onClick = {
                    // Pasar la ubicación seleccionada al ViewModel
                    ubicacionReporte?.let { latLng ->
                        viewModel.establecerUbicacion(latLng.latitude, latLng.longitude)
                    }
                    viewModel.crearReporte()
                },
                icon = { Icon(Icons.Default.Send, contentDescription = "Enviar reporte") },
                text = { Text("Enviar Reporte") },
                modifier = Modifier.padding(16.dp)
            )
        }
    ) { paddingValues ->
        Column(
            modifier = Modifier
                .padding(paddingValues)
                .fillMaxSize()
                .verticalScroll(rememberScrollState())
                .padding(16.dp),
            verticalArrangement = Arrangement.spacedBy(16.dp)
        ) {
            // Título del reporte
            OutlinedTextField(
                value = viewModel.titulo,
                onValueChange = { viewModel.actualizarTitulo(it) },
                label = { Text("Título del reporte *") },
                placeholder = { Text("Ej: Bache grande en avenida principal") },
                modifier = Modifier.fillMaxWidth(),
                singleLine = true,
                isError = viewModel.mostrarError && viewModel.titulo.isBlank(),
                supportingText = {
                    if (viewModel.mostrarError && viewModel.titulo.isBlank()) Text("El título es requerido")
                    else Text("${viewModel.titulo.length}/100")
                },
                trailingIcon = {
                    if (viewModel.titulo.isNotBlank()) {
                        IconButton(onClick = { viewModel.actualizarTitulo("") }) {
                            Icon(Icons.Default.Clear, contentDescription = "Limpiar")
                        }
                    }
                }
            )

            // Descripción
            OutlinedTextField(
                value = viewModel.descripcion,
                onValueChange = { viewModel.actualizarDescripcion(it) },
                label = { Text("Descripción detallada *") },
                placeholder = { Text("Describe el problema con detalle...") },
                modifier = Modifier
                    .fillMaxWidth()
                    .height(120.dp),
                singleLine = false,
                maxLines = 5,
                isError = viewModel.mostrarError && viewModel.descripcion.isBlank(),
                supportingText = {
                    if (viewModel.mostrarError && viewModel.descripcion.isBlank()) Text("La descripción es requerida")
                    else Text("${viewModel.descripcion.length}/500")
                }
            )

            // Tipo de problema
            Text("Tipo de problema:", style = MaterialTheme.typography.labelMedium, fontWeight = FontWeight.Medium)
            Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                TipoReporte.entries.forEach { tipo ->
                    TipoReporteItem(
                        tipo = tipo,
                        seleccionado = viewModel.tipoSeleccionado == tipo,
                        onSeleccionar = { viewModel.actualizarTipo(tipo) }
                    )
                }
            }

            // Nivel de gravedad
            Text("Nivel de gravedad:", style = MaterialTheme.typography.labelMedium, fontWeight = FontWeight.Medium)
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                listOf("Baja", "Media", "Alta", "Urgente").forEach { gravedad ->
                    GravedadChip(
                        texto = gravedad,
                        seleccionado = viewModel.gravedadSeleccionada == gravedad,
                        onClick = { viewModel.actualizarGravedad(gravedad) }
                    )
                }
            }

            // SELECCIÓN DE UBICACIÓN (SEGMENTO CORREGIDO)
            Card(
                modifier = Modifier
                    .fillMaxWidth()
                    .clickable {
                        mostrarSelectorUbicacion = true
                    },
                colors = CardDefaults.cardColors(
                    containerColor = if (ubicacionReporte != null) MaterialTheme.colorScheme.primaryContainer
                    else MaterialTheme.colorScheme.surfaceVariant
                )
            ) {
                Column(modifier = Modifier.padding(16.dp)) {
                    Row(verticalAlignment = Alignment.CenterVertically) {
                        Icon(
                            Icons.Default.LocationOn,
                            contentDescription = "Ubicación",
                            tint = if (ubicacionReporte != null) MaterialTheme.colorScheme.primary
                            else MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Spacer(Modifier.width(8.dp))
                        Text(
                            "Ubicación del Reporte *",
                            style = MaterialTheme.typography.titleSmall,
                            fontWeight = FontWeight.SemiBold,
                            color = if (ubicacionReporte != null) MaterialTheme.colorScheme.primary
                            else MaterialTheme.colorScheme.onSurface
                        )
                    }
                    Spacer(Modifier.height(12.dp))

                    if (ubicacionReporte != null) {
                        Text(
                            "Ubicación establecida:",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Spacer(Modifier.height(4.dp))
                        Text(
                            "Lat: ${"%.6f".format(ubicacionReporte?.latitude)}",
                            style = MaterialTheme.typography.bodySmall
                        )
                        Text(
                            "Lng: ${"%.6f".format(ubicacionReporte?.longitude)}",
                            style = MaterialTheme.typography.bodySmall
                        )
                        Spacer(Modifier.height(8.dp))
                        Text(
                            "Toque para cambiar la ubicación",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.primary
                        )
                    } else {
                        Text(
                            "Presione para seleccionar ubicación en el mapa",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            }

            // Botones para selección de ubicación (alternativos)
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                Button(
                    onClick = { viewModel.obtenerUbicacionActual() },
                    modifier = Modifier.weight(1f),
                    enabled = !estaObteniendoUbicacion
                ) {
                    if (estaObteniendoUbicacion) {
                        CircularProgressIndicator(
                            modifier = Modifier.size(16.dp),
                            strokeWidth = 2.dp,
                            color = Color.White
                        )
                        Spacer(Modifier.width(8.dp))
                        Text("Obteniendo...")
                    } else {
                        Icon(
                            Icons.Default.MyLocation,
                            contentDescription = "Ubicación actual",
                            modifier = Modifier.size(18.dp)
                        )
                        Spacer(Modifier.width(8.dp))
                        Text("Actual")
                    }
                }

                Button(
                    onClick = {
                        mostrarSelectorUbicacion = true
                    },
                    modifier = Modifier.weight(1f)
                ) {
                    Icon(
                        Icons.Default.Map,
                        contentDescription = "Seleccionar en mapa",
                        modifier = Modifier.size(18.dp)
                    )
                    Spacer(Modifier.width(8.dp))
                    Text("Mapa")
                }

                Button(
                    onClick = {
                        navController.navigate("input_coordenadas") {
                            launchSingleTop = true
                        }
                    },
                    modifier = Modifier.weight(1f)
                ) {
                    Icon(
                        Icons.Default.Edit,
                        contentDescription = "Ingresar coordenadas",
                        modifier = Modifier.size(18.dp)
                    )
                    Spacer(Modifier.width(8.dp))
                    Text("Manual")
                }
            }

            errorUbicacion?.let { error ->
                Text(
                    error,
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.error
                )
            }

            // Imágenes
            Card(modifier = Modifier.fillMaxWidth()) {
                Column(modifier = Modifier.padding(16.dp)) {
                    Text("Imágenes (opcional)", style = MaterialTheme.typography.titleSmall, fontWeight = FontWeight.SemiBold)
                    Spacer(Modifier.height(8.dp))
                    Text(
                        "Puedes agregar hasta 5 imágenes. ${viewModel.imagenes.size}/5",
                        style = MaterialTheme.typography.bodySmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Spacer(Modifier.height(8.dp))

                    if (viewModel.imagenes.isEmpty()) {
                        Box(
                            modifier = Modifier.fillMaxWidth().height(80.dp),
                            contentAlignment = Alignment.Center
                        ) {
                            Text(
                                "No hay imágenes seleccionadas",
                                style = MaterialTheme.typography.bodySmall,
                                color = MaterialTheme.colorScheme.onSurfaceVariant
                            )
                        }
                    } else {
                        LazyRow(
                            horizontalArrangement = Arrangement.spacedBy(8.dp),
                            modifier = Modifier.fillMaxWidth()
                        ) {
                            itemsIndexed(
                                viewModel.imagenes,
                                key = { index, imagen -> "$index-${imagen.hashCode()}" }
                            ) { index, imagenUri ->
                                Box(modifier = Modifier.size(100.dp)) {
                                    AsyncImage(
                                        model = imagenUri,
                                        contentDescription = "Imagen del reporte",
                                        modifier = Modifier
                                            .size(100.dp)
                                            .clip(MaterialTheme.shapes.medium),
                                        contentScale = ContentScale.Crop
                                    )
                                    IconButton(
                                        onClick = { viewModel.eliminarImagen(index) },
                                        modifier = Modifier
                                            .align(Alignment.TopEnd)
                                            .size(24.dp)
                                    ) {
                                        Icon(
                                            Icons.Default.Close,
                                            contentDescription = "Eliminar imagen",
                                            tint = Color.White
                                        )
                                    }
                                }
                            }
                        }
                    }

                    Spacer(Modifier.height(8.dp))
                    Row(
                        modifier = Modifier.fillMaxWidth(),
                        horizontalArrangement = Arrangement.spacedBy(8.dp)
                    ) {
                        Button(
                            onClick = {
                                seleccionarImagenLauncher.launch(
                                    PickVisualMediaRequest(ActivityResultContracts.PickVisualMedia.ImageOnly)
                                )
                            },
                            modifier = Modifier.weight(1f),
                            enabled = viewModel.imagenes.size < 5
                        ) {
                            Icon(Icons.Default.Photo, contentDescription = "Seleccionar imagen")
                            Spacer(Modifier.width(8.dp))
                            Text("Agregar Imagen")
                        }

                        if (viewModel.imagenes.isNotEmpty()) {
                            OutlinedButton(
                                onClick = { viewModel.limpiarImagenes() },
                                modifier = Modifier.weight(1f),
                                colors = ButtonDefaults.outlinedButtonColors(
                                    contentColor = MaterialTheme.colorScheme.error
                                )
                            ) {
                                Icon(Icons.Default.Delete, contentDescription = "Limpiar imágenes")
                                Spacer(Modifier.width(8.dp))
                                Text("Limpiar")
                            }
                        }
                    }

                    if (viewModel.imagenes.size >= 5) {
                        Spacer(Modifier.height(8.dp))
                        Text(
                            "Límite de 5 imágenes alcanzado",
                            style = MaterialTheme.typography.labelSmall,
                            color = MaterialTheme.colorScheme.error
                        )
                    }
                }
            }

            // Mostrar errores generales
            if (viewModel.mostrarError) {
                Card(
                    modifier = Modifier.fillMaxWidth(),
                    colors = CardDefaults.cardColors(
                        containerColor = MaterialTheme.colorScheme.errorContainer
                    )
                ) {
                    Row(
                        modifier = Modifier.padding(16.dp),
                        verticalAlignment = Alignment.CenterVertically
                    ) {
                        Icon(
                            Icons.Default.Warning,
                            contentDescription = "Error",
                            tint = MaterialTheme.colorScheme.onErrorContainer
                        )
                        Spacer(Modifier.width(12.dp))
                        Text(
                            viewModel.mensajeError,
                            color = MaterialTheme.colorScheme.onErrorContainer,
                            modifier = Modifier.weight(1f)
                        )
                        IconButton(
                            onClick = {
                                viewModel.mostrarError = false
                                viewModel.mensajeError = ""
                            }
                        ) {
                            Icon(
                                Icons.Default.Close,
                                contentDescription = "Cerrar",
                                tint = MaterialTheme.colorScheme.onErrorContainer
                            )
                        }
                    }
                }
            }

            // Estado de carga
            if (estadoUI is ViewModelCrearReporte.EstadoUI.Cargando) {
                Card(modifier = Modifier.fillMaxWidth()) {
                    Column(
                        modifier = Modifier.padding(16.dp),
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        CircularProgressIndicator()
                        Spacer(Modifier.height(8.dp))
                        Text("Creando reporte...")
                    }
                }
            }

            // Estado de éxito
            if (estadoUI is ViewModelCrearReporte.EstadoUI.Exito) {
                Card(
                    modifier = Modifier.fillMaxWidth(),
                    colors = CardDefaults.cardColors(
                        containerColor = MaterialTheme.colorScheme.primaryContainer
                    )
                ) {
                    Column(
                        modifier = Modifier.padding(16.dp),
                        horizontalAlignment = Alignment.CenterHorizontally
                    ) {
                        Icon(
                            Icons.Default.CheckCircle,
                            contentDescription = "Éxito",
                            tint = MaterialTheme.colorScheme.primary
                        )
                        Spacer(Modifier.height(8.dp))
                        Text(
                            "¡Reporte creado exitosamente!",
                            style = MaterialTheme.typography.bodyMedium,
                            fontWeight = FontWeight.Medium
                        )
                    }
                }
            }

            Spacer(Modifier.height(80.dp))
        }
    }

    // Pantalla de selección de ubicación (si se necesita mostrar)
    if (mostrarSelectorUbicacion) {
        PantallaSeleccionUbicacionCompleta(
            navController = navController,
            onUbicacionSeleccionada = { latLng ->
                ubicacionReporte = latLng
                mostrarSelectorUbicacion = false
            },
            onCancelar = {
                mostrarSelectorUbicacion = false
            }
        )
    }
}

@Composable
fun TipoReporteItem(tipo: TipoReporte, seleccionado: Boolean, onSeleccionar: () -> Unit) {
    Row(
        modifier = Modifier
            .fillMaxWidth()
            .selectable(selected = seleccionado, onClick = onSeleccionar)
            .padding(12.dp),
        verticalAlignment = Alignment.CenterVertically
    ) {
        RadioButton(selected = seleccionado, onClick = null)
        Spacer(Modifier.width(12.dp))
        Column {
            Text(
                text = when (tipo) {
                    TipoReporte.BACHE -> "Bache"
                    TipoReporte.ALUMBRADO -> "Alumbrado público"
                    TipoReporte.BASURA -> "Basura acumulada"
                    TipoReporte.AGUA -> "Problema de agua"
                    TipoReporte.OTRO -> "Otro"
                },
                style = MaterialTheme.typography.bodyMedium
            )
            Text(
                text = when (tipo) {
                    TipoReporte.BACHE -> "Huecos o daños en el pavimento"
                    TipoReporte.ALUMBRADO -> "Lámparas quemadas o dañadas"
                    TipoReporte.BASURA -> "Basura en vía pública"
                    TipoReporte.AGUA -> "Fugas o falta de agua"
                    TipoReporte.OTRO -> "Otro tipo de problema"
                },
                style = MaterialTheme.typography.bodySmall,
                color = MaterialTheme.colorScheme.onSurfaceVariant
            )
        }
    }
}

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun GravedadChip(texto: String, seleccionado: Boolean, onClick: () -> Unit) {
    val colors = when (texto) {
        "Baja" -> Color(0xFF4CAF50) to Color(0xFFE8F5E8)
        "Media" -> Color(0xFF2196F3) to Color(0xFFE3F2FD)
        "Alta" -> Color(0xFFFF9800) to Color(0xFFFFF3E0)
        else -> Color(0xFFF44336) to Color(0xFFFFEBEE)
    }
    FilterChip(
        selected = seleccionado,
        onClick = onClick,
        label = { Text(text = texto) },
        colors = FilterChipDefaults.filterChipColors(
            selectedLabelColor = colors.first,
            selectedContainerColor = colors.second
        )
    )
}
```
# PantallaDetalleResporte.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyRow
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.text.KeyboardOptions
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.*
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.graphics.vector.ImageVector
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.input.KeyboardCapitalization
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.hilt.navigation.compose.hiltViewModel
import androidx.lifecycle.compose.collectAsStateWithLifecycle
import coil.compose.AsyncImage
import mx.edu.utng.mrs.mycomunidad.datos.modelo.Comentario
import mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.RolUsuario
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelAutenticacion
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelComentarios
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelDetalleReporte
import java.text.SimpleDateFormat
import java.util.*
/**
 * Pantalla que muestra los detalles completos de un reporte específico
 * Incluye información, comentarios, estado y actualizaciones
 *
 * @param modifier Modificador para personalizar el layout
 * @param reportId ID del reporte a mostrar
 * @param viewModel ViewModel que maneja los detalles del reporte
 * @param onBack Callback para regresar a la pantalla anterior
 * @param onEditReport Callback para editar el reporte (si es posible)
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaDetalleReporte(
    reporteId: String,
    onNavegarAtras: () -> Unit,
    onNavegarAEditarReporte: (String) -> Unit = {},
    viewModel: ViewModelDetalleReporte = hiltViewModel(),
    viewModelComentarios: ViewModelComentarios = hiltViewModel(),
    viewModelAutenticacion: ViewModelAutenticacion = hiltViewModel()
) {
    // Implementación de la pantalla de detalle de reporte
    // Incluiría: información del reporte, comentarios, historial de estado
    /**
     * Componente de información principal del reporte
     *
     * @param report Datos del reporte a mostrar
     */
    val estadoUI by viewModel.estadoUI.collectAsStateWithLifecycle()
    val cantidadComentarios by viewModel.cantidadComentarios.collectAsStateWithLifecycle()

    val comentarios by viewModelComentarios.comentarios.collectAsStateWithLifecycle()
    val estadoUIComentarios by viewModelComentarios.estadoUI.collectAsStateWithLifecycle()
    val mensajeErrorComentarios by viewModelComentarios.mensajeError.collectAsStateWithLifecycle()

    val usuarioActual by viewModelAutenticacion.usuarioActual.collectAsStateWithLifecycle()
    val usuarioId = usuarioActual?.id ?: ""
    val esAdmin = usuarioActual?.rol == RolUsuario.ADMINISTRADOR

    var reporteCargado by remember { mutableStateOf<mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte?>(null) }
    var puedeEditarReporte by remember { mutableStateOf(false) }

    LaunchedEffect(reporteId) {
        viewModel.cargarReporte(reporteId)
        viewModelComentarios.cargarComentarios(reporteId)
    }
    /**
     * Componente de sección de comentarios del reporte
     *
     * @param comments Lista de comentarios
     * @param onAddComment Callback para agregar un comentario
     */
    LaunchedEffect(estadoUI) {
        if (estadoUI is ViewModelDetalleReporte.EstadoUI.Exito) {
            val reporte = (estadoUI as ViewModelDetalleReporte.EstadoUI.Exito).reporte
            reporteCargado = reporte
            puedeEditarReporte = reporte.usuarioId == usuarioId || esAdmin
        }
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Detalle del Reporte") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    if (puedeEditarReporte) {
                        IconButton(
                            onClick = { onNavegarAEditarReporte(reporteId) }
                        ) {
                            Icon(Icons.Default.Edit, contentDescription = "Editar Reporte")
                        }
                    }
                }
            )
        }
    ) { paddingValues ->
        when (estadoUI) {
            is ViewModelDetalleReporte.EstadoUI.Cargando -> {
                Box(
                    modifier = Modifier
                        .fillMaxSize()
                        .padding(paddingValues),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        verticalArrangement = Arrangement.spacedBy(16.dp)
                    ) {
                        CircularProgressIndicator()
                        Text("Cargando reporte...")
                    }
                }
            }
            is ViewModelDetalleReporte.EstadoUI.Error -> {
                Box(
                    modifier = Modifier
                        .fillMaxSize()
                        .padding(paddingValues),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        verticalArrangement = Arrangement.spacedBy(16.dp)
                    ) {
                        Icon(
                            Icons.Default.Error,
                            contentDescription = "Error",
                            modifier = Modifier.size(64.dp),
                            tint = MaterialTheme.colorScheme.error
                        )
                        Text(
                            text = (estadoUI as ViewModelDetalleReporte.EstadoUI.Error).mensaje,
                            style = MaterialTheme.typography.bodyLarge,
                            textAlign = androidx.compose.ui.text.style.TextAlign.Center
                        )
                        Button(onClick = { viewModel.cargarReporte(reporteId) }) {
                            Text("Reintentar")
                        }
                    }
                }
            }
            is ViewModelDetalleReporte.EstadoUI.Exito -> {
                val reporte = (estadoUI as ViewModelDetalleReporte.EstadoUI.Exito).reporte
                ContenidoDetalleReporteCompleto(
                    reporte = reporte,
                    comentarios = comentarios,
                    cantidadComentarios = cantidadComentarios,
                    estadoUIComentarios = estadoUIComentarios,
                    mensajeErrorComentarios = mensajeErrorComentarios,
                    onAgregarComentario = { texto ->
                        viewModelComentarios.agregarComentario(reporteId, texto)
                    },
                    onEliminarComentario = { comentarioId, comentarioUsuarioId ->
                        viewModelComentarios.eliminarComentario(
                            reporteId,
                            comentarioId,
                            usuarioId,
                            esAdmin
                        )
                    },
                    onLimpiarError = {
                        viewModelComentarios.limpiarError()
                    },
                    usuarioActualId = usuarioId,
                    esUsuarioAdmin = esAdmin,
                    modifier = Modifier
                        .padding(paddingValues)
                        .fillMaxSize()
                )
            }
            else -> {
                Box(
                    modifier = Modifier
                        .fillMaxSize()
                        .padding(paddingValues),
                    contentAlignment = Alignment.Center
                ) {
                    CircularProgressIndicator()
                }
            }
        }
    }
}

@Composable
fun ContenidoDetalleReporteCompleto(
    reporte: mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte,
    comentarios: List<Comentario>,
    cantidadComentarios: Int,
    estadoUIComentarios: ViewModelComentarios.EstadoUI,
    mensajeErrorComentarios: String?,
    onAgregarComentario: (String) -> Unit,
    onEliminarComentario: (String, String) -> Unit,
    onLimpiarError: () -> Unit,
    usuarioActualId: String,
    esUsuarioAdmin: Boolean,
    modifier: Modifier = Modifier
) {
    Column(
        modifier = modifier
            .verticalScroll(rememberScrollState())
    ) {
        // Sección de información del reporte
        ContenidoDetalleReporteBasico(
            reporte = reporte,
            cantidadComentarios = cantidadComentarios,
            esUsuarioAdmin = esUsuarioAdmin
        )

        // Sección de comentarios
        SeccionComentarios(
            comentarios = comentarios,
            cantidadComentarios = cantidadComentarios,
            estadoUI = estadoUIComentarios,
            mensajeError = mensajeErrorComentarios,
            onAgregarComentario = onAgregarComentario,
            onEliminarComentario = onEliminarComentario,
            onLimpiarError = onLimpiarError,
            usuarioActualId = usuarioActualId,
            esUsuarioAdmin = esUsuarioAdmin,
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp)
        )

        Spacer(modifier = Modifier.height(80.dp))
    }
}

@Composable
fun ContenidoDetalleReporteBasico(
    reporte: mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte,
    cantidadComentarios: Int,
    esUsuarioAdmin: Boolean = false,
    modifier: Modifier = Modifier
) {
    Column(
        modifier = modifier
            .padding(16.dp),
        verticalArrangement = Arrangement.spacedBy(16.dp)
    ) {
        // Encabezado con título y estado
        Card(
            modifier = Modifier.fillMaxWidth(),
            elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
        ) {
            Column(
                modifier = Modifier.padding(16.dp)
            ) {
                Row(
                    modifier = Modifier.fillMaxWidth(),
                    horizontalArrangement = Arrangement.SpaceBetween,
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Text(
                        text = reporte.titulo,
                        style = MaterialTheme.typography.headlineSmall,
                        fontWeight = FontWeight.Bold,
                        modifier = Modifier.weight(1f)
                    )
                    BadgeEstado(estado = reporte.estado)
                }
                Spacer(modifier = Modifier.height(8.dp))
                // Contador de interacciones
                Row {
                    Text(
                        text = "${reporte.meGustas.size} 👍 • $cantidadComentarios 💬",
                        style = MaterialTheme.typography.labelMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }
            }
        }

        Card(
            modifier = Modifier.fillMaxWidth(),
            elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
        ) {
            Column(
                modifier = Modifier.padding(16.dp)
            ) {
                Text(
                    text = "Descripción",
                    style = MaterialTheme.typography.titleMedium,
                    fontWeight = FontWeight.SemiBold
                )
                Spacer(modifier = Modifier.height(8.dp))
                Text(
                    text = reporte.descripcion,
                    style = MaterialTheme.typography.bodyMedium,
                    lineHeight = 20.sp
                )
            }
        }

        Card(
            modifier = Modifier.fillMaxWidth(),
            elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
        ) {
            Column(
                modifier = Modifier.padding(16.dp)
            ) {
                Text(
                    text = "Información del Reporte",
                    style = MaterialTheme.typography.titleMedium,
                    fontWeight = FontWeight.SemiBold
                )
                Spacer(modifier = Modifier.height(12.dp))
                InfoItem(
                    icono = Icons.Default.Category,
                    titulo = "Tipo de problema",
                    valor = when (reporte.tipo) {
                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.BACHE -> "Bache"
                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.ALUMBRADO -> "Alumbrado público"
                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.BASURA -> "Basura acumulada"
                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.AGUA -> "Problema de agua"
                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.OTRO -> "Otro"
                    }
                )
                InfoItem(
                    icono = Icons.Default.Warning,
                    titulo = "Gravedad",
                    valor = reporte.gravedad
                )
                InfoItem(
                    icono = Icons.Default.DateRange,
                    titulo = "Fecha de reporte",
                    valor = formatearFecha(reporte.fechaCreacion)
                )
                InfoItem(
                    icono = Icons.Default.LocationOn,
                    titulo = "Ubicación",
                    valor = "Lat: ${"%.6f".format(reporte.latitud)}, Lng: ${"%.6f".format(reporte.longitud)}"
                )
            }
        }

        Card(
            modifier = Modifier.fillMaxWidth(),
            elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
        ) {
            Column(
                modifier = Modifier.padding(16.dp)
            ) {
                Text(
                    text = "Reportado por",
                    style = MaterialTheme.typography.titleMedium,
                    fontWeight = FontWeight.SemiBold
                )
                Spacer(modifier = Modifier.height(8.dp))

                if (esUsuarioAdmin) {
                    // ✅ PARA ADMINISTRADOR: Mostrar nombre, email e ID
                    Column(verticalArrangement = Arrangement.spacedBy(4.dp)) {
                        Text(
                            text = reporte.usuarioNombre.ifBlank { "Usuario anónimo" },
                            style = MaterialTheme.typography.bodyMedium,
                            fontWeight = FontWeight.Medium
                        )
                        Text(
                            text = reporte.usuarioEmail.ifBlank { "Sin email" },
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Text(
                            text = "ID: ${reporte.usuarioId.take(8)}...",
                            style = MaterialTheme.typography.bodySmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant,
                            fontSize = 12.sp
                        )
                    }
                } else {
                    // ✅ PARA USUARIO NORMAL: Mostrar solo el nombre
                    Text(
                        text = reporte.usuarioNombre.ifBlank { "Usuario anónimo" },
                        style = MaterialTheme.typography.bodyMedium,
                        fontWeight = FontWeight.Medium
                    )
                }
            }
        }

        if (reporte.imagenUrls.isNotEmpty()) {
            Card(
                modifier = Modifier.fillMaxWidth(),
                elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        text = "Imágenes del reporte (${reporte.imagenUrls.size})",
                        style = MaterialTheme.typography.titleMedium,
                        fontWeight = FontWeight.SemiBold
                    )
                    Spacer(modifier = Modifier.height(12.dp))
                    LazyRow(
                        horizontalArrangement = Arrangement.spacedBy(12.dp),
                        modifier = Modifier.fillMaxWidth()
                    ) {
                        items(reporte.imagenUrls) { imagenUrl ->
                            Card(
                                modifier = Modifier
                                    .size(220.dp)
                                    .clip(MaterialTheme.shapes.medium),
                                elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
                            ) {
                                AsyncImage(
                                    model = imagenUrl,
                                    contentDescription = "Imagen del reporte",
                                    modifier = Modifier.fillMaxSize(),
                                    contentScale = ContentScale.Crop
                                )
                            }
                        }
                    }
                }
            }
        }
    }
}

@Composable
fun SeccionComentarios(
    comentarios: List<Comentario>,
    cantidadComentarios: Int,
    estadoUI: ViewModelComentarios.EstadoUI,
    mensajeError: String?,
    onAgregarComentario: (String) -> Unit,
    onEliminarComentario: (String, String) -> Unit,
    onLimpiarError: () -> Unit,
    usuarioActualId: String,
    esUsuarioAdmin: Boolean,
    modifier: Modifier = Modifier
) {
    var textoComentario by remember { mutableStateOf("") }
    var estaEnviando by remember { mutableStateOf(false) }

    Column(modifier = modifier) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(bottom = 16.dp),
            horizontalArrangement = Arrangement.SpaceBetween,
            verticalAlignment = Alignment.CenterVertically
        ) {
            Text(
                text = "Comentarios ($cantidadComentarios)",
                style = MaterialTheme.typography.titleLarge,
                fontWeight = FontWeight.Bold
            )
        }

        // Input para nuevo comentario
        Card(
            modifier = Modifier
                .fillMaxWidth()
                .padding(bottom = 16.dp),
            elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
        ) {
            Column(modifier = Modifier.padding(16.dp)) {
                OutlinedTextField(
                    value = textoComentario,
                    onValueChange = { textoComentario = it },
                    label = { Text("Escribe un comentario...") },
                    placeholder = { Text("Comparte tu opinión o información adicional...") },
                    modifier = Modifier
                        .fillMaxWidth()
                        .height(100.dp),
                    maxLines = 4,
                    singleLine = false,
                    shape = MaterialTheme.shapes.medium,
                    keyboardOptions = KeyboardOptions(capitalization = KeyboardCapitalization.Sentences)
                )

                Spacer(modifier = Modifier.height(12.dp))

                Button(
                    onClick = {
                        if (textoComentario.isNotBlank()) {
                            estaEnviando = true
                            onAgregarComentario(textoComentario)
                            textoComentario = ""
                            estaEnviando = false
                        }
                    },
                    modifier = Modifier
                        .fillMaxWidth()
                        .height(48.dp),
                    enabled = textoComentario.isNotBlank() && !estaEnviando
                ) {
                    if (estaEnviando) {
                        CircularProgressIndicator(
                            modifier = Modifier.size(20.dp),
                            strokeWidth = 2.dp,
                            color = Color.White
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text("Enviando...")
                    } else {
                        Icon(
                            Icons.Default.Send,
                            contentDescription = "Enviar comentario",
                            modifier = Modifier.size(20.dp)
                        )
                        Spacer(modifier = Modifier.width(8.dp))
                        Text("Enviar Comentario")
                    }
                }
            }
        }

        // Mostrar errores
        mensajeError?.let { error ->
            Card(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(bottom = 16.dp),
                colors = CardDefaults.cardColors(
                    containerColor = MaterialTheme.colorScheme.errorContainer
                )
            ) {
                Row(
                    modifier = Modifier.padding(16.dp),
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Icon(
                        Icons.Default.Warning,
                        contentDescription = "Error",
                        tint = MaterialTheme.colorScheme.onErrorContainer
                    )
                    Spacer(modifier = Modifier.width(12.dp))
                    Text(
                        text = error,
                        color = MaterialTheme.colorScheme.onErrorContainer,
                        modifier = Modifier.weight(1f)
                    )
                    IconButton(
                        onClick = onLimpiarError
                    ) {
                        Icon(
                            Icons.Default.Close,
                            contentDescription = "Cerrar",
                            tint = MaterialTheme.colorScheme.onErrorContainer
                        )
                    }
                }
            }
        }

        // Lista de comentarios
        when {
            estadoUI is ViewModelComentarios.EstadoUI.Cargando && comentarios.isEmpty() -> {
                Box(
                    modifier = Modifier
                        .fillMaxWidth()
                        .height(100.dp)
                        .padding(16.dp),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        verticalArrangement = Arrangement.spacedBy(12.dp)
                    ) {
                        CircularProgressIndicator()
                        Text(
                            "Cargando comentarios...",
                            style = MaterialTheme.typography.bodyMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            }
            comentarios.isEmpty() -> {
                Box(
                    modifier = Modifier
                        .fillMaxWidth()
                        .padding(32.dp),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        verticalArrangement = Arrangement.spacedBy(12.dp)
                    ) {
                        Icon(
                            Icons.Default.Comment,
                            contentDescription = "Sin comentarios",
                            tint = MaterialTheme.colorScheme.onSurfaceVariant,
                            modifier = Modifier.size(64.dp)
                        )
                        Text(
                            text = "No hay comentarios aún",
                            style = MaterialTheme.typography.titleMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                        Text(
                            text = "Sé el primero en comentar",
                            style = MaterialTheme.typography.bodyMedium,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }
            }
            else -> {
                Column(
                    verticalArrangement = Arrangement.spacedBy(12.dp)
                ) {
                    comentarios.forEach { comentario ->
                        TarjetaComentario(
                            comentario = comentario,
                            usuarioActualId = usuarioActualId,
                            esUsuarioAdmin = esUsuarioAdmin,
                            onEliminarComentario = onEliminarComentario
                        )
                    }
                }
            }
        }
    }
}

@Composable
fun TarjetaComentario(
    comentario: Comentario,
    usuarioActualId: String,
    esUsuarioAdmin: Boolean,
    onEliminarComentario: (String, String) -> Unit
) {
    var mostrarDialogoEliminar by remember { mutableStateOf(false) }

    val puedeEliminar = comentario.usuarioId == usuarioActualId || esUsuarioAdmin

    Card(
        modifier = Modifier
            .fillMaxWidth(),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp),
        colors = CardDefaults.cardColors(
            containerColor = MaterialTheme.colorScheme.surfaceVariant
        )
    ) {
        Column(modifier = Modifier.padding(16.dp)) {
            Text(
                text = comentario.texto,
                style = MaterialTheme.typography.bodyMedium,
                modifier = Modifier.fillMaxWidth(),
                color = MaterialTheme.colorScheme.onSurface
            )

            Spacer(modifier = Modifier.height(12.dp))

            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Column {
                    Text(
                        text = "Por: ${comentario.usuarioNombre}",
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.primary,
                        fontWeight = FontWeight.Medium
                    )
                    Text(
                        text = formatearFechaComentario(comentario.fecha),
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    if (comentario.editado) {
                        Text(
                            text = "• editado",
                            style = MaterialTheme.typography.labelSmall,
                            color = MaterialTheme.colorScheme.onSurfaceVariant
                        )
                    }
                }

                if (puedeEliminar) {
                    IconButton(
                        onClick = { mostrarDialogoEliminar = true },
                        modifier = Modifier.size(32.dp)
                    ) {
                        Icon(
                            Icons.Default.Delete,
                            contentDescription = "Eliminar comentario",
                            tint = MaterialTheme.colorScheme.error,
                            modifier = Modifier.size(18.dp)
                        )
                    }
                }
            }
        }
    }

    if (mostrarDialogoEliminar) {
        AlertDialog(
            onDismissRequest = { mostrarDialogoEliminar = false },
            title = { Text("Eliminar comentario") },
            text = {
                Text(
                    if (esUsuarioAdmin && comentario.usuarioId != usuarioActualId) {
                        "¿Estás seguro de que quieres eliminar este comentario como administrador?"
                    } else {
                        "¿Estás seguro de que quieres eliminar tu comentario?"
                    }
                )
            },
            confirmButton = {
                TextButton(
                    onClick = {
                        onEliminarComentario(comentario.id, comentario.usuarioId)
                        mostrarDialogoEliminar = false
                    },
                    colors = ButtonDefaults.textButtonColors(
                        contentColor = MaterialTheme.colorScheme.error
                    )
                ) {
                    Text("Eliminar")
                }
            },
            dismissButton = {
                TextButton(
                    onClick = { mostrarDialogoEliminar = false }
                ) {
                    Text("Cancelar")
                }
            }
        )
    }
}

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun BadgeEstado(estado: EstadoReporte) {
    val (color, texto) = when (estado) {
        EstadoReporte.PENDIENTE -> Color(0xFFFFA000) to "Pendiente"
        EstadoReporte.APROBADO -> Color(0xFF4CAF50) to "Aprobado"
        EstadoReporte.RECHAZADO -> Color(0xFFF44336) to "Rechazado"
        EstadoReporte.RESUELTO -> Color(0xFF2196F3) to "Resuelto"
    }

    Badge(
        containerColor = color,
        contentColor = Color.White
    ) {
        Text(text = texto)
    }
}

@Composable
fun InfoItem(
    icono: ImageVector,
    titulo: String,
    valor: String
) {
    Row(
        modifier = Modifier
            .fillMaxWidth()
            .padding(vertical = 4.dp),
        verticalAlignment = Alignment.CenterVertically
    ) {
        Icon(
            imageVector = icono,
            contentDescription = titulo,
            modifier = Modifier.size(20.dp),
            tint = MaterialTheme.colorScheme.primary
        )
        Spacer(modifier = Modifier.width(12.dp))
        Column {
            Text(
                text = titulo,
                style = MaterialTheme.typography.labelMedium,
                color = MaterialTheme.colorScheme.onSurfaceVariant
            )
            Text(
                text = valor,
                style = MaterialTheme.typography.bodyMedium
            )
        }
    }
}

private fun formatearFecha(tiempoMillis: Long): String {
    val fecha = Date(tiempoMillis)
    val formateador = SimpleDateFormat("dd/MM/yyyy 'a las' HH:mm", Locale.getDefault())
    return formateador.format(fecha)
}

private fun formatearFechaComentario(tiempoMillis: Long): String {
    val fecha = Date(tiempoMillis)
    val formateador = SimpleDateFormat("dd/MM/yy 'a las' HH:mm", Locale.getDefault())
    return formateador.format(fecha)
}
```
# PantallaEditarReportes
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.selection.selectable
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Save
import androidx.compose.material.icons.filled.Warning
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import androidx.lifecycle.compose.collectAsStateWithLifecycle
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelEditarReporte
/**
 * Pantalla para editar un reporte existente creado por el usuario
 * Permite modificar los detalles de un reporte previamente creado
 *
 * @param modifier Modificador para personalizar el layout
 * @param reportId ID del reporte a editar
 * @param viewModel ViewModel que maneja la edición de reportes
 * @param onUpdateSuccess Callback cuando la actualización es exitosa
 * @param onCancel Callback para cancelar la edición
 */

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaEditarReporte(
    reporteId: String,
    onNavegarAtras: () -> Unit,
    onEdicionCompletada: () -> Unit,
    viewModel: ViewModelEditarReporte = hiltViewModel()
) {
    /**
     * Componente de validación de edición
     *
     * @param canEdit Indica si el reporte puede ser editado
     * @param editReasons Razones por las que se puede/no se puede editar
     */
    val reporte by viewModel.reporte.collectAsStateWithLifecycle()
    val estaCargando by viewModel.estaCargando.collectAsStateWithLifecycle()
    val error by viewModel.error.collectAsStateWithLifecycle()
    val edicionExitosa by viewModel.edicionExitosa.collectAsStateWithLifecycle()

    var titulo by remember { mutableStateOf("") }
    var descripcion by remember { mutableStateOf("") }
    var tipoSeleccionado by remember { mutableStateOf(mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.OTRO) }
    var gravedadSeleccionada by remember { mutableStateOf("Media") }

    LaunchedEffect(reporteId) { viewModel.cargarReporte(reporteId) }

    LaunchedEffect(reporte) {
        reporte?.let {
            titulo = it.titulo
            descripcion = it.descripcion
            tipoSeleccionado = it.tipo
            gravedadSeleccionada = it.gravedad
        }
    }

    LaunchedEffect(edicionExitosa) {
        if (edicionExitosa) onEdicionCompletada()
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Editar Reporte") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    if (reporte != null) {
                        IconButton(
                            onClick = {
                                viewModel.editarReporte(
                                    reporteId = reporteId,
                                    titulo = titulo,
                                    descripcion = descripcion,
                                    tipo = tipoSeleccionado,
                                    gravedad = gravedadSeleccionada,
                                    latitud = reporte!!.latitud,
                                    longitud = reporte!!.longitud
                                )
                            },
                            enabled = !estaCargando && titulo.isNotBlank() && descripcion.isNotBlank()
                        ) {
                            if (estaCargando) {
                                CircularProgressIndicator(
                                    modifier = Modifier.size(24.dp),
                                    strokeWidth = 2.dp
                                )
                            } else {
                                Icon(Icons.Default.Save, contentDescription = "Guardar")
                            }
                        }
                    }
                }
            )
        }
    ) { paddingValues ->
        Column(
            modifier = Modifier
                .padding(paddingValues)
                .fillMaxSize()
                .verticalScroll(rememberScrollState())
                .padding(16.dp),
            verticalArrangement = Arrangement.spacedBy(16.dp)
        ) {
            when {
                estaCargando && reporte == null -> {
                    Box(
                        modifier = Modifier.fillMaxSize(),
                        contentAlignment = Alignment.Center
                    ) {
                        CircularProgressIndicator()
                    }
                }

                reporte == null -> {
                    Box(
                        modifier = Modifier.fillMaxSize(),
                        contentAlignment = Alignment.Center
                    ) {
                        Text("No se pudo cargar el reporte")
                    }
                }

                else -> {
                    error?.let { mensajeError ->
                        Card(
                            modifier = Modifier.fillMaxWidth(),
                            colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.errorContainer)
                        ) {
                            Row(
                                modifier = Modifier.padding(16.dp),
                                verticalAlignment = Alignment.CenterVertically
                            ) {
                                Icon(Icons.Default.Warning, contentDescription = "Error", tint = MaterialTheme.colorScheme.error)
                                Spacer(modifier = Modifier.width(8.dp))
                                Text(text = mensajeError, color = MaterialTheme.colorScheme.error, modifier = Modifier.weight(1f))
                            }
                        }
                    }

                    Card(modifier = Modifier.fillMaxWidth()) {
                        Column(modifier = Modifier.padding(16.dp)) {
                            Text(
                                "Información actual del reporte",
                                style = MaterialTheme.typography.titleSmall,
                                fontWeight = FontWeight.Bold
                            )
                            Spacer(modifier = Modifier.height(8.dp))
                            Text("Estado: ${reporte!!.estado}")
                            Text("Fecha creación: ${java.text.SimpleDateFormat("dd/MM/yyyy HH:mm").format(java.util.Date(reporte!!.fechaCreacion))}")
                            Text("Ubicación: ${"%.6f".format(reporte!!.latitud)}, ${"%.6f".format(reporte!!.longitud)}")
                        }
                    }

                    OutlinedTextField(
                        value = titulo,
                        onValueChange = { titulo = it },
                        label = { Text("Título del reporte *") },
                        modifier = Modifier.fillMaxWidth(),
                        singleLine = true,
                        isError = titulo.isBlank()
                    )

                    OutlinedTextField(
                        value = descripcion,
                        onValueChange = { descripcion = it },
                        label = { Text("Descripción detallada *") },
                        modifier = Modifier.fillMaxWidth().height(120.dp),
                        singleLine = false,
                        maxLines = 5,
                        isError = descripcion.isBlank()
                    )

                    Text("Tipo de problema:", style = MaterialTheme.typography.labelMedium, fontWeight = FontWeight.Medium)

                    Column(verticalArrangement = Arrangement.spacedBy(8.dp)) {
                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.entries.forEach { tipo ->
                            Row(
                                modifier = Modifier.fillMaxWidth().selectable(selected = tipoSeleccionado == tipo, onClick = { tipoSeleccionado = tipo }).padding(12.dp),
                                verticalAlignment = Alignment.CenterVertically
                            ) {
                                RadioButton(selected = tipoSeleccionado == tipo, onClick = null)
                                Spacer(modifier = Modifier.width(12.dp))
                                Text(
                                    text = when (tipo) {
                                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.BACHE -> "Bache"
                                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.ALUMBRADO -> "Alumbrado público"
                                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.BASURA -> "Basura acumulada"
                                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.AGUA -> "Problema de agua"
                                        mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte.OTRO -> "Otro"
                                    },
                                    style = MaterialTheme.typography.bodyMedium
                                )
                            }
                        }
                    }

                    Text("Nivel de gravedad:", style = MaterialTheme.typography.labelMedium, fontWeight = FontWeight.Medium)

                    Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.spacedBy(8.dp)) {
                        listOf("Baja", "Media", "Alta", "Urgente").forEach { gravedad ->
                            FilterChip(
                                selected = gravedadSeleccionada == gravedad,
                                onClick = { gravedadSeleccionada = gravedad },
                                label = { Text(gravedad) }
                            )
                        }
                    }

                    Card(
                        modifier = Modifier.fillMaxWidth(),
                        colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.primaryContainer)
                    ) {
                        Column(modifier = Modifier.padding(16.dp)) {
                            Text(
                                "⚠️ Información importante",
                                style = MaterialTheme.typography.labelMedium,
                                fontWeight = FontWeight.Bold,
                                color = MaterialTheme.colorScheme.onPrimaryContainer
                            )
                            Spacer(modifier = Modifier.height(8.dp))
                            Text(
                                "• Solo puedes editar reportes que te pertenecen\n" +
                                        "• No puedes cambiar el estado del reporte\n" +
                                        "• La ubicación no se puede modificar",
                                style = MaterialTheme.typography.bodySmall,
                                color = MaterialTheme.colorScheme.onPrimaryContainer
                            )
                        }
                    }
                }
            }
        }
    }
}
```
# PantallaEliminarCuenta.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.*
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import androidx.navigation.NavController
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelPerfil
/**
 * Pantalla para confirmar y procesar la eliminación de la cuenta de usuario
 * Requiere confirmación y verificación de identidad del usuario
 *
 * @param modifier Modificador para personalizar el layout
 * @param onConfirmDelete Callback para confirmar la eliminación
 * @param onCancel Callback para cancelar la eliminación
 * @param onBack Callback para regresar
 */

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaEliminarCuentaSimple(
    navController: NavController
) {
    // Implementación de la pantalla de eliminación de cuenta
    // Incluiría: advertencias, verificación de contraseña, confirmación
    /**
     * Componente de advertencia de eliminación de cuenta
     *
     * @param consequences Consecuencias de eliminar la cuenta
     */
    val viewModel: ViewModelPerfil = hiltViewModel()
    val context = LocalContext.current

    val usuario by viewModel.usuario.collectAsState()
    val error by viewModel.error.collectAsState()

    LaunchedEffect(Unit) {
        viewModel.limpiarError()
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Eliminar Cuenta") },
                navigationIcon = {
                    IconButton(onClick = { navController.popBackStack() }) {
                        Icon(Icons.Default.ArrowBack, "Regresar")
                    }
                }
            )
        }
    ) { paddingValues ->
        Column(
            modifier = Modifier
                .fillMaxSize()
                .padding(paddingValues)
                .verticalScroll(rememberScrollState())
        ) {
            // Advertencia importante
            Card(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(16.dp),
                colors = CardDefaults.cardColors(
                    containerColor = MaterialTheme.colorScheme.errorContainer.copy(alpha = 0.1f)
                ),
                border = CardDefaults.outlinedCardBorder()
            ) {
                Column(
                    modifier = Modifier.padding(16.dp),
                    horizontalAlignment = Alignment.CenterHorizontally
                ) {
                    Icon(
                        Icons.Default.Warning,
                        contentDescription = "Advertencia",
                        modifier = Modifier.size(64.dp),
                        tint = MaterialTheme.colorScheme.error
                    )
                    Spacer(modifier = Modifier.height(16.dp))
                    Text(
                        "Eliminar Mi Cuenta",
                        style = MaterialTheme.typography.headlineSmall,
                        fontWeight = FontWeight.Bold,
                        color = MaterialTheme.colorScheme.error,
                        textAlign = TextAlign.Center
                    )
                    Spacer(modifier = Modifier.height(8.dp))
                    Text(
                        "Esta acción es permanente y no se puede deshacer",
                        style = MaterialTheme.typography.bodyMedium,
                        textAlign = TextAlign.Center
                    )
                }
            }

            // Información del usuario
            Card(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(horizontal = 16.dp)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        "Tu información:",
                        style = MaterialTheme.typography.titleMedium,
                        fontWeight = FontWeight.Bold,
                        modifier = Modifier.padding(bottom = 12.dp)
                    )

                    Row(
                        verticalAlignment = Alignment.CenterVertically,
                        modifier = Modifier.padding(vertical = 4.dp)
                    ) {
                        Icon(
                            Icons.Default.Person,
                            contentDescription = "Nombre",
                            modifier = Modifier.size(20.dp)
                        )
                        Spacer(modifier = Modifier.width(12.dp))
                        Text(
                            "Nombre: ${usuario?.nombre ?: "No disponible"}",
                            style = MaterialTheme.typography.bodyMedium
                        )
                    }

                    Row(
                        verticalAlignment = Alignment.CenterVertically,
                        modifier = Modifier.padding(vertical = 4.dp)
                    ) {
                        Icon(
                            Icons.Default.Email,
                            contentDescription = "Email",
                            modifier = Modifier.size(20.dp)
                        )
                        Spacer(modifier = Modifier.width(12.dp))
                        Text(
                            "Email: ${usuario?.email ?: "No disponible"}",
                            style = MaterialTheme.typography.bodyMedium
                        )
                    }

                    Row(
                        verticalAlignment = Alignment.CenterVertically,
                        modifier = Modifier.padding(vertical = 4.dp)
                    ) {
                        Icon(
                            Icons.Default.DateRange,
                            contentDescription = "Fecha",
                            modifier = Modifier.size(20.dp)
                        )
                        Spacer(modifier = Modifier.width(12.dp))
                        Text(
                            "Miembro desde: ${usuario?.fechaCreacion?.let {
                                java.text.SimpleDateFormat("dd/MM/yyyy", java.util.Locale.getDefault()).format(java.util.Date(it))
                            } ?: "No disponible"}",
                            style = MaterialTheme.typography.bodyMedium
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(24.dp))

            // Instrucciones
            Card(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(horizontal = 16.dp),
                colors = CardDefaults.cardColors(
                    containerColor = MaterialTheme.colorScheme.surfaceVariant
                )
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        "¿Cómo eliminar mi cuenta?",
                        style = MaterialTheme.typography.titleMedium,
                        fontWeight = FontWeight.Bold,
                        textAlign = TextAlign.Center,
                        modifier = Modifier.fillMaxWidth()
                    )
                    Spacer(modifier = Modifier.height(12.dp))

                    Row(
                        verticalAlignment = Alignment.Top,
                        modifier = Modifier.padding(vertical = 8.dp)
                    ) {
                        Text(
                            "1.",
                            fontWeight = FontWeight.Bold,
                            modifier = Modifier.padding(top = 2.dp)
                        )
                        Spacer(modifier = Modifier.width(12.dp))
                        Text(
                            "Haz clic en el botón 'Enviar Solicitud por Email'",
                            style = MaterialTheme.typography.bodyMedium
                        )
                    }

                    Row(
                        verticalAlignment = Alignment.Top,
                        modifier = Modifier.padding(vertical = 8.dp)
                    ) {
                        Text(
                            "2.",
                            fontWeight = FontWeight.Bold,
                            modifier = Modifier.padding(top = 2.dp)
                        )
                        Spacer(modifier = Modifier.width(12.dp))
                        Text(
                            "Se abrirá tu aplicación de email con un mensaje pre-escrito",
                            style = MaterialTheme.typography.bodyMedium
                        )
                    }

                    Row(
                        verticalAlignment = Alignment.Top,
                        modifier = Modifier.padding(vertical = 8.dp)
                    ) {
                        Text(
                            "3.",
                            fontWeight = FontWeight.Bold,
                            modifier = Modifier.padding(top = 2.dp)
                        )
                        Spacer(modifier = Modifier.width(12.dp))
                        Text(
                            "Envíanos el email y nuestro equipo procesará tu solicitud en 24-48 horas",
                            style = MaterialTheme.typography.bodyMedium
                        )
                    }
                }
            }

            Spacer(modifier = Modifier.height(24.dp))

            // Botón principal
            Column(
                modifier = Modifier.padding(horizontal = 16.dp),
                horizontalAlignment = Alignment.CenterHorizontally
            ) {
                Button(
                    onClick = {
                        if (viewModel.enviarEmailEliminacion(context)) {
                            // Email enviado exitosamente
                        }
                    },
                    modifier = Modifier.fillMaxWidth(),
                    colors = ButtonDefaults.buttonColors(
                        containerColor = MaterialTheme.colorScheme.error
                    ),
                    elevation = ButtonDefaults.buttonElevation(
                        defaultElevation = 8.dp,
                        pressedElevation = 4.dp
                    )
                ) {
                    Icon(
                        Icons.Default.Email,
                        contentDescription = "Enviar email",
                        modifier = Modifier.size(24.dp)
                    )
                    Spacer(modifier = Modifier.width(12.dp))
                    Text(
                        "ENVIAR SOLICITUD POR EMAIL",
                        fontWeight = FontWeight.Bold
                    )
                }

                Spacer(modifier = Modifier.height(12.dp))

                Text(
                    text = "Opcionalmente, puedes enviar un email directamente a:",
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant,
                    textAlign = TextAlign.Center
                )

                Spacer(modifier = Modifier.height(8.dp))

                Card(
                    modifier = Modifier.fillMaxWidth(),
                    colors = CardDefaults.cardColors(
                        containerColor = MaterialTheme.colorScheme.surfaceVariant
                    )
                ) {
                    Text(
                        text = "1224100827.mrs@gmail.com",
                        modifier = Modifier.padding(12.dp),
                        style = MaterialTheme.typography.bodyMedium,
                        fontWeight = FontWeight.Medium,
                        textAlign = TextAlign.Center
                    )
                }
            }

            Spacer(modifier = Modifier.height(24.dp))

            // Información de contacto
            Card(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(16.dp)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        "Información importante",
                        style = MaterialTheme.typography.titleMedium,
                        fontWeight = FontWeight.Bold,
                        modifier = Modifier.padding(bottom = 8.dp)
                    )

                    Text(
                        "• La eliminación de tu cuenta es permanente",
                        style = MaterialTheme.typography.bodyMedium
                    )

                    Text(
                        "• Todos tus datos serán eliminados de nuestros servidores",
                        style = MaterialTheme.typography.bodyMedium
                    )

                    Text(
                        "• No podrás recuperar tu cuenta después de este proceso",
                        style = MaterialTheme.typography.bodyMedium
                    )

                    Text(
                        "• Te contactaremos para confirmar antes de proceder",
                        style = MaterialTheme.typography.bodyMedium
                    )
                }
            }

            // Mostrar error si existe
            error?.let { mensajeError ->
                if (mensajeError.isNotBlank()) {
                    Spacer(modifier = Modifier.height(16.dp))
                    Card(
                        modifier = Modifier
                            .fillMaxWidth()
                            .padding(horizontal = 16.dp),
                        colors = CardDefaults.cardColors(
                            containerColor = MaterialTheme.colorScheme.errorContainer
                        )
                    ) {
                        Text(
                            text = "Error: $mensajeError",
                            modifier = Modifier.padding(16.dp),
                            color = MaterialTheme.colorScheme.onErrorContainer,
                            textAlign = TextAlign.Center
                        )
                    }
                }
            }
        }
    }
}
```
# PantallaEstadistica.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.automirrored.filled.ArrowBack
import androidx.compose.material.icons.filled.*
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import androidx.lifecycle.compose.collectAsStateWithLifecycle
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.componentes.*
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelEstadisticas
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.EstadoUIEstadisticas
/**
 * Pantalla que muestra estadísticas y métricas de reportes
 * Incluye gráficos y datos sobre la actividad de reportes
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja las estadísticas
 * @param timeRange Rango de tiempo para las estadísticas
 * @param onTimeRangeChange Callback para cambiar el rango de tiempo
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaEstadisticas(
    onNavegarAtras: () -> Unit,
    viewModel: ViewModelEstadisticas = hiltViewModel()
) {





    /**
     * Componente de gráfico de reportes por categoría
     *
     * @param data Datos para el gráfico
     * @param category Categoría seleccionada (opcional)
     */
    val estadoUI by viewModel.estadoUI.collectAsStateWithLifecycle()
    val estadisticas by viewModel.estadisticas.collectAsStateWithLifecycle()
    val pestanaSeleccionada by viewModel.pestanaSeleccionada.collectAsStateWithLifecycle()
    val filtros by viewModel.filtros.collectAsStateWithLifecycle()
    val mostrarDialogoFiltros by viewModel.mostrarDialogoFiltros.collectAsStateWithLifecycle()

    Scaffold(
        topBar = {
            TopAppBar(
                title = {
                    Text("Estadísticas Avanzadas", style = MaterialTheme.typography.headlineSmall)
                },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.AutoMirrored.Filled.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    IconButton(
                        onClick = { viewModel.exportarDatos() },
                        enabled = estadoUI !is EstadoUIEstadisticas.Exportando
                    ) {
                        if (estadoUI is EstadoUIEstadisticas.Exportando) {
                            CircularProgressIndicator(modifier = Modifier.size(20.dp))
                        } else {
                            Icon(Icons.Default.Download, contentDescription = "Exportar datos")
                        }
                    }
                    IconButton(onClick = { viewModel.mostrarDialogoFiltros() }) {
                        if (filtros.tieneFiltros) {
                            BadgedBox(badge = { Badge { Text("!") } }) {
                                Icon(Icons.Default.FilterList, contentDescription = "Filtros")
                            }
                        } else {
                            Icon(Icons.Default.FilterList, contentDescription = "Filtros")
                        }
                    }
                }
            )
        }
    ) { paddingValues ->
        when (estadoUI) {
            is EstadoUIEstadisticas.Cargando -> {
                Box(
                    modifier = Modifier.fillMaxSize().padding(paddingValues),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        verticalArrangement = Arrangement.spacedBy(16.dp)
                    ) {
                        CircularProgressIndicator()
                        Text("Cargando estadísticas...")
                    }
                }
            }
            is EstadoUIEstadisticas.Error -> {
                Box(
                    modifier = Modifier.fillMaxSize().padding(paddingValues),
                    contentAlignment = Alignment.Center
                ) {
                    Column(
                        horizontalAlignment = Alignment.CenterHorizontally,
                        verticalArrangement = Arrangement.spacedBy(16.dp)
                    ) {
                        Icon(Icons.Default.Error, contentDescription = "Error", tint = MaterialTheme.colorScheme.error, modifier = Modifier.size(64.dp))
                        Text(text = (estadoUI as EstadoUIEstadisticas.Error).mensaje, style = MaterialTheme.typography.bodyLarge)
                        Button(onClick = { viewModel.cargarEstadisticas() }) { Text("Reintentar") }
                    }
                }
            }
            else -> {
                Column(
                    modifier = Modifier.padding(paddingValues).fillMaxSize()
                ) {
                    MetricasPrincipales(estadisticas = estadisticas)
                    Spacer(modifier = Modifier.height(16.dp))
                    PestanasGraficas(
                        pestanaSeleccionada = pestanaSeleccionada,
                        onPestanaCambiada = { viewModel.cambiarPestana(it) },
                        estadisticas = estadisticas,
                        modifier = Modifier.weight(1f)
                    )
                }
            }
        }

        if (mostrarDialogoFiltros) {
            DialogoFiltros(
                filtrosActuales = filtros,
                onFiltrosActualizados = { nuevosFiltros ->
                    viewModel.actualizarFiltros(nuevosFiltros)
                    viewModel.ocultarDialogoFiltros()
                },
                onLimpiarFiltros = {
                    viewModel.limpiarFiltros()
                    viewModel.ocultarDialogoFiltros()
                },
                onCancelar = { viewModel.ocultarDialogoFiltros() }
            )
        }
    }
}

@Composable
fun MetricasPrincipales(estadisticas: mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.Estadisticas) {
    Row(
        modifier = Modifier.fillMaxWidth().padding(horizontal = 16.dp),
        horizontalArrangement = Arrangement.spacedBy(12.dp)
    ) {
        TarjetaMetrica(
            titulo = "Total",
            valor = estadisticas.totalReportes.toString(),
            icono = Icons.Default.Assignment,
            color = MaterialTheme.colorScheme.primary,
            modifier = Modifier.weight(1f)
        )
        TarjetaMetrica(
            titulo = "Resueltos",
            valor = "${estadisticas.porcentajeResueltos.toInt()}%",
            icono = Icons.Default.CheckCircle,
            color = Color(0xFF4CAF50),
            modifier = Modifier.weight(1f)
        )
        TarjetaMetrica(
            titulo = "Pendientes",
            valor = estadisticas.reportesPendientes.toString(),
            icono = Icons.Default.Schedule,
            color = Color(0xFFFF9800),
            modifier = Modifier.weight(1f)
        )
    }
}

@Composable
fun TarjetaMetrica(titulo: String, valor: String, icono: androidx.compose.ui.graphics.vector.ImageVector, color: Color, modifier: Modifier = Modifier) {
    Card(
        modifier = modifier,
        colors = CardDefaults.cardColors(containerColor = color.copy(alpha = 0.1f))
    ) {
        Column(modifier = Modifier.padding(16.dp), horizontalAlignment = Alignment.CenterHorizontally) {
            Icon(imageVector = icono, contentDescription = titulo, tint = color, modifier = Modifier.size(24.dp))
            Spacer(modifier = Modifier.height(8.dp))
            Text(text = valor, style = MaterialTheme.typography.titleLarge, fontWeight = FontWeight.Bold, color = color)
            Text(text = titulo, style = MaterialTheme.typography.labelSmall, color = MaterialTheme.colorScheme.onSurfaceVariant)
        }
    }
}

@Composable
fun PestanasGraficas(pestanaSeleccionada: Int, onPestanaCambiada: (Int) -> Unit, estadisticas: mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.Estadisticas, modifier: Modifier = Modifier) {
    val pestanas = listOf("Distribución", "Tendencia", "Actividad")
    Column(modifier = modifier) {
        TabRow(selectedTabIndex = pestanaSeleccionada, modifier = Modifier.fillMaxWidth()) {
            pestanas.forEachIndexed { index, titulo ->
                Tab(selected = pestanaSeleccionada == index, onClick = { onPestanaCambiada(index) }, text = { Text(titulo) })
            }
        }
        Box(modifier = Modifier.fillMaxSize()) {
            when (pestanaSeleccionada) {
                0 -> SeccionDistribucion(estadisticas = estadisticas)
                1 -> SeccionTendencia(estadisticas = estadisticas)
                2 -> SeccionActividad(estadisticas = estadisticas)
            }
        }
    }
}

@Composable
fun SeccionDistribucion(estadisticas: mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.Estadisticas) {
    Column(
        modifier = Modifier
            .fillMaxSize()
            .verticalScroll(rememberScrollState())
            .padding(16.dp),
        verticalArrangement = Arrangement.spacedBy(24.dp)
    ) {
        Text("Distribución por Tipo de Reporte", style = MaterialTheme.typography.titleMedium, fontWeight = FontWeight.SemiBold)
        GraficaBarrasTipoReal(estadisticas.distribucionPorTipo)

        Spacer(modifier = Modifier.height(16.dp))

        Text("Distribución por Estado", style = MaterialTheme.typography.titleMedium, fontWeight = FontWeight.SemiBold)
        GraficaPastelEstadoReal(estadisticas.distribucionPorEstado)
    }
}

@Composable
fun SeccionTendencia(estadisticas: mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.Estadisticas) {
    Column(
        modifier = Modifier
            .fillMaxSize()
            .verticalScroll(rememberScrollState())
            .padding(16.dp),
        verticalArrangement = Arrangement.spacedBy(24.dp)
    ) {
        Text("Tendencia Mensual de Reportes", style = MaterialTheme.typography.titleMedium, fontWeight = FontWeight.SemiBold)
        GraficaLineasTendenciaReal(estadisticas.tendenciaMensual)

        Text("Resumen de Tendencia", style = MaterialTheme.typography.titleMedium, fontWeight = FontWeight.SemiBold)
        Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.spacedBy(12.dp)) {
            Card(
                modifier = Modifier.weight(1f),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surfaceVariant)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp),
                    horizontalAlignment = Alignment.CenterHorizontally
                ) {
                    Text("Mes Actual", style = MaterialTheme.typography.labelMedium)
                    Text(
                        estadisticas.tendenciaMensual.values.lastOrNull()?.toString() ?: "0",
                        style = MaterialTheme.typography.titleLarge,
                        fontWeight = FontWeight.Bold
                    )
                    Text("reportes", style = MaterialTheme.typography.labelSmall)
                }
            }
            Card(
                modifier = Modifier.weight(1f),
                colors = CardDefaults.cardColors(containerColor = MaterialTheme.colorScheme.surfaceVariant)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp),
                    horizontalAlignment = Alignment.CenterHorizontally
                ) {
                    Text("Promedio Mensual", style = MaterialTheme.typography.labelMedium)
                    Text(
                        "${estadisticas.tendenciaMensual.values.average().toInt()}",
                        style = MaterialTheme.typography.titleLarge,
                        fontWeight = FontWeight.Bold
                    )
                    Text("reportes", style = MaterialTheme.typography.labelSmall)
                }
            }
        }
    }
}

@Composable
fun SeccionActividad(estadisticas: mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.Estadisticas) {
    Column(
        modifier = Modifier
            .fillMaxSize()
            .verticalScroll(rememberScrollState())
            .padding(16.dp),
        verticalArrangement = Arrangement.spacedBy(16.dp)
    ) {
        Text("Reportes Más Activos", style = MaterialTheme.typography.titleMedium, fontWeight = FontWeight.SemiBold)
        Text(
            "Reportes con más comentarios",
            style = MaterialTheme.typography.bodyMedium,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )

        if (estadisticas.reportesMasActivos.isEmpty()) {
            Box(
                modifier = Modifier
                    .fillMaxWidth()
                    .height(200.dp),
                contentAlignment = Alignment.Center
            ) {
                Column(
                    horizontalAlignment = Alignment.CenterHorizontally,
                    verticalArrangement = Arrangement.spacedBy(12.dp)
                ) {
                    Icon(
                        Icons.Default.Forum,
                        contentDescription = "Sin comentarios",
                        tint = MaterialTheme.colorScheme.onSurfaceVariant,
                        modifier = Modifier.size(48.dp)
                    )
                    Text(
                        "No hay reportes con comentarios",
                        style = MaterialTheme.typography.bodyMedium,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }
            }
        } else {
            Column(verticalArrangement = Arrangement.spacedBy(12.dp)) {
                estadisticas.reportesMasActivos.forEach { reporte ->
                    TarjetaReporteActivo(reporte = reporte)
                }
            }
        }
    }
}

@Composable
fun TarjetaReporteActivo(reporte: mx.edu.utng.mrs.mycomunidad.datos.modelo.Reporte) {
    Card(
        modifier = Modifier.fillMaxWidth(),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Column(modifier = Modifier.padding(16.dp)) {
            Row(
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.Top
            ) {
                Column(modifier = Modifier.weight(1f)) {
                    Text(
                        text = reporte.titulo,
                        style = MaterialTheme.typography.bodyLarge,
                        fontWeight = FontWeight.Medium,
                        maxLines = 2
                    )
                    Spacer(modifier = Modifier.height(4.dp))
                    Text(
                        text = "Por: ${reporte.usuarioNombre}",
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Text(
                        text = "Tipo: ${reporte.tipo.name}",
                        style = MaterialTheme.typography.labelSmall,
                        color = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                }
                Badge(containerColor = MaterialTheme.colorScheme.primary.copy(alpha = 0.1f)) {
                    Text("${reporte.comentarios.size}", color = MaterialTheme.colorScheme.primary)
                }
            }
            Spacer(modifier = Modifier.height(8.dp))
            if (reporte.comentarios.isNotEmpty()) {
                Text(
                    text = "\"${reporte.comentarios.last().texto.take(60)}...\"",
                    style = MaterialTheme.typography.bodySmall,
                    color = MaterialTheme.colorScheme.onSurfaceVariant,
                    fontStyle = androidx.compose.ui.text.font.FontStyle.Italic
                )
            }
        }
    }
}
```
# PantallasInicioSesion.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas


import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.verticalScroll
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Email
import androidx.compose.material.icons.filled.Lock
import androidx.compose.material3.Button
import androidx.compose.material3.CircularProgressIndicator
import androidx.compose.material3.ExperimentalMaterial3Api
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.material3.TextButton
import androidx.compose.material3.TopAppBar
import androidx.compose.material3.TopAppBarDefaults
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.text.input.PasswordVisualTransformation
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.datos.modelo.RolUsuario
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.EstadoAutenticacion
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelAutenticacion
/**
 * Pantalla de inicio de sesión para usuarios registrados
 * Permite autenticarse con correo electrónico y contraseña
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja la autenticación
 * @param onLoginSuccess Callback cuando el login es exitoso
 * @param onNavigateToRegister Callback para navegar al registro
 * @param onForgotPassword Callback para recuperar contraseña
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaInicioSesion(
    onInicioSesionExitoso: () -> Unit,
    onNavegarAPanelAdmin: () -> Unit,
    onNavegarAtras: () -> Unit,
    viewModel: ViewModelAutenticacion = hiltViewModel()
) {
    /**
     * Componente del formulario de inicio de sesión
     *
     * @param onEmailChange Callback cuando cambia el email
     * @param onPasswordChange Callback cuando cambia la contraseña
     * @param onLogin Click para iniciar sesión
     * @param isLoading Indica si está cargando
     */
    var email by remember { mutableStateOf("") }
    var contrasena by remember { mutableStateOf("") }
    var mostrarError by remember { mutableStateOf(false) }
    var mensajeError by remember { mutableStateOf("") }

    val estadoUI by viewModel.estadoUI.collectAsState()
    val usuario by viewModel.usuarioActual.collectAsState()

    LaunchedEffect(estadoUI) {
        when (estadoUI) {
            is EstadoAutenticacion.Exito -> {
                val usuario = (estadoUI as EstadoAutenticacion.Exito).usuario
                if (usuario.rol == RolUsuario.ADMINISTRADOR) {
                    onNavegarAPanelAdmin()
                } else {
                    onInicioSesionExitoso()
                }
            }
            is EstadoAutenticacion.Error -> {
                mostrarError = true
                mensajeError = (estadoUI as EstadoAutenticacion.Error).mensaje
            }
            else -> {}
        }
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Iniciar Sesión") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primary,
                    titleContentColor = MaterialTheme.colorScheme.onPrimary
                )
            )
        }
    ) { paddingValores ->
        Column(
            modifier = Modifier
                .padding(paddingValores)
                .padding(24.dp)
                .fillMaxSize()
                .verticalScroll(rememberScrollState()),
            horizontalAlignment = Alignment.CenterHorizontally,
            verticalArrangement = Arrangement.Center
        ) {
            // Campo Email
            OutlinedTextField(
                value = email,
                onValueChange = {
                    email = it
                    mostrarError = false
                },
                label = { Text("Correo electrónico") },
                leadingIcon = {
                    Icon(Icons.Default.Email, contentDescription = "Email")
                },
                isError = mostrarError,
                modifier = Modifier.fillMaxWidth()
            )

            Spacer(modifier = Modifier.height(16.dp))

            // Campo Contraseña
            OutlinedTextField(
                value = contrasena,
                onValueChange = {
                    contrasena = it
                    mostrarError = false
                },
                label = { Text("Contraseña") },
                leadingIcon = {
                    Icon(Icons.Default.Lock, contentDescription = "Contraseña")
                },
                visualTransformation = PasswordVisualTransformation(),
                isError = mostrarError,
                modifier = Modifier.fillMaxWidth()
            )

            Spacer(modifier = Modifier.height(24.dp))

            // Botón Iniciar Sesión
            Button(
                onClick = {
                    if (email.isNotBlank() && contrasena.isNotBlank()) {
                        viewModel.iniciarSesion(email, contrasena)
                    } else {
                        mostrarError = true
                        mensajeError = "Por favor completa todos los campos"
                    }
                },
                enabled = estadoUI !is EstadoAutenticacion.Cargando,
                modifier = Modifier
                    .fillMaxWidth()
                    .height(50.dp)
            ) {
                if (estadoUI is EstadoAutenticacion.Cargando) {
                    CircularProgressIndicator(
                        modifier = Modifier.size(20.dp),
                        color = MaterialTheme.colorScheme.onPrimary
                    )
                } else {
                    Text("Iniciar Sesión", fontSize = 16.sp)
                }
            }

            Spacer(modifier = Modifier.height(16.dp))

            // Enlace recuperar contraseña
            TextButton(onClick = { /* TODO: Recuperar contraseña */ }) {
                Text("¿Olvidaste tu contraseña?")
            }

            // Mostrar error si existe
            if (mostrarError) {
                Spacer(modifier = Modifier.height(16.dp))
                Text(
                    text = mensajeError,
                    color = MaterialTheme.colorScheme.error,
                    textAlign = TextAlign.Center
                )
            }
        }
    }
}
```
# PantallaInputCoordenadas.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import android.annotation.SuppressLint
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.text.KeyboardOptions
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Check
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.platform.LocalContext
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.input.KeyboardType
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import com.google.android.gms.maps.model.LatLng
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelSeleccionUbicacion
/**
 * Pantalla para ingresar coordenadas manualmente (latitud y longitud)
 * Alternativa a la selección por mapa para ubicaciones específicas
 *
 * @param modifier Modificador para personalizar el layout
 * @param initialCoords Coordenadas iniciales (opcional)
 * @param onCoordinatesSubmit Callback cuando se envían las coordenadas
 * @param onCancel Callback para cancelar
 */
@SuppressLint("StateFlowValueCalledInComposition")
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaInputCoordenadas(
    onCoordenadasConfirmadas: (LatLng) -> Unit,
    onCancelar: () -> Unit,
    viewModel: ViewModelSeleccionUbicacion = hiltViewModel()
) {
    /**
     * Componente de validación de coordenadas
     *
     * @param latitude Latitud ingresada
     * @param longitude Longitud ingresada
     * @param isValid Indica si las coordenadas son válidas
     */
    var latitud by remember { mutableStateOf("") }
    var longitud by remember { mutableStateOf("") }
    var mostrarError by remember { mutableStateOf(false) }
    val error by viewModel.error.collectAsState()
    val context = LocalContext.current

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Ingresar Coordenadas Manualmente") },
                navigationIcon = {
                    IconButton(onClick = onCancelar) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    IconButton(
                        onClick = {
                            try {
                                val lat = latitud.toDouble()
                                val lng = longitud.toDouble()

                                if (lat in -90.0..90.0 && lng in -180.0..180.0) {
                                    val coordenadas = LatLng(lat, lng)
                                    viewModel.establecerUbicacionManual(lat, lng)
                                    onCoordenadasConfirmadas(coordenadas)
                                } else {
                                    mostrarError = true
                                }
                            } catch (e: NumberFormatException) {
                                mostrarError = true
                            }
                        }
                    ) {
                        Icon(Icons.Default.Check, contentDescription = "Confirmar")
                    }
                }
            )
        }
    ) { paddingValues ->
        Column(
            modifier = Modifier
                .padding(paddingValues)
                .fillMaxSize()
                .padding(16.dp),
            verticalArrangement = Arrangement.spacedBy(16.dp)
        ) {
            Card(
                modifier = Modifier.fillMaxWidth()
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        text = "Coordenadas para Dolores Hidalgo, Gto.",
                        style = MaterialTheme.typography.titleSmall,
                        fontWeight = FontWeight.Bold
                    )
                    Spacer(modifier = Modifier.height(8.dp))
                    Text(
                        text = "• Latitud: 21.156100",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Text(
                        text = "• Longitud: -100.934200",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Spacer(modifier = Modifier.height(8.dp))
                    Text(
                        text = "Rangos válidos:",
                        style = MaterialTheme.typography.labelSmall,
                        fontWeight = FontWeight.Medium
                    )
                    Text(
                        text = "• Latitud: -90° a 90° (ej: 21.156100)",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Text(
                        text = "• Longitud: -180° a 180° (ej: -100.934200)",
                        style = MaterialTheme.typography.bodySmall
                    )
                }
            }

            // Campo Latitud
            OutlinedTextField(
                value = latitud,
                onValueChange = {
                    latitud = it
                    mostrarError = false
                },
                label = { Text("Latitud") },
                placeholder = { Text("Ej: 21.156100") },
                modifier = Modifier.fillMaxWidth(),
                keyboardOptions = KeyboardOptions(
                    keyboardType = KeyboardType.Decimal
                ),
                isError = mostrarError,
                supportingText = {
                    if (mostrarError) {
                        Text("Latitud inválida. Debe ser entre -90 y 90")
                    }
                }
            )

            // Campo Longitud
            OutlinedTextField(
                value = longitud,
                onValueChange = {
                    longitud = it
                    mostrarError = false
                },
                label = { Text("Longitud") },
                placeholder = { Text("Ej: -100.934200") },
                modifier = Modifier.fillMaxWidth(),
                keyboardOptions = KeyboardOptions(
                    keyboardType = KeyboardType.Decimal
                ),
                isError = mostrarError,
                supportingText = {
                    if (mostrarError) {
                        Text("Longitud inválida. Debe ser entre -180 y 180")
                    }
                }
            )

            // Botón para usar ubicación actual del dispositivo
            Button(
                onClick = { viewModel.obtenerUbicacionActual(context) },
                modifier = Modifier.fillMaxWidth()
            ) {
                Text("Usar Mi Ubicación Actual del Dispositivo")
            }

            // Mostrar error del ViewModel
            error?.let { mensajeError ->
                Card(
                    modifier = Modifier.fillMaxWidth(),
                    colors = CardDefaults.cardColors(
                        containerColor = MaterialTheme.colorScheme.errorContainer
                    )
                ) {
                    Text(
                        text = mensajeError,
                        modifier = Modifier.padding(16.dp),
                        color = MaterialTheme.colorScheme.onErrorContainer
                    )
                }
            }

            // Coordenadas actuales si están disponibles
            viewModel.ubicacionActual.value?.let { ubicacion ->
                Card(
                    modifier = Modifier.fillMaxWidth()
                ) {
                    Column(
                        modifier = Modifier.padding(16.dp)
                    ) {
                        Text(
                            text = "Ubicación actual detectada:",
                            style = MaterialTheme.typography.labelMedium,
                            fontWeight = FontWeight.Medium
                        )
                        Spacer(modifier = Modifier.height(8.dp))
                        Text(
                            text = "Lat: ${"%.6f".format(ubicacion.latitude)}",
                            style = MaterialTheme.typography.bodySmall
                        )
                        Text(
                            text = "Lng: ${"%.6f".format(ubicacion.longitude)}",
                            style = MaterialTheme.typography.bodySmall
                        )
                        Spacer(modifier = Modifier.height(8.dp))
                        Button(
                            onClick = {
                                latitud = "%.6f".format(ubicacion.latitude)
                                longitud = "%.6f".format(ubicacion.longitude)
                            },
                            modifier = Modifier.fillMaxWidth()
                        ) {
                            Text("Usar Estas Coordenadas")
                        }
                    }
                }
            }

            // Botón para usar coordenadas de Dolores Hidalgo
            OutlinedButton(
                onClick = {
                    latitud = "21.156100"
                    longitud = "-100.934200"
                },
                modifier = Modifier.fillMaxWidth()
            ) {
                Text("Usar Coordenadas de Dolores Hidalgo")
            }
        }
    }
}
```
# PantallaListaReportes.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.PaddingValues
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Add
import androidx.compose.material.icons.filled.ArrowBack // ¡AGREGA ESTE IMPORT!
import androidx.compose.material.icons.filled.Search
import androidx.compose.material3.CircularProgressIndicator
import androidx.compose.material3.ExperimentalMaterial3Api
import androidx.compose.material3.FloatingActionButton
import androidx.compose.material3.Icon
import androidx.compose.material3.IconButton
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.material3.TopAppBar
import androidx.compose.material3.TopAppBarDefaults
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.presentacion.componentes.TarjetaReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelReportes
/**
 * Pantalla que muestra una lista de reportes disponibles
 * Puede filtrarse por categoría, ubicación y estado
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja la lista de reportes
 * @param onReportClick Callback cuando se hace clic en un reporte
 * @param onFilterChange Callback para cambiar filtros
 */

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaListaReportes(
    onNavegarACrearReporte: () -> Unit,
    onNavegarADetalleReporte: (String) -> Unit,
    onNavegarAEditarReporte: (String) -> Unit,
    onNavegarAtras: () -> Unit, // ¡AGREGA ESTE PARÁMETRO!
    viewModel: ViewModelReportes = hiltViewModel()
) {
    /**
     * Componente de búsqueda de reportes
     *
     * @param searchText Texto de búsqueda
     * @param onSearchTextChange Callback cuando cambia el texto de búsqueda
     * @param onSearch Callback para ejecutar la búsqueda
     */
    val reportes by viewModel.reportes.collectAsState(emptyList())
    val estaCargando by viewModel.estaCargando.collectAsState()

    LaunchedEffect(Unit) {
        viewModel.cargarReportes()
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Reportes de la Comunidad") },
                navigationIcon = { // ¡AGREGA ESTE BLOQUE!
                    IconButton(onClick = onNavegarAtras) {
                        Icon(
                            Icons.Default.ArrowBack,
                            contentDescription = "Regresar",
                            tint = MaterialTheme.colorScheme.onPrimary
                        )
                    }
                },
                actions = {
                    IconButton(onClick = { /* TODO: Implementar búsqueda */ }) {
                        Icon(
                            Icons.Default.Search,
                            contentDescription = "Buscar",
                            tint = MaterialTheme.colorScheme.onPrimary
                        )
                    }
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primary,
                    titleContentColor = MaterialTheme.colorScheme.onPrimary
                )
            )
        },
        floatingActionButton = {
            FloatingActionButton(
                onClick = onNavegarACrearReporte,
                containerColor = MaterialTheme.colorScheme.primary
            ) {
                Icon(Icons.Default.Add, contentDescription = "Nuevo Reporte")
            }
        }
    ) { paddingValores ->
        if (estaCargando) {
            Column(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(paddingValores),
                horizontalAlignment = Alignment.CenterHorizontally,
                verticalArrangement = Arrangement.Center
            ) {
                CircularProgressIndicator()
                Text("Cargando reportes...", modifier = Modifier.padding(top = 16.dp))
            }
        } else if (reportes.isEmpty()) {
            Column(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(paddingValores),
                horizontalAlignment = Alignment.CenterHorizontally,
                verticalArrangement = Arrangement.Center
            ) {
                Text(
                    "No hay reportes aún",
                    style = MaterialTheme.typography.bodyLarge
                )
                Text(
                    "Sé el primero en reportar algo en tu comunidad",
                    style = MaterialTheme.typography.bodyMedium,
                    color = MaterialTheme.colorScheme.onSurfaceVariant
                )
            }
        } else {
            LazyColumn(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(paddingValores),
                contentPadding = PaddingValues(16.dp),
                verticalArrangement = Arrangement.spacedBy(12.dp)
            ) {
                items(reportes) { reporte ->
                    TarjetaReporte(
                        reporte = reporte,
                        onClic = { onNavegarADetalleReporte(reporte.id) },
                        onMeGusta = {
                            viewModel.alternarMeGusta(reporte.id)
                        },
                        onComentar = {
                            onNavegarADetalleReporte(reporte.id)
                        },
                        estaLiked = reporte.meGustas.contains(viewModel.obtenerUsuarioActualId()),
                        puedeEditar = reporte.usuarioId == viewModel.obtenerUsuarioActualId(),
                        onEditar = {
                            onNavegarAEditarReporte(reporte.id)
                        },
                        onEliminar = { },
                        usuarioActualId = viewModel.obtenerUsuarioActualId()
                    )
                }
            }
        }
    }
}
```
# PantallaMapa.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.MyLocation
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import com.google.android.gms.maps.model.BitmapDescriptorFactory
import com.google.android.gms.maps.model.CameraPosition
import com.google.android.gms.maps.model.LatLng
import com.google.maps.android.compose.*
import mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelMapa
/**
 * Pantalla principal del mapa interactivo con reportes geolocalizados
 * Muestra reportes en un mapa y permite interactuar con ellos
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja el mapa y reportes
 * @param onReportClick Callback cuando se hace clic en un marcador de reporte
 * @param onUserLocationClick Callback cuando se hace clic en la ubicación del usuario
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaMapa(
    onNavegarAtras: () -> Unit,
    onNavegarADetalleReporte: (String) -> Unit,
    viewModel: ViewModelMapa = hiltViewModel()
) {
    /**
     * Componente del mapa con marcadores de reportes
     *
     * @param reports Lista de reportes a mostrar en el mapa
     * @param userLocation Ubicación del usuario (opcional)
     * @param onMarkerClick Callback al hacer clic en un marcador
     */
    val reportes by viewModel.reportes.collectAsState()
    val ubicacionActual by viewModel.ubicacionActual.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()

    val doloresHidalgo = LatLng(21.156100, -100.934200)
    val cameraPositionState = rememberCameraPositionState {
        position = CameraPosition.fromLatLngZoom(doloresHidalgo, 14f)
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Mapa de Reportes") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                }
            )
        },
        floatingActionButton = {
            if (ubicacionActual != null) {
                FloatingActionButton(
                    onClick = {
                        ubicacionActual?.let { ubicacion ->
                            cameraPositionState.position = CameraPosition.fromLatLngZoom(
                                LatLng(ubicacion.latitude, ubicacion.longitude), 15f
                            )
                        }
                    },
                    containerColor = MaterialTheme.colorScheme.primary
                ) {
                    Icon(Icons.Default.MyLocation, contentDescription = "Mi ubicación")
                }
            }
        }
    ) { paddingValues ->
        Box(
            modifier = Modifier
                .fillMaxSize()
                .padding(paddingValues)
        ) {
            GoogleMap(
                modifier = Modifier.fillMaxSize(),
                cameraPositionState = cameraPositionState,
                properties = MapProperties(
                    mapType = MapType.NORMAL,
                    isMyLocationEnabled = true
                ),
                uiSettings = MapUiSettings(
                    zoomControlsEnabled = true,
                    myLocationButtonEnabled = false,
                    compassEnabled = true
                )
            ) {
                Marker(
                    state = MarkerState(position = doloresHidalgo),
                    title = "Dolores Hidalgo, Gto.",
                    snippet = "Cuna de la Independencia Nacional",
                    icon = BitmapDescriptorFactory.defaultMarker(BitmapDescriptorFactory.HUE_VIOLET)
                )

                // Marcadores de reportes
                reportes.forEach { reporte ->
                    if (reporte.estado == EstadoReporte.APROBADO || reporte.estado == EstadoReporte.RESUELTO) {
                        Marker(
                            state = MarkerState(
                                position = LatLng(reporte.latitud, reporte.longitud)
                            ),
                            title = reporte.titulo,
                            snippet = "Tipo: ${reporte.tipo.name} • Estado: ${reporte.estado.name}",
                            icon = BitmapDescriptorFactory.defaultMarker(
                                obtenerColorPorTipo(reporte.tipo)
                            ),
                            onClick = {

                                onNavegarADetalleReporte(reporte.id)
                                true
                            }
                        )
                    }
                }

                // Marcador de ubicación actual si está disponible
                ubicacionActual?.let { ubicacion ->
                    Marker(
                        state = MarkerState(
                            position = LatLng(ubicacion.latitude, ubicacion.longitude)
                        ),
                        title = "Mi ubicación",
                        icon = BitmapDescriptorFactory.defaultMarker(BitmapDescriptorFactory.HUE_BLUE)
                    )
                }
            }

            // Leyenda de colores
            LeyendaMapa(
                modifier = Modifier
                    .align(Alignment.TopEnd)
                    .padding(16.dp)
            )

            // Indicador de carga
            if (estaCargando) {
                CircularProgressIndicator(
                    modifier = Modifier.align(Alignment.Center)
                )
            }
        }
    }
}

@Composable
fun LeyendaMapa(modifier: Modifier = Modifier) {
    Card(
        modifier = modifier,
        elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
    ) {
        Column(
            modifier = Modifier.padding(8.dp)
        ) {
            Text(
                "Leyenda",
                style = MaterialTheme.typography.labelLarge,
                fontWeight = FontWeight.Bold
            )
            Spacer(modifier = Modifier.height(4.dp))
            LeyendaItem("Baches", Color(0xFFF44336))
            LeyendaItem("Alumbrado", Color(0xFFFFC107))
            LeyendaItem("Basura", Color(0xFF4CAF50))
            LeyendaItem("Agua", Color(0xFF2196F3))
            LeyendaItem("Otros", Color(0xFFFF9800))
        }
    }
}

@Composable
fun LeyendaItem(tipo: String, color: Color) {
    Row(
        verticalAlignment = Alignment.CenterVertically,
        modifier = Modifier.padding(vertical = 2.dp)
    ) {
        Box(
            modifier = Modifier
                .size(12.dp)
                .background(color)
        )
        Spacer(modifier = Modifier.width(8.dp))
        Text(
            text = tipo,
            style = MaterialTheme.typography.labelSmall
        )
    }
}

private fun obtenerColorPorTipo(tipo: TipoReporte): Float {
    return when (tipo) {
        TipoReporte.BACHE -> BitmapDescriptorFactory.HUE_RED
        TipoReporte.ALUMBRADO -> BitmapDescriptorFactory.HUE_YELLOW
        TipoReporte.BASURA -> BitmapDescriptorFactory.HUE_GREEN
        TipoReporte.AGUA -> BitmapDescriptorFactory.HUE_BLUE
        TipoReporte.OTRO -> BitmapDescriptorFactory.HUE_ORANGE
    }
}
```
# PantallaMapaPublico.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.height
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Info
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import com.google.android.gms.maps.model.BitmapDescriptorFactory
import com.google.android.gms.maps.model.CameraPosition
import com.google.android.gms.maps.model.LatLng
import com.google.maps.android.compose.*
import mx.edu.utng.mrs.mycomunidad.datos.modelo.EstadoReporte
import mx.edu.utng.mrs.mycomunidad.datos.modelo.TipoReporte
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelMapaPublico
/**
 * Pantalla de mapa público para visualización sin autenticación
 * Muestra reportes públicos y permite explorar sin login
 *
 * @param modifier Modificador para personalizar el layout
 * @param publicReports Lista de reportes públicos
 * @param onReportClick Callback cuando se hace clic en un reporte
 * @param onNavigateToLogin Callback para navegar al login
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaMapaPublico(
    onNavegarAtras: () -> Unit,
    viewModel: ViewModelMapaPublico = hiltViewModel()
) {
    val reportes by viewModel.reportesPublicos.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()

    // Posición inicial: Dolores Hidalgo
    val doloresHidalgo = LatLng(21.156100, -100.934200)
    val cameraPositionState = rememberCameraPositionState {
        position = CameraPosition.fromLatLngZoom(doloresHidalgo, 14f)
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Mapa de Reportes - Público") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                },
                actions = {
                    IconButton(onClick = { /* Mostrar información */ }) {
                        Icon(Icons.Default.Info, contentDescription = "Información")
                    }
                }
            )
        }
    ) { paddingValues ->
        Box(
            modifier = Modifier
                .fillMaxSize()
                .padding(paddingValues)
        ) {
            GoogleMap(
                modifier = Modifier.fillMaxSize(),
                cameraPositionState = cameraPositionState,
                properties = MapProperties(
                    mapType = MapType.NORMAL
                ),
                uiSettings = MapUiSettings(
                    zoomControlsEnabled = true,
                    compassEnabled = true
                )
            ) {
                // Marcador de Dolores Hidalgo
                Marker(
                    state = MarkerState(position = doloresHidalgo),
                    title = "Dolores Hidalgo, Gto.",
                    snippet = "Cuna de la Independencia Nacional",
                    icon = BitmapDescriptorFactory.defaultMarker(BitmapDescriptorFactory.HUE_VIOLET)
                )

                // Marcadores de reportes públicos (solo aprobados y resueltos)
                reportes.forEach { reporte ->
                    // Asegurarse de que solo mostramos reportes aprobados o resueltos
                    if (reporte.estado == EstadoReporte.APROBADO || reporte.estado == EstadoReporte.RESUELTO) {
                        Marker(
                            state = MarkerState(
                                position = LatLng(reporte.latitud, reporte.longitud)
                            ),
                            title = reporte.titulo,
                            snippet = "Tipo: ${reporte.tipo.name} • Estado: ${reporte.estado.name}",
                            // ¡¡¡¡¡AQUÍ ESTÁ LA SOLUCIÓN!!!!!
                            // Agregar el color según el tipo de reporte
                            icon = BitmapDescriptorFactory.defaultMarker(
                                obtenerColorPorTipoPublico(reporte.tipo)
                            )
                        )
                    }
                }
            }

            // Leyenda
            LeyendaMapaPublico(
                modifier = Modifier
                    .align(Alignment.TopEnd)
                    .padding(16.dp)
            )

            // Indicador de carga
            if (estaCargando) {
                CircularProgressIndicator(
                    modifier = Modifier.align(Alignment.Center)
                )
            }

            // Información para usuarios no autenticados
            Card(
                modifier = Modifier
                    .align(Alignment.BottomCenter)
                    .padding(16.dp)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        text = "Vista Pública",
                        style = MaterialTheme.typography.labelLarge,
                        fontWeight = FontWeight.Bold
                    )
                    Spacer(modifier = Modifier.height(8.dp))
                    Text(
                        text = "• Solo se muestran reportes aprobados y resueltos",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Text(
                        text = "• Inicia sesión para crear reportes y ver más detalles",
                        style = MaterialTheme.typography.bodySmall
                    )
                    Text(
                        text = "• Los colores representan el tipo de problema",
                        style = MaterialTheme.typography.bodySmall
                    )
                }
            }
        }
    }
}

// Función para obtener el color según el tipo de reporte (VERSIÓN PÚBLICA)
private fun obtenerColorPorTipoPublico(tipo: TipoReporte): Float {
    return when (tipo) {
        TipoReporte.BACHE -> BitmapDescriptorFactory.HUE_RED
        TipoReporte.ALUMBRADO -> BitmapDescriptorFactory.HUE_YELLOW
        TipoReporte.BASURA -> BitmapDescriptorFactory.HUE_GREEN
        TipoReporte.AGUA -> BitmapDescriptorFactory.HUE_BLUE
        TipoReporte.OTRO -> BitmapDescriptorFactory.HUE_ORANGE
    }
}

@Composable
fun LeyendaMapaPublico(modifier: Modifier = Modifier) {
    Card(
        modifier = modifier,
        elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
    ) {
        Column(
            modifier = Modifier.padding(8.dp)
        ) {
            Text(
                "Leyenda",
                style = MaterialTheme.typography.labelLarge,
                fontWeight = FontWeight.Bold
            )
            Spacer(modifier = Modifier.height(4.dp))
            LeyendaItemPublico("Baches", Color(0xFFF44336), BitmapDescriptorFactory.HUE_RED)
            LeyendaItemPublico("Alumbrado", Color(0xFFFFC107), BitmapDescriptorFactory.HUE_YELLOW)
            LeyendaItemPublico("Basura", Color(0xFF4CAF50), BitmapDescriptorFactory.HUE_GREEN)
            LeyendaItemPublico("Agua", Color(0xFF2196F3), BitmapDescriptorFactory.HUE_BLUE)
            LeyendaItemPublico("Otros", Color(0xFFFF9800), BitmapDescriptorFactory.HUE_ORANGE)

            Spacer(modifier = Modifier.height(8.dp))
            Text(
                "Estados:",
                style = MaterialTheme.typography.labelSmall,
                fontWeight = FontWeight.Medium
            )
            Text("• ✅ Aprobados", style = MaterialTheme.typography.bodySmall)
            Text("• ✅ Resueltos", style = MaterialTheme.typography.bodySmall)
        }
    }
}

@Composable
fun LeyendaItemPublico(tipo: String, color: Color, hue: Float? = null) {
    Row(
        verticalAlignment = Alignment.CenterVertically,
        modifier = Modifier.padding(vertical = 2.dp)
    ) {
        Box(
            modifier = Modifier
                .size(12.dp)
                .background(color)
        )
        Spacer(modifier = Modifier.width(8.dp))
        Column {
            Text(
                text = tipo,
                style = MaterialTheme.typography.labelSmall
            )
            hue?.let {
                Text(
                    text = "Color: ${hueToString(it)}",
                    style = MaterialTheme.typography.bodySmall,
                    color = Color.Gray
                )
            }
        }
    }
}

// Función para convertir el valor hue a texto descriptivo
private fun hueToString(hue: Float): String {
    return when (hue) {
        BitmapDescriptorFactory.HUE_RED -> "Rojo"
        BitmapDescriptorFactory.HUE_YELLOW -> "Amarillo"
        BitmapDescriptorFactory.HUE_GREEN -> "Verde"
        BitmapDescriptorFactory.HUE_BLUE -> "Azul"
        BitmapDescriptorFactory.HUE_ORANGE -> "Naranja"
        else -> "Desconocido"
    }
} 
```
# PantallaNotificasiones.kt
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas


import androidx.compose.foundation.background
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.ArrowBack
import androidx.compose.material.icons.filled.Notifications
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelNotificaciones
/**
 * Pantalla que muestra las notificaciones del usuario
 * Incluye notificaciones de reportes, comentarios y sistema
 *
 * @param modifier Modificador para personalizar el layout
 * @param viewModel ViewModel que maneja las notificaciones
 * @param onNotificationClick Callback cuando se hace clic en una notificación
 * @param onMarkAllRead Callback para marcar todas como leídas
 */
@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaNotificaciones(
    onNavegarAtras: () -> Unit,
    viewModel: ViewModelNotificaciones = hiltViewModel()
) {
    /**
     * Componente de item de notificación
     *
     * @param notification Notificación a mostrar
     * @param onClick Callback al hacer clic
     * @param onSwipeAction Acción al deslizar
     */
    val notificaciones by viewModel.notificaciones.collectAsState()
    val estaCargando by viewModel.estaCargando.collectAsState()

    LaunchedEffect(Unit) {
        viewModel.cargarNotificaciones()
    }

    Scaffold(
        topBar = {
            TopAppBar(
                title = { Text("Notificaciones") },
                navigationIcon = {
                    IconButton(onClick = onNavegarAtras) {
                        Icon(Icons.Default.ArrowBack, contentDescription = "Regresar")
                    }
                }
            )
        }
    ) { padding ->
        if (estaCargando) {
            Box(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(padding),
                contentAlignment = Alignment.Center
            ) {
                CircularProgressIndicator()
            }
        } else if (notificaciones.isEmpty()) {
            Box(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(padding),
                contentAlignment = Alignment.Center
            ) {
                Column(
                    horizontalAlignment = Alignment.CenterHorizontally
                ) {
                    Icon(
                        Icons.Default.Notifications,
                        contentDescription = "Sin notificaciones",
                        modifier = Modifier.size(64.dp),
                        tint = MaterialTheme.colorScheme.onSurfaceVariant
                    )
                    Spacer(modifier = Modifier.height(16.dp))
                    Text(
                        "No tienes notificaciones",
                        style = MaterialTheme.typography.bodyLarge
                    )
                }
            }
        } else {
            LazyColumn(
                modifier = Modifier
                    .padding(padding)
                    .fillMaxSize(),
                contentPadding = PaddingValues(16.dp),
                verticalArrangement = Arrangement.spacedBy(8.dp)
            ) {
                items(notificaciones) { notificacion ->
                    TarjetaNotificacion(notificacion = notificacion)
                }
            }
        }
    }
}

@Composable
fun TarjetaNotificacion(notificacion: mx.edu.utng.mrs.mycomunidad.datos.modelo.Notificacion) {
    Card(
        modifier = Modifier.fillMaxWidth(),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp)
    ) {
        Column(
            modifier = Modifier.padding(16.dp)
        ) {
            Text(
                text = notificacion.titulo,
                style = MaterialTheme.typography.titleMedium,
                fontWeight = FontWeight.SemiBold
            )
            Spacer(modifier = Modifier.height(4.dp))
            Text(
                text = notificacion.mensaje,
                style = MaterialTheme.typography.bodyMedium
            )
            Spacer(modifier = Modifier.height(8.dp))
            Text(
                text = "Hace ${obtenerTiempoTranscurrido(notificacion.fecha)}",
                style = MaterialTheme.typography.labelSmall,
                color = MaterialTheme.colorScheme.onSurfaceVariant
            )
        }
    }
}

private fun obtenerTiempoTranscurrido(tiempoMillis: Long): String {
    val diferencia = System.currentTimeMillis() - tiempoMillis
    val minutos = diferencia / (1000 * 60)
    val horas = minutos / 60
    val dias = horas / 24

    return when {
        minutos < 1 -> "un momento"
        minutos < 60 -> "$minutos min"
        horas < 24 -> "$horas h"
        else -> "$dias d"
    }
}
@Composable
fun TarjetaNotificacion(
    notificacion: mx.edu.utng.mrs.mycomunidad.datos.modelo.Notificacion,
    onMarcarLeida: (String) -> Unit
) {
    Card(
        modifier = Modifier.fillMaxWidth(),
        elevation = CardDefaults.cardElevation(defaultElevation = 2.dp),
        colors = CardDefaults.cardColors(
            containerColor = if (notificacion.leida)
                MaterialTheme.colorScheme.surface
            else
                MaterialTheme.colorScheme.primaryContainer.copy(alpha = 0.1f)
        )
    ) {
        Column(
            modifier = Modifier
                .padding(16.dp)
                .clickable {
                    if (!notificacion.leida) {
                        onMarcarLeida(notificacion.id)
                    }
                }
        ) {
            Row(
                modifier = Modifier.fillMaxWidth(),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.Top
            ) {
                Text(
                    text = notificacion.titulo,
                    style = MaterialTheme.typography.titleMedium,
                    fontWeight = FontWeight.SemiBold,
                    modifier = Modifier.weight(1f)
                )

                if (!notificacion.leida) {
                    Box(
                        modifier = Modifier
                            .size(8.dp)
                            .background(
                                color = MaterialTheme.colorScheme.primary,
                                shape = CircleShape
                            )
                    )
                }
            }

            Spacer(modifier = Modifier.height(4.dp))
            Text(
                text = notificacion.mensaje,
                style = MaterialTheme.typography.bodyMedium
            )
            Spacer(modifier = Modifier.height(8.dp))
            Text(
                text = "Hace ${obtenerTiempoTranscurrido(notificacion.fecha)} • ${notificacion.tipo}",
                style = MaterialTheme.typography.labelSmall,
                color = MaterialTheme.colorScheme.onSurfaceVariant
            )
        }
    }
}
```
# PantallaPrincipal
```
package mx.edu.utng.mrs.mycomunidad.presentacion.pantallas

import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.grid.GridCells
import androidx.compose.foundation.lazy.grid.LazyVerticalGrid
import androidx.compose.foundation.lazy.grid.items
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.*
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.runtime.LaunchedEffect
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.vector.ImageVector
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.unit.dp
import androidx.hilt.navigation.compose.hiltViewModel
import mx.edu.utng.mrs.mycomunidad.presentacion.viewmodel.ViewModelEstadisticas
/**
 * Pantalla principal de la aplicación después del login
 * Sirve como hub central con acceso a todas las funciones principales
 *
 * @param modifier Modificador para personalizar el layout
 * @param user Usuario actual
 * @param onNavigateToReports Callback para navegar a reportes
 * @param onNavigateToMap Callback para navegar al mapa
 * @param onNavigateToProfile Callback para navegar al perfil
 * @param onNavigateToNotifications Callback para navegar a notificaciones
 */

data class Funcionalidad(
    val id: String,
    val icono: ImageVector,
    val titulo: String,
    val descripcion: String,
    val ruta: String? = null,
    val onClick: (() -> Unit)? = null
)

/**
 * Componente de dashboard con accesos rápidos
 *
 * @param userRole Rol del usuario para mostrar opciones relevantes
 * @param quickActions Acciones rápidas disponibles
 */

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun PantallaPrincipal(
    onCerrarSesion: () -> Unit,
    onNavegarACrearReporte: () -> Unit,
    onNavegarAMapa: () -> Unit,
    onNavegarAMisReportes: () -> Unit,
    onNavegarAReportesComunidad: () -> Unit,
    onNavegarAValidacion: () -> Unit,
    onNavegarAPerfil: () -> Unit,
    onNavegarANotificaciones: () -> Unit,
    onNavegarAEstadisticas: () -> Unit,
    esAdministrador: Boolean = false
) {
    val viewModelEstadisticas: ViewModelEstadisticas = hiltViewModel()
    val estadisticas by viewModelEstadisticas.estadisticas.collectAsState()

    LaunchedEffect(Unit) {
        viewModelEstadisticas.cargarEstadisticas()
    }

    // Funcionalidades BASE para todos los usuarios
    val funcionalidadesBase = listOf(
        Funcionalidad(
            id = "mapa",
            icono = Icons.Default.Map,
            titulo = "Mapa",
            descripcion = "Ver reportes en el mapa",
            onClick = onNavegarAMapa
        ),
        Funcionalidad(
            id = "mis_reportes",
            icono = Icons.Default.List,
            titulo = "Mis Reportes",
            descripcion = "Ver mis reportes enviados",
            onClick = onNavegarAMisReportes
        ),
        Funcionalidad(
            id = "reportes_comunidad",
            icono = Icons.Default.Public,
            titulo = "Reportes Comunidad",
            descripcion = "Ver reportes de la comunidad",
            onClick = onNavegarAReportesComunidad
        ),
        Funcionalidad(
            id = "crear_reporte",
            icono = Icons.Default.Add,
            titulo = "Crear Reporte",
            descripcion = "Reportar un problema",
            onClick = onNavegarACrearReporte
        ),
        Funcionalidad(
            id = "notificaciones",
            icono = Icons.Default.Notifications,
            titulo = "Notificaciones",
            descripcion = "Ver mis notificaciones",
            onClick = onNavegarANotificaciones
        ),
        Funcionalidad(
            id = "perfil",
            icono = Icons.Default.Person,
            titulo = "Mi Perfil",
            descripcion = "Ver y editar mi perfil",
            onClick = onNavegarAPerfil
        )
    )

    // Funcionalidades EXTRAS solo para administradores
    val funcionalidadesAdmin = if (esAdministrador) {
        listOf(
            Funcionalidad(
                id = "validacion",
                icono = Icons.Default.Verified,
                titulo = "Validar Reportes",
                descripcion = "Revisar reportes pendientes",
                onClick = onNavegarAValidacion
            ),
            Funcionalidad(
                id = "estadisticas",
                icono = Icons.Default.Analytics,
                titulo = "Estadísticas",
                descripcion = "Ver estadísticas de la comunidad",
                onClick = onNavegarAEstadisticas
            )
        )
    } else {
        emptyList()
    }

    // Combinar funcionalidades
    val funcionalidades = funcionalidadesBase + funcionalidadesAdmin

    Scaffold(
        topBar = {
            TopAppBar(
                title = {
                    Text(
                        "Mi Comunidad",
                        style = MaterialTheme.typography.titleLarge
                    )
                },
                colors = TopAppBarDefaults.topAppBarColors(
                    containerColor = MaterialTheme.colorScheme.primaryContainer,
                    titleContentColor = MaterialTheme.colorScheme.onPrimaryContainer
                ),
                actions = {
                    IconButton(onClick = onNavegarAPerfil) {
                        Icon(
                            Icons.Default.Person,
                            contentDescription = "Mi perfil",
                            tint = MaterialTheme.colorScheme.onPrimaryContainer
                        )
                    }
                    IconButton(onClick = onCerrarSesion) {
                        Icon(
                            Icons.Default.Logout,
                            contentDescription = "Cerrar sesión",
                            tint = MaterialTheme.colorScheme.onPrimaryContainer
                        )
                    }
                }
            )
        },
        floatingActionButton = {
            FloatingActionButton(
                onClick = onNavegarACrearReporte,
                containerColor = MaterialTheme.colorScheme.primary
            ) {
                Icon(Icons.Default.Add, "Nuevo reporte")
            }
        }
    ) { padding ->
        Column(
            modifier = Modifier
                .padding(padding)
                .fillMaxSize()
        ) {
            Card(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(16.dp),
                elevation = CardDefaults.cardElevation(defaultElevation = 4.dp)
            ) {
                Column(
                    modifier = Modifier.padding(16.dp)
                ) {
                    Text(
                        "¡Bienvenido a Mi Comunidad!",
                        style = MaterialTheme.typography.headlineSmall,
                        fontWeight = FontWeight.Bold
                    )
                    Spacer(modifier = Modifier.height(8.dp))
                    Text(
                        "Reporta problemas y mejora Dolores Hidalgo",
                        style = MaterialTheme.typography.bodyMedium
                    )

                    if (estadisticas.totalReportes > 0) {
                        Spacer(modifier = Modifier.height(16.dp))
                        Row(
                            modifier = Modifier.fillMaxWidth(),
                            horizontalArrangement = Arrangement.SpaceEvenly
                        ) {
                            EstadisticaItem(
                                valor = estadisticas.totalReportes.toString(),
                                etiqueta = "Reportes totales"
                            )
                            EstadisticaItem(
                                valor = estadisticas.reportesResueltos.toString(),
                                etiqueta = "Resueltos"
                            )
                            EstadisticaItem(
                                valor = "${estadisticas.porcentajeResueltos.toInt()}%",
                                etiqueta = "Eficiencia"
                            )
                        }
                    }
                }
            }
            Text(
                text = "Funcionalidades",
                style = MaterialTheme.typography.titleMedium,
                fontWeight = FontWeight.SemiBold,
                modifier = Modifier.padding(start = 16.dp, top = 8.dp, bottom = 8.dp)
            )

            LazyVerticalGrid(
                columns = GridCells.Fixed(2),
                modifier = Modifier
                    .fillMaxSize()
                    .padding(horizontal = 16.dp),
                verticalArrangement = Arrangement.spacedBy(12.dp),
                horizontalArrangement = Arrangement.spacedBy(12.dp)
            ) {
                items(funcionalidades) { funcionalidad ->
                    TarjetaFuncionalidad(
                        funcionalidad = funcionalidad,
                        onClick = funcionalidad.onClick
                    )
                }
            }
        }
    }
}

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun TarjetaFuncionalidad(
    funcionalidad: Funcionalidad,
    onClick: (() -> Unit)? = null
) {
    Card(
        onClick = { onClick?.invoke() },
        modifier = Modifier
            .fillMaxWidth()
            .height(120.dp),
        shape = RoundedCornerShape(12.dp),
        elevation = CardDefaults.cardElevation(defaultElevation = 4.dp),
        enabled = onClick != null
    ) {
        Column(
            modifier = Modifier
                .fillMaxSize()
                .padding(16.dp),
            horizontalAlignment = Alignment.CenterHorizontally,
            verticalArrangement = Arrangement.Center
        ) {
            Icon(
                imageVector = funcionalidad.icono,
                contentDescription = funcionalidad.titulo,
                modifier = Modifier.size(32.dp),
                tint = if (onClick != null) MaterialTheme.colorScheme.primary
                else MaterialTheme.colorScheme.onSurface.copy(alpha = 0.38f)
            )
            Spacer(modifier = Modifier.height(8.dp))
            Text(
                text = funcionalidad.titulo,
                style = MaterialTheme.typography.titleSmall,
                fontWeight = FontWeight.Bold,
                textAlign = TextAlign.Center,
                color = if (onClick != null) MaterialTheme.colorScheme.onSurface
                else MaterialTheme.colorScheme.onSurface.copy(alpha = 0.38f)
            )
            Text(
                text = funcionalidad.descripcion,
                style = MaterialTheme.typography.bodySmall,
                textAlign = TextAlign.Center,
                color = if (onClick != null) MaterialTheme.colorScheme.onSurfaceVariant
                else MaterialTheme.colorScheme.onSurface.copy(alpha = 0.38f)
            )
        }
    }
}

@Composable
fun EstadisticaItem(valor: String, etiqueta: String) {
    Column(
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Text(
            text = valor,
            style = MaterialTheme.typography.titleMedium,
            fontWeight = FontWeight.Bold,
            color = MaterialTheme.colorScheme.primary
        )
        Text(
            text = etiqueta,
            style = MaterialTheme.typography.labelSmall,
            color = MaterialTheme.colorScheme.onSurfaceVariant
        )
    }
}
```
# PantallaRegistro
```
```


















