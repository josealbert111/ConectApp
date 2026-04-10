# ConectApp 🤝

**ConectApp** es una aplicación de acción social diseñada para conectar a personas mayores y jóvenes en eventos comunitarios. Facilita la interacción intergeneracional y promueve la participación en actividades sociales con una interfaz accesible e intuitiva.

## 🎯 Visión

Crear un espacio digital inclusivo donde:
- 👴👵 Las personas mayores encuentren actividades y compañía de forma fácil
- 👨👩 Los jóvenes descubran oportunidades de voluntariado y acción social
- 🤝 Ambos grupos se conecten y construyan comunidades más fuertes

## ✨ Características principales

### MVP (Producto Mínimo Viable)
- ✅ Registro e inicio de sesión seguros
- ✅ Exploración de eventos por categoría y ubicación
- ✅ Crear y gestionar eventos
- ✅ Perfiles de usuario con información básica
- ✅ Sistema de notificaciones
- ✅ Interfaz accesible y responsive

### Características futuras
- 💬 Chat directo entre usuarios
- 📍 Mapa interactivo de eventos
- ⭐ Sistema de reseñas y valoraciones
- 📅 Calendario personalizado
- 🔔 Recordatorios de eventos
- 👥 Grupos comunitarios

## 🛠️ Stack Tecnológico

### Frontend
- **React** 18+ con TypeScript
- **Vite** (bundler)
- **Tailwind CSS** (estilos)
- **React Router** (navegación)
- **Axios** (requests HTTP)

### Backend
- **Node.js** + **Express**
- **PostgreSQL** (base de datos)
- **Prisma** (ORM)
- **JWT** (autenticación)
- **Nodemailer** (notificaciones por email)

### DevOps
- **Git** + **GitHub**
- **ESLint** + **Prettier** (código limpio)
- **Docker** (opcional)

## 📂 Estructura del proyecto

```
conect-app/
├── frontend/               # Aplicación React
│   ├── src/
│   │   ├── components/    # Componentes reutilizables
│   │   ├── pages/         # Páginas principales
│   │   ├── services/      # API requests
│   │   ├── hooks/         # Custom hooks
│   │   ├── utils/         # Funciones auxiliares
│   │   ├── styles/        # CSS global
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── package.json
│   ├── tsconfig.json
│   ├── vite.config.ts
│   └── index.html
│
├── backend/                # API Node.js
│   ├── src/
│   │   ├── routes/        # Rutas de la API
│   │   ├── controllers/   # Lógica de negocio
│   │   ├── models/        # Esquemas Prisma
│   │   ├── middleware/    # Middlewares
│   │   ├── utils/         # Funciones auxiliares
│   │   ├── app.ts
│   │   └── server.ts
│   ├── prisma/
│   │   └── schema.prisma  # Definición de BD
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
│
├── docs/                   # Documentación
│   ├── API.md             # Documentación de endpoints
│   ├── DESARROLLO.md      # Guía de desarrollo
│   └── ARQUITECTURA.md    # Arquitectura del proyecto
│
├── .gitignore
└── README.md
```

## 🚀 Inicio rápido

### Requisitos previos
- Node.js 18+
- npm o yarn
- PostgreSQL 12+
- Git

### Setup Frontend

```bash
cd frontend
npm install
npm run dev
```

Accede a `http://localhost:5173`

### Setup Backend

```bash
cd backend
npm install
cp .env.example .env
# Configura las variables de entorno en .env
npm run dev
```

El servidor correrá en `http://localhost:3000`

## 📖 Documentación

- [API Endpoints](./docs/API.md)
- [Guía de Desarrollo](./docs/DESARROLLO.md)
- [Arquitectura](./docs/ARQUITECTURA.md)

## 🎨 Características de Accesibilidad

ConectApp está diseñada pensando en la inclusión:

- 🔤 **Texto legible**: Fuentes grandes y claras
- 🌈 **Alto contraste**: Colores que facilitan la lectura
- 🖱️ **Interfaz simple**: Navegación intuitiva con botones grandes
- 📱 **Responsive**: Funciona en dispositivos de todos los tamaños
- ⌨️ **Accesible por teclado**: Navegación sin ratón
- 🔊 **Soporte de lectores de pantalla**: Compatible con tecnologías asistivas

## 🤝 Contribuir

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

Consulta [DESARROLLO.md](./docs/DESARROLLO.md) para más detalles.

## 📝 Licencia

Este proyecto está bajo la licencia MIT. Consulta [LICENSE](./LICENSE) para más detalles.

## 👥 Autores

- **José Alberto** - Creador inicial

## 📧 Contacto

Para preguntas o sugerencias: contacto@conectapp.com

---

**ConectApp**: Conectando generaciones, construyendo comunidades 🤝
