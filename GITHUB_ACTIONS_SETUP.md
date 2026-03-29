# 🔧 Инструкция по включению GitHub Actions

## Если вкладка Actions пустая

### Шаг 1: Включите GitHub Actions

1. Перейдите в репозиторий: **https://github.com/devdox-del/Housexgram-Beta**
2. Нажмите на вкладку **Actions**
3. Если видите сообщение "GitHub Actions is disabled for this repository":
   - Нажмите кнопку **I understand my workflows, go ahead and enable them**
   - Или перейдите в **Settings** → **Actions** → **General**
   - Выберите **Allow all actions and reusable workflows**
   - Нажмите **Save**

### Шаг 2: Проверьте настройки репозитория

1. Перейдите в **Settings** → **Actions** → **General**
2. Убедитесь, что выбрано: **Allow all actions and reusable workflows**
3. В разделе **Workflow permissions** выберите: **Read and write permissions**
4. Нажмите **Save**

### Шаг 3: Настройте GitHub Pages

1. Перейдите в **Settings** → **Pages**
2. В разделе **Build and deployment**:
   - **Source**: GitHub Actions
3. GitHub автоматически определит workflow файл

### Шаг 4: Добавьте секреты (обязательно!)

1. Перейдите в **Settings** → **Secrets and variables** → **Actions**
2. Нажмите **New repository secret**
3. Добавьте два секрета:

   ```
   Name: TELEGRAM_API_ID
   Value: 27593191
   ```

   ```
   Name: TELEGRAM_API_HASH
   Value: 8d7fa6b5ad916aebf8c60d110b124fe8
   ```

### Шаг 5: Запустите сборку вручную (если автоматически не запустилась)

1. Перейдите во вкладку **Actions**
2. Нажмите на workflow **Deploy to GitHub Pages**
3. Нажмите кнопку **Run workflow** (справа)
4. Выберите ветку **main**
5. Нажмите **Run workflow**

### Шаг 6: Проверьте статус сборки

1. Во вкладке **Actions** вы увидите запущенную сборку
2. Нажмите на неё, чтобы увидеть прогресс
3. Дождитесь завершения (обычно 3-5 минут)
4. После успеха сайт будет доступен по адресу:

**https://devdox-del.github.io/Housexgram-Beta/**

---

## 🚨 Если сборка не запускается

### Проверьте файл workflow

Убедитесь, что файл `.github/workflows/deploy.yml` существует и содержит правильный код.

### Проверьте ветку

Workflow настроен на запуск при пуше в ветку `main`. Убедитесь, что вы пушите в эту ветку:

```bash
git branch  # должна быть main
git push origin main
```

### Проверьте логи

Если сборка запустилась, но упала с ошибкой:
1. Нажмите на запущенную сборку в Actions
2. Нажмите на job **build**
3. Посмотрите логи ошибок

---

## ✅ Чеклист готовности

- [ ] GitHub Actions включены
- [ ] Workflow permissions: Read and write
- [ ] GitHub Pages Source: GitHub Actions
- [ ] Секреты TELEGRAM_API_ID и TELEGRAM_API_HASH добавлены
- [ ] Последний коммит отправлен в ветку main
- [ ] Сборка запустилась автоматически или вручную

После выполнения всех шагов сайт будет доступен по адресу: **https://devdox-del.github.io/Housexgram-Beta/**
