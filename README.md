# Лендинг «Shift Inspector Bot»

Статичный сайт: `index.html`, `styles.css`, `app.js` — без сборки и зависимостей
(шрифты подгружаются из Google Fonts, без интернета используются системные).

Открыть локально:

```bash
python -m http.server 8765 --directory landing
```

и перейти на http://localhost:8765. Для публикации достаточно выложить папку на любой
статический хостинг (GitHub Pages, Netlify, nginx).

Что где править:

- тексты разделов — `index.html`;
- пошаговые инструкции по ролям (шаги и «экраны» Telegram) — массив `ROLES` в `app.js`;
- пример Excel-табеля — объекты `PEOPLE` и `SHEETS` в `app.js`;
- цвета и шрифты — переменные в начале `styles.css` (палитра взята с аватара бота);
- аватар бота — `assets/avatar.webp`, иконки — SVG-спрайт в начале `index.html`.

После правок CSS/JS увеличьте `?v=` в ссылках на `styles.css` и `app.js` в `index.html`,
чтобы браузеры не показывали старую версию из кеша.

## PDF-копия

`shift-inspector-bot.pdf` — копия сайта, где все инструкции по ролям раскрыты разом.
Версия для печати открывается по адресу `?pdf=1`. Пересобрать при запущенном локальном
сервере (см. выше):

```bash
"/c/Program Files/Google/Chrome/Application/chrome.exe" --headless=new --no-pdf-header-footer --window-size=1280,1810 --virtual-time-budget=15000 --print-to-pdf="landing/shift-inspector-bot.pdf" "http://localhost:8765/?pdf=1"
```

Из браузера тоже можно: Ctrl+P → «Сохранить как PDF» (инструкции раскроются сами).
