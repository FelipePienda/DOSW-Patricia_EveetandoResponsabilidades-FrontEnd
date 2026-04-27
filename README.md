# Patricia  - Frontend

![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-4.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![React Router](https://img.shields.io/badge/React-Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-HTTP-5A29E4?style=for-the-badge&logo=axios&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-16+-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-Design-F24E1E?style=for-the-badge&logo=figma&logoColor=white)
![Stitch](https://img.shields.io/badge/Stitch-Component-FF6B35?style=for-the-badge&logo=stitch&logoColor=white)
--

Plataforma de comunidad para estudiantes universitarios que permite conectar con otros estudiantes, formar grupos de estudio, crear parchas para actividades académicas y de entretenimiento.

## Tecnologías Utilizadas

- React 18
- TypeScript
- Tailwind CSS
- Vite
- React Router
- Axios
- Context API para manejo de estado
- Responsive Design (Mobile First)

## Descripción General

EciBuddy es una aplicación web que funciona como una red social académica y de entretenimiento para estudiantes universitarios. La plataforma facilita la conexión entre estudiantes con intereses similares, permitiendo la formación de grupos de estudio (Parchas) y la exploración de comunidades basadas en diferentes categorías.

### Flujo de Usuario

1. El usuario accede a la aplicación a través de la pantalla de login
2. Se autentica con credenciales de correo o mediante Google/Facebook
3. Completa su perfil con intereses y preferencias
4. Navega por la plataforma para descubrir estudiantes y parchas
5. Puede unirse a parchas existentes o crear nuevas
6. Interactúa con otros miembros de la comunidad

## Navegación de la Aplicación

La aplicación está dividida en las siguientes secciones principales:

### 1. Autenticación
- Pantalla de Login: Autenticación con correo/contraseña o redes sociales
- Pantalla de Registro: Creación de nuevas cuentas de usuario
- Recuperación de contraseña: Opción para restablecer credenciales

### 2. Dashboard Principal (Find your Vibe)
Pantalla central donde el usuario descubre estudiantes con intereses similares. Presenta:
- Perfect Matches: Recomendación de estudiantes basada en intereses y energía compartida
- Tarjetas de perfil con información básica del estudiante
- Botón "Say Hello" para iniciar contacto
- Sección "University Pulse" con actividades recientes de la comunidad

### 3. Gestión de Parchas (Your Next Parche starts here)
Funcionalidad para crear y gestionar grupos de estudio y entretenimiento:
- Vista de parchas activas categorizadas por tipo (Academic, Social, Sports)
- Creación de nuevas parchas con parámetros personalizables
- Unirse a parchas existentes
- Vista detallada de cada parcha con miembros y actividades

### 4. Perfil de Usuario
Visualización completa del perfil del usuario con:
- Información personal y avatar
- Social Progress: Indicador del progreso en la comunidad (XP, eventos, clubes)
- Eventos asistidos y milestones alcanzados
- Galería de fotos y conexiones
- Opción "Need a little boost?" para acceso a chatbot de soporte

## Funcionalidades Principales

### Happy Path

El flujo feliz de la aplicación comprende:

1. Autenticación exitosa del usuario
2. Visualización del dashboard principal con recomendaciones
3. Descubrimiento de estudiantes con intereses similares
4. Creación o unión a una parcha
5. Interacción con miembros y visualización de progreso
6. Acceso a funcionalidades adicionales como galería y milestones

### Manejo de Errores

El sistema implementa manejo de excepciones en tres niveles:

- E1: Errores de autenticación y autorización (credenciales inválidas, sesión expirada, acceso denegado)
- E2: Errores de validación de datos (campos requeridos vacíos, formato inválido, duplicados)
- E3: Errores del servidor y conectividad (timeout, error 500, desconexión de red)

Cada error muestra al usuario un mensaje claro indicando el problema y sugiriendo una acción correctiva.

## Arquitectura de Componentes

La arquitectura frontend está organizada en componentes reutilizables y modulares:

```
src/
├── components/
│   ├── Auth/
│   │   ├── LoginForm.tsx
│   │   ├── RegisterForm.tsx
│   │   └── AuthLayout.tsx
│   ├── Dashboard/
│   │   ├── MainDashboard.tsx
│   │   ├── PerfectMatches.tsx
│   │   └── UniversityPulse.tsx
│   ├── Parche/
│   │   ├── ParcheCard.tsx
│   │   ├── ParcheList.tsx
│   │   ├── ParcheDetail.tsx
│   │   └── CreateParche.tsx
│   ├── Profile/
│   │   ├── UserProfile.tsx
│   │   ├── ProfileHeader.tsx
│   │   ├── SocialProgress.tsx
│   │   └── MilestonesSection.tsx
│   ├── Common/
│   │   ├── Header.tsx
│   │   ├── Navigation.tsx
│   │   ├── Button.tsx
│   │   └── Card.tsx
│   └── Chat/
│       ├── ChatBot.tsx
│       └── ChatInterface.tsx
├── pages/
│   ├── LoginPage.tsx
│   ├── DashboardPage.tsx
│   ├── ParchePage.tsx
│   ├── ProfilePage.tsx
│   └── NotFoundPage.tsx
├── services/
│   ├── authService.ts
│   ├── userService.ts
│   ├── parcheService.ts
│   └── api.ts
├── context/
│   ├── AuthContext.tsx
│   ├── UserContext.tsx
│   └── ParcheContext.tsx
├── hooks/
│   ├── useAuth.ts
│   ├── useUser.ts
│   ├── useParche.ts
│   └── useApi.ts
├── utils/
│   ├── validators.ts
│   ├── formatters.ts
│   └── constants.ts
├── styles/
│   ├── globals.css
│   ├── variables.css
│   └── themes.css
└── App.tsx
```

## Diagrama de Navegación

```
Login/Register
    ↓
Dashboard Principal
├── Perfect Matches (Descubrimiento de usuarios)
├── University Pulse (Actividades recientes)
└── Navigation Menu
    ├── Your Next Parche starts here
    │   ├── Active Parchas (Listado)
    │   ├── Create New Parche (Formulario)
    │   └── Parche Detail (Vista detallada)
    ├── Profile
    │   ├── User Info
    │   ├── Social Progress
    │   ├── Milestones
    │   ├── Gallery
    │   └── Need a boost? (Chat)
    └── Settings
        ├── Preferences
        └── Logout
```

## Secuencias de Interacción

### Secuencia: Crear una Parcha

1. Usuario navega a "Your Next Parche starts here"
2. Click en botón "Create New Parche"
3. Completa formulario con:
   - Nombre de la parcha
   - Categoría (Academic, Social, Sports)
   - Descripción
   - Capacidad máxima de miembros
   - Horarios y ubicación
4. Sistema valida los datos (E2)
5. Petición al backend para crear parcha
6. Redirección a página de la parcha creada
7. Opción para invitar miembros

### Secuencia: Descubrir y Conectar

1. Usuario visualiza Perfect Matches en dashboard
2. Ve tarjeta de estudiante recomendado
3. Click en "Say Hello"
4. Sistema envía solicitud de conexión
5. Notification al otro usuario
6. Al aceptar, se abre chat directo
7. Usuario puede invitar a parcha o continuar conversando

### Secuencia: Ver Progreso Social

1. Usuario accede a su perfil
2. Visualiza barra de progreso social (XP/Nivel)
3. Ve eventos asistidos y clubes a los que pertenece
4. Consulta milestones recientes
5. Accede a galería de fotos de eventos

## Pantallas y Funcionalidades

### Pantalla de Login
- Campos: Email, Contraseña
- Opciones de autenticación social (Google, Facebook)
- Link a registro y recuperación de contraseña
- Validación de credenciales contra backend
- Manejo de error E1

### Pantalla de Dashboard Principal
- Hero section con mensaje personalizado
- Sección Perfect Matches con scroll horizontal
- Tarjetas de usuario con avatar, nombre, intereses
- Botones de acción (Say Hello)
- Sección University Pulse con timeline de actividades

### Pantalla de Parchas
- Vista de parchas activas con filtros por categoría
- Card de cada parcha con:
  - Imagen representativa
  - Nombre y descripción
  - Número de miembros
  - Botón para unirse
- Opción para crear nueva parcha
- Vista detallada de parcha seleccionada

### Pantalla de Perfil
- Header del perfil con avatar y nombre
- Sección de Social Progress con barra de XP
- Estadísticas: Eventos, Clubes, Grupos
- Milestones recientes
- Galería de fotos
- Chat flotante "Need a little boost?"

## Diseño y Sistema de Colores

La aplicación utiliza un sistema de diseño coherente basado en:

### Paleta Principal
- Primary (Rosa/Magenta): #E83E8C utilizado en botones, enlaces y elementos interactivos
- Secondary (Naranja): #FF6B35 para énfasis y gradientes
- Gradiente Principal: De rosa a naranja para botones y secciones destacadas

### Tipografía
- Fuente principal: Sistema de fuentes del dispositivo (sans-serif)
- Tamaños: Escalables según responsive breakpoints
- Pesos: Regular (400), Medium (500), Bold (700)

### Componentes Reutilizables
- Botones con estados (default, hover, active, disabled)
- Cards con sombras y bordes redondeados
- Input fields con validación visual
- Badges para categorías e indicadores
- Avatares circulares para perfiles

## Módulos de Backend Utilizados

Para cada funcionalidad principal, el frontend se conecta con módulos backend específicos:

- Autenticación: Módulo Auth (JWT, OAuth2)
- Gestión de usuarios: Módulo User (Perfil, preferencias, búsqueda)
- Gestión de Parchas: Módulo Parche (CRUD, membresía)
- Mensajería: Módulo Chat (Mensajes directos, chat bot)
- Social: Módulo Social (Conexiones, progreso, milestones)

## Pruebas Funcionales

Todas las funcionalidades han sido probadas siguiendo los escenarios definidos:

1. Test de autenticación: Login correcto, login fallido, logout
2. Test de descubrimiento: Carga de Perfect Matches, filtrado
3. Test de parchas: Crear, unirse, listar, eliminar
4. Test de perfil: Carga de datos, actualización, galería
5. Test de mensajería: Envío de mensajes, notificaciones
6. Test de errores: Validación de flujos E1, E2, E3

## Ejecución del Proyecto

### Requisitos Previos
- Node.js 16+
- npm o yarn
- Variables de entorno configuradas (.env)

### Instalación
```bash
npm install
```

### Variables de Entorno
Crear archivo `.env` con:
```
VITE_API_URL=http://localhost:8080/api
VITE_GOOGLE_CLIENT_ID=your_google_client_id
VITE_FACEBOOK_APP_ID=your_facebook_app_id
```

### Desarrollo
```bash
npm run dev
```
La aplicación se abre en `http://localhost:5173`

### Build para Producción
```bash
npm run build
```

### Linting y Formato
```bash
npm run lint
npm run format
```

## CI/CD Pipeline

El proyecto implementa dos pipelines en GitHub Actions:

### Pipeline de Desarrollo
- Se ejecuta en cada push a rama `develop`
- Instalación de dependencias
- Linting y validación de código
- Ejecución de pruebas unitarias
- Build de desarrollo

### Pipeline de Producción
- Se ejecuta en cada push a rama `main`
- Todos los pasos anteriores
- Build optimizado
- Deploy a Azure App Service
- Verificación de despliegue

## Documentación de Código

Cada componente, servicio y función contiene documentación inline:

```typescript
/**
 * Componente PerfectMatches
 * 
 * Renderiza una lista de estudiantes recomendados basada en intereses
 * y energía compartida del usuario actual.
 * 
 * Props:
 * - onConnect: Callback cuando usuario hace click en "Say Hello"
 * - limit: Número máximo de tarjetas a mostrar (default: 10)
 * 
 * Estado:
 * - matches: Array de usuarios recomendados
 * - loading: Indicador de carga de datos
 * - error: Mensaje de error si existe
 */
export function PerfectMatches({ onConnect, limit = 10 }: Props) {
  // Implementación...
}
```

## Conexiones con Servicios Externos

La aplicación se integra con servicios externos para:

- Google OAuth: Autenticación con cuenta Google
- Facebook Login: Autenticación con cuenta Facebook
- Backend API: Todas las operaciones CRUD
- Chat Bot: API de conversación para soporte

## Evidencia de Despliegue

El proyecto está configurado para despliegue continuo:

- Link de demostración en Azure: [Link del despliegue]
- CI/CD con GitHub Actions validando cada cambio
- Dos pipelines: desarrollo y producción

## Licencia

Este proyecto es parte del curso de Ingeniería de Software - Escuela de Ingeniería.