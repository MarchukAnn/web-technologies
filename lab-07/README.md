# Keepsake — landing

Адаптивний односторінковий лендінг дизайн-агенції Keepsake (ЛР №7, завдання 4).

- **Демо:** https://<your-github-username>.github.io/landing-keepsake/  ← вставте посилання після публікації на GitHub Pages
- **Макет:** [Figma — Keepsake](https://www.figma.com/design/IQsFPId7DeATziA3BFtvRZ/Keepsake-%E2%80%94Kom)

## Технології
HTML5 (семантичні `header / nav / main / section / article / footer / form`, один `h1`), CSS3 (змінні в `:root`, Flexbox, media-запити), без JS, фреймворків і UI-бібліотек. Шрифти Oswald, Open Sans, Dancing Script — Google Fonts із `font-display: swap`. Іконки — inline SVG, зображення — WebP з `width/height` і `loading="lazy"`.

## Ключові рішення
- **Mobile first:** базові стилі для 375, далі `@media (min-width: 768px)` і `(min-width: 1280px)`; контейнер максимум 1100px по центру; без горизонтального скролу від 320 до 1920px (виняток — рядок чипсів на мобайлі).
- **Сітки на Flexbox без `gap` і без `grid`:** батьківський `flex-wrap` з від'ємним margin + padding на елементах (`--gutter`), ширини через `flex-basis` (100% / 50% / 33.33%).
- **Дизайн-токени** (кольори, шрифти, розміри, відступи) — тільки через CSS-змінні; значення, що змінюються по брейкпоінтах, перевизначаються в `:root` у media-запитах.
- **Мобільне меню без JS:** прихований `checkbox` поверх бургера + `:checked ~ .menu`; бургер перетворюється на хрестик.
- **Фільтр портфоліо без JS:** radio-кнопки + `:checked ~ .works__grid .card:not([data-category=…])`.
- **Ховер картки** працює також для `:focus-visible` / `:focus-within`.
- **Форма підписки:** HTML-валідація (`type="email"`, `required`), помилка через `:user-invalid` + `:has()`, success через `:target`, `aria-describedby`.
- **Fixed header** і кнопка «вгору» 44×44.
- Позиціонування `absolute/fixed` використано лише для header, меню, оверлея картки та кнопки «вгору», не для розкладки сітки.

## Структура
```
landing-keepsake/
├── index.html
├── css/ (reset.css, style.css)
├── images/ (WebP)
└── fonts/
```
