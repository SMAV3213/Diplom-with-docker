# 🏨 Baikal Breeze - Resort Booking System

[![TypeScript](https://img.shields.io/badge/TypeScript-5.9+-blue?logo=typescript)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-19.2+-61dafb?logo=react)](https://react.dev/)
[![.NET](https://img.shields.io/badge/.NET-10.0+-512bd4?logo=dotnet)](https://dotnet.microsoft.com/)
[![Docker](https://img.shields.io/badge/Docker-Latest-2496ed?logo=docker)](https://www.docker.com/)

> Современная система бронирования номеров отеля "Baikal Breeze" с полной поддержкой адаптивного дизайна, JWT аутентификацией и админ-панелью.

## ✨ Основные возможности

### 🔐 Аутентификация
- ✅ Регистрация и вход по почте
- ✅ JWT токены (access + refresh)
- ✅ Защита маршрутов с ролями (User, Admin)
- ✅ Безопасное хранение паролей (bcrypt)

### 🛏️ Управление номерами
- ✅ Просмотр доступных номеров
- ✅ Фильтрация по цене, удобствам, количеству мест
- ✅ Детальная информация о номере с галереей
- ✅ Проверка доступности на конкретные даты

### 📅 Система бронирования
- ✅ Бронирование номеров на нужные даты
- ✅ Проверка пересечений дат
- ✅ История бронирований пользователя
- ✅ Отмена и изменение бронирований

### 👨‍💼 Админ-панель
- ✅ Управление номерами (добавление, редактирование, удаление)
- ✅ Управление типами номеров
- ✅ Просмотр всех бронирований
- ✅ Статистика и отчеты

### 🌙 Интерфейс
- ✅ Light/Dark mode
- ✅ Адаптивный дизайн (mobile-first)
- ✅ Smooth animations
- ✅ Accessibility (WCAG 2.1 AA)

---

## 🛠 Технологический стек

### Frontend
| Технология | Версия | Назначение |
|-----------|--------|-----------|
| React | 19.2+ | UI фреймворк |
| TypeScript | 5.9+ | Типизация |
| Vite | 7.2+ | Сборка |
| React Router | 7.12+ | Маршрутизация |
| SCSS | 1.97+ | Стилизация |
| Axios | 1.13+ | HTTP запросы |
| Headless UI | Latest | Accessible компоненты |
| clsx | 2.1+ | Условные классы |

### Backend
| Технология | Версия | Назначение |
|-----------|--------|-----------|
| .NET | 10.0+ | Фреймворк |
| Entity Framework | 8.0+ | ORM |
| MSSQL (SQL Server) | 2022+ | База данных |
| JWT | Latest | Аутентификация |
| FluentValidation | Latest | Валидация |
| AutoMapper | Latest | Маппинг данных |

### DevOps
| Технология | Назначение |
|-----------|-----------|
| Docker | Контейнеризация |
| Docker Compose | Оркестрация контейнеров |
| Nginx | Web сервер (frontend) |
| MSSQL (SQL Server) | Функциональная БД |

---

## 📋 Требования

### Минимальные требования

```bash
# Frontend
Node.js >= 18.0.0
npm >= 9.0.0

# Backend
.NET 10.0 SDK
MSSQL (SQL Server) 2022+

# DevOps
Docker >= 20.10
Docker Compose >= 2.0
```

### Рекомендуемое окружение
- **OS:** Windows 10+, macOS 11+, Ubuntu 20.04+
- **RAM:** 8GB (4GB minimum)
- **Disk:** 5GB свободного места

---

## 🚀 Быстрый старт

### 1️⃣ Клонирование репозитория

```bash
git clone --recurse-submodules https://github.com/SMAV3213/Diplom-with-docker.git
cd Diplom-with-docker
```

### 2️⃣ Локальная разработка (без Docker)

#### Frontend
```bash
cd frontend

# Установка зависимостей
npm install

# Запуск dev сервера (localhost:5173)
npm run dev

# Production build
npm run build

# Preview production build
npm run preview

# Линтинг
npm run lint
```

#### Backend
```bash
cd backend

# Восстановление зависимостей
dotnet restore

# Запуск миграций БД
dotnet ef database update

# Запуск (localhost:5000)
dotnet run
```

### 3️⃣ Docker Compose (рекомендуется для production)

```bash
# Simple setup (все сервисы)
docker-compose -f docker-compose.simple.yml up -d

# Development
docker-compose -f docker-compose.dev.yml up -d

# Production
docker-compose -f docker-compose.prod.yml up -d

# Просмотр логов
docker-compose logs -f

# Остановка контейнеров
docker-compose down
```

**Доступ после запуска:**
- Frontend: http://localhost:3000 (или :80)
- Backend API: http://localhost:5000 (или :8080)
- MSSQL (SQL Server): localhost:1433 (dev password в .env)

---

## 📂 Структура проекта

```
baikal-breeze/
│
├── 📄 README.md                    # Этот файл
├── 📄 docker-compose.yml          # Production compose
├── 📄 docker-compose.dev.yml      # Development compose
├── 📄 docker-compose.simple.yml   # Simple compose
│
├── 📁 frontend/
│   ├── 📄 package.json            # Dependencies
│   ├── 📄 tsconfig.json           # TypeScript config
│   ├── 📄 vite.config.ts          # Vite config
│   ├── 📄 eslint.config.js        # ESLint config
│   │
│   ├── 📁 src/
│   │   ├── 📄 main.tsx            # Entry point
│   │   ├── 📄 App.tsx             # Root component
│   │   │
│   │   ├── 📁 api/                # API calls
│   │   ├── 📁 auth/               # Auth context & providers
│   │   ├── 📁 components/         # Reusable components
│   │   │   ├── Header/            # Header with burger menu
│   │   │   ├── Footer/            # Footer component
│   │   │   ├── Hero/              # Hero section
│   │   │   ├── TypeCard/          # Room type card
│   │   │   ├── TypeList/          # Room type list
│   │   │   ├── TypeInfo/          # Room details modal
│   │   │   └── Layout/            # Main layout wrapper
│   │   │
│   │   ├── 📁 pages/              # Page components
│   │   │   ├── Home/              # Homepage
│   │   │   ├── Auth/              # Login/Register
│   │   │   ├── Profile/           # User profile
│   │   │   ├── Admin/             # Admin panel
│   │   │   └── AboutUs/           # About page
│   │   │
│   │   ├── 📁 styles/             # Global styles
│   │   │   ├── global.scss
│   │   │   ├── responsive.scss
│   │   │   ├── theme.scss
│   │   │   └── _variables.scss
│   │   │
│   │   ├── 📁 theme/              # Theme provider
│   │   ├── 📁 types/              # TypeScript types
│   │   ├── 📁 utils/              # Helper functions
│   │   ├── 📁 shared/             # Shared utilities
│   │   └── 📁 routes/             # Route definitions
│   │
│   ├── 📁 public/                 # Static files
│   └── 📄 Dockerfile              # Frontend container
│
├── 📁 backend/
│   ├── 📄 ResortBooking.sln       # Solution file
│   │
│   ├── 📁 ResortBooking.API/
│   │   ├── 📄 Program.cs          # App setup
│   │   ├── 📄 appsettings.json    # Config
│   │   │
│   │   ├── 📁 Controllers/        # API endpoints
│   │   │   ├── AuthController.cs
│   │   │   ├── BookingController.cs
│   │   │   ├── RoomController.cs
│   │   │   ├── RoomTypesController.cs
│   │   │   └── UserController.cs
│   │   │
│   │   ├── 📁 Filters/            # JWT auth filter
│   │   └── 📄 Dockerfile          # Backend container
│   │
│   ├── 📁 ResortBooking.Application/
│   │   ├── 📁 DTOs/               # Data transfer objects
│   │   ├── 📁 Services/           # Business logic
│   │   ├── 📁 Validators/         # FluentValidation
│   │   ├── 📁 Interfaces/         # Service contracts
│   │   └── 📁 Responses/          # API responses
│   │
│   ├── 📁 ResortBooking.Domain/
│   │   ├── 📁 Entities/           # Domain models
│   │   └── 📁 Enums/              # Enumerations
│   │
│   ├── 📁 ResortBooking.Infrastructure/
│   │   ├── 📁 Data/               # DbContext
│   │   ├── 📁 Migrations/         # EF migrations
│   │   ├── 📁 Persistence/        # Database config
│   │   ├── 📁 Repositories/       # Data access
│   │   └── 📁 Services/           # Infrastructure services
│   │
│   └── 📄 Dockerfile              # Backend container
│
└── 📁 docs/
    ├── RESPONSIVE_DESIGN.md       # Design guide
    ├── API.md                     # API documentation
    └── DEPLOYMENT.md              # Deployment guide
```

---

## 🔌 API Документация

### Base URL
```
Development:  http://localhost:5000
Production:   https://api.example.com
```

### Аутентификация (JWT)

#### Register
```http
POST /api/auth/register
Content-Type: application/json

{
  "login": "username",
  "email": "user@example.com",
  "password": "SecurePassword123!"
}

Response: 201 Created
{
  "success": true,
  "data": {
    "id": "user-id",
    "login": "username",
    "email": "user@example.com"
  }
}
```

#### Login
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "SecurePassword123!"
}

Response: 200 OK
{
  "success": true,
  "data": {
    "accessToken": "eyJ...",
    "refreshToken": "eyJ...",
    "user": { "id": "...", "login": "...", "email": "..." }
  }
}
```

### Номера

#### Get all rooms
```http
GET /api/rooms?page=1&pageSize=20
Authorization: Bearer {accessToken}

Response: 200 OK
{
  "success": true,
  "data": {
    "items": [ /* Room objects */ ],
    "totalCount": 42,
    "page": 1,
    "pageSize": 20
  }
}
```

#### Get room details
```http
GET /api/rooms/{id}
Authorization: Bearer {accessToken}

Response: 200 OK
{
  "success": true,
  "data": { /* Room object */ }
}
```

### Бронирования

#### Create booking
```http
POST /api/bookings
Authorization: Bearer {accessToken}
Content-Type: application/json

{
  "roomId": "room-id",
  "checkInDate": "2024-03-15",
  "checkOutDate": "2024-03-18",
  "guestCount": 2
}

Response: 201 Created
```

#### Get my bookings
```http
GET /api/bookings/my
Authorization: Bearer {accessToken}

Response: 200 OK
{
  "success": true,
  "data": [ /* Booking objects */ ]
}
```

### Admin endpoints

#### Create room
```http
POST /api/admin/rooms
Authorization: Bearer {adminToken}
Content-Type: application/json

{
  "name": "Deluxe Suite",
  "description": "...",
  "roomTypeId": "type-id",
  "pricePerNight": 150.00
}
```

#### Update room
```http
PUT /api/admin/rooms/{id}
Authorization: Bearer {adminToken}
```

#### Delete room
```http
DELETE /api/admin/rooms/{id}
Authorization: Bearer {adminToken}
```

Полная API документация: [docs/API.md](./docs/API.md)

---

## 🎨 Features & Components

### Frontend Components

#### Header
- Responsive navigation
- Burger menu на мобильных
- Смена темы (Light/Dark)
- Пользовательское меню

#### Hero Section
- Large call-to-action
- Search form
- Animated gradient background

#### Room Cards
- Image gallery
- Price display
- Amenities badges
- Quick details

#### Type Info Modal
- Full room details
- Image carousel
- Amenities list
- Booking button

#### Admin Panel
- Room management
- Booking management
- User management
- Statistics

---

## 🎯 Адаптивный дизайн

### Breakpoints
```scss
$bp-sm: 520px    // Small mobile
$bp-md: 760px    // Tablet
$bp-lg: 980px    // Desktop
$bp-xl: 1200px   // Large desktop
```

### Mobile-first approach
- Base styles для мобильных
- Enhancements на больших экранах
- Всё работает на 375px и выше
- Touch-friendly интерфейс (44px+ targets)

---

## 🔒 Безопасность

- ✅ JWT токены для аутентификации
- ✅ Refresh token rotation
- ✅ CORS protection
- ✅ Input validation (FluentValidation)
- ✅ SQL injection prevention (Entity Framework)
- ✅ Password hashing (bcrypt)
- ✅ HTTPS support в production

---

## 🧪 Тестирование

```bash
# Frontend linting
cd frontend && npm run lint

# Build проверка
npm run build

# Preview production
npm run preview

# Backend tests (если есть)
cd backend && dotnet test
```

---

## 🚢 Deployment

### Docker Deployment (Recommended)

```bash
# Production build
docker-compose -f docker-compose.prod.yml build

# Run production
docker-compose -f docker-compose.prod.yml up -d

# View logs
docker-compose logs -f

# Остановка
docker-compose down
```

### Manual Deployment

**Frontend:**
1. `npm run build` → создает `/dist` папку
2. Загрузить `/dist` на Nginx/Apache
3. Настроить routing для SPA

**Backend:**
1. `dotnet publish -c Release`
2. Загрузить на сервер
3. Запустить как systemd service или в IIS

Подробнее: [docs/DEPLOYMENT.md](./docs/DEPLOYMENT.md)

---

## 📊 Environment Variables

### Frontend (.env)
```bash
VITE_API_URL=http://localhost:5000
VITE_APP_NAME=Baikal Breeze
```

### Backend (appsettings.json)
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost,1433;Database=BaikalBreeze;User Id=sa;Password=Your_password123;"
  },
  "Jwt": {
    "Key": "your-secret-key",
    "Issuer": "baikal-breeze",
    "Audience": "baikal-breeze-users"
  }
}
```

---

## 🐛 Troubleshooting

### Frontend issues

**Port already in use**
```bash
# Kill process on port 5173
npx kill-port 5173

# Or use different port
npm run dev -- --port 3000
```

**Dependencies conflict**
```bash
rm -rf node_modules package-lock.json
npm install
```

### Backend issues

**Database connection failed**
```bash
# Check MSSQL (SQL Server) is running
# Verify connection string in appsettings.json
# Run migrations again
dotnet ef database update
```

**Port conflict**
```bash
# Change port in Program.cs
app.Urls.Add("http://localhost:5001");
```

---

## 📝 License

MIT License - see [LICENSE](LICENSE) file for details

---

## 🤝 Contributing

Contributions welcome! Please:

1. Fork репозиторий
2. Создайте feature branch (`git checkout -b feature/amazing-feature`)
3. Commit изменения (`git commit -m 'Add amazing feature'`)
4. Push в branch (`git push origin feature/amazing-feature`)
5. Откройте Pull Request

### Code Style
- Frontend: ESLint + Prettier
- Backend: .NET style guidelines
- Commit messages: Conventional Commits

---

## 👥 Authors

- **Владислав** - Full Stack Developer
  - Frontend: React, TypeScript, SCSS
  - Backend: .NET, MSSQL (SQL Server), EF Core
  - DevOps: Docker, Docker Compose

---

---

## 🙏 Acknowledgments

- [Headless UI](https://headlessui.com/) - Accessible components
- [Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/) - ORM
- [React Router](https://reactrouter.com/) - Routing
- [Vite](https://vitejs.dev/) - Build tool

---

**Last Updated:** March 1, 2026  
**Version:** 2.1.0  
**Status:** Production Ready ✅

---

*Made with ❤️ for Resort Booking*



