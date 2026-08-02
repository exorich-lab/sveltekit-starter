# SvelteKit Starter

Готовый стартер для быстрого запуска сайтов и фронтендов.

**Стек:** SvelteKit 2 · Svelte 5 (runes) · TypeScript · Tailwind CSS v4 · shadcn-svelte · Vite 8

## Что внутри

- ⚡ **SvelteKit 2** — файловая маршрутизация, SSR, адаптеры
- 🧪 **Svelte 5 runes** — принудительный runes-режим (никакого legacy-синтаксиса)
- 🎨 **Tailwind CSS v4** — через `@tailwindcss/vite`, без `tailwind.config`
- 🧩 **shadcn-svelte** — 15+ готовых компонентов в `src/lib/components/ui/` (button, card, badge, input, dialog, dropdown-menu, tabs, switch, tooltip, sonner и др.)
- 🌙 **Тёмная тема** — переключатель «Светлая / Тёмная / Системная» (mode-watcher, выбор хранится в localStorage, без вспышки при загрузке)
- 🔔 **Тосты** — svelte-sonner подключён
- 🛠 **Тулинг** — TypeScript, ESLint, Prettier, svelte-check

## Быстрый старт

```bash
pnpm install
pnpm dev          # http://localhost:5173
```

## Скрипты

| Команда        | Описание                      |
| -------------- | ----------------------------- |
| `pnpm dev`     | Dev-сервер с HMR              |
| `pnpm build`   | Продакшн-сборка               |
| `pnpm preview` | Превью продакшн-сборки        |
| `pnpm check`   | Проверка типов (svelte-check) |
| `pnpm lint`    | Prettier + ESLint             |
| `pnpm format`  | Автоформатирование            |

## Добавление компонентов shadcn

```bash
pnpm dlx shadcn-svelte@latest add <component>
```

Например: `pnpm dlx shadcn-svelte@latest add select calendar sidebar`.

## Структура

```
src/
├── app.css                  # Tailwind v4 + тема shadcn (CSS-переменные, dark mode)
├── app.html                 # anti-FOUC скрипт тёмной темы
├── lib/
│   ├── components/
│   │   ├── theme-toggle.svelte   # переключатель темы
│   │   └── ui/                   # shadcn-компоненты
│   └── utils.ts             # cn() + type-хелперы
└── routes/
    ├── +layout.svelte       # шапка, футер, ModeWatcher, Toaster
    └── +page.svelte         # демо-страница
```

## Тёмная тема

- Класс `dark` вешается на `<html>` (mode-watcher).
- CSS-переменные темы — в `src/app.css` (`:root` / `.dark`, oklch).
- Скрипт в `src/app.html` применяет сохранённую тему до первой отрисовки — нет «вспышки».
- Изменить дефолтный цвет можно через `pnpm dlx shadcn-svelte@latest apply <preset>` или правкой переменных в `app.css`.

## Деплой

По умолчанию стоит `@sveltejs/adapter-auto` — соберётся под Vercel, Netlify, Cloudflare Pages и др. Для выделенного Node-сервера замените на `adapter-node`:

```bash
pnpm add -D @sveltejs/adapter-node
```

и обновите `vite.config.ts` (см. https://svelte.dev/docs/kit/adapters).

## Полезные ссылки

- [SvelteKit docs](https://svelte.dev/docs/kit)
- [Svelte 5 runes](https://svelte.dev/docs/svelte/what-are-runes)
- [Tailwind CSS v4](https://tailwindcss.com/docs)
- [shadcn-svelte](https://shadcn-svelte.com)
