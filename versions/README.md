# versions

`index.json` es el único fichero que consume la app **Spensa**. Lista TODAS las
releases publicadas con sus cambios. La app calcula la última (mayor `versionNumber`)
y muestra los cambios de todas las versiones posteriores a la instalada.

## Esquema (`index.json`)

```json
{
  "releases": [
    { "versionNumber": "X.Y.Z", "releaseDate": "YYYY-MM-DD", "changes": [
        { "type": "feature|improvement|fix", "description": "..." }
    ] }
  ]
}
```

- `versionNumber` (obligatorio): formato `X.Y.Z`. Debe coincidir con la `version`
  de `package.json` de la app en esa release.
- `releaseDate` (opcional): `YYYY-MM-DD`.
- `changes` (opcional): cada entrada tiene `description` (obligatorio) y `type`
  (opcional: `feature` | `improvement` | `fix`).
- El orden de `releases` no importa: la app ordena por `versionNumber`.

## Proceso de release

Añade una nueva entrada al array `releases` de `index.json` y haz push a `main`.
