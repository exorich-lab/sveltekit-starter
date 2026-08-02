# ⚡ SvelteKit Starter

Стартер для быстрого запуска сайтов и фронтендов на **SvelteKit 2 + Svelte 5 (runes) + Tailwind CSS v4**.

| Svelte 5                                                                            | SvelteKit 2                                                                               | Tailwind CSS v4                                                                                     | TypeScript                                                                                      | shadcn-svelte                                                                         | Лицензия                                               |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| ![Svelte](https://img.shields.io/badge/Svelte-5-FF3E00?logo=svelte&logoColor=white) | ![SvelteKit](https://img.shields.io/badge/SvelteKit-2-FF3E00?logo=svelte&logoColor=white) | ![Tailwind](https://img.shields.io/badge/Tailwind%20CSS-v4-06B6D4?logo=tailwindcss&logoColor=white) | ![TypeScript](https://img.shields.io/badge/TypeScript-6-3178C6?logo=typescript&logoColor=white) | ![shadcn-svelte](https://img.shields.io/badge/shadcn--svelte-40%20компонентов-000000) | ![MIT](https://img.shields.io/badge/license-MIT-green) |

## ✨ Что внутри

- 🧩 **shadcn-svelte — 40 компонентов** в `src/lib/components/ui/`: кнопки, формы, диалоги, палитра команд, таблицы, аккордеоны, тосты и десятки других
- 🗂 **UI Kit галерея** — страница `/kit` с живыми демо всех компонентов по категориям
- 🌙 **Тёмная тема** — переключатель «Светлая / Тёмная / Системная» с сохранением выбора и без вспышки при загрузке
- ⚡ **Svelte 5 runes** — принудительный runes-режим, никакого legacy-синтаксиса
- 🎨 **Tailwind CSS v4** — без `tailwind.config`, тема на CSS-переменных (oklch)
- 🛠 **Полный тулинг** — TypeScript 6, ESLint, Prettier, svelte-check
- ✨ **Свои примитивы** — `SectionHeading`, `GlassCard` для красивых секций

## 🚀 Быстрый старт

### Способ 1 — degit (рекомендую)

[degit](https://github.com/Rich-Harris/degit) скачивает репозиторий без истории git — идеально для старта нового проекта:

```bash
npx degit exorich-lab/sveltekit-starter my-app
cd my-app
pnpm install
pnpm dev
```

Готово — сайт на http://localhost:5173. 🎉

### Способ 2 — одной командой (macOS / Linux)

```bash
npx degit exorich-lab/sveltekit-starter my-app && cd my-app && pnpm install && pnpm dev
```

### Способ 3 — alias в shell

Добавьте в `~/.zshrc` или `~/.bashrc`:

```bash
alias new-site='npx degit exorich-lab/sveltekit-starter'
```

Теперь новый проект создаётся так:

```bash
new-site my-app && cd my-app && pnpm i && pnpm dev
```

### Способ 4 — git clone

```bash
git clone https://github.com/exorich-lab/sveltekit-starter.git my-app
cd my-app
pnpm install
pnpm dev
```

> 💡 **Требования:** Node.js ≥ 22 и [pnpm](https://pnpm.io/installation).

## 🧩 UI Kit

После запуска откройте **http://localhost:5173/kit** — там все компоненты с интерактивными демо:

- **Кнопки** — 5 вариантов, 3 размера, состояния
- **Бейджи** — метки статусов и категорий
- **Формы** — input, select, checkbox, radio, switch, slider, toggle и др.
- **Обратная связь** — алерты, прогресс, скелетоны, тосты, empty-состояния
- **Данные** — карточки, аватары, таблицы, aspect-ratio
- **Оверлеи** — диалоги, sheet, popover, hover-card, палитра команд
- **Навигация** — tabs, accordion, menubar, breadcrumb, pagination

Новый компонент добавляется одной командой:

```bash
pnpm dlx shadcn-svelte@latest add <component>
```

Например: `pnpm dlx shadcn-svelte@latest add calendar sidebar`.

## 🗂 Структура проекта

```
src/
├── app.css                    # Tailwind v4 + тема shadcn (CSS-переменные, dark mode)
├── app.html                   # anti-FOUC скрипт тёмной темы
├── lib/
│   ├── components/
│   │   ├── theme-toggle.svelte     # переключатель темы
│   │   ├── section-heading.svelte  # заголовок секции (eyebrow + title + описание)
│   │   ├── glass-card.svelte       # стеклянная карточка с glow
│   │   ├── kit/
│   │   │   └── demo-card.svelte    # карточка превью для галереи
│   │   └── ui/                     # shadcn-компоненты (40 шт)
│   └── utils.ts               # cn() + type-хелперы
└── routes/
    ├── +layout.svelte         # шапка, футер, ModeWatcher, Toaster
    ├── +page.svelte           # демо-страница
    └── kit/+page.svelte       # UI Kit галерея
```

## ⚙️ Скрипты

| Команда        | Описание                      |
| -------------- | ----------------------------- |
| `pnpm dev`     | Dev-сервер с HMR              |
| `pnpm build`   | Продакшн-сборка               |
| `pnpm preview` | Превью продакшн-сборки        |
| `pnpm check`   | Проверка типов (svelte-check) |
| `pnpm lint`    | Prettier + ESLint             |
| `pnpm format`  | Автоформатирование            |

## 🌙 Тёмная тема

- Класс `dark` вешается на `<html>` (библиотека [mode-watcher](https://github.com/svecosystem/mode-watcher)).
- Выбор пользователя хранится в `localStorage`, поддерживается системная тема.
- Скрипт в `src/app.html` применяет тему до первой отрисовки — нет «вспышки».
- Переключатель — `src/lib/components/theme-toggle.svelte` (три режима: светлая, тёмная, системная).

## 🎨 Кастомизация

**Цветовая схема.** По умолчанию `neutral`. Сменить базовый цвет можно пресетом shadcn-svelte:

```bash
pnpm dlx shadcn-svelte@latest apply <preset>
```

Или вручную — отредактируйте CSS-переменные в `src/app.css` (`:root` / `.dark`, формат oklch).

**Шрифты.** Подключите шрифт в `src/app.html` и задайте его в `@theme` внутри `src/app.css`.

**Стиль компонентов.** Все компоненты — обычные `.svelte`-файлы в `src/lib/components/ui/`, их можно править напрямую.

## 🚀 Деплой

По умолчанию стоит `@sveltejs/adapter-auto` — проект соберётся под Vercel, Netlify, Cloudflare Pages и другие платформы. Для выделенного Node-сервера замените на `adapter-node`:

```bash
pnpm add -D @sveltejs/adapter-node
```

и обновите адаптер в `vite.config.ts` (см. [документацию](https://svelte.dev/docs/kit/adapters)).

## 🛠 Технологии

| Технология                                                    | Версия | Назначение                    |
| ------------------------------------------------------------- | ------ | ----------------------------- |
| [Svelte](https://svelte.dev)                                  | 5      | Компоненты, runes-режим       |
| [SvelteKit](https://svelte.dev/docs/kit)                      | 2      | Фреймворк, роутинг, SSR       |
| [Tailwind CSS](https://tailwindcss.com)                       | 4      | Стили, тема на CSS-переменных |
| [shadcn-svelte](https://shadcn-svelte.com)                    | —      | UI-компоненты                 |
| [mode-watcher](https://github.com/svecosystem/mode-watcher)   | —      | Тёмная тема                   |
| [svelte-sonner](https://github.com/svecosystem/svelte-sonner) | —      | Тосты                         |
| TypeScript / Vite                                             | 6 / 8  | Типы и сборка                 |

## 📄 Лицензия

[MIT](./LICENSE) © exorich-lab
