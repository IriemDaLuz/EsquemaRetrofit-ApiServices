# Esquema de Retrofit

## ¿Qué es Retrofit?
Retrofit es una librería de Android (y Java) que facilita las solicitudes HTTP y la conversión automática de las respuestas JSON en objetos Java. Retrofit se utiliza para interactuar con APIs web de manera eficiente y sencilla.

## Dependencias  
Para usar Retrofit, agrega las siguientes dependencias en tu archivo `build.gradle`:

```gradle
dependencies {
    def retrofit_version = "2.9.0"
    
    // Retrofit
    implementation "com.squareup.retrofit2:retrofit:$retrofit_version"

    // Convertidor Gson (para transformar JSON a objetos)
    implementation "com.squareup.retrofit2:converter-gson:$retrofit_version"
    
    // OkHttp (opcional, para manejar el cliente HTTP)
    implementation "com.squareup.okhttp3:logging-interceptor:5.0.0-alpha.11"
}
```
## ¿Para qué se usa?
Se utiliza para realizar solicitudes de red, como obtener datos desde una API o enviar información a un servidor, transformando automáticamente las respuestas JSON a objetos Java y viceversa.

## Componentes Clave:
- **Interfaz de API**: Define los endpoints y sus métodos HTTP.
- **Retrofit.Builder**: Configura y crea una instancia de Retrofit.
- **Convertidor**: Utiliza un convertidor como Gson para transformar los datos JSON en objetos Java.

## ¿Cómo funciona?
1. Definimos una interfaz que describe los métodos HTTP (`GET`, `POST`, etc.).
2. Retrofit usa esta interfaz para generar el código necesario para realizar las solicitudes.
3. Retrofit convierte automáticamente las respuestas JSON a objetos Java usando un convertidor como Gson.

# Código de Ejemplo con Retrofit

## 1. Crear la Interfaz de API  
Define los endpoints de tu API:

```kotlin
import retrofit2.Call
import retrofit2.http.GET

interface ApiService {
    @GET("posts")
    fun getPosts(): Call<List<Post>>
}
```
## 2. Definir el Modelo de Datos  
Crea una clase que represente los datos que recibirás:

```kotlin
data class Post(
    val userId: Int,
    val id: Int,
    val title: String,
    val body: String
)
```
## 3. Configurar Retrofit  
Configura Retrofit y crea una instancia de la API:

```kotlin
import retrofit2.Retrofit
import retrofit2.converter.gson.GsonConverterFactory

val retrofit = Retrofit.Builder()
    .baseUrl("https://jsonplaceholder.typicode.com/")
    .addConverterFactory(GsonConverterFactory.create())
    .build()

val apiService = retrofit.create(ApiService::class.java)
