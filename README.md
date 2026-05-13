# API – Tipos de Archivos Adjuntos

API de solo lectura servida con [My JSON Server](https://my-json-server.typicode.com/) que expone un catálogo de tipos de archivos adjuntos (extensiones, MIME types y descripciones).

**URL base**

```
https://my-json-server.typicode.com/liljuanxxo6/api
```

---

## Recursos disponibles

| Recurso | Descripción |
|---|---|
| `tiposArchivosAdjuntos` | Catálogo de tipos de archivo soportados |

---

## Endpoints

### 1. Listar todos los tipos de archivos

Devuelve el arreglo completo de tipos de archivos adjuntos.

**GET** `/tiposArchivosAdjuntos`

```
GET https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos
```

**Ejemplo de respuesta**

```json
[
  {
    "id": 1,
    "extension": ".pdf",
    "mimeType": "application/pdf",
    "descripcion": "Documento PDF"
  },
  {
    "id": 2,
    "extension": ".doc",
    "mimeType": "application/msword",
    "descripcion": "Documento Word"
  }
  ...
]
```

---

### 2. Obtener un tipo de archivo por ID

Devuelve el objeto correspondiente al `id` indicado.

**GET** `/tiposArchivosAdjuntos/{id}`

```
GET https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos/1
```

**Ejemplo de respuesta**

```json
{
  "id": 1,
  "extension": ".pdf",
  "mimeType": "application/pdf",
  "descripcion": "Documento PDF"
}
```

---

### 3. Filtrar por campo

Puedes filtrar los resultados usando cualquier campo como parámetro de consulta (`query string`).

**GET** `/tiposArchivosAdjuntos?campo=valor`

#### Filtrar por extensión

```
GET https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos?extension=.pdf
```

#### Filtrar por MIME type

```
GET https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos?mimeType=image/png
```

---

### 4. Paginación

Usa los parámetros `_page` y `_limit` para paginar los resultados.

```
GET https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos?_page=1&_limit=5
```

---

### 5. Ordenar resultados

Usa `_sort` y `_order` para ordenar.

```
GET https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos?_sort=extension&_order=asc
```

---

## Estructura del objeto

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | `number` | Identificador único del tipo de archivo |
| `extension` | `string` | Extensión del archivo (e.g. `.pdf`, `.png`) |
| `mimeType` | `string` | MIME type del archivo (e.g. `application/pdf`) |
| `descripcion` | `string` | Descripción legible del tipo de archivo |

---

## Catálogo completo

| ID | Extensión | MIME Type | Descripción |
|---|---|---|---|
| 1 | `.pdf` | `application/pdf` | Documento PDF |
| 2 | `.doc` | `application/msword` | Documento Word |
| 3 | `.docx` | `application/vnd.openxmlformats-officedocument.wordprocessingml.document` | Documento Word moderno |
| 4 | `.xls` | `application/vnd.ms-excel` | Archivo Excel |
| 5 | `.xlsx` | `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet` | Archivo Excel moderno |
| 6 | `.ppt` | `application/vnd.ms-powerpoint` | Presentación PowerPoint |
| 7 | `.pptx` | `application/vnd.openxmlformats-officedocument.presentationml.presentation` | Presentación PowerPoint moderna |
| 8 | `.txt` | `text/plain` | Archivo de texto |
| 9 | `.csv` | `text/csv` | Archivo CSV |
| 10 | `.json` | `application/json` | Archivo JSON |
| 11 | `.xml` | `application/xml` | Archivo XML |
| 12 | `.zip` | `application/zip` | Archivo comprimido ZIP |
| 13 | `.rar` | `application/vnd.rar` | Archivo comprimido RAR |
| 14 | `.jpg` | `image/jpeg` | Imagen JPG |
| 15 | `.jpeg` | `image/jpeg` | Imagen JPEG |
| 16 | `.png` | `image/png` | Imagen PNG |
| 17 | `.gif` | `image/gif` | Imagen GIF |
| 18 | `.webp` | `image/webp` | Imagen WEBP |
| 19 | `.mp4` | `video/mp4` | Video MP4 |
| 20 | `.mp3` | `audio/mpeg` | Audio MP3 |

---

## Ejemplos de uso

### JavaScript (fetch)

```js
// Obtener todos los tipos de archivo
fetch('https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos')
  .then(res => res.json())
  .then(data => console.log(data));

// Obtener el tipo de archivo con id=3
fetch('https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos/3')
  .then(res => res.json())
  .then(data => console.log(data));
```

### cURL

```bash
# Listar todos
curl https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos

# Obtener por ID
curl https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos/1

# Filtrar imágenes
curl "https://my-json-server.typicode.com/liljuanxxo6/api/tiposArchivosAdjuntos?mimeType=image/png"
```

---

## Notas

- Esta API es de **solo lectura** (My JSON Server no persiste cambios en producción).
- No requiere autenticación.
- Responde siempre con `Content-Type: application/json`.
