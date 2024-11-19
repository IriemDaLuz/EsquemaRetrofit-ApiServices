# Esquema de Retrofit

## ¿Qué es Retrofit?
Retrofit es una librería de Android (y Java) que facilita las solicitudes HTTP y la conversión automática de las respuestas JSON en objetos Java. Retrofit se utiliza para interactuar con APIs web de manera eficiente y sencilla.

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
