# Карточка Kate Leopard на raidopert.ru — инструкция

Дата: 26.11.2026 · v0.4.1 · © Raidopert

## Что где

| Файл | Что это |
| --- | --- |
| `kate-leopard-card.html` | **Готовый блок `<article>`** для секции «ПРОГРАММЫ» сайта — та же разметка, что у CatScribbles / MuzStudio (панель rps-panel, чипы, кнопки, строка с репозиторием) |
| `demo-kartochki-na-sayte.html` | Демо-страница: открой в браузере — увидишь карточку точно в стилях сайта |
| `kate-leopard-site.zip` | Файлы приложения для папки `public/` сборки сайта (папка `kate-leopard/`: index.html, manifest.json, sw.js, icons/) |

## Как добавить карточку (2 минуты)

1. В исходнике сайта открой страницу с секцией `id="programs"`, найди `<div class="grid gap-6 md:grid-cols-2">`.
2. Вставь содержимое `kate-leopard-card.html` после карточки MUZSTUDIO (или последней карточки).
   - В Next.js это JSX: заменить `class=` → `className=` (атрибуты svg уже совместимы), либо вставить как есть через `dangerouslySetInnerHTML`.
3. Пересобрать и задеплоить сайт как обычно.

Иконку карточка берёт с GitHub Pages (`raidopert.github.io/KAteLeoPard/icons/icon-192.png`, уже работает), ссылки — на веб-версию приложения: `https://raidopert.github.io/KAteLeoPard/`.

## Кнопки — как они работают

Приложение сейчас — **PWA (веб-приложение, ставится на телефон как приложение и работает офлайн)**:

- «Открыть веб-версию» → веб-версия в браузере.
- «Скачать на Android» → там же; Chrome показывает баннер установки / меню ⋮ → «Установить приложение». Ставится иконка на главный экран, запускается как приложение без адресной строки.
- «Скачать на iPhone» → там же; Safari: «Поделиться» → «На экран „Домой“» (ограничение iOS: установка PWA на главный экран — единственный способ ставить приложение без App Store).

Если появятся нативные сборки (Capacitor → .apk / .ipa), достаточно поменять `href` двух кнопок на ссылки релизов — разметку менять не надо.

## Хостинг на своём домене (опционально)

Чтобы приложение жило на `raidopert.ru/kate-leopard/`:

1. Разархивируй `kate-leopard-site.zip` в `public/` проекта сайта → появится `public/kate-leopard/`.
2. В `kate-leopard-card.html` замени три `https://raidopert.github.io/KAteLeoPard/` на `/kate-leopard/` и `src` иконки на `/kate-leopard/icons/icon-192.png`.
3. Пересобрать сайт. GitHub-версия при этом остаётся как резервный адрес.

## Ссылки

- Веб-версия: https://raidopert.github.io/KAteLeoPard/
- Репозиторий: https://github.com/Raidopert/KAteLeoPard
- Релиз v0.4.1 (zip): https://github.com/Raidopert/KAteLeoPard/releases/tag/v0.4.1
