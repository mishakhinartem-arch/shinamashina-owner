# Как выложить страницу владельца без карты

Это обычные файлы: `index.html`, `manifest.webmanifest`, `icon.svg`, `apple-touch-icon.png`. Сборки нет. Сервер должен отдавать `index.html` как `text/html`.

Не кладите страницу в Supabase Storage. Бакет отдаёт HTML как `text/plain`, и Safari показывает исходный текст, а не приложение. Storage здесь не хостинг.

Ниже только бесплатная статика, без `service_role` и без покупки домена. Если форма просит банковскую карту, остановитесь и возьмите другой вариант.

| Вариант | Как выложить | Карта | Что получить |
|---|---|---|---|
| Cloudflare Pages | Регистрация, Create project, загрузите папку `owner-web` или подключите git-репозиторий и укажите корень `owner-web` | Для бесплатного тарифа Pages карту не спрашивают | Адрес `*.pages.dev`, HTTPS, `text/html` |
| Netlify Drop | Откройте [app.netlify.com/drop](https://app.netlify.com/drop) и перетащите папку `owner-web` | Бесплатный тариф статики карту не требует; платный план не включайте | Адрес `*.netlify.app` |
| GitHub Pages | Публичный репозиторий, Settings → Pages, ветка и папка с этими файлами | Аккаунт GitHub бесплатный, карта не нужна | Адрес `*.github.io` |

После публикации откройте сайт в Safari на iPhone: Поделиться → «На экран Домой». Ярлык откроется без панели Safari (`display: standalone` и `apple-touch-icon`).

Вход — email и пароль пользователя с ролью `owner` в `allowlist`. Ключ в форме — публичный `sb_publishable_`, не `service_role`.
