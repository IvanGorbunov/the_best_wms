# 📋 **ОГЛАВЛЕНИЕ**

<!-- START TOC -->
## **ОСНОВНЫЕ РАЗДЕЛЫ**

### 🎯 **[0. Архитектурные принципы и фундамент](#0-архитектурные-принципы-и-фундамент)**
- [0.1 Выбор архитектурного подхода](#01-выбор-архитектурного-подхода)
- [0.2 Технологический стек](#02-технологический-стек)
- [0.3 Структура Backend-проекта](#03-структура-backend-проекта-целевая)

### 🔧 **[1. План разработки БЭКЕНДА (MVP)](#1-план-разработки-бэкенда-mvp)**
- [1.1 Инициализация и настройка проекта](#шаг-11-инициализация-и-настройка-проекта)
- [1.2 Пользователи и авторизация](#шаг-12-пользователи-и-авторизация-приоритет-1)
- [1.3 Управление запасами](#шаг-13-управление-запасами-приоритет-2)
- [1.4 Поступление товаров](#шаг-14-поступление-товаров-приоритет-3)
- [1.5 Реализация и отгрузка](#шаг-15-реализация-и-отгрузка-приоритет-4)
- [1.6 Модуль обучения персонала](#шаг-16-модуль-обучения-персонала-приоритет-5)
- [1.7 Волновое планирование](#шаг-17-волновое-планирование-приоритет-6)
- [1.8 Продвинутые стратегии размещения](#шаг-18-продвинутые-стратегии-размещения-enhancement-for-inventory)
- [1.9 Кросс-докинг](#шаг-19-кросс-докинг-приоритет-7)
- [1.10 Real-time аналитика](#шаг-110-real-time-аналитика-приоритет-8)
- [1.11 AI/ML Integration](#шаг-111-aiml-integration-приоритет-9)
- [1.12 IoT Integration](#шаг-112-iot-integration-приоритет-10)
- [1.13 Real-time уведомления](#шаг-113-real-time-уведомления-приоритет-11)
- [1.14 Отчетность и статистика](#шаг-114-отчетность-и-статистика-reports-module)

### 🎨 **[2. План разработки ФРОНТЕНДА (MVP)](#2-план-разработки-фронтенда-mvp)**
- [2.1 Инициализация и настройка проекта](#шаг-21-инициализация-и-настройка-проекта)
- [2.2 Аутентификация и основной Layout](#шаг-22-аутентификация-и-основной-layout-приоритет-1)
- [2.3 Управление запасами (Frontend)](#шаг-23-управление-запасами-приоритет-2)
- [2.4 Поступление товаров (Frontend)](#шаг-24-поступление-товаров-приоритет-3)
- [2.5 Реализация и отгрузка (Frontend)](#шаг-25-реализация-и-отгрузка-приоритет-4)
- [2.6 Модуль обучения персонала (Frontend)](#шаг-26-модуль-обучения-персонала-приоритет-5)
- [2.7 Волновое планирование (Frontend)](#шаг-27-волновое-планирование-frontend)
- [2.8 Кросс-докинг (Frontend)](#шаг-28-кросс-докинг-frontend)
- [2.9 Real-time Analytics (Frontend)](#шаг-29-real-time-analytics-frontend)
- [2.10 Mobile-First Approach](#шаг-210-mobile-first-approach)

### 🎨 **[3. План разработки ДИЗАЙНА](#3-план-разработки-дизайна)**
- [3.1 Design System и UI Kit](#31-design-system-и-ui-kit)
- [3.2 UX Research и User Journey](#32-ux-research-и-user-journey)
- [3.3 Adaptive Design](#33-adaptive-design-mobile-first)
- [3.4 Real-time UI Components](#34-real-time-ui-components)

### 🔄 **[4. SSE-архитектура для Real-time обновлений](#4-sse-архитектура-для-real-time-обновлений)**
- [4.1 Архитектура SSE](#41-архитектура-sse)
- [4.2 Реализация SSE в Django](#42-реализация-sse-в-django)
- [4.3 Frontend интеграция с SSE](#43-frontend-интеграция-с-sse)
- [4.4 Event-driven архитектура](#44-event-driven-архитектура)

### 🏗️ **[5. Dependency Injection Pattern](#5-dependency-injection-pattern)**
- [5.1 Принципы применения DI](#51-принципы-применения-di)
- [5.2 Конфигурация DI контейнера](#52-конфигурация-di-контейнера)
- [5.3 Интеграции с внешними сервисами](#53-интеграции-с-внешними-сервисами)

### 🐳 **[6. CI/CD и DevOps](#6-cicd-и-devops)**
- [6.1 Dockerfile](#61-dockerfile)
- [6.2 Docker Compose](#62-docker-compose)
- [6.3 GitLab CI/CD](#63-gitlab-cicd)

### 🚀 **[7. Современные API и интеграции](#7-современные-api-и-интеграции)**
- [7.1 Enhanced API Design](#71-enhanced-api-design)
- [7.2 API Versioning и Backward Compatibility](#72-api-versioning-и-backward-compatibility)

### 🛡️ **[8. Безопасность и Compliance](#8-безопасность-и-compliance)**
- [8.1 Enhanced Security](#81-enhanced-security)
- [8.2 Compliance & Audit](#82-compliance--audit)

### ☁️ **[9. Cloud-Native технологии](#9-cloud-native-технологии)**
- [9.1 Kubernetes Deployment](#91-kubernetes-deployment)
- [9.2 Monitoring & Observability](#92-monitoring--observability)
- [9.3 CI/CD Pipeline Enhancement](#93-cicd-pipeline-enhancement)
- [9.4 Performance Optimization](#94-performance-optimization)

<!-- END TOC -->

---

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
  - Server-Sent Events (SSE) для real-time updates
  - Pandas, NumPy для data analytics
  - Scikit-learn, TensorFlow для ML
  - MQTT для IoT device communication

Frontend:
  - React 18+ с TypeScript
  - Vite для сборки
  - Berry (MUI v5) — купленный шаблон
  - React Router v6 для навигации
  - Zustand или Redux Toolkit для управления состоянием
  - Axios для HTTP-запросов
  - React Hook Form + Zod для форм и валидации
  - Progressive Web App (PWA) поддержка
  - EventSource API для SSE connections

Infrastructure:
  - PostgreSQL 17.5+
  - Redis (для Celery, кеширования и pub/sub)
  - GitLab CI/CD (или GitHub Actions)
  - Docker + Docker Compose
  - Kubernetes для продуктивной среды
  - Nginx для reverse proxy
  - Prometheus + Grafana для мониторинга
  - ELK Stack (Elasticsearch, Logstash, Kibana) для логирования

Security & Auth:
  - OAuth 2.0 + PKCE для secure authentication
  - JWT с refresh tokens
  - Role-based access control (RBAC)
  - API rate limiting
  - Data encryption at rest и in transit

Analytics & ML:
  - Time-series database для metrics
  - Real-time analytics engine
  - Machine Learning pipeline для predictive analytics
  - Business Intelligence dashboard
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
│   │   ├── wave_planning/    # Волновое планирование (Приоритет 6)
│   │   ├── cross_docking/    # Кросс-докинг операции (Приоритет 7)
│   │   ├── analytics/        # Real-time аналитика и KPI (Приоритет 8)
│   │   ├── ml/              # Machine Learning сервисы (Приоритет 9)
│   │   ├── iot/             # IoT интеграция и устройства (Приоритет 10)
│   │   ├── notifications/    # Real-time уведомления (Приоритет 11)
│   │   └── reports/          # Отчетность и статистика
│   ├── utils/                # Общие утилиты и middleware
│   │   ├── middleware/       # Кастомные middleware
│   │   ├── permissions/      # Система разрешений
│   │   ├── validators/       # Валидаторы
│   │   ├── serializers/      # Базовые сериализаторы
│   │   ├── exceptions/       # Кастомные исключения
│   │   └── helpers/         # Вспомогательные функции
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
├── k8s/                      # Kubernetes манифесты
├── .github/workflows/        # GitHub Actions CI/CD
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
- **Описание:** Users & Auth Module (Пользователи и авторизация) — обеспечивает аутентификацию, регистрацию, RBAC и одноразовые пароли (OTP) для восстановления доступа.

#### 📌 **Что делает модуль пользователей?**
Обеспечивает аутентификацию, регистрацию, RBAC и одноразовые пароли (OTP) для восстановления доступа.

#### 🔧 **Задачи модуля**
- **Управление учетными записями.**
- **Восстановление паролей через OTP.**
- **Авторизация через JWT.**
- **RBAC: доступ по ролям и позициям.**

#### 🧠 **Архитектурные паттерны**
- **Service Layer** — вся логика инкапсулирована.
- **Factory** — генерация OTP.
- **Strategy** — смена пароля, восстановление, регистрация.
- **Policy** — проверка разрешений (permissions).

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

#### 💡 **Пример использования:**
1. Новый сотрудник регистрируется.
2. Админ присваивает ему позицию "Сборщик".
3. Он входит в систему, может видеть только свои задачи.

#### 🏁 **Результаты и выгоды**
- Безопасный доступ к системе.
- Централизованное управление пользователями.
- Гибкая система прав (per warehouse, per role).

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
- **Описание:** Inbound Module (Поступление товаров) — оркестрирует процесс приемки поставок от момента получения ASN до размещения товаров на складе.

#### 📌 **Что делает inbound-модуль?**
Оркестрирует процесс приемки поставок от момента получения ASN до размещения товаров на складе.

#### 🔧 **Задачи модуля**
- **Обработка ASN и PO.**
- **Приемка по факту (инспекция, сканирование).**
- **Создание записей остатков (StockItem).**
- **Автоматическая аллокация на ячейки хранения.**

#### 🧠 **Архитектурные паттерны**
- **Workflow** — цепочка: ASN → Shipment → Stock.
- **Builder** — построение приемки по ASN.
- **Command** — действия: confirm, reject, accept partial.
- **Observer** — уведомление inventory об изменении.

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

#### 💡 **Пример использования:**
1. Менеджер вводит ASN на 100 единиц SKU.
2. В день поставки создается InboundShipment.
3. Приемщик сканирует 98 штук, создается StockItem и фиксируется отклонение.

#### 🏁 **Результаты и выгоды**
- Быстрая приемка с проверками.
- Точное отражение остатков.
- Автоматическое размещение без бумажных накладных.

- **Тесты:** Ключевой тест — корректное создание `StockItem` после подтверждения приемки.

### **Шаг 1.5: Реализация и отгрузка (Приоритет 4)**
- **Модуль:** `src/apps/outbound/`
- **Описание:** Outbound Module (Сборка и отгрузка) — обеспечивает полную обработку заказов клиентов от получения до формирования отгрузки, включая подбор и списание.

#### 📌 **Что делает outbound-модуль?**
Обеспечивает полную обработку заказов клиентов от получения до формирования отгрузки, включая подбор и списание.

#### 🔧 **Задачи модуля**
- **Получение и хранение заказов (Sales Orders).**
- **Аллокация на основе стратегии (FIFO/FEFO).**
- **Формирование PickingList с оптимальными маршрутами.**
- **Подтверждение сборки и создание отгрузки.**

#### 🧠 **Архитектурные паттерны**
- **Strategy** — выбор стратегии аллокации.
- **Command** — действия: allocate, confirm pick, ship.
- **Builder** — формирование picking lists.
- **Workflow** — SO → Picking → Shipment.

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

#### 💡 **Пример использования:**
1. Клиент оформляет заказ на 5 SKU.
2. AllocationService создает задание на сборку.
3. После сканирования все позиции считаются подобранными.
4. OutboundService формирует отгрузку и списывает StockItem.

#### 🏁 **Результаты и выгоды**
- Точный и быстрый процесс сборки.
- Оптимизация маршрутов по складу.
- Контроль выполнения по каждому заказу.

- **Тесты:** Проверить корректность списания остатков при отгрузке.

### **Шаг 1.6: Модуль обучения персонала (Приоритет 5)**
- **Модуль:** `src/apps/training/`
- **Описание:** Training Module (Обучение и аттестация персонала) — обеспечивает персонализированное обучение сотрудников склада через статьи, планы, дорожные карты и аттестации.

#### 📌 **Что делает модуль обучения?**
Обеспечивает персонализированное обучение сотрудников склада через статьи, планы, дорожные карты и аттестации.

#### 🔧 **Задачи модуля**
- **Обучение по ролям и позициям (roadmaps).**
- **Хранение и распространение обучающих материалов.**
- **Проведение и оценка аттестаций.**
- **Отслеживание прогресса пользователей.**

#### 🧠 **Архитектурные паттерны**
- **Composite** — дерево статей → планы → roadmap.
- **Observer** — фиксация просмотров и лайков.
- **State** — прогресс пользователя.
- **Strategy** — шаблоны аттестаций.

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

#### 💡 **Пример использования:**
1. Новому кладовщику назначается roadmap.
2. Он изучает материалы, лайкает статьи, проходит аттестацию.
3. Результаты фиксируются, HR получает отчет.

#### 🏁 **Результаты и выгоды**
- Быстрое введение новых сотрудников.
- Повышение качества операций.
- Снижение ошибок при сборке и приемке.

- **Тесты:** Тестирование системы обучения, tracking прогресса и оценки аттестаций.

### **Шаг 1.7: Волновое планирование (Приоритет 6)**
- **Модуль:** `src/apps/wave_planning/`
- **Описание:** Wave Planning Module (модуль волнового планирования) — это подсистема в WMS, отвечающая за группировку заказов на отгрузку в "волны" (waves), чтобы эффективно организовать и оптимизировать процессы подбора, упаковки и отгрузки товаров на складе.

#### 📌 **Что такое "волна"?**
Волна (wave) — это пакет заказов, сгруппированных по определённым критериям (время отгрузки, клиент, зона склада, тип товара и т.д.), которые будут обрабатываться одновременно или по единому сценарию.

#### 🔧 **Задачи модуля волнового планирования**
- **Группировка заказов:**
    - По расписанию (например, все заказы до 12:00).
    - По приоритету (VIP/обычные).
    - По маршруту или транспортному средству.
    - По зоне склада или типу хранения.
- **Оптимизация подбора (picking):**
    - Минимизация пробега (кластеризация по маршрутам).
    - Выбор метода подбора (batch, zone, wave, cluster picking).
    - Назначение задач сотрудникам/роботам.
- **Контроль готовности:**
    - Проверка наличия товара перед запуском волны.
    - Зарезервировать товар под волну.
    - Подготовить задания перемещения/пополнения.
- **Мониторинг выполнения:**
    - Трекинг выполнения задач по волне.
    - SLA по волне.
    - Отчеты по эффективности (время сборки, ошибки и т.д.).

#### 🧠 **Используемые паттерны (архитектурно)**
- **Builder** — построение волны из набора заказов.
- **Strategy** — разные стратегии волнового планирования.
- **Observer** — реакция на события (например, заказ готов → включить в волну).
- **Command** — отдельные операции в процессе волны (подбор, упаковка и т.д.).

- **Модели (`models.py`):**
    - `Wave`: Основная модель волны (статус, тип, время создания/релиза).
    - `WaveTemplate`: Шаблон волны с правилами группировки.
    - `WaveRule`: Правила для автоматического создания волн.
    - `WaveOrder`: Связь между волной и заказами.
    - `WaveTask`: Задачи в рамках волны (picking, packing).
    - `WaveMetrics`: Метрики производительности волны.

- **Сервисы (`services.py`):**
    - `WaveCreationService`: Создание и конфигурация волн.
    - `WaveOptimizationService`: Оптимизация маршрутов и группировки.
    - `WaveExecutionService`: Управление выполнением волны.
    - `WaveMetricsService`: Сбор и анализ метрик.

- **API (`views.py` и `serializers.py`):**
    - **Waves:**
        - `GET, POST /api/v1/waves/`
        - `GET, PUT, PATCH, DELETE /api/v1/waves/{id}/`
        - `POST /api/v1/waves/{id}/release/`
        - `POST /api/v1/waves/{id}/cancel/`
        - `GET /api/v1/waves/{id}/metrics/`
    - **Wave Templates:**
        - `GET, POST /api/v1/wave-templates/`
        - `GET, PUT, PATCH, DELETE /api/v1/wave-templates/{id}/`
    - **Wave Optimization:**
        - `POST /api/v1/waves/optimize/`
        - `GET /api/v1/waves/{id}/routing/`

#### 💡 **Пример использования:**
1. В 10:00 система запускает планировщик волны.
2. Выбираются все заказы на доставку до 14:00.
3. Эти заказы объединяются в одну "волну".
4. Генерируются задания на подбор (сортированы по зонам).
5. Назначаются сотрудники, печатаются задания и этикетки.
6. После завершения сборки волна закрывается и отправляется на упаковку.

#### 🏁 **Результаты и выгоды**
- Снижение времени обработки заказов.
- Предсказуемость и масштабируемость.
- Повышение эффективности персонала.
- Гибкость для приоритетных клиентов/товаров.

- **Тесты:** Тестирование алгоритмов оптимизации, создания волн и метрик производительности.

### **Шаг 1.8: Продвинутые стратегии размещения (Enhancement for Inventory)**
- **Модуль:** Расширение `src/apps/inventory/`
- **Описание:** Advanced Inventory Strategies (Inventory Enhancements) — расширение базового инвентаря для поддержки продвинутых стратегий размещения, перемещений, replenishment и анализа оборачиваемости.

#### 📌 **Что это за модуль?**
Расширение базового инвентаря для поддержки продвинутых стратегий размещения, перемещений, replenishment и анализа оборачиваемости.

#### 🔧 **Задачи модуля**
- **Аллокация: выборка партий по FEFO/FIFO/LIFO.**
- **Слоттинг: динамическое размещение товаров.**
- **Скоростной анализ: классификация ABC, прогнозы.**
- **Автоматические рекомендации по пополнению.**

#### 🧠 **Архитектурные паттерны**
- **Strategy** — выбор стратегии размещения.
- **Rules Engine** — пользовательские правила.
- **Analyzer** — velocity и ABC-анализ.
- **Scheduler** — фоновые задачи пополнения.

- **Новые сервисы в `inventory/services.py`:**
    - `AllocationOptimizationService`: 
        - FIFO/FEFO/LIFO стратегии с настраиваемыми правилами
        - Zone-based allocation для оптимизации маршрутов
        - Multi-criteria optimization (расстояние, приоритет, вместимость)
    - `SlottingOptimizationService`:
        - Dynamic slotting на основе анализа скорости оборота
        - ABC analysis для категоризации товаров
        - Automated replenishment suggestions
    - `VelocityAnalysisService`:
        - Анализ скорости движения товаров
        - Seasonal pattern recognition
        - Demand forecasting integration

- **Новые модели:**
    - `AllocationRule`: Правила размещения товаров
    - `SlottingRule`: Правила оптимизации слотов
    - `VelocityMetrics`: Метрики скорости оборота товаров

- **Новые API эндпоинты:**
    - `POST /api/v1/inventory/optimize-allocation/`
    - `POST /api/v1/inventory/optimize-slotting/`
    - `GET /api/v1/inventory/velocity-analysis/`
    - `POST /api/v1/inventory/replenishment-suggestions/`

#### 💡 **Пример использования:**
1. При приходе нового товара система определяет оптимальный слот.
2. Если скорость оборота высокая — размещается ближе к выходу.
3. Старые партии — обрабатываются по FEFO.

#### 🏁 **Результаты и выгоды**
- Снижение ошибок и времени на подбор.
- Повышение эффективности размещения.
- Минимизация просрочек и затрат на ручное пополнение.

- **Тесты:** Тестирование алгоритмов аллокации, слоттинга и velocity анализа.

### **Шаг 1.9: Кросс-докинг (Приоритет 7)**
- **Модуль:** `src/apps/cross_docking/`
- **Описание:** Cross-Docking Module (Модуль кросс-докинга) — подсистема в WMS для операций, при которых товары поступают на склад и практически сразу перенаправляются на отгрузку, минуя этап хранения.

#### 📌 **Что такое кросс-докинг?**
Кросс-докинг — логистическая операция, при которой товары поступают на склад и практически сразу перенаправляются на отгрузку, минуя этап хранения.

#### 🔧 **Задачи модуля**
- **Планирование прибытия и отгрузки транспорта.**
- **Сопоставление inbound и outbound заказов.**
- **Оптимизация использования доков.**
- **Создание и исполнение задач на перемещение без хранения.**

#### 🧠 **Архитектурные паттерны**
- **Scheduler** — планирование временных окон.
- **Rule Engine** — сопоставление входящих и исходящих потоков.
- **Workflow** — последовательная оркестрация задач.
- **Observer** — реагирование на появление транспорта.

- **Модели (`models.py`):**
    - `CrossDockingOrder`: Заказ на кросс-докинг операцию
    - `DockDoor`: Модель доковых ворот (inbound/outbound)
    - `Appointment`: Записи на прием/отгрузку транспорта
    - `CrossDockingTask`: Задачи по перемещению товаров
    - `DockSchedule`: Расписание использования доков

- **Сервисы (`services.py`):**
    - `AppointmentSchedulingService`: Планирование записей транспорта
    - `CrossDockingExecutionService`: Управление операциями кросс-докинга
    - `DockOptimizationService`: Оптимизация использования доков

- **API (`views.py`):**
    - **Cross-docking Orders:**
        - `GET, POST /api/v1/cross-docking/orders/`
        - `GET, PUT, PATCH, DELETE /api/v1/cross-docking/orders/{id}/`
    - **Appointments:**
        - `GET, POST /api/v1/cross-docking/appointments/`
        - `GET, PUT, PATCH, DELETE /api/v1/cross-docking/appointments/{id}/`
    - **Dock Management:**
        - `GET /api/v1/cross-docking/docks/`
        - `GET /api/v1/cross-docking/docks/{id}/schedule/`

#### 💡 **Пример использования:**
1. Поставщик бронирует слот на доставку.
2. Система определяет соответствующий outbound заказ.
3. Формируется задача перемещения от дока к зоне отгрузки.
4. Заказ отгружается в течение 30 минут с момента прибытия.

#### 🏁 **Результаты и выгоды**
- Снижение потребности в хранении.
- Ускорение товарооборота.
- Повышение пропускной способности склада.

- **Тесты:** Тестирование алгоритмов сопоставления заказов, планирования доков и оптимизации временных окон.

### **Шаг 1.10: Real-time аналитика (Приоритет 8)**
- **Модуль:** `src/apps/analytics/`
- **Описание:** Analytics Module (Real-Time Аналитика) — подсистема для отслеживания ключевых KPI, генерации отчетов и формирования алертов для принятия решений в реальном времени.

#### 📌 **Что такое аналитика WMS?**
Аналитика позволяет в реальном времени отслеживать ключевые KPI, генерировать отчеты и формировать алерты для принятия решений.

#### 🔧 **Задачи модуля**
- **Сбор метрик в реальном времени.**
- **Расчет KPI и построение дашбордов.**
- **Уведомления при отклонениях от норм.**
- **Генерация отчетов по производительности.**

#### 🧠 **Архитектурные паттерны**
- **CQRS + Event Sourcing** — метрики как event stream.
- **Observer** — события → алерты.
- **Pipeline** — обработка данных.
- **DashboardBuilder** — визуализация.

- **Модели (`models.py`):**
    - `KPI`: Ключевые показатели эффективности
    - `Dashboard`: Настраиваемые дашборды
    - `Alert`: Система уведомлений о критических событиях
    - `MetricSnapshot`: Снимки метрик в реальном времени
    - `PerformanceReport`: Отчеты о производительности

- **Сервисы (`services.py`):**
    - `RealTimeAnalyticsService`: Обработка данных в реальном времени
    - `KPIService`: Расчет и мониторинг KPI
    - `AlertService`: Система уведомлений
    - `ReportGenerationService`: Генерация отчетов

- **Ключевые метрики:**
    - Order fulfillment rate (целевой: >99%)
    - Average picking time per order
    - Inventory accuracy (целевой: >99.5%)
    - Dock-to-stock time для inbound
    - Perfect order rate
    - Labor productivity metrics

- **API (`views.py`):**
    - **Analytics:**
        - `GET /api/v1/analytics/real-time/`
        - `GET /api/v1/analytics/kpi/`
        - `POST /api/v1/analytics/alerts/`
    - **Dashboards:**
        - `GET, POST /api/v1/analytics/dashboards/`
        - `GET, PUT, PATCH, DELETE /api/v1/analytics/dashboards/{id}/`
    - **Reports:**
        - `GET /api/v1/analytics/reports/`
        - `POST /api/v1/analytics/reports/generate/`

#### 💡 **Пример использования:**
1. В процессе сборки отслеживается время выполнения каждой задачи.
2. При снижении productivity ниже 80% создается alert.
3. Менеджер получает уведомление и может оперативно перераспределить ресурсы.

#### 🏁 **Результаты и выгоды**
- Повышение прозрачности работы склада.
- Прогнозирование проблем до их появления.
- Мониторинг SLA и операционных узких мест.

- **Тесты:** Тестирование алгоритмов сбора метрик, расчета KPI и системы алертов.

### **Шаг 1.11: AI/ML Integration (Приоритет 9)**
- **Модуль:** `src/apps/ml/`
- **Описание:** ML Module (AI/ML интеграция) — модуль отвечает за прогнозирование спроса, обнаружение аномалий, предиктивное обслуживание и оптимизацию цен с использованием машинного обучения.

#### 📌 **Что делает ML модуль?**
Модуль отвечает за прогнозирование спроса, обнаружение аномалий, предиктивное обслуживание и оптимизацию цен.

#### 🔧 **Задачи модуля**
- **Прогнозирование спроса (на основе истории и внешних факторов).**
- **Предиктивное ТО оборудования.**
- **Выявление аномалий (ошибки размещения, пики).**
- **Оптимизация ценообразования в реальном времени.**

#### 🧠 **Архитектурные паттерны**
- **Pipeline** — обучение и инференс моделей.
- **Strategy** — разные типы ML-моделей.
- **Observer** — запуск по событию.
- **Repository** — управление метаданными моделей.

- **Модели (`models.py`):**
    - `MLModel`: Метаданные ML моделей
    - `Prediction`: Результаты прогнозирования
    - `TrainingJob`: Задачи обучения моделей
    - `FeatureStore`: Хранилище признаков для ML

- **Сервисы (`services.py`):**
    - `DemandForecastingService`: Прогнозирование спроса
    - `PredictiveMaintenanceService`: Predictive maintenance для оборудования
    - `AnomalyDetectionService`: Обнаружение аномалий в inventory
    - `PricingOptimizationService`: Dynamic pricing recommendations

- **ML Pipeline:**
    - Data preprocessing и feature engineering
    - Model training и validation
    - Model deployment и monitoring
    - A/B testing для ML models

- **API (`views.py`):**
    - **ML Models:**
        - `GET /api/v1/ml/models/`
        - `POST /api/v1/ml/models/{id}/predict/`
        - `POST /api/v1/ml/models/{id}/train/`
    - **Predictions:**
        - `GET /api/v1/ml/predictions/`
        - `GET /api/v1/ml/demand-forecast/`
        - `GET /api/v1/ml/anomalies/`

#### 💡 **Пример использования:**
1. Модель прогнозирует, что SKU#123 потребуется в 2 раза больше через неделю.
2. Генерируется рекомендация на пополнение.
3. Пользователь подтверждает заказ у поставщика.

#### 🏁 **Результаты и выгоды**
- Минимизация out-of-stock.
- Снижение затрат на хранение.
- Обнаружение ошибок до их проявления.

- **Тесты:** Тестирование accuracy ML моделей, pipeline обучения и системы прогнозирования.

### **Шаг 1.12: IoT Integration (Приоритет 10)**
- **Модуль:** `src/apps/iot/`
- **Описание:** IoT Module (Интеграция IoT устройств) — подключает сенсоры, RFID, BLE-метки и прочие устройства для автоматического отслеживания состояния склада и активов.

#### 📌 **Что делает IoT модуль?**
Подключает сенсоры, RFID, BLE-метки и прочие устройства для автоматического отслеживания состояния склада и активов.

#### 🔧 **Задачи модуля**
- **Сбор и хранение данных с сенсоров.**
- **Отслеживание активов (например, тележек).**
- **Реагирование на условия окружающей среды (температура, движение).**
- **Интеграция с MQTT-брокером и edge-вычислениями.**

#### 🧠 **Архитектурные паттерны**
- **Observer** — сенсор → событие.
- **Rules Engine** — реагирование на условия.
- **Pub/Sub** — обмен событиями через Redis.
- **Edge Pattern** — локальная обработка.

- **Модели (`models.py`):**
    - `IoTDevice`: Устройства IoT (sensors, RFID readers, etc.)
    - `SensorReading`: Показания сенсоров
    - `DeviceStatus`: Статус устройств
    - `IoTRule`: Правила обработки IoT данных

- **Сервисы (`services.py`):**
    - `IoTDeviceService`: Управление IoT устройствами
    - `SensorDataService`: Обработка данных сенсоров
    - `AssetTrackingService`: Отслеживание активов через RFID/BLE

- **IoT Capabilities:**
    - MQTT broker для device communication
    - Edge computing для local processing
    - Sensor integration (temperature, humidity, motion)
    - RFID/BLE tracking для asset monitoring

- **API (`views.py`):**
    - **IoT Devices:**
        - `GET, POST /api/v1/iot/devices/`
        - `GET, PUT, PATCH, DELETE /api/v1/iot/devices/{id}/`
    - **Sensor Data:**
        - `GET /api/v1/iot/sensors/readings/`
        - `POST /api/v1/iot/sensors/data/`
    - **Asset Tracking:**
        - `GET /api/v1/iot/assets/track/`
        - `POST /api/v1/iot/assets/locate/`

#### 💡 **Пример использования:**
1. Сенсор температуры на складе передает значение 18°C.
2. Срабатывает правило → предупреждение, если ниже 16°C.
3. Сотрудник получает push-уведомление.

#### 🏁 **Результаты и выгоды**
- Снижение человеческих ошибок.
- Реакция на реальные условия в моменте.
- Повышение безопасности и контроль активов.

- **Тесты:** Тестирование обработки IoT данных, rule engine и системы уведомлений.

### **Шаг 1.13: Real-time уведомления (Приоритет 11)**
- **Модуль:** `src/apps/notifications/`
- **Описание:** Notifications Module (Real-time уведомления) — обеспечивает информирование пользователей о событиях системы в реальном времени через SSE, email и push-уведомления.

#### 📌 **Что делает модуль уведомлений?**
Обеспечивает информирование пользователей о событиях системы в реальном времени через SSE, email и push-уведомления.

#### 🔧 **Задачи модуля**
- **Доставка уведомлений по событиям (создание заказа, ошибка, алерт).**
- **Поддержка каналов: SSE, email, push, SMS.**
- **Управление предпочтениями пользователей.**

#### 🧠 **Архитектурные паттерны**
- **Observer** — события генерируют уведомления.
- **Pub/Sub** — Redis используется как шина сообщений.
- **Strategy** — разные каналы доставки.
- **Template Method** — генерация сообщений.

- **Модели (`models.py`):**
    - `Notification`: Уведомления для пользователей
    - `NotificationTemplate`: Шаблоны уведомлений
    - `NotificationChannel`: Каналы доставки (email, push, SMS)
    - `UserPreferences`: Настройки пользователей

- **Сервисы (`services.py`):**
    - `NotificationService`: Отправка уведомлений
    - `SSEService`: Real-time updates через Server-Sent Events
    - `EmailService`: Email уведомления
    - `PushNotificationService`: Push уведомления для mobile

- **Technologies:**
    - Server-Sent Events (SSE) для real-time updates
    - Redis pub/sub для message broadcasting
    - EventSource API на клиенте для SSE connections

- **API (`views.py`):**
    - **Notifications:**
        - `GET /api/v1/notifications/`
        - `POST /api/v1/notifications/{id}/mark-read/`
        - `GET /api/v1/notifications/unread-count/`
    - **SSE endpoints:**
        - `GET /api/v1/stream/notifications/{user_id}/`
        - `GET /api/v1/stream/updates/{topic}/`

#### 💡 **Пример использования:**
1. Пользователь запускает волну.
2. Когда задача выполнена, приходит уведомление.
3. SSE соединение отображает это сразу на экране.

#### 🏁 **Результаты и выгоды**
- Повышенная прозрачность происходящего.
- Мгновенная реакция на события.
- Персонализированная доставка информации.

- **Тесты:** Тестирование SSE connections, delivery channels и user preferences.

### **Шаг 1.14: Отчетность и статистика (Reports Module)**
- **Модуль:** `src/apps/reports/`
- **Описание:** Reports Module (Отчетность и статистика) — формирует статистические и операционные отчеты по ключевым процессам склада.

#### 📌 **Что делает модуль отчетов?**
Формирует статистические и операционные отчеты по ключевым процессам склада.

#### 🔧 **Задачи модуля**
- **Генерация PDF/Excel отчетов.**
- **Сбор агрегированных данных по заказам, остаткам, операциям.**
- **Экспорт по расписанию или запросу.**

#### 🧠 **Архитектурные паттерны**
- **Builder** — создание отчетов.
- **Template Method** — разные типы отчетов (stock, performance).
- **Scheduler** — плановые отчеты.

- **Модели (`models.py`):**
    - `ReportTemplate`: Шаблоны отчетов (название, тип, параметры).
    - `ReportJob`: Задания на генерацию отчетов (статус, время создания/выполнения).
    - `GeneratedReport`: Сохраненные отчеты (ссылка на файл, дата создания).
    - `ReportSchedule`: Расписание автоматической генерации отчетов.

- **Сервисы (`services.py`):**
    - `ReportGenerationService`: Основная логика генерации отчетов.
    - `ReportExportService`: Экспорт в различные форматы (PDF, Excel, CSV).
    - `ReportSchedulerService`: Управление плановыми отчетами.
    - `ReportDataAggregationService`: Сбор и агрегация данных для отчетов.

- **API (`views.py`):**
    - **Reports:**
        - `GET, POST /api/v1/reports/templates/`
        - `GET, PUT, PATCH, DELETE /api/v1/reports/templates/{id}/`
        - `POST /api/v1/reports/generate/`
        - `GET /api/v1/reports/history/`
        - `GET /api/v1/reports/{id}/download/`
    - **Scheduled Reports:**
        - `GET, POST /api/v1/reports/schedules/`
        - `GET, PUT, PATCH, DELETE /api/v1/reports/schedules/{id}/`

#### 💡 **Пример использования:**
1. В конце дня запускается генерация отчета по приемке.
2. Менеджер получает PDF с деталями всех входящих партий.
3. История сохраняется в системе.

#### 🏁 **Результаты и выгоды**
- Поддержка внутренних и внешних аудитов.
- Снижение ручной отчетности.
- Возможность визуального контроля за SLA.

- **Тесты:** Тестирование генерации отчетов, экспорта в различные форматы и планового выполнения.

---
## **2. 📝 ПЛАН РАЗРАБОТКИ ФРОНТЕНДА (MVP)**

### **Шаг 2.1: Инициализация и настройка проекта**
- **Задача:** Адаптировать шаблон Berry для работы с Django-бэкендом и SSE интеграцией.
- **Действия:**
    1. Настроить `vite.config.mts` для проксирования запросов вида `/api/v1/*` на бэкенд (`http://localhost:8000/api/v1/`).
    2. Создать файл `.env` для хранения URL бэкенда (`VITE_API_URL=/api/v1`, `VITE_SSE_URL=/api/v1/sse`).
    3. Настроить `axios`: создать инстанс с `baseURL` из `.env` и `interceptors` для управления JWT.
    4. Настроить `Zustand`: создать `store` для `user`, `isAuthenticated`, `tokens`, `real-time state`.
    5. Установить зависимости для PWA: `vite-plugin-pwa`, `workbox-window`.
    6. Настроить Service Worker для offline capabilities.
    7. Добавить TypeScript конфигурацию для строгой типизации.

#### 🎯 **Современная архитектура Frontend**
```typescript
// src/store/useAppStore.ts - Centralized state management
interface AppState {
  user: User | null;
  isAuthenticated: boolean;
  tokens: TokenPair | null;
  realTimeData: {
    inventory: InventoryUpdate[];
    orders: OrderUpdate[];
    notifications: Notification[];
  };
  ui: {
    theme: 'light' | 'dark';
    sidebarCollapsed: boolean;
    activeModule: string;
  };
}

// src/hooks/useSSE.ts - Server-Sent Events integration
export const useSSE = (endpoint: string) => {
  // SSE connection management with automatic reconnection
};

// src/utils/api.ts - HTTP client with interceptors
const apiClient = axios.create({
  baseURL: import.meta.env.VITE_API_URL,
  timeout: 10000,
});
```

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

### **Шаг 2.7: Волновое планирование (Frontend)**
- **Задача:** Создать интерфейс для управления волнами.
- **Компоненты (`views/wave-planning/`):**
    - `WaveList.tsx`: Таблица волн (`GET /waves/`) с фильтрами по статусу и времени.
    - `WaveForm.tsx`: Форма создания/редактирования волны (`POST /waves/`, `PUT /waves/{id}/`).
    - `WaveDetail.tsx`: Детальная страница волны с метриками и задачами.
    - `WaveOptimization.tsx`: Интерфейс оптимизации волн (`POST /waves/optimize/`).
    - `WaveTemplates.tsx`: Управление шаблонами волн.

### **Шаг 2.8: Кросс-докинг (Frontend)**
- **Задача:** Создать интерфейс для кросс-докинг операций.
- **Компоненты (`views/cross-docking/`):**
    - `CrossDockingDashboard.tsx`: Дашборд кросс-докинг операций.
    - `AppointmentScheduler.tsx`: Планировщик записей транспорта.
    - `DockManagement.tsx`: Управление доковыми воротами.

### **Шаг 2.9: Real-time Analytics (Frontend)**
- **Задача:** Создать интерактивные дашборды и отчеты.
- **Компоненты (`views/analytics/`):**
    - `RealTimeDashboard.tsx`: Real-time метрики с SSE обновлениями.
    - `KPIDashboard.tsx`: Ключевые показатели эффективности.
    - `CustomDashboard.tsx`: Настраиваемые дашборды пользователей.
    - `AlertCenter.tsx`: Центр уведомлений и алертов.

### **Шаг 2.10: Mobile-First Approach**
- **Задача:** Обеспечить мобильную совместимость и PWA функциональность для операций на складе.

#### 📱 **Progressive Web App (PWA) Implementation**
```typescript
// vite.config.ts - PWA configuration
import { VitePWA } from 'vite-plugin-pwa';

export default defineConfig({
  plugins: [
    VitePWA({
      registerType: 'autoUpdate',
      includeAssets: ['favicon.ico', 'apple-touch-icon.png'],
      manifest: {
        name: 'WMS System',
        short_name: 'WMS',
        description: 'Warehouse Management System',
        theme_color: '#1976d2',
        icons: [
          {
            src: 'pwa-192x192.png',
            sizes: '192x192',
            type: 'image/png'
          }
        ]
      },
      workbox: {
        globPatterns: ['**/*.{js,css,html,ico,png,svg}'],
        runtimeCaching: [
          {
            urlPattern: /^https:\/\/api\./,
            handler: 'NetworkFirst',
            options: {
              cacheName: 'api-cache',
              cacheableResponse: {
                statuses: [0, 200]
              }
            }
          }
        ]
      }
    })
  ]
});
```

#### 🔧 **Offline-First Architecture**
- **Service Worker Strategy:**
  - Critical operations (picking, receiving) работают offline
  - Data synchronization при восстановлении соединения
  - Background sync для отложенных операций

#### 📷 **Barcode/QR Scanning Integration**
```typescript
// src/components/MobileScanner.tsx
import { Html5QrcodeScanner } from 'html5-qrcode';

export const MobileScanner: React.FC = () => {
  const [scanResult, setScanResult] = useState<string>('');
  
  const onScanSuccess = (decodedText: string) => {
    // Handle successful scan
    setScanResult(decodedText);
    // Auto-lookup product/location info
    lookupScannedItem(decodedText);
  };

  // Integration with picking workflow
  return (
    <div className="scanner-container">
      <Html5QrcodeScanner
        qrCodeSuccessCallback={onScanSuccess}
        qrCodeErrorCallback={onScanError}
      />
    </div>
  );
};
```

#### 🎤 **Voice Picking Support**
```typescript
// src/hooks/useVoiceCommands.ts
export const useVoiceCommands = () => {
  const recognition = new (window as any).webkitSpeechRecognition();
  
  const commands = {
    'confirm': () => confirmCurrentAction(),
    'skip': () => skipCurrentItem(),
    'quantity [number]': (number: string) => setQuantity(parseInt(number)),
    'location [code]': (code: string) => navigateToLocation(code)
  };

  return { startListening, stopListening, isListening };
};
```

#### 📲 **Mobile-Optimized Components**
- **Touch-Friendly Interface:**
  - Minimum 44px touch targets
  - Swipe gestures for navigation
  - Pull-to-refresh functionality
  - Haptic feedback for confirmations

- **Adaptive UI Patterns:**
  - Bottom sheet для modal dialogs
  - Tab bar navigation на mobile
  - Collapsible lists для большого контента
  - Floating action buttons для primary actions

#### 🔄 **Offline Data Synchronization**
```typescript
// src/utils/offlineSync.ts
class OfflineSync {
  private pendingOperations: Operation[] = [];
  
  async queueOperation(operation: Operation) {
    if (navigator.onLine) {
      return await this.executeOperation(operation);
    } else {
      this.pendingOperations.push(operation);
      await this.saveToIndexedDB(operation);
    }
  }
  
  async syncPendingOperations() {
    if (!navigator.onLine) return;
    
    for (const operation of this.pendingOperations) {
      try {
        await this.executeOperation(operation);
        this.removePendingOperation(operation);
      } catch (error) {
        // Handle sync conflicts
        this.handleSyncConflict(operation, error);
      }
    }
  }
}
```

#### 📊 **Mobile Analytics & Performance**
- **Performance Monitoring:**
  - First Contentful Paint < 1.5s
  - Largest Contentful Paint < 2.5s
  - Cumulative Layout Shift < 0.1
  
- **Mobile-Specific Metrics:**
  - Touch response time < 100ms
  - Scroll smoothness (60fps)
  - Battery usage optimization

---
## **3. 🎨 ПЛАН РАЗРАБОТКИ ДИЗАЙНА**

### 3.1 **Design System и UI Kit**
**Задача:** Создать единую дизайн-систему для всех компонентов WMS-интерфейса.

#### 📌 **Компоненты Design System**
- **Color Palette:**
  - Primary: #1976d2 (Blue) - основные действия
  - Secondary: #f57c00 (Orange) - второстепенные действия  
  - Success: #388e3c (Green) - успешные операции
  - Warning: #f9a825 (Yellow) - предупреждения
  - Error: #d32f2f (Red) - ошибки
  - Neutral: #424242, #757575, #e0e0e0 - текст и фоны

- **Typography Scale:**
  - Headers: Inter/Roboto Bold (H1: 32px, H2: 24px, H3: 20px, H4: 18px)
  - Body: Inter/Roboto Regular (16px/14px)
  - Captions: 12px
  - Code: Fira Code Mono

- **Spacing System:**
  - Base unit: 8px
  - Spacing scale: 4px, 8px, 16px, 24px, 32px, 48px, 64px

#### 🎨 **Component Library**
- **Data Display:**
  - Tables with sorting, filtering, pagination
  - Cards for inventory items
  - Charts (Line, Bar, Pie, Real-time)
  - Dashboards with metrics widgets
  
- **Navigation:**
  - Sidebar navigation with collapsible sections
  - Breadcrumbs
  - Tab navigation
  - Stepper for multi-step processes

- **Forms & Inputs:**
  - Text inputs with validation states
  - Select dropdowns with search
  - Date/time pickers
  - File upload with drag & drop
  - Checkbox/radio groups

- **Feedback & Status:**
  - Toast notifications (success/error/warning)
  - Loading states (spinners, skeletons)
  - Progress indicators
  - Status badges

### 3.2 **UX Research и User Journey**
**Задача:** Исследовать пользовательские потребности и создать оптимальные пользовательские пути.

#### 👥 **User Personas**
- **Warehouse Manager:** Контроль KPI, планирование, отчеты
- **Inventory Specialist:** Управление остатками, размещение товаров
- **Picking Operator:** Сборка заказов, сканирование
- **Receiving Clerk:** Приемка товаров, проверка качества
- **System Administrator:** Настройка системы, управление пользователями

#### 🗺️ **User Journey Maps**
- **Order Fulfillment Journey:**
  1. Order Creation → 2. Allocation → 3. Picking → 4. Packing → 5. Shipping
- **Inventory Management Journey:**
  1. Receiving → 2. Put-away → 3. Stock monitoring → 4. Replenishment
- **Returns Processing Journey:**
  1. Return Authorization → 2. Inspection → 3. Disposition → 4. Restocking

#### 📱 **Mobile-First Considerations**
- Touch-friendly interface (минимум 44px для кнопок)
- Thumb-zone navigation
- Offline capabilities для критических операций
- Voice input для hands-free операций
- Barcode/QR scanning integration

### 3.3 **Adaptive Design (Mobile-First)**
**Задача:** Обеспечить отличный UX на всех устройствах и размерах экранов.

#### 📱 **Breakpoints**
```css
/* Mobile First */
@media (min-width: 320px) { /* Mobile portrait */ }
@media (min-width: 480px) { /* Mobile landscape */ }
@media (min-width: 768px) { /* Tablet portrait */ }
@media (min-width: 1024px) { /* Tablet landscape / Small desktop */ }
@media (min-width: 1200px) { /* Desktop */ }
@media (min-width: 1440px) { /* Large desktop */ }
```

#### 🔄 **Responsive Patterns**
- **Navigation:** Collapsible sidebar → Bottom tab bar на mobile
- **Tables:** Horizontal scroll → Card view на mobile
- **Forms:** Single column → Multi-column на desktop
- **Dashboards:** Stacked widgets → Grid layout на desktop

#### 🎛️ **Progressive Web App (PWA)**
- Service Workers для offline functionality
- App Shell архитектура
- Push notifications для real-time updates
- Add to Home Screen capability

### 3.4 **Real-time UI Components**
**Задача:** Создать компоненты для отображения real-time данных и статусов.

#### 📊 **Real-time Data Visualization**
- **Live Charts:** С SSE-обновлениями для KPI дашбордов
- **Status Indicators:** Real-time статусы заказов, оборудования, персонала
- **Progress Bars:** Динамические индикаторы выполнения задач
- **Activity Feeds:** Живая лента событий склада

#### 🔔 **Notification System**
- **Toast Notifications:** Автоматически исчезающие уведомления
- **Alert Banners:** Критические уведомления в header
- **Notification Center:** Центральное место для всех уведомлений
- **Real-time Counters:** Счетчики непрочитанных уведомлений

#### 🎨 **Animation & Micro-interactions**
- **Loading States:** Skeleton screens во время загрузки
- **State Transitions:** Плавные переходы между состояниями
- **Hover Effects:** Интерактивные эффекты для кнопок и карточек
- **Success Animations:** Визуальная обратная связь при успешных действиях

---
## **4. 🔄 SSE-АРХИТЕКТУРА ДЛЯ REAL-TIME ОБНОВЛЕНИЙ**

### 4.1 **Архитектура SSE**
**Задача:** Реализовать эффективную архитектуру для real-time обновлений через Server-Sent Events.

#### 📡 **SSE vs WebSockets Выбор**
```yaml
Выбор SSE для WMS когда:
  - Односторонняя коммуникация (server → client)
  - Простота реализации критична
  - Нужна автоматическая реконнекция
  - HTTP/2 multiplexing достаточно
  
Используем для:
  - Inventory updates (остатки товаров)
  - Order status changes (статусы заказов)  
  - Task assignments (назначение задач)
  - System notifications (системные уведомления)
  - KPI dashboard updates (обновления дашбордов)
```

#### 🏗️ **SSE Event Architecture**
```python
# Структура SSE события
{
    "event": "inventory_update",  # Тип события
    "data": {                     # Данные события
        "product_id": "SKU123",
        "location": "A-1-01", 
        "quantity": 150,
        "timestamp": "2024-01-15T10:30:00Z"
    },
    "id": "evt_001",             # ID для resume
    "retry": 3000                # Время переподключения
}
```

### 4.2 **Реализация SSE в Django**
**Задача:** Создать Django backend для SSE с использованием Django Channels и ASGI.

#### 🔧 **Django SSE Consumer**
```python
# src/utils/sse/consumers.py
from channels.generic.http import AsyncHttpConsumer
from channels.db import database_sync_to_async
import json
import asyncio

class WMSSSEConsumer(AsyncHttpConsumer):
    async def handle(self, body):
        # Добавляем пользователя в группу для его warehouse
        warehouse_id = self.scope["user"].profile.warehouse_id
        await self.channel_layer.group_add(
            f"warehouse_{warehouse_id}", 
            self.channel_name
        )
        
        # Устанавливаем SSE headers
        await self.send_headers([
            (b"Content-Type", b"text/event-stream"),
            (b"Cache-Control", b"no-cache"),
            (b"Connection", b"keep-alive"),
            (b"Access-Control-Allow-Origin", b"*"),
        ])
        
        # Отправляем initial heartbeat
        await self.send_sse_event("connected", {"status": "connected"})
        
        # Держим соединение открытым
        try:
            while True:
                await asyncio.sleep(30)  # Heartbeat каждые 30 сек
                await self.send_sse_event("heartbeat", {"timestamp": timezone.now()})
        except Exception:
            await self.disconnect()

    async def send_sse_event(self, event_type: str, data: dict):
        """Отправка SSE события клиенту"""
        message = f"event: {event_type}\ndata: {json.dumps(data)}\n\n"
        await self.send_body(message.encode(), more_body=True)

    # Event handlers для различных типов событий
    async def inventory_update(self, event):
        await self.send_sse_event("inventory_update", event["data"])
    
    async def order_status_change(self, event):
        await self.send_sse_event("order_status", event["data"])
    
    async def task_assignment(self, event):
        await self.send_sse_event("task_assigned", event["data"])
```

#### 📨 **Event Broadcasting System**
```python
# src/utils/sse/broadcaster.py
from channels.layers import get_channel_layer
from asgiref.sync import async_to_sync
from typing import Dict, Any

class SSEBroadcaster:
    def __init__(self):
        self.channel_layer = get_channel_layer()
    
    def broadcast_to_warehouse(self, warehouse_id: int, event_type: str, data: Dict[Any, Any]):
        """Отправка события всем пользователям склада"""
        async_to_sync(self.channel_layer.group_send)(
            f"warehouse_{warehouse_id}",
            {
                "type": event_type.replace("-", "_"),  # inventory-update -> inventory_update
                "data": data
            }
        )
    
    def broadcast_to_user(self, user_id: int, event_type: str, data: Dict[Any, Any]):
        """Отправка события конкретному пользователю"""
        async_to_sync(self.channel_layer.group_send)(
            f"user_{user_id}",
            {
                "type": event_type.replace("-", "_"),
                "data": data
            }
        )

# Использование в сервисах
broadcaster = SSEBroadcaster()

# В InventoryService при обновлении остатков
def update_stock_level(self, product_id: str, location: str, new_quantity: int):
    # ... бизнес-логика обновления ...
    
    # Отправляем real-time обновление
    broadcaster.broadcast_to_warehouse(
        warehouse_id=self.warehouse_id,
        event_type="inventory-update",
        data={
            "product_id": product_id,
            "location": location,
            "quantity": new_quantity,
            "timestamp": timezone.now().isoformat()
        }
    )
```

### 4.3 **Frontend интеграция с SSE**
**Задача:** Создать React компоненты для получения и обработки SSE событий.

#### ⚛️ **React SSE Hook**
```typescript
// src/hooks/useSSE.ts
import { useEffect, useRef, useCallback } from 'react';
import { useAuth } from './useAuth';

interface SSEHookOptions {
  url: string;
  onEvent?: (eventType: string, data: any) => void;
  onError?: (error: Event) => void;
  onOpen?: () => void;
}

export const useSSE = ({ url, onEvent, onError, onOpen }: SSEHookOptions) => {
  const eventSourceRef = useRef<EventSource | null>(null);
  const { token } = useAuth();

  const connect = useCallback(() => {
    if (eventSourceRef.current) {
      eventSourceRef.current.close();
    }

    const eventSource = new EventSource(`${url}?token=${token}`, {
      withCredentials: true
    });

    eventSource.onopen = () => {
      console.log('SSE connection opened');
      onOpen?.();
    };

    eventSource.onerror = (error) => {
      console.error('SSE error:', error);
      onError?.(error);
    };

    // Слушаем различные типы событий
    eventSource.addEventListener('inventory-update', (event) => {
      const data = JSON.parse(event.data);
      onEvent?.('inventory-update', data);
    });

    eventSource.addEventListener('order-status', (event) => {
      const data = JSON.parse(event.data);
      onEvent?.('order-status', data);
    });

    eventSource.addEventListener('task-assigned', (event) => {
      const data = JSON.parse(event.data);
      onEvent?.('task-assigned', data);
    });

    eventSourceRef.current = eventSource;
  }, [url, token, onEvent, onError, onOpen]);

  useEffect(() => {
    connect();
    
    return () => {
      if (eventSourceRef.current) {
        eventSourceRef.current.close();
      }
    };
  }, [connect]);

  return {
    reconnect: connect,
    disconnect: () => eventSourceRef.current?.close()
  };
};
```

#### 📊 **Real-time Dashboard Component**
```typescript
// src/components/RealTimeDashboard.tsx
import React, { useState, useCallback } from 'react';
import { useSSE } from '../hooks/useSSE';
import { InventoryWidget } from './widgets/InventoryWidget';
import { OrderStatusWidget } from './widgets/OrderStatusWidget';

export const RealTimeDashboard: React.FC = () => {
  const [inventoryData, setInventoryData] = useState({});
  const [orderStatuses, setOrderStatuses] = useState([]);
  const [connectionStatus, setConnectionStatus] = useState('connecting');

  const handleSSEEvent = useCallback((eventType: string, data: any) => {
    switch (eventType) {
      case 'inventory-update':
        setInventoryData(prev => ({
          ...prev,
          [data.product_id]: data
        }));
        break;
      
      case 'order-status':
        setOrderStatuses(prev => 
          prev.map(order => 
            order.id === data.order_id 
              ? { ...order, status: data.status }
              : order
          )
        );
        break;
      
      case 'heartbeat':
        setConnectionStatus('connected');
        break;
    }
  }, []);

  useSSE({
    url: '/api/v1/sse/warehouse-events/',
    onEvent: handleSSEEvent,
    onOpen: () => setConnectionStatus('connected'),
    onError: () => setConnectionStatus('error')
  });

  return (
    <div className="dashboard-grid">
      <div className="connection-status">
        Status: {connectionStatus}
      </div>
      
      <InventoryWidget data={inventoryData} />
      <OrderStatusWidget orders={orderStatuses} />
    </div>
  );
};
```

### 4.4 **Event-driven архитектура**
**Задача:** Создать event-driven систему для реагирования на изменения в системе.

#### 🎯 **Domain Events**
```python
# src/utils/events/domain_events.py
from dataclasses import dataclass
from datetime import datetime
from typing import Any, Dict
import uuid

@dataclass
class DomainEvent:
    event_id: str
    event_type: str
    aggregate_id: str
    aggregate_type: str
    data: Dict[str, Any]
    timestamp: datetime
    version: int = 1

    def __post_init__(self):
        if not self.event_id:
            self.event_id = str(uuid.uuid4())

# Конкретные domain events
@dataclass  
class InventoryUpdatedEvent(DomainEvent):
    def __init__(self, product_id: str, location: str, old_quantity: int, new_quantity: int):
        super().__init__(
            event_id="",
            event_type="inventory.updated",
            aggregate_id=product_id,
            aggregate_type="Product",
            data={
                "product_id": product_id,
                "location": location,
                "old_quantity": old_quantity,
                "new_quantity": new_quantity
            },
            timestamp=datetime.now()
        )

@dataclass
class OrderStatusChangedEvent(DomainEvent):
    def __init__(self, order_id: str, old_status: str, new_status: str, user_id: str):
        super().__init__(
            event_id="",
            event_type="order.status_changed", 
            aggregate_id=order_id,
            aggregate_type="Order",
            data={
                "order_id": order_id,
                "old_status": old_status,
                "new_status": new_status,
                "changed_by": user_id
            },
            timestamp=datetime.now()
        )
```

#### 📮 **Event Publisher/Subscriber**
```python
# src/utils/events/event_bus.py
from typing import List, Callable, Dict
from .domain_events import DomainEvent
from ..sse.broadcaster import SSEBroadcaster

class EventBus:
    def __init__(self):
        self._handlers: Dict[str, List[Callable]] = {}
        self.sse_broadcaster = SSEBroadcaster()
    
    def subscribe(self, event_type: str, handler: Callable[[DomainEvent], None]):
        """Подписка на события"""
        if event_type not in self._handlers:
            self._handlers[event_type] = []
        self._handlers[event_type].append(handler)
    
    def publish(self, event: DomainEvent):
        """Публикация события"""
        # Сохраняем событие в event store
        self._save_event(event)
        
        # Вызываем handlers
        if event.event_type in self._handlers:
            for handler in self._handlers[event.event_type]:
                try:
                    handler(event)
                except Exception as e:
                    logger.error(f"Error handling event {event.event_id}: {e}")
        
        # Отправляем через SSE
        self._broadcast_sse_event(event)
    
    def _broadcast_sse_event(self, event: DomainEvent):
        """Преобразование domain event в SSE event"""
        if event.event_type == "inventory.updated":
            self.sse_broadcaster.broadcast_to_warehouse(
                warehouse_id=1,  # TODO: получать из context
                event_type="inventory-update",
                data=event.data
            )
        elif event.event_type == "order.status_changed":
            self.sse_broadcaster.broadcast_to_warehouse(
                warehouse_id=1,
                event_type="order-status", 
                data=event.data
            )

# Глобальная instance
event_bus = EventBus()

# Настройка handlers
def handle_inventory_updated(event: DomainEvent):
    """Handler для обновления inventory в аналитике"""
    # Логика обновления analytics
    pass

def handle_order_status_changed(event: DomainEvent):
    """Handler для уведомлений об изменении статуса заказа"""
    # Логика отправки уведомлений
    pass

# Регистрируем handlers
event_bus.subscribe("inventory.updated", handle_inventory_updated)
event_bus.subscribe("order.status_changed", handle_order_status_changed)
```

---
## **5. 🏗️ DEPENDENCY INJECTION PATTERN**

### 5.1 **Принципы применения DI**
**Задача:** Определить правильные случаи использования DI в Django/DRF проекте.

#### ✅ **Где применять DI (Рекомендуется)**
```python
# 1. Внешние интеграции и API
class ExternalAPIService:
    def __init__(self, http_client: HttpClient, config: APIConfig):
        self.http_client = http_client
        self.config = config

# 2. Кеширование и Redis операции  
class CacheService:
    def __init__(self, redis_client: Redis, serializer: Serializer):
        self.redis_client = redis_client
        self.serializer = serializer

# 3. IoT и Device интеграции
class IoTDeviceService:
    def __init__(self, mqtt_client: MQTTClient, device_registry: DeviceRegistry):
        self.mqtt_client = mqtt_client
        self.device_registry = device_registry

# 4. Email/SMS сервисы
class NotificationService:
    def __init__(self, email_backend: EmailBackend, sms_backend: SMSBackend):
        self.email_backend = email_backend  
        self.sms_backend = sms_backend

# 5. File storage и обработка документов
class DocumentProcessingService:
    def __init__(self, storage: FileStorage, pdf_processor: PDFProcessor):
        self.storage = storage
        self.pdf_processor = pdf_processor
```

#### ❌ **Где НЕ применять DI (Стандартный DRF)**
```python
# Стандартные DRF паттерны работают отлично
class ProductViewSet(ModelViewSet):
    queryset = Product.objects.all()
    serializer_class = ProductSerializer
    filter_backends = [DjangoFilterBackend]
    filterset_fields = ['category', 'warehouse']

# Простые сервисы без внешних зависимостей  
class InventoryService:
    def calculate_stock_level(self, product_id: str) -> int:
        return StockItem.objects.filter(product_id=product_id).aggregate(
            total=Sum('quantity')
        )['total'] or 0
```

### 5.2 **Конфигурация DI контейнера**
**Задача:** Настроить dependency-injector для управления сложными зависимостями.

#### 🏗️ **Container Configuration**
```python
# src/containers.py
from dependency_injector import containers, providers
from dependency_injector.wiring import Provide, inject
import redis
import requests
from pika import BlockingConnection, ConnectionParameters

class ApplicationContainer(containers.DeclarativeContainer):
    
    # Configuration
    config = providers.Configuration()
    
    # Infrastructure providers
    redis_client = providers.Singleton(
        redis.Redis,
        host=config.redis.host,
        port=config.redis.port,
        db=config.redis.db,
        password=config.redis.password,
    )
    
    http_client = providers.Singleton(
        requests.Session
    )
    
    rabbitmq_connection = providers.Singleton(
        BlockingConnection,
        ConnectionParameters(
            host=config.rabbitmq.host,
            port=config.rabbitmq.port,
            credentials=providers.Object(
                pika.PlainCredentials(
                    config.rabbitmq.username,
                    config.rabbitmq.password
                )
            )
        )
    )
    
    # Application services  
    cache_service = providers.Factory(
        CacheService,
        redis_client=redis_client
    )
    
    external_api_service = providers.Factory(
        ExternalAPIService,
        http_client=http_client,
        base_url=config.external_api.base_url,
        api_key=config.external_api.key
    )
    
    notification_service = providers.Factory(
        NotificationService,
        redis_client=redis_client,
        rabbitmq_connection=rabbitmq_connection
    )
    
    iot_service = providers.Factory(
        IoTDeviceService,
        redis_client=redis_client,
        mqtt_config=config.mqtt
    )

# Инициализация в settings.py
container = ApplicationContainer()
container.config.from_dict({
    'redis': {
        'host': os.getenv('REDIS_HOST', 'localhost'),
        'port': int(os.getenv('REDIS_PORT', 6379)),
        'db': int(os.getenv('REDIS_DB', 0)),
        'password': os.getenv('REDIS_PASSWORD')
    },
    'external_api': {
        'base_url': os.getenv('EXTERNAL_API_URL'),
        'key': os.getenv('EXTERNAL_API_KEY')
    },
    'rabbitmq': {
        'host': os.getenv('RABBITMQ_HOST', 'localhost'),
        'port': int(os.getenv('RABBITMQ_PORT', 5672)),
        'username': os.getenv('RABBITMQ_USER', 'guest'),
        'password': os.getenv('RABBITMQ_PASS', 'guest')
    },
    'mqtt': {
        'host': os.getenv('MQTT_HOST', 'localhost'),
        'port': int(os.getenv('MQTT_PORT', 1883))
    }
})
```

### 5.3 **Интеграции с внешними сервисами**
**Задача:** Реализовать интеграции с внешними системами используя DI.

#### 🔗 **External API Integration**
```python
# src/apps/integrations/services.py
from typing import Dict, Any, Optional
import requests
from dataclasses import dataclass

@dataclass
class APIResponse:
    success: bool
    data: Optional[Dict[str, Any]] = None
    error: Optional[str] = None
    status_code: Optional[int] = None

class ExternalAPIService:
    """Сервис для интеграции с внешними API (ERP, TMS, etc.)"""
    
    def __init__(self, http_client: requests.Session, base_url: str, api_key: str):
        self.http_client = http_client
        self.base_url = base_url.rstrip('/')
        self.api_key = api_key
        
        # Настройка headers для всех запросов
        self.http_client.headers.update({
            'Authorization': f'Bearer {self.api_key}',
            'Content-Type': 'application/json',
            'User-Agent': 'WMS-System/1.0'
        })
    
    def sync_product_catalog(self, last_sync: datetime) -> APIResponse:
        """Синхронизация каталога товаров с ERP"""
        try:
            response = self.http_client.get(
                f'{self.base_url}/api/products',
                params={'modified_since': last_sync.isoformat()}
            )
            response.raise_for_status()
            
            return APIResponse(
                success=True,
                data=response.json(),
                status_code=response.status_code
            )
        except requests.RequestException as e:
            return APIResponse(
                success=False,
                error=str(e),
                status_code=getattr(e.response, 'status_code', None)
            )
    
    def send_shipment_notification(self, shipment_data: Dict[str, Any]) -> APIResponse:
        """Отправка уведомления об отгрузке в TMS"""
        try:
            response = self.http_client.post(
                f'{self.base_url}/api/shipments',
                json=shipment_data
            )
            response.raise_for_status()
            
            return APIResponse(
                success=True,
                data=response.json(),
                status_code=response.status_code
            )
        except requests.RequestException as e:
            return APIResponse(
                success=False,
                error=str(e),
                status_code=getattr(e.response, 'status_code', None)
            )

# src/apps/integrations/views.py
from dependency_injector.wiring import inject, Provide
from rest_framework.views import APIView
from rest_framework.response import Response
from .containers import ApplicationContainer

class ProductSyncView(APIView):
    @inject
    def post(
        self, 
        request,
        external_api_service: ExternalAPIService = Provide[ApplicationContainer.external_api_service]
    ):
        last_sync = request.data.get('last_sync')
        result = external_api_service.sync_product_catalog(last_sync)
        
        if result.success:
            # Обработка полученных данных
            self._process_product_data(result.data)
            return Response({'status': 'success', 'products_updated': len(result.data)})
        else:
            return Response({'status': 'error', 'message': result.error}, status=400)
    
    def _process_product_data(self, products_data):
        # Логика обработки и сохранения данных продуктов
        pass
```

#### 📦 **Cache Service с Redis**
```python
# src/utils/cache/services.py
import json
import pickle
from typing import Any, Optional, Union
from datetime import timedelta
import redis

class CacheService:
    """Сервис для работы с Redis кешем"""
    
    def __init__(self, redis_client: redis.Redis):
        self.redis_client = redis_client
    
    def get(self, key: str, default: Any = None) -> Any:
        """Получение значения из кеша"""
        try:
            value = self.redis_client.get(key)
            if value is None:
                return default
            return pickle.loads(value)
        except (redis.RedisError, pickle.UnpicklingError):
            return default
    
    def set(self, key: str, value: Any, ttl: Optional[Union[int, timedelta]] = None) -> bool:
        """Сохранение значения в кеш"""
        try:
            serialized_value = pickle.dumps(value)
            if ttl:
                if isinstance(ttl, timedelta):
                    ttl = int(ttl.total_seconds())
                return self.redis_client.setex(key, ttl, serialized_value)
            else:
                return self.redis_client.set(key, serialized_value)
        except (redis.RedisError, pickle.PicklingError):
            return False
    
    def delete(self, key: str) -> bool:
        """Удаление значения из кеша"""
        try:
            return bool(self.redis_client.delete(key))
        except redis.RedisError:
            return False
    
    def get_inventory_summary(self, warehouse_id: int) -> Optional[Dict[str, Any]]:
        """Получение сводки по складу из кеша"""
        cache_key = f"inventory_summary:warehouse:{warehouse_id}"
        return self.get(cache_key)
    
    def set_inventory_summary(self, warehouse_id: int, summary: Dict[str, Any], ttl_minutes: int = 15):
        """Кеширование сводки по складу"""
        cache_key = f"inventory_summary:warehouse:{warehouse_id}"
        return self.set(cache_key, summary, timedelta(minutes=ttl_minutes))

# Использование в сервисах
from dependency_injector.wiring import inject, Provide

class InventoryService:
    @inject
    def __init__(
        self,
        cache_service: CacheService = Provide[ApplicationContainer.cache_service]
    ):
        self.cache_service = cache_service
    
    def get_warehouse_summary(self, warehouse_id: int) -> Dict[str, Any]:
        # Сначала проверяем кеш
        cached_summary = self.cache_service.get_inventory_summary(warehouse_id)
        if cached_summary:
            return cached_summary
        
        # Если нет в кеше, вычисляем и кешируем
        summary = self._calculate_warehouse_summary(warehouse_id)
        self.cache_service.set_inventory_summary(warehouse_id, summary)
        
        return summary
```

---
## **6. 🐳 CI/CD и DevOps**

### 6.1 **Dockerfile**
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

---
## **7. 🚀 СОВРЕМЕННЫЕ API И ИНТЕГРАЦИИ**

### 7.1 **Enhanced API Design**
**Задача:** Создать современную API архитектуру с поддержкой real-time обновлений и высокой производительности.

#### 📡 **Server-Sent Events (SSE) Endpoints**
```python
# SSE Endpoints для real-time обновлений
SSE_ENDPOINTS = {
    # Warehouse-level updates
    '/api/v1/sse/warehouse/{warehouse_id}/': {
        'events': ['inventory-update', 'order-status', 'wave-progress'],
        'auth': 'warehouse-access'
    },
    
    # User-specific updates  
    '/api/v1/sse/user/{user_id}/': {
        'events': ['task-assigned', 'notification', 'alert'],
        'auth': 'user-specific'
    },
    
    # Global system events
    '/api/v1/sse/system/': {
        'events': ['system-alert', 'maintenance', 'broadcast'],
        'auth': 'admin-only'
    }
}

# Пример SSE события
{
    "event": "inventory-update",
    "data": {
        "product_id": "SKU123",
        "location": "A-1-01",
        "old_quantity": 100,
        "new_quantity": 95,
        "transaction_type": "pick",
        "order_id": "ORD-456",
        "timestamp": "2024-01-15T10:30:00Z"
    },
    "id": "evt_001",
    "retry": 3000
}
```

#### ⚡ **High-Performance Bulk Operations API**
```python
# Bulk API для массовых операций
BULK_ENDPOINTS = {
    'POST /api/v1/bulk/inventory/update/': {
        'description': 'Массовое обновление остатков',
        'max_items': 10000,
        'rate_limit': '100/minute',
        'response_format': 'batch_result'
    },
    
    'POST /api/v1/bulk/orders/create/': {
        'description': 'Создание множественных заказов',
        'max_items': 1000,
        'rate_limit': '50/minute',
        'async': True
    },
    
    'POST /api/v1/bulk/products/import/': {
        'description': 'Импорт товаров',
        'max_items': 50000,
        'file_formats': ['CSV', 'Excel', 'JSON'],
        'async': True
    }
}

# Пример bulk запроса
{
    "operations": [
        {
            "action": "update",
            "product_id": "SKU123",
            "location": "A-1-01",
            "quantity": 100
        },
        {
            "action": "move",
            "product_id": "SKU124", 
            "from_location": "B-2-01",
            "to_location": "A-1-02",
            "quantity": 50
        }
    ],
    "options": {
        "validate_only": false,
        "stop_on_error": true,
        "return_details": true
    }
}
```

#### 🔗 **HATEOAS Implementation для Self-Documenting APIs**
```python
# Пример HATEOAS response
{
    "id": 123,
    "order_number": "ORD-2024-001",
    "status": "allocated",
    "customer": "ACME Corp",
    "items_count": 5,
    "created_at": "2024-01-15T09:00:00Z",
    
    # Доступные действия в зависимости от статуса и прав
    "_links": {
        "self": {
            "href": "/api/v1/orders/123/",
            "method": "GET"
        },
        "pick": {
            "href": "/api/v1/orders/123/pick/",
            "method": "POST",
            "description": "Start picking process"
        },
        "cancel": {
            "href": "/api/v1/orders/123/cancel/",
            "method": "POST", 
            "description": "Cancel order",
            "confirmation_required": true
        },
        "priority": {
            "href": "/api/v1/orders/123/priority/",
            "method": "PATCH",
            "description": "Change order priority"
        }
    },
    
    # Метаданные для клиента
    "_meta": {
        "permissions": ["read", "update", "cancel"],
        "next_valid_statuses": ["picked", "cancelled"],
        "estimated_completion": "2024-01-15T14:00:00Z"
    }
}
```

#### 🎯 **GraphQL-подобные возможности через JSON API**
```python
# Flexible field selection
GET /api/v1/orders/?fields=id,status,customer&include=items,shipping

# Response:
{
    "data": [
        {
            "id": 123,
            "status": "allocated", 
            "customer": "ACME Corp",
            "items": [...],
            "shipping": {...}
        }
    ],
    "included": {
        "items": [...],
        "shipping": [...]
    }
}
```

#### 📊 **Advanced Filtering и Search**
```python
# Complex filtering examples
GET /api/v1/inventory/?filter[product.category]=electronics&filter[quantity__gte]=100
GET /api/v1/orders/?filter[status__in]=allocated,picked&filter[created_at__range]=2024-01-01,2024-01-31
GET /api/v1/products/?search=apple&filter[warehouse]=1&sort=-created_at&page=1&page_size=20

# Full-text search с highlight
GET /api/v1/search/?q=damaged+goods&entities=orders,products&highlight=true
```

### 7.2 **API Versioning и Backward Compatibility**
- **URL Versioning:** `/api/v1/`, `/api/v2/`
- **Header Versioning:** `Accept: application/vnd.wms.v1+json`
- **Deprecation Warnings:** Градуальный переход между версиями
- **Feature Flags:** A/B testing новых API features

---
## **8. 🛡️ БЕЗОПАСНОСТЬ И COMPLIANCE**

### 8.1 **Enhanced Security**
- **Authentication & Authorization:**
    - OAuth 2.0 + PKCE для secure authentication
    - JWT с refresh tokens и short-lived access tokens
    - Multi-factor authentication (MFA)
    - Single Sign-On (SSO) integration

- **Role-Based Access Control (RBAC):**
    ```python
    # Модель разрешений
    class Permission(models.Model):
        codename = models.CharField(max_length=100)
        content_type = models.ForeignKey(ContentType)
        
    class Role(models.Model):
        name = models.CharField(max_length=80)
        permissions = models.ManyToManyField(Permission)
        
    class UserRole(models.Model):
        user = models.ForeignKey(User)
        role = models.ForeignKey(Role)
        warehouse = models.ForeignKey(Warehouse)  # Per-warehouse permissions
    ```

- **API Security:**
    - Rate limiting: 1000 requests/hour per user
    - API key management для integration partners
    - Request/Response encryption
    - SQL injection и XSS protection
    - CORS policy management

- **Data Protection:**
    - Data encryption at rest (AES-256)
    - Data encryption in transit (TLS 1.3)
    - PII data anonymization
    - GDPR compliance tools
    - Audit logging для всех операций

### 8.2 **Compliance & Audit**
- **Audit Trail:**
    ```python
    class AuditLog(models.Model):
        user = models.ForeignKey(User)
        action = models.CharField(max_length=50)  # CREATE, UPDATE, DELETE
        model_name = models.CharField(max_length=50)
        object_id = models.CharField(max_length=50)
        changes = models.JSONField()  # Детали изменений
        ip_address = models.GenericIPAddressField()
        timestamp = models.DateTimeField(auto_now_add=True)
    ```

- **Regulatory Compliance:**
    - GxP compliance для pharmaceutical
    - FDA 21 CFR Part 11 для electronic records
    - ISO 27001 security standards
    - SOX compliance для financial reporting

---
## **9. ☁️ CLOUD-NATIVE ТЕХНОЛОГИИ**

### 9.1 **Kubernetes Deployment**
- **Infrastructure as Code:**
    ```yaml
    # k8s/backend-deployment.yaml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: wms-backend
    spec:
      replicas: 3
      selector:
        matchLabels:
          app: wms-backend
      template:
        spec:
          containers:
          - name: wms-backend
            image: wms-backend:latest
            ports:
            - containerPort: 8000
    ```

- **Auto-scaling:**
    - Horizontal Pod Autoscaler (HPA)
    - Vertical Pod Autoscaler (VPA)
    - Cluster Autoscaler для node scaling

### 9.2 **Monitoring & Observability**
- **Metrics Collection:**
    - Prometheus для сбора метрик
    - Grafana для визуализации
    - Custom metrics для business KPIs

- **Logging:**
    - ELK Stack (Elasticsearch, Logstash, Kibana)
    - Centralized logging для всех services
    - Log correlation и tracing

- **Health Checks:**
    ```python
    # Health check endpoints
    @api_view(['GET'])
    def health_check(request):
        return Response({
            'status': 'healthy',
            'database': check_database_connection(),
            'redis': check_redis_connection(),
            'timestamp': timezone.now()
        })
    ```

### 9.3 **CI/CD Pipeline Enhancement**
- **Modern CI/CD Features:**
    ```yaml
    # .github/workflows/deploy.yml
    name: Deploy WMS
    on:
      push:
        branches: [main]
    
    jobs:
      test:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v3
          - name: Run tests
            run: |
              poetry install
              poetry run pytest
              poetry run black --check .
              poetry run ruff check .
      
      build:
        needs: test
        runs-on: ubuntu-latest
        steps:
          - name: Build Docker image
            run: docker build -t wms-backend:${{ github.sha }} .
          - name: Push to registry
            run: docker push wms-backend:${{ github.sha }}
      
      deploy:
        needs: build
        runs-on: ubuntu-latest
        steps:
          - name: Deploy to Kubernetes
            run: |
              kubectl set image deployment/wms-backend \
                wms-backend=wms-backend:${{ github.sha }}
    ```

- **Advanced Deployment Strategies:**
    - Blue-green deployments для zero-downtime
    - Canary releases для safe feature rollouts
    - Feature flags для gradual feature enabling
    - Automated rollback при detection проблем

### 9.4 **Performance Optimization**
- **Database Optimization:**
    - Connection pooling с PgBouncer
    - Read replicas для scale read operations
    - Database indexing optimization
    - Query performance monitoring

- **Caching Strategy:**
    - Redis для session storage
    - Application-level caching
    - CDN для static assets
    - Database query result caching

- **Application Performance:**
    - Async processing с Celery
    - Background task optimization
    - Memory usage optimization
    - CPU profiling и optimization