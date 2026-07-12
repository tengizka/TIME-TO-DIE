# ШахМатч 67 ♟️

Одностраничное шахматное приложение: играешь белыми против бота **Карины**
(с шутками про Краснодар и секретное число 67). Работает офлайн после
загрузки, без бэкенда — всё на чистом HTML/CSS/JS + библиотека chess.js.

## Структура
```
index.html   — вся игра целиком (разметка, стили, логика, ИИ)
README.md    — этот файл
```

## 1. Залить на GitHub

```bash
git init
git add index.html README.md
git commit -m "ШахМатч 67: шахматы против Карины"
git branch -M main
git remote add origin https://github.com/<твой_логин>/<репозиторий>.git
git push -u origin main
```

## 2. Включить GitHub Pages

1. В репозитории: **Settings → Pages**.
2. Source: **Deploy from a branch**.
3. Branch: `main`, папка `/ (root)`.
4. Сохранить — через минуту-две сайт будет доступен по адресу вида:
   `https://<твой_логин>.github.io/<репозиторий>/`

Это и есть публичный HTTPS-адрес, который нужен Telegram.

## 3. Подключить как Telegram Mini App

1. Открой **@BotFather** в Telegram.
2. Если бота ещё нет — `/newbot`, дай имя и username.
3. Дальше: `/newapp` (или `/mybots` → выбрать бота → **Bot Settings → Menu Button / Mini App**).
4. Укажи:
   - **Web App URL** — ссылка на GitHub Pages из шага 2.
   - Название, короткое описание, иконку (по желанию).
5. В самом боте пропиши кнопку меню, которая открывает Mini App
   (BotFather → `/setmenubutton`, вставь ту же ссылку).
6. Открой бота в Telegram → нажми на кнопку меню — приложение откроется
   внутри Telegram и подстроится под тему клиента (в `index.html` уже
   подключён `telegram-web-app.js` и настроены цвета шапки/фона).

## Настроить под себя

- Реплики Карины — массивы `KARINA_OPENERS`, `KARINA_ON_CAPTURE`,
  `KARINA_ON_CHECK`, `KARINA_ON_MATE`, `KARINA_IDLE` в конце `index.html`.
- Сложность бота — переменная глубины в `minimax(2, ...)` внутри
  `karinaMove()`: 2 — быстро и не идеально, 3 — сильнее, но чуть медленнее
  на телефонах.
- Пасхалка на 67-м полуходе и цветовая палитра (зелёный/золото Краснодара)
  — переменные `:root` вверху `<style>`.
