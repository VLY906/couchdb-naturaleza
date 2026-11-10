# Consultas Mango utilizadas

Las consultas se ejecutan en el panel de CouchDB, en **Run A Query with Mango**.

## Fichas de tipo planta

```json
{
  "selector": {
    "tipo": "planta"
  }
}
```

## Fichas publicadas

```json
{
  "selector": {
    "estado": "publicado"
  }
}
```

Antes de actualizar el hongo, esta consulta devuelve la planta y el animal. Después de cambiar el estado del hongo a `publicado`, devuelve las tres fichas.
