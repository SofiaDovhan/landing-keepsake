# Keepsake — адаптивний лендінг дизайн-агенції
Макет: Figma «Keepsake — Responsive» (Desktop 1280, Tablet 768, Mobile 375, Mobile — menu open, UI states).

## Технології
- Семантичний HTML5 (`header`, `nav`, `main`, `section`, `article`, `footer`, `form`), один `h1`, правильна ієрархія `h2`–`h3`.
- Чистий CSS без фреймворків: Flexbox для розкладки, CSS Grid для сітки робіт, послуг, статистики та клієнтів.
- Шрифти Oswald (300/400/700), Open Sans (300/400/700), Dancing Script 700 з Google Fonts, `font-display: swap`.
- Іконки — інлайн-SVG (`<symbol>` + `<use>`).

## Основні рішення
- **Дизайн-токени** (кольори, шрифти, відступи, висота header) — у `:root`, на брейкпоінтах змінюються лише змінні.
- **Mobile first**: базові стилі для 375, далі `@media (min-width: 768px)` та `(min-width: 1280px)`. Контейнер до 1100px, центрується.
- **Мобільне меню без JS**: `<button popovertarget="main-nav">` відкриває `nav[popover]`; іконка бургера змінюється на хрестик через `:has(.nav:popover-open)`.
- **Фільтр портфоліо без JS**: радіокнопки + `:checked ~ …` і атрибут `data-category`; «All» показує 5 / 8 / 9 карточок залежно від ширини.
- **Ховер карточки** працює також для `:focus-within` і `:focus-visible`.
- **Форма підписки**: HTML-валідація (`type="email"`, `required`), стани focus / error (`:user-invalid`) / success (`:target`), помилка пов'язана з полем через `aria-describedby`.
- Fixed header, кнопка «вгору» 44×44, `aspect-ratio` для карточок (1 : 0.79, на мобайлі 1 : 0.72).
- Зображення у WebP з `width`/`height` і `loading="lazy"`.

## Структура
```
landing-keepsake/
├── index.html
├── style.css
└── images/

```
