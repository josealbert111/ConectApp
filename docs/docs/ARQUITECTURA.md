# Arquitectura - ConectApp

## 🏗️ Visión General

ConectApp utiliza una arquitectura de **tres capas**:

```
┌─────────────────────┐
│   Frontend (React)  │  ← Interfaz de usuario
├─────────────────────┤
│  Backend (Express)  │  ← Lógica de negocio
├─────────────────────┤
│ Database (PostgreSQL)│ ← Almacenamiento
└─────────────────────┘
```

## 📡 Flujo de Datos

1. **Usuario interactúa** con la interfaz React
2. **Frontend hace request** HTTP al backend
3. **Backend procesa** la lógica y valida datos
4. **Base de datos** almacena/recupera información
5. **Respuesta regresa** al frontend
6. **UI se actualiza** para mostrar cambios

## 🔀 Componentes Principales

### Frontend (React)
- **Pages**: Vistas principales (Login, Events, Profile)
- **Components**: Elementos reutilizables (Button, Card, Form)
- **Services**: Funciones para comunicarse con el backend
- **Hooks**: Lógica de estado y efectos
- **Utils**: Funciones auxiliares

### Backend (Express)
- **Routes**: Define los endpoints de la API
- **Controllers**: Maneja la lógica de cada ruta
- **Models**: Esquemas de datos con Prisma
- **Middleware**: Autenticación, validación, logging
- **Utils**: Funciones auxiliares

### Base de Datos (PostgreSQL)
- **Users**: Información de usuarios
- **Events**: Eventos creados
- **EventAttendees**: Relación usuario-evento

## 🔐 Seguridad

### Autenticación
- JWT tokens con expiración
- Contraseñas hasheadas con bcrypt
- Validación de email

### Autorización
- Middleware de autenticación en rutas protegidas
- Control de acceso basado en roles (futuro)

### Validación
- Validación de entrada en el backend
- Sanitización de datos
- Manejo de errores robusto

## 📊 Diagrama de Base de Datos

```
┌──────────────┐         ┌──────────────┐
│    Users     │         │    Events    │
├──────────────┤         ├──────────────┤
│ id (PK)      │         │ id (PK)      │
│ email        │         │ title        │
│ password     │         │ description  │
│ name         │         │ date         │
│ birthDate    │         │ location     │
│ createdAt    │         │ category     │
│ updatedAt    │         │ createdBy(FK)├──┐
└──────────────┘         └──────────────┘  │
        ▲                                   │
        │                                   │
        │                                   │
        │                 ┌─────────────────┘
        │                 │
        │         ┌───────────────────┐
        │         │ EventAttendees    │
        └─────────┤───────────────────┤
                  │ id (PK)           │
                  │ userId (FK)       │
                  │ eventId (FK)      │
                  └───────────────────┘
```

## 🔄 Ciclo de Vida de una Solicitud

### Crear un evento (POST /api/events)

1. **Cliente**: Envía formulario con datos del evento
2. **Frontend**: Valida datos localmente
3. **API Call**: Envía request a backend con token JWT
4. **Middleware**: Valida token y autenticación
5. **Controller**: Procesa la solicitud
6. **Validación**: Valida datos en el backend
7. **Database**: Guarda evento en PostgreSQL
8. **Response**: Devuelve evento creado
9. **Frontend**: Actualiza estado y UI

## 🚀 Escalabilidad Futura

### Posibles mejoras
- **Caché** (Redis) para eventos populares
- **Queue** (Bull) para procesamiento asincrónico
- **Microservicios** si crece significativamente
- **GraphQL** como alternativa a REST
- **WebSockets** para notificaciones en tiempo real

## 📱 Consideraciones Mobile

- API REST agnóstica a plataforma
- Respuestas JSON ligeras
- Soporte para offline (future)
- Sincronización de datos

## 📊 Monitoreo y Logs

### Backend
- Logs de errores
- Tracking de requests
- Métricas de performance (futuro)

### Frontend
- Error tracking (Sentry, futuro)
- Analytics (futuro)
- User session tracking (futuro)

---

**Última actualización**: 2026-04-10

