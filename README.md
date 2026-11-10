# couchdb-naturaleza

Ejemplo sencillo de **Apache CouchDB**, una base de datos NoSQL documental, usando su versión gratuita (código abierto, licencia Apache 2.0).

## ¿Qué hace este ejemplo?

Imagina una página web educativa para niños sobre naturaleza: plantas, animales y hongos. Los niños solo ven la página, pero por detrás todo el contenido se guarda en CouchDB como **fichas** (documentos en formato JSON).

Cada ficha guarda solo los datos que necesita:

- Una planta tiene `riego` y `luz`.
- Un animal tiene `habitat` y `dieta`.
- Un hongo tiene `donde_crece`.

En una base de datos con tablas, todos tendrían que tener las mismas columnas. En CouchDB, no.

El ejemplo muestra las cuatro operaciones **CRUD**:

| Letra | Operación | Qué se hace en el ejemplo |
|-------|-----------|---------------------------|
| C | Create | Crear fichas nuevas |
| R | Read | Consultar fichas por tipo y por estado |
| U | Update | Cambiar el estado de una ficha de `borrador` a `publicado` |
| D | Delete | Eliminar una ficha |

## Contenido del repositorio

- `fichas/`: las fichas de ejemplo en formato JSON.
- `consultas/`: las consultas que se usan para buscar fichas.

## Cómo ejecutarlo

### 1. Requisitos

- Tener **Apache CouchDB** instalado (descarga gratuita en https://couchdb.apache.org).
- Un navegador web.

### 2. Abrir el panel de CouchDB

Con CouchDB instalado, abre en el navegador:

```
http://127.0.0.1:5984/_utils
```

Inicia sesión con el usuario y la contraseña de administrador que creaste al instalar CouchDB. Esas credenciales son tuyas y no se suben a este repositorio.

### 3. Crear la base de datos

1. Haz clic en **Create Database**.
2. Escribe el nombre `explorando_naturaleza`.
3. Deja la opción **Non-partitioned** y haz clic en **Create**.

### 4. Crear las fichas (Create)

1. Dentro de la base, haz clic en **Create Document**.
2. Borra el texto que aparece.
3. Copia el contenido de un archivo de la carpeta `fichas/` y pégalo.
4. Haz clic en **Create Document**.
5. Repite con los otros dos archivos.

### 5. Consultar las fichas (Read)

1. En el menú izquierdo, abre **Run A Query with Mango**.
2. Pega una de las consultas de `consultas/consultas-mango.md`.
3. Haz clic en **Run Query**.

### 6. Actualizar una ficha (Update)

1. Ve a **All Documents** y abre `hongo001`.
2. Cambia `"estado": "borrador"` por `"estado": "publicado"`.
3. Haz clic en **Save Changes**.
4. Repite la consulta por estado: ahora el hongo también aparece.

### 7. Eliminar una ficha (Delete)

1. Abre `hongo001` en **All Documents**.
2. Haz clic en el icono de la papelera y confirma.

## Notas

- CouchDB le asigna a cada documento un `_rev` que cambia en cada modificación y sirve para llevar el control de versiones.
- Este repositorio no contiene contraseñas ni claves de acceso.

## Autores

Grupo 2 – Apache CouchDB. Universidad San Buenaventura, Bogotá.
Ruiz María Paula, Correa Antonella, León Virginia y Ramos Ángela.
