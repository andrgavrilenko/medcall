# MedCall — Вызов врача на дом

> Мобильная лендинг-страница для приёма онлайн-заявок на выезд врача. Один файл, никаких зависимостей.

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JS](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![EmailJS](https://img.shields.io/badge/EmailJS-4A90D9?style=flat&logoColor=white)

---

## Демо

Открой `index.html` в браузере — готово. Никаких серверов, сборщиков и `npm install`.

---

## Что внутри

| Раздел | Описание |
|--------|----------|
| **Hero** | Заголовок, слоган, три бейджа-характеристики |
| **Статистика** | 24/7 / 40–90 мин / 12+ специалистов |
| **Как это работает** | Три шага с карточками |
| **Форма** | Имя, телефон, адрес, симптомы, тип вызова |
| **Footer** | Навигация, копирайт, дисклеймер |

### Ключевые фичи

- **Переключатель типа вызова** — «Обычный» (зелёный) / «Срочно!» (оранжево-красный)
- **Маска телефона** — автоформат `+7 (___) ___-__-__` при вводе
- **Валидация** — подсветка незаполненных полей + flash кнопки
- **Отправка email** — через EmailJS без бекенда (200 писем/мес бесплатно)
- **Success-стейт** — чекмарк + подтверждение с временем прибытия
- **Анимации** — fade-up с stagger-задержкой на всех блоках
- **Ссылка на звонок** — `tel:` открывает дозвон на мобильном

---

## Стек

- **HTML + CSS + Vanilla JS** — никаких фреймворков
- **Google Fonts** — Playfair Display (заголовки) + Mulish (текст)
- **EmailJS Browser SDK v4** — отправка писем со стороны клиента

---

## Настройка Email

Письмо с заявкой приходит через [EmailJS](https://www.emailjs.com/) — бесплатно до 200 заявок/мес.

### Шаги

1. Зарегистрируйтесь на [emailjs.com](https://www.emailjs.com/)
2. **Email Services** → добавьте Gmail / Yandex / Mail.ru → скопируйте `Service ID`
3. **Email Templates** → создайте шаблон → скопируйте `Template ID`

   Доступные переменные в шаблоне:

   | Переменная | Значение |
   |-----------|---------|
   | `{{urgency}}` | `Обычный вызов` или `🚨 СРОЧНО` |
   | `{{from_name}}` | Имя и фамилия пациента |
   | `{{phone}}` | Номер телефона |
   | `{{address}}` | Адрес выезда |
   | `{{symptoms}}` | Жалобы/симптомы |
   | `{{time}}` | Дата и время заявки |

4. **Account → API Keys** → скопируйте `Public Key`
5. В `index.html` найдите блок конфигурации и вставьте ключи:

```js
const EMAILJS_PUBLIC_KEY  = 'ваш_public_key';
const EMAILJS_SERVICE_ID  = 'service_xxxxxxx';
const EMAILJS_TEMPLATE_ID = 'template_xxxxxxx';
```

---

## Деплой

### GitHub Pages

```
Settings → Pages → Branch: main → / (root) → Save
```

Сайт появится по адресу `https://andrgavrilenko.github.io/medcall/` через ~30 секунд.

### Netlify Drop (быстрее всего)

Перетащите папку с `index.html` на [app.netlify.com/drop](https://app.netlify.com/drop) — сразу получите публичную ссылку.

---

## Структура

```
medcall/
└── index.html    # единственный файл — весь HTML, CSS и JS
```

---

## Дизайн-решения

| Параметр | Значение |
|----------|---------|
| Основной цвет | `#1B4F45` — тёмно-зелёный (доверие, медицина) |
| Фон | `#F7F3EE` — тёплый офф-уайт |
| Акцент «Срочно» | `#E05A2B` — оранжево-красный |
| Шрифт заголовков | Playfair Display (серьёзность, доверие) |
| Шрифт текста | Mulish (читаемость, лёгкость) |
| Макс. ширина | 430 px — iPhone 14 Pro Max |

---

## Лицензия

MIT — используйте свободно.
