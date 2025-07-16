# 🏗️ **ДЕТАЛЬНЫЙ ПЛАН РЕАЛИЗАЦИИ WMS-СИСТЕМЫ**
## *На базе Django (DRF) + PostgreSQL + React (Berry MUI)*

---

## 🎯 **0. Архитектурные принципы и фундамент**

### 0.1 **Выбор архитектурного подхода**
```
📋 Сервис-ориентированный монолит на Django
├── Bounded Contexts реализуются как Django-приложения в `src/apps/`
├── Бизнес-логика инкапсулируется в сервисном слое (`services.py`)
├── "Тонкие" контроллеры (DRF Class-Based Views) для обработки HTTP
├── Четкое разделение слоев: Presentation (API) -> Application (Services) -> Domain (Models)
└── Hexagonal Architecture для изоляции инфраструктурных зависимостей (например, внешние API)
```

### 0.2 **Технологический стек**
```yaml
Backend:
  - Python 3.12+
  - Django 5.1.4+
  - Django REST Framework (DRF)
  - Poetry для управления зависимостями
  - Gunicorn + Uvicorn для ASGI
  - Celery 5+ и Redis для фоновых задач
  - Pytest, factory-boy для тестирования

Frontend:
  - React 18+ с TypeScript
  - Vite для сборки
  - Berry (MUI v5) — купленный шаблон
  - React Router v6 для навигации
  - Zustand или Redux Toolkit для управления состоянием
  - Axios для HTTP-запросов
  - React Hook Form + Zod для форм и валидации

Infrastructure:
  - PostgreSQL 17.5+
  - Redis (для Celery и кеширования)
  - GitLab CI/CD (или GitHub Actions)
  - Docker + Docker Compose
  - Nginx для reverse proxy
```

### 0.3 **Структура Backend-проекта (целевая)**
```
the_best_wms_backend/
├── src/
│   ├── apps/
│   │   ├── users/            # Аутентификация, профили, должности, права (Приоритет 1)
│   │   ├── inventory/        # Управление запасами, продуктами, складами (Приоритет 2)
│   │   ├── inbound/          # Приемка товаров (ASN, PO) (Приоритет 3)
│   │   ├── outbound/         # Сборка и отгрузка (SO) (Приоритет 4)
│   │   ├── training/         # Обучение и аттестация персонала (Приоритет 5)
│   │   ├── reports/          # Отчетность и аналитика
│   │   └── .../              # Остальные блоки
│   ├── settings/
│   │   ├── asgi.py
│   │   ├── celery.py
│   │   ├── urls.py           # Основной роут с маршрутами к /admin и /api/1.0
│   │   ├── urls_admin.py     # Маршруты для /admin
│   │   ├── urls_api_v1.py    # Маршруты для /api/v1/
│   │   ├── wsgi.py
│   │   ├── yasg.py           # Маршруты для swagger и redoc
│   │   └── settings/         # Файлы настроек (base, development, production)
│   ├── static/
│   ├── templates/            # Кастомные шаблоны для админ-панели
│   └── manage.py
├── .pre-commit-config.yaml   # Конфигурация pre-commit (black, isort, ruff)
├── docker-compose.yml
├── Dockerfile
└── pyproject.toml            # Зависимости и конфигурация проекта (Poetry)
```
---
## **1. 📝 ПЛАН РАЗРАБОТКИ БЭКЕНДА (MVP)**

### **Шаг 1.1: Инициализация и настройка проекта**
- **Задача:** Создать структуру проекта, настроить Poetry, Django, DRF и инструменты качества кода.
- **Действия:**
    1.  `poetry init` для создания `pyproject.toml`.
    2.  Добавить зависимости: `django`, `djangorestframework`, `psycopg2-binary`, `gunicorn`, `uvicorn`, `python-dotenv`.
    3.  Добавить dev-зависимости: `black`, `isort`, `ruff`, `pre-commit`.
    4.  `django-admin startproject settings src`. Переместить `manage.py` в корень.
    5.  Создать структуру директорий `src/apps`, `src/settings`.
    6.  Настроить `settings/` на три файла: `base.py`, `development.py`, `production.py` с использованием `python-dotenv` для секретов.
    7.  Настроить `pre-commit` с `black`, `isort`, `ruff`.

### **Шаг 1.2: Пользователи и авторизация (Приоритет 1)**
- **Модуль:** `src/apps/users/`
- **Модели (`models.py`):**
    - `Position`: Справочник должностей (название, иерархия `parent = models.ForeignKey('self', ...)`).
    - `User(AbstractUser)`: Расширенная модель пользователя (добавить `position = models.ForeignKey(Position, ...)`).
    - `OneTimePassword(OTP)`: Модель для одноразовых паролей
        - `user`: ForeignKey к `User`
        - `code`: 6-значный код
        - `expires_at`: `DateTimeField`
        - `attempts_left`: `PositiveSmallIntegerField` (e.g., default 3)
        - `last_failed_attempt_at`: `DateTimeField` (nullable)
- **Сервисы (`services.py`):**
    - `AuthService`:
        - Логика генерации/валидации JWT.
        - `register_user(...)`: Регистрация нового пользователя.
        - `request_password_recovery(email)`: Создает и отправляет OTP.
        - `confirm_password_recovery(otp, new_password)`: Проверяет OTP и сбрасывает пароль.
        - `change_password(user, old_password, new_password)`: Смена пароля для авторизованного пользователя.
    - `UserService`: CRUD для пользователей и должностей.
- **API (DRF `views.py` и `serializers.py`):**
    - **Auth:**
        - `POST /api/v1/auth/register/`
        - `POST /api/v1/auth/login/`
        - `POST /api/v1/auth/logout/`
        - `POST /api/v1/auth/password/change/`
        - `POST /api/v1/auth/password/recovery/`
        - `POST /api/v1/auth/password/recovery/confirm/`
    - **Users:**
        - `GET /api/v1/users/me/`
        - `GET, POST /api/v1/users/` (Список и создание)
        - `GET, PUT, PATCH, DELETE /api/v1/users/{id}/` (CRUD для пользователя)
    - **Positions:**
        - `GET, POST /api/v1/positions/` (Список и создание)
        - `GET, PUT, PATCH, DELETE /api/v1/positions/{id}/` (CRUD для должности)
- **Тесты:** Написать тесты для сервисов и API-эндпоинтов.

### **Шаг 1.3: Управление запасами (Приоритет 2)**
- **Модуль:** `src/apps/inventory/`
- **Модели (`models.py`):**
    - `Warehouse`: Склад (название, адрес).
    - `StorageZone`: Зона хранения внутри склада (e.g., "A-1").
    - `StorageLocation`: Ячейка хранения (e.g., "A-1-01").
    - `Product`: Товар/SKU (название, артикул, описание).
    - `StockItem`: Единица запаса (ссылка на `Product`, `StorageLocation`, количество, LOT, дата годности).
- **Сервисы (`services.py`):**
    - `InventoryService`: Логика для получения остатков, перемещения товара между ячейками, списания.
- **API (`views.py`):**
    - **Products:**
        - `GET, POST /api/v1/inventory/products/`
        - `GET, PUT, PATCH, DELETE /api/v1/inventory/products/{id}/`
    - **Stock:**
        - `GET /api/v1/inventory/stock/` (Агрегированные данные)
    - **Transfers:**
        - `POST /api/v1/inventory/transfer/` (Внутреннее перемещение)
- **Тесты:** Покрыть тестами логику расчета остатков и перемещений.

### **Шаг 1.4: Поступление товаров (Приоритет 3)**
- **Модуль:** `src/apps/inbound/`
- **Модели (`models.py`):**
    - `PurchaseOrder (PO)` / `AdvancedShippingNotice (ASN)`: Ожидаемая поставка (поставщик, ожидаемая дата).
    - `InboundShipment`: Фактическая приемка (ссылка на PO/ASN, дата приемки).
    - `InboundShipmentItem`: Позиция в приемке (ссылка на `Product`, принятое количество).
- **Сервисы (`services.py`):**
    - `InboundService`: Обработка приемки. При подтверждении создает `StockItem` в `inventory`.
- **API (`views.py`):**
    - **ASNs:**
        - `GET, POST /api/v1/inbound/asns/`
        - `GET, PUT, PATCH, DELETE /api/v1/inbound/asns/{id}/`
    - **Shipments:**
        - `POST /api/v1/inbound/shipments/{id}/confirm/`
- **Тесты:** Ключевой тест — корректное создание `StockItem` после подтверждения приемки.

### **Шаг 1.5: Реализация и отгрузка (Приоритет 4)**
- **Модуль:** `src/apps/outbound/`
- **Модели (`models.py`):**
    - `SalesOrder (SO)`: Заказ клиента.
    - `PickingList`: Задание на сборку (ссылка на `SO`).
    - `PickingListItem`: Позиция для сборки (ссылка на `Product`, ячейка, количество).
    - `OutboundShipment`: Отгрузка.
- **Сервисы (`services.py`):**
    - `AllocationService`: Сервис аллокации — создает `PickingList` из `SO` на основе остатков и стратегий (FIFO/FEFO).
    - `OutboundService`: Обработка сборки и отгрузки (списывает `StockItem` из `inventory`).
- **API (`views.py`):**
    - **Orders:**
        - `GET, POST /api/v1/outbound/orders/`
        - `GET, PUT, PATCH, DELETE /api/v1/outbound/orders/{id}/`
        - `POST /api/v1/outbound/orders/{id}/allocate/`
    - **Picking:**
        - `GET /api/v1/outbound/picking/{id}/`
        - `POST /api/v1/outbound/picking/{id}/confirm/`
- **Тесты:** Проверить корректность списания остатков при отгрузке.

### **Шаг 1.6: Модуль обучения персонала (Приоритет 5)**
- **Модуль:** `src/apps/training/`
- **Модели (`models.py`):**
    - `Article`: Статья/новость (заголовок, контент, автор).
    - `ArticleMeta`: Просмотры и лайки (`OneToOneField` к `Article`, `views_count`, `likes_count`).
    - `UserArticleRelation`: Лайкнул/просмотрел ли конкретный юзер (`User`, `Article`, `liked`, `viewed`).
    - `TrainingPlan`: Учебный план (название).
    - `TrainingPlanItem`: Элемент плана (ссылка на `Article`, `TrainingPlan`, порядок).
    - `Roadmap`: Дорожная карта для должности (`OneToOneField` к `users.Position`, `training_plan`).
    - `Assessment`: Аттестация (название, ссылка на `TrainingPlan`).
    - `AssessmentResult`: Результат аттестации (`user`, `assessment`, `score`, дата).
- **Сервисы (`services.py`):**
    - `TrainingService`: Логика по работе со статьями (лайки, просмотры), планами, дорожными картами.
    - `AssessmentService`: Логика проведения и оценки аттестаций.
- **API (`views.py`):**
    - **Articles:**
        - `GET, POST /api/v1/training/articles/`
        - `GET, PUT, PATCH, DELETE /api/v1/training/articles/{id}/`
        - `POST /api/v1/training/articles/{id}/like/`
    - **Roadmaps:**
        - `GET /api/v1/training/roadmaps/my/`
    - **Assessments:**
        - `GET, POST /api/v1/training/assessments/`
        - `GET, PUT, PATCH, DELETE /api/v1/training/assessments/{id}/`
        - `GET /api/v1/training/assessments/{id}/results/`

---
## **2. 📝 ПЛАН РАЗРАБОТКИ ФРОНТЕНДА (MVP)**

### **Шаг 2.1: Инициализация и настройка проекта**
- **Задача:** Адаптировать шаблон Berry для работы с Django-бэкендом.
- **Действия:**
    1. Настроить `vite.config.mts` для проксирования запросов вида `/api/v1/*` на бэкенд (`http://localhost:8000/api/v1/`).
    2. Создать файл `.env` для хранения URL бэкенда (`VITE_API_URL=/api/v1`).
    3. Настроить `axios`: создать инстанс с `baseURL` из `.env` и `interceptors` для управления JWT.
    4. Настроить `Zustand`: создать `store` для `user`, `isAuthenticated`, `tokens`.

### **Шаг 2.2: Аутентификация и основной Layout (Приоритет 1)**
- **Задача:** Реализовать регистрацию, вход, выход, сброс пароля и защищенные роуты.
- **Компоненты (`views/`):**
    - `pages/authentication/Login.tsx`: Форма входа. Вызывает `POST /auth/login/`.
    - `pages/authentication/Register.tsx`: Форма регистрации. Вызывает `POST /auth/register/`.
    - `pages/authentication/ForgotPassword.tsx`: Форма запроса OTP. Вызывает `POST /auth/password/recovery/`.
    - `pages/authentication/ResetPassword.tsx`: Форма ввода OTP и нового пароля. Вызывает `POST /auth/password/recovery/confirm/`.
    - `pages/profile/Settings.tsx`: Страница профиля пользователя. Включает форму для смены пароля, вызывающую `POST /auth/password/change/`.
- **Роутинг (`routes/`):**
    - `AuthGuard`: Компонент-обертка, проверяет `isAuthenticated` в `store`, иначе редирект на `/login`.
    - `MainRoutes.tsx`: Защищенные роуты, обернутые в `AuthGuard`.
    - `LoginRoutes.tsx`: Публичные роуты для аутентификации.
- **Layout (`layout/`):**
    - `MainLayout.tsx`: Получает данные пользователя из `store` и отображает в хэдере. Реализует кнопку "Выход" (`POST /auth/logout/`).

### **Шаг 2.3: Управление запасами (Приоритет 2)**
- **Задача:** Отобразить данные по товарам и остаткам, реализовать CRUD.
- **Компоненты (`views/inventory/`):**
    - `ProductList.tsx`: Таблица с товарами (`GET /inventory/products/`). Включает пагинацию, поиск, кнопки для создания/редактирования.
    - `ProductForm.tsx`: Форма для создания/редактирования товара (`POST /inventory/products/`, `PUT /inventory/products/{id}/`).
    - `StockOverview.tsx`: Дэшборд с остатками (`GET /inventory/stock/`) в виде карточек и графиков.
- **Роутинг и навигация:** Добавить роуты в `MainRoutes.tsx` и ссылки в `menu-items/`.

### **Шаг 2.4: Поступление товаров (Приоритет 3)**
- **Задача:** Создать интерфейс для управления приемкой.
- **Компоненты (`views/inbound/`):**
    - `ASNList.tsx`: Таблица ожидаемых поставок (`GET /inbound/asns/`).
    - `ASNForm.tsx`: Форма для создания/редактирования ASN (`POST /inbound/asns/`, `PUT /inbound/asns/{id}/`).
    - `ASNDetail.tsx`: Страница просмотра ASN (`GET /inbound/asns/{id}/`). Содержит логику для подтверждения приемки (`POST /inbound/shipments/{id}/confirm/`).
- **Роутинг и навигация:** Аналогично предыдущему шагу.

### **Шаг 2.5: Реализация и отгрузка (Приоритет 4)**
- **Задача:** Создать интерфейс для управления заказами и сборкой.
- **Компоненты (`views/outbound/`):**
    - `OrderList.tsx`: Таблица заказов клиентов (`GET /outbound/orders/`).
    - `OrderForm.tsx`: Форма для создания/редактирования заказа (`POST /outbound/orders/`, `PUT /outbound/orders/{id}/`).
    - `OrderDetail.tsx`: Детальная страница заказа (`GET /outbound/orders/{id}/`) с кнопкой "На сборку" (`POST /outbound/orders/{id}/allocate/`).
    - `PickingList.tsx`: Интерфейс для сборщика, показывающий, что и где собирать (`GET /outbound/picking/{id}/`).
- **Роутинг и навигация:** Аналогично предыдущему шагу.

### **Шаг 2.6: Модуль обучения персонала (Приоритет 5)**
- **Задача:** Создать интерфейсы для обучения и аттестации.
- **Компоненты (`views/training/`):**
    - `ArticleFeed.tsx`: Лента статей (`GET /training/articles/`) с лайками (`POST /training/articles/{id}/like/`).
    - `ArticleDetail.tsx`: Просмотр статьи (`GET /training/articles/{id}/`).
    - `MyRoadmap.tsx`: Визуализация персонального плана обучения (`GET /training/roadmaps/my/`).
    - `AssessmentPage.tsx`: Страница прохождения аттестации (`GET /training/assessments/{id}/`).
    - `AssessmentResults.tsx`: Отчет о результатах (`GET /training/assessments/{id}/results/`).
- **Админка (`views/admin/training/`):**
    - Компоненты для CRUD должностей, планов обучения, статей и аттестаций.
- **Роутинг и навигация:** Добавить новый раздел "Обучение" в `menu-items`.

---
## **3. 🐳 CI/CD и DevOps**

### 3.1 **Dockerfile**
- **Задача:** Создать `Dockerfile` для production-сборки Django-приложения.
- **Структура:**
    - Использовать multi-stage build.
    - **Stage 1 (`builder`):** Установить `poetry`, скопировать `pyproject.toml` и `poetry.lock`, установить зависимости `poetry install --no-dev`.
    - **Stage 2 (`runtime`):** Скопировать `site-packages` из `builder`, скопировать исходный код `src`, создать пользователя без прав `root`, запустить `gunicorn`.

### 3.2 **Docker Compose**
- **Задача:** Настроить `docker-compose.yml` для локальной разработки.
- **Сервисы:**
    - `db`: PostgreSQL 17.
    - `redis`: Redis 7.
    - `backend`: Сборка из `Dockerfile`, монтирование `src` для hot-reload, запуск `manage.py runserver`.
    - `frontend`: Сборка из `the_best_wms_front/Dockerfile` (нужно будет создать), запуск `vite`.
    - `nginx`: Reverse-proxy, который будет направлять запросы `/api/*` на `backend`, а остальные на `frontend`.

### 3.3 **GitLab CI/CD**
- **Задача:** Адаптировать `.gitlab-ci.yml` из первоначального плана.
- **Изменения:**
    - **`validate` stage:** Заменить `ruff`, `black`, `mypy` на команды, запускаемые через `poetry run`.
    - **`test` stage:** Настроить `pytest` для работы с БД в CI.
    - **`build` stage:** Сборка backend-образа (и frontend-образа, если он будет в отдельном контейнере).
    - **`deploy` stage:** Остается без изменений, если деплой идет через Helm в Kubernetes.