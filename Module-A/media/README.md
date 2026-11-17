# Ассеты «Цифровой навигатор»

Папка `media/` готова к загрузке на сервер рядом с `index.html`. Все изображения нарисованы с нуля (векторные SVG + растровые копии), шрифты — под свободной лицензией OFL, поэтому ограничений по правам нет.

## Структура
```
media/
├── favicon.ico
├── fonts/            Inter (400–800), Lora; .woff для сайта, .otf/.ttf — исходники; fonts.css; лицензия OFL
├── css/tokens.css    палитра и переменные (цвета направлений, шрифты, радиусы)
├── icons/
│   ├── ui/           44 интерфейсных иконки (SVG, stroke=currentColor)
│   ├── directions/   бейджи направлений: it, engineering, design, creativity, sport (SVG + PNG)
│   └── favicon/      favicon.svg/.ico, 16/32/48, apple-touch-icon, android 192/512, maskable, site.webmanifest
├── images/
│   ├── logo/         logo, logo-white, logo-mark, logo-mark-mono (SVG + PNG)
│   ├── hero/         иллюстрация главной (SVG, WebP, PNG)
│   ├── about/        иллюстрация секции «О платформе»
│   ├── benefits/     4 иконки «Польза дополнительного образования»
│   ├── courses/      5 обложек курсов 800×500 (SVG, WebP, JPG) + thumbs/ 400×250
│   ├── avatars/      parent-woman, parent-man, child-boy, child-girl
│   ├── errors/       404
│   ├── states/       empty-courses (пустой кабинет), success (модальное окно)
│   ├── backgrounds/  pattern-dots, blob-1..3, wave-footer
│   └── og/           og-image 1200×630 для соцсетей
├── data/courses.json  5 курсов из задания + пути к обложкам
└── text/              тексты: о платформе, польза образования, контакты, тексты интерфейса
```

## Подключение
```html
<link rel="icon" href="media/favicon.ico" sizes="48x48">
<link rel="icon" href="media/icons/favicon/favicon.svg" type="image/svg+xml">
<link rel="apple-touch-icon" href="media/icons/favicon/apple-touch-icon.png">
<link rel="manifest" href="media/icons/favicon/site.webmanifest">
<meta name="theme-color" content="#3D5AFE">
<meta property="og:image" content="media/images/og/og-image.jpg">
<link rel="stylesheet" href="media/fonts/fonts.css">
<link rel="stylesheet" href="media/css/tokens.css">
```
```html
<picture>
  <source srcset="media/images/courses/course-1-first-code.webp" type="image/webp">
  <img src="media/images/courses/course-1-first-code.jpg" alt="Курс «Первый код»" width="800" height="500" loading="lazy">
</picture>
```

## Соответствие курсов и обложек
| ID | Курс | Файл |
|---|---|---|
| 1 | Первый код | course-1-first-code |
| 2 | Юный робототехник | course-2-robotics |
| 3 | Цифровой художник | course-3-digital-artist |
| 4 | Python Start | course-4-python-start |
| 5 | 3D-моделирование | course-5-3d-modeling |

## Заметки
- Иконки из `icons/ui/` используют `currentColor` — цвет задаётся CSS (`color`). Если подключаете через `<img>`, цвет не поменять: вставляйте SVG инлайном или через CSS `mask-image`.
- В логотипе и 404 текст переведён в контуры — они выглядят одинаково без подключения шрифтов.
- В иллюстрациях есть мягкая анимация (мигающий курсор, пульс антенны), она работает, если SVG подключён через `<img>` или инлайном.
- Фавиконки в сети: `favicon.ico` лежит и в корне `media/`; для работы в браузере по умолчанию скопируйте его в корень сайта.
- Шрифтовые .woff — подмножества (латиница + кириллица + №, ₽, стрелки). Формат .woff2 в этой среде собрать не удалось (нет brotli); при желании сконвертируйте сами — Chrome поддерживает оба формата.
