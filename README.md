# Documentación de Tienda de Puntos

Documentación pública de [Tienda de Puntos](https://www.tiendadepuntos.com): guías del panel, referencia de la API y catálogo de integraciones. Corre sobre [Mintlify](https://mintlify.com/docs) y se publica automáticamente al pushear a `main`.

## Estructura

| Ruta | Qué es |
| --- | --- |
| `docs.json` | Navegación, colores, logos y footer del sitio |
| `index.mdx` | Tab de ayuda |
| `documentacion.mdx`, `primeros-pasos.mdx`, `pantallas-principales.mdx` | Guías del panel |
| `api-reference/` | Referencia de la API pública ([ver README](api-reference/README.md)) |
| `integraciones.mdx` | Catálogo de integraciones con POS, ERP y e-commerce |
| `style.css` | Overrides de estilo |
| `logo/`, `images/`, `favicon.png` | Assets |

El `api-reference/openapi.json` **es un archivo generado** desde los controllers `/external` del backend: no lo edites a mano. Está explicado en [api-reference/README.md](api-reference/README.md).

## Desarrollo

```bash
npx mint@latest dev        # preview en http://localhost:3000
npx mint@latest validate   # valida docs.json, MDX y OpenAPI
```

Si `mint dev` no arranca, corré `npx mint@latest update` para actualizar la CLI. Si una página da 404, chequeá que esté listada en el `docs.json`.

## Publicar cambios

Los cambios en `main` se despliegan solos vía la [GitHub app de Mintlify](https://dashboard.mintlify.com/settings/organization/github-app).

## Assets de marca

Los logos salen de `tdp-webapp/src/assets/icons/logo_completo.png`. `logo/light.png` usa el wordmark en el violeta de marca (`#5b53f1`) y `logo/dark.png` la variante en blanco para el tema oscuro; los dos comparten el ícono. Si cambia la marca, hay que actualizar los dos.
