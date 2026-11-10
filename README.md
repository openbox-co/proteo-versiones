# Versiones de PROTEO

Manifiesto firmado de las versiones publicadas. Cada instalación lo consulta una vez al día
(y al pulsar «Buscar actualizaciones» en Ajustes → Sistema) en
`https://openbox-co.github.io/proteo-versiones/estable.json`, verifica la firma con la clave
incrustada en su binario y muestra las versiones nuevas que cubre su licencia.

- `versiones.json`: la lista que se edita a mano al publicar una versión.
- `estable.json`: lo mismo, firmado. **No se edita a mano**:

```bash
go run ./cmd/proteo-versiones firmar -id versiones-2026-1 \
  -privada ~/.proteo/versiones-2026-1.pem -datos ../proteo-versiones/versiones.json \
  > ../proteo-versiones/estable.json
go run ./cmd/proteo-versiones verificar ../proteo-versiones/estable.json
```

(desde el repo `openbox-co/proteo`). La clave privada nunca entra a un repo.
