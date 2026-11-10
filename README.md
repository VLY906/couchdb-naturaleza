# couchdb-naturaleza

Ejemplo de implementación de **Apache CouchDB**, una base de datos NoSQL documental de código abierto (licencia Apache 2.0), utilizada en su versión gratuita.

## Qué se hizo

Se planteó el caso de una página web educativa para niños sobre naturaleza. Los niños solo ven la página; el contenido que esta muestra se almacena en CouchDB como fichas (documentos en formato JSON).

Se creó la base de datos `explorando_naturaleza` y se almacenaron en ella tres fichas, cada una con sus propios campos:

| Ficha | Tipo | Campos propios |
|-------|------|----------------|
| `planta001` (girasol) | planta | `riego`, `luz` |
| `animal001` (rana arborícola) | animal | `habitat`, `dieta` |
| `hongo001` (champiñón) | hongo | `donde_crece` |

Todas las fichas tienen además el campo `estado`, que indica si el contenido está en `borrador` o `publicado`. Esto permite que la página muestre únicamente el contenido ya publicado.

Con estas fichas se realizaron las cuatro operaciones **CRUD**:

| Letra | Operación | Qué se hizo |
|-------|-----------|-------------|
| C | Create | Se crearon las fichas de la planta, el animal y el hongo |
| R | Read | Se consultaron las fichas por tipo (`planta`) y por estado (`publicado`) mediante consultas Mango |
| U | Update | Se cambió el estado del hongo de `borrador` a `publicado` |
| D | Delete | Se eliminó una de las fichas |

Durante el ejercicio se observó que cada ficha conserva solo los datos que necesita, y que CouchDB asigna a cada documento un campo `_rev`, que cambia con cada modificación y permite llevar el control de versiones.

## Contenido del repositorio

- `fichas/`: las fichas utilizadas, en formato JSON.
- `consultas/`: las consultas Mango utilizadas para buscar fichas.

## Cómo ejecutarlo

### Requisitos

- Apache CouchDB instalado (descarga gratuita en https://couchdb.apache.org).
- Un navegador web.

### Pasos

1. Abra el panel de CouchDB en el navegador:

   ```
   http://127.0.0.1:5984/_utils
   ```

   Inicie sesión con el usuario y la contraseña de administrador definidos durante la instalación de CouchDB.

2. Haga clic en **Create Database**, escriba `explorando_naturaleza` y haga clic en **Create**.
3. **Create:** dentro de la base, haga clic en **Create Document**, borre el texto que aparece, pegue el contenido de un archivo de la carpeta `fichas/` y haga clic en **Create Document**. Repita con los otros dos archivos.
4. **Read:** abra **Run A Query with Mango**, pegue una de las consultas de `consultas/consultas-mango.md` y haga clic en **Run Query**.
5. **Update:** en **All Documents**, abra `hongo001`, cambie `"estado": "borrador"` por `"estado": "publicado"` y haga clic en **Save Changes**. Al repetir la consulta por estado, el hongo ahora aparece.
6. **Delete:** abra una ficha y haga clic en el icono de la papelera para eliminarla.

## Nota de seguridad

Este repositorio no contiene contraseñas ni claves de acceso. Las credenciales de administrador de CouchDB se definen de forma local en el equipo de cada usuario.

## Autoras

Grupo 2 – Apache CouchDB. Universidad San Buenaventura, Bogotá.
María Paula Ruiz, Antonella Correa, Virginia León y Ángela Ramos.
