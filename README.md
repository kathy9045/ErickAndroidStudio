# ErickAndroidStudiopackage co.edu.sena.myapp

val nombreInmutable: String = "Katherin"
val edadInmutable: Int = 30
val valorPiInmutable = 3.14159 


var nombreMutable: String = "Katherin"
nombreMutable = "Dayann" 

var edadMutable: Int = 30
edadMutable = 31 

var valorPiMutable = 3.14159
valorPiMutable = 3.14 


val numeroByte: Byte = 1
val numeroShort: Short = 10
val numeroInt: Int = 100
val numeroLong: Long = 1000L


val numeroFloat: Float = 1.23F
val numeroDouble: Double = 1.23

val caracter: Char = 'A'

val esVerdadero: Boolean = true
val esFalso: Boolean = false


val mensaje: String = "Hola, Katherin!"

fun main() {
    val nombreLocal: String = "Juanito"
    var edadLocal: Int = 30
    println("Nombre: $nombreLocal, Edad: $edadLocal")
}


var nombreNullable: String? = "Kevin"
nombreNullable = null 

lateinit var nombreTardio: String

fun inicializarNombreTardio() {
    nombreTardio = "Carlos"
}

const val PI = 3.14159
const val MAX_AGE = 100
const val APP_NAME = "MyApp"

object Constantes {
    const val URL_BASE = "https://api.example.com/"
    const val TIEMPO_ESPERA = 30
}


class Configuracion {
    companion object {
        const val VERSION_APP = "1.0.0"
        const val IDIOMA_POR_DEFECTO = "en"
    }
}

// 4 Tipos de Datos
// Solo primitivos (Byte, Short, Int, Long, Float, Double, Char, Boolean) y String


val longitudNombre = nombreNullable!!.length  // Lanzará una NullPointerException si 'nombreNullable' es null


val longitudNombreConElvis = nombreNullable?.length ?: 0  

val longitudNombreSafeCall = nombreNullable?.length  

nombreNullable?.let { println("Nombre tiene una longitud de ${it.length}") }

val nombreNoNulo = requireNotNull(nombreNullable) { "El nombre no puede ser nulo" }


val nombreChequeado = checkNotNull(nombreNullable) { "El nombre no puede ser nulo" }

class Opcional<T>(private val valor: T?) {
    fun estaPresente(): Boolean = valor != null

    fun obtener(): T = valor ?: throw NoSuchElementException("No hay valor presente")

    fun siEstaPresente(accion: (T) -> Unit) {
        valor?.let(accion)
    }

    fun oDeLoContrario(otro: T): T = valor ?: otro
}
