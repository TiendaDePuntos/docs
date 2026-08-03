# Referencia de la API

## `openapi.json` es un archivo generado

No lo edites a mano: se regenera desde el código del backend y cualquier cambio manual se pierde en el próximo export.

Para regenerarlo, desde el repo `tdp-backend`:

```bash
cd TiendaDePuntos.WebApi
npm run openapi:docs
```

Eso escribe `docs/api-reference/openapi.json` a partir de los controllers `/external` del WebApi. El script no necesita base de datos ni Redis.

Si querés cambiar la descripción de un endpoint, sus parámetros o sus ejemplos de respuesta, editá los decoradores Swagger del controller correspondiente en el backend y volvé a exportar.

## Las páginas `.mdx` sí se editan a mano

| Archivo | Qué es |
| --- | --- |
| `introduccion.mdx` | Panorama de la API, URL base, formato de respuestas |
| `autenticacion.mdx` | API key, header `x-branch-id`, errores de auth |
| `quickstart.mdx` | Guía paso a paso para integrar un POS |
| `errores.mdx` | Códigos de error, idempotencia, rate limits |

Las páginas de cada endpoint las genera Mintlify desde el spec: no existen como archivos.

## Probar los cambios

```bash
npx mint@latest dev        # preview en http://localhost:3000
npx mint@latest validate   # valida docs.json, MDX y OpenAPI
```
