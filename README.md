# ElfShop — каталог вейпов

Статический сайт-каталог одноразовых вейпов для GitHub Pages.

## Структура

```
elf_shop/
├── index.html      # Главная страница
├── style.css       # Стили (тёмная тема)
├── products.js     # Массив товаров
├── images/         # Фото товаров (добавь сам)
└── README.md
```

## Настройка перед деплоем

### 1. Контакт для заказов

В `index.html` найди строку:

```js
const CONTACT_URL = 'https://wa.me/79000000000';
```

Замени на свой номер WhatsApp или ник Telegram:

```js
// WhatsApp (номер без +, пробелов и скобок):
const CONTACT_URL = 'https://wa.me/79161234567';

// Telegram:
const CONTACT_URL = 'https://t.me/your_username';
```

### 2. Instagram

В `index.html` в двух местах замени `@your_instagram` и ссылку:

```html
<a href="https://instagram.com/your_instagram" ...>@your_instagram</a>
```

### 3. Фото товаров

Создай папку `images/` и положи туда фото с именами из `products.js`.  
Если фото нет — карточка показывает цветной placeholder автоматически.

Рекомендуемый размер: **600×800 px** (соотношение 3:4).

### 4. Товары

Редактируй массив в `products.js`:

```js
{
  id: 11,                              // уникальный номер
  name: "Elfbar BC5000",               // название устройства
  brand: "Elfbar",                     // Elfbar | RandM | Waspe | Oxbar
  flavor: "Blueberry Ice",             // вкус
  puffs: 5000,                         // количество затяжек
  price: 890,                          // цена в рублях
  image: "images/elfbar-bc5000.jpg",   // путь к фото
  color: "#3a7bd5"                     // цвет placeholder (hex)
}
```

---

## Деплой на GitHub Pages

### Шаг 1 — Создай репозиторий

1. Зайди на [github.com](https://github.com) → **New repository**
2. Имя: `elf-shop` (или любое другое)
3. Видимость: **Public**
4. Нажми **Create repository**

### Шаг 2 — Загрузи файлы

```bash
cd /path/to/elf_shop

git init
git add .
git commit -m "Initial commit"

git remote add origin https://github.com/YOUR_USERNAME/elf-shop.git
git branch -M main
git push -u origin main
```

### Шаг 3 — Включи GitHub Pages

1. Репозиторий → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)`
4. Нажми **Save**

### Шаг 4 — Готово!

Через 1–2 минуты сайт будет доступен по адресу:

```
https://YOUR_USERNAME.github.io/elf-shop/
```

---

## Кастомный домен (опционально)

1. Settings → Pages → **Custom domain** → введи `elfshop.ru`
2. У регистратора домена добавь DNS-записи:
   ```
   A     @    185.199.108.153
   A     @    185.199.109.153
   A     @    185.199.110.153
   A     @    185.199.111.153
   CNAME www  YOUR_USERNAME.github.io.
   ```
3. Включи **Enforce HTTPS** в настройках Pages

---

## Дисклеймер

Сайт предназначен для лиц **старше 18 лет**.  
Продажа никотиносодержащих изделий несовершеннолетним запрещена.
