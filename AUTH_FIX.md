# 🔐 Решение проблемы UPDATE_APP_TO_LOGIN

## Проблема

При попытке авторизации появляется ошибка:
```
UPDATE_APP_TO_LOGIN
```

Это означает, что Telegram требует более новую версию приложения для авторизации.

## Причина

Telegram Web App использует TDLib версии 1.7.x/1.8.x, которая больше не поддерживается Telegram. 
К сожалению, старые версии TDLib были заблокированы на стороне серверов Telegram.

## ✅ Решение

### Вариант 1: Получить новые API ключи (Рекомендуется)

1. Перейдите на https://my.telegram.org/apps
2. Войдите под своим аккаунтом Telegram
3. Создайте **НОВОЕ** приложение:
   - Title: HouseGram Beta
   - Short name: housegram
   - Platform: Web
4. Скопируйте новые **API ID** и **API Hash**
5. Обновите файл `.env`:
   ```
   REACT_APP_TELEGRAM_API_ID=your_new_api_id
   REACT_APP_TELEGRAM_API_HASH=your_new_api_hash
   ```
6. Отправьте изменения:
   ```bash
   git add .env
   git commit -m "update: новые API ключи"
   git push
   ```

### Вариант 2: Использовать альтернативную версию TDLib

Можно попробовать использовать форк tdweb с более новой версией TDLib:

```bash
npm install @arseny30/tdweb@latest
```

Но это требует дополнительных изменений в конфигурации сборки.

### Вариант 3: Использовать официальный Telegram Web K/Z

Если авторизация критически важна, рассмотрите возможность использования:
- **Telegram Web K**: https://web.telegram.org/k/
- **Telegram Web Z**: https://web.telegram.org/z/

Это официальные клиенты Telegram с полной поддержкой.

## 📝 Примечание

Проект telegram-react (на котором основан HouseGram) больше не поддерживается автором.
Для production использования рекомендуется рассмотреть другие проекты:
- https://github.com/morethanwords/tweb (официальный Web K)
- https://github.com/Ajaxy/telegram-tt (Telegram Web Z)

## 🔗 Полезные ссылки

- [Получение API ключей](https://core.telegram.org/api/obtaining_api_id)
- [Telegram API Documentation](https://core.telegram.org/api)
- [TDLib Documentation](https://core.telegram.org/tdlib)
