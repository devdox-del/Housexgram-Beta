# 🚀 Инструкция по развертыванию на GitHub Pages

## Вариант 1: Автоматический деплой через GitHub Actions (Рекомендуется)

### Шаг 1: Настройка секретов GitHub

1. Перейдите в репозиторий на GitHub: https://github.com/devdox-del/Housexgram-Beta
2. Нажмите **Settings** → **Secrets and variables** → **Actions**
3. Нажмите **New repository secret**
4. Добавьте два секрета:

   ```
   Name: TELEGRAM_API_ID
   Value: 27593191
   ```

   ```
   Name: TELEGRAM_API_HASH
   Value: 8d7fa6b5ad916aebf8c60d110b124fe8
   ```

### Шаг 2: Включение GitHub Pages

1. Перейдите в **Settings** → **Pages**
2. В разделе **Build and deployment**:
   - **Source**: GitHub Actions
3. GitHub автоматически создаст сайт после следующего коммита

### Шаг 3: Автоматический деплой

После каждого пуша в ветку `main` сайт будет автоматически обновляться по адресу:
**https://devdox-del.github.io/Housexgram-Beta/**

---

## Вариант 2: Ручной деплой через npm

### Шаг 1: Установите зависимости

```bash
npm install
```

### Шаг 2: Скопируйте TDLib файлы

```bash
cp node_modules/tdweb/dist/* public/
```

### Шаг 3: Задеплойте

```bash
npm run deploy
```

Эта команда:
1. Создаст production сборку (`npm run build`)
2. Опубликует папку `build` на GitHub Pages

---

## ⚠️ Важно

- **Никогда не коммитьте файл `.env`** в репозиторий
- Используйте GitHub Secrets для хранения API ключей
- Файл `.github/workflows/deploy.yml` уже настроен для автоматического деплоя

---

## 🔗 Ссылки

- Ваш сайт: https://devdox-del.github.io/Housexgram-Beta/
- Репозиторий: https://github.com/devdox-del/Housexgram-Beta
- GitHub Actions: https://github.com/devdox-del/Housexgram-Beta/actions
