# HouseGram Beta - Telegram Web Client

Веб-клиент Telegram на React с использованием TDLib.

## 🚀 Быстрый старт

### 1. Установка зависимостей

```bash
npm install
```

### 2. Настройка API ключей

API ключи уже настроены в файле `.env`. Если нужно получить новые:

1. Посетите https://my.telegram.org/apps
2. Создайте новое приложение
3. Скопируйте API ID и API Hash в файл `.env`

### 3. Копирование TDLib файлов

```bash
cp node_modules/tdweb/dist/* public/
```

### 4. Запуск

```bash
# Режим разработки
npm run start

# Production сборка
npm run build
```

## 📦 Основные возможности

- ✅ Авторизация по номеру телефона и QR-коду
- ✅ Чаты и сообщения
- ✅ Медиафайлы (фото, видео, аудио, документы)
- ✅ Голосовые сообщения
- ✅ Стикеры и эмодзи
- ✅ Групповые звонки
- ✅ Темы (светлая/темная)
- ✅ Многоязычность
- ✅ Instant View
- ✅ Service Worker для offline работы

## 🛠 Технологии

- **React** 16.12
- **Material-UI** v4
- **TDLib** (Telegram Database Library) via WebAssembly
- **i18next** для локализации
- **react-app-rewired** для кастомизации сборки

## 📁 Структура проекта

```
├── public/              # Статические файлы
├── src/
│   ├── Actions/         # Redux-like actions
│   ├── Components/      # React компоненты
│   ├── Controllers/     # Контроллеры (TdLib)
│   ├── Stores/          # Stores/State management
│   ├── Utils/           # Утилиты
│   ├── Resources/       # Ресурсы локализации
│   └── Assets/          # Изображения, иконки
├── .env                 # Переменные окружения
└── package.json         # Зависимости
```

## 🔧 Скрипты

| Команда | Описание |
|---------|----------|
| `npm run start` | Запуск в режиме разработки |
| `npm run build` | Production сборка |
| `npm run test` | Запуск тестов |
| `npm run deploy` | Деплой на GitHub Pages |
| `npm run stats` | Анализ размера бандла |

## ⚠️ Важно

- **Не коммитьте файл `.env`** с вашими API ключами в публичные репозитории
- Используйте `.env.example` как шаблон
- TDLib файлы должны быть скопированы в `public/` перед запуском

## 📄 Лицензия

GPL v3.0 - см. файл [LICENSE](LICENSE)

## 🔗 Ссылки

- [GitHub Repository](https://github.com/devdox-del/Housexgram-Beta)
- [Telegram API Documentation](https://core.telegram.org/api)
- [TDLib Documentation](https://core.telegram.org/tdlib)
