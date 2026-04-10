# Documentación de API - ConectApp

## Base URL
```
http://localhost:3000/api
```

## Autenticación
Los endpoints protegidos requieren un token JWT en el header:
```
Authorization: Bearer <token>
```

## Endpoints

### 🔐 Autenticación

#### Registrar Usuario
```http
POST /auth/register
Content-Type: application/json

{
  "email": "usuario@example.com",
  "password": "contraseña123",
  "name": "Juan Pérez",
  "birthDate": "1950-05-15"
}
```

**Respuesta (201):**
```json
{
  "id": "user123",
  "email": "usuario@example.com",
  "name": "Juan Pérez",
  "token": "eyJhbGciOiJIUzI1NiIs..."
}
```

#### Iniciar Sesión
```http
POST /auth/login
Content-Type: application/json

{
  "email": "usuario@example.com",
  "password": "contraseña123"
}
```

**Respuesta (200):**
```json
{
  "id": "user123",
  "email": "usuario@example.com",
  "name": "Juan Pérez",
  "token": "eyJhbGciOiJIUzI1NiIs..."
}
```

### 👤 Usuarios

#### Obtener Perfil
```http
GET /users/:id
Authorization: Bearer <token>
```

**Respuesta (200):**
```json
{
  "id": "user123",
  "email": "usuario@example.com",
  "name": "Juan Pérez",
  "bio": "Me encanta pasar tiempo con la comunidad",
  "avatar": "https://...",
  "phone": "+34 123 456 789",
  "createdAt": "2026-04-10T10:00:00Z"
}
```

#### Actualizar Perfil
```http
PUT /users/:id
Authorization: Bearer <token>
Content-Type: application/json

{
  "name": "Juan Carlos Pérez",
  "bio": "Nueva biografía",
  "phone": "+34 987 654 321"
}
```

### 📅 Eventos

#### Listar Eventos
```http
GET /events?category=social&limit=10&offset=0
```

**Query Parameters:**
- `category` (optional): Categoría del evento
- `limit` (optional, default: 10): Número de resultados
- `offset` (optional, default: 0): Desplazamiento
- `search` (optional): Búsqueda por texto

**Respuesta (200):**
```json
{
  "total": 25,
  "limit": 10,
  "offset": 0,
  "data": [
    {
      "id": "event123",
      "title": "Clase de baile",
      "description": "Aprende a bailar con nosotros",
      "date": "2026-05-15T18:00:00Z",
      "location": "Calle Principal 123",
      "category": "cultural",
      "maxAttendees": 30,
      "attendeesCount": 12,
      "creator": {
        "id": "user123",
        "name": "María García"
      }
    }
  ]
}
```

#### Crear Evento
```http
POST /events
Authorization: Bearer <token>
Content-Type: application/json

{
  "title": "Clase de baile",
  "description": "Aprende a bailar con nosotros",
  "date": "2026-05-15T18:00:00Z",
  "location": "Calle Principal 123",
  "category": "cultural",
  "maxAttendees": 30
}
```

**Respuesta (201):**
```json
{
  "id": "event123",
  "title": "Clase de baile",
  "description": "Aprende a bailar con nosotros",
  "date": "2026-05-15T18:00:00Z",
  "location": "Calle Principal 123",
  "category": "cultural",
  "maxAttendees": 30,
  "createdBy": "user123",
  "createdAt": "2026-04-10T10:00:00Z"
}
```

#### Obtener Detalle de Evento
```http
GET /events/:id
```

**Respuesta (200):**
```json
{
  "id": "event123",
  "title": "Clase de baile",
  "description": "Aprende a bailar con nosotros",
  "date": "2026-05-15T18:00:00Z",
  "location": "Calle Principal 123",
  "category": "cultural",
  "maxAttendees": 30,
  "attendees": [
    {
      "id": "user123",
      "name": "Juan Pérez"
    }
  ],
  "creator": {
    "id": "user456",
    "name": "María García"
  }
}
```

#### Actualizar Evento
```http
PUT /events/:id
Authorization: Bearer <token>
Content-Type: application/json

{
  "title": "Clase de baile (Actualizada)",
  "description": "Nueva descripción"
}
```

#### Eliminar Evento
```http
DELETE /events/:id
Authorization: Bearer <token>
```

**Respuesta (204):** No content

### ✅ Asistencia a Eventos

#### Asistir a Evento
```http
POST /events/:id/attend
Authorization: Bearer <token>
```

**Respuesta (201):**
```json
{
  "message": "Te has unido al evento exitosamente"
}
```

#### Dejar de Asistir
```http
DELETE /events/:id/attend
Authorization: Bearer <token>
```

**Respuesta (204):** No content

## Códigos de Error

| Código | Descripción |
|--------|-------------|
| 200 | Exitoso |
| 201 | Creado |
| 204 | Sin contenido |
| 400 | Solicitud inválida |
| 401 | No autorizado |
| 403 | Prohibido |
| 404 | No encontrado |
| 500 | Error del servidor |

---

**Última actualización**: 2026-04-10

