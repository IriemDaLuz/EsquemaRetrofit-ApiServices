# Esquema de SQLite

## ¿Qué es SQLite?
SQLite es una base de datos ligera integrada que se utiliza para almacenar datos de forma local en dispositivos Android. Es ideal para aplicaciones que necesitan persistir información en el dispositivo sin depender de un servidor externo.

---

## ¿Para qué se usa?
SQLite se utiliza para:
- Almacenar datos estructurados en tablas.
- Gestionar información de la aplicación, como usuarios, configuraciones o historiales.
- Ofrecer una solución de almacenamiento local para aplicaciones móviles.

---

## Componentes Clave

1. **SQLiteOpenHelper**:
   - Facilita la creación, actualización y gestión de la base de datos.
   - Maneja eventos como crear tablas o actualizar su esquema.

2. **SQLiteDatabase**:
   - Proporciona métodos para interactuar directamente con la base de datos.
   - Permite realizar operaciones como `INSERT`, `SELECT`, `UPDATE` y `DELETE`.

3. **ContentValues**:
   - Contenedor de pares clave-valor para insertar o actualizar datos en la base de datos.

4. **Cursor**:
   - Representa los resultados de una consulta SQL.
   - Permite recorrer los datos devueltos por la base de datos.

---

## ¿Cómo funciona?

1. Se extiende la clase `SQLiteOpenHelper` para gestionar la base de datos.
2. Se definen las tablas y su esquema en el método `onCreate`.
3. Se realizan operaciones como insertar, consultar, actualizar y eliminar datos utilizando la clase `SQLiteDatabase`.

---
