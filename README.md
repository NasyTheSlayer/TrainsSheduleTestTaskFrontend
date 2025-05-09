# 🚄 Train Schedule App

<div align="center">

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Chakra UI](https://img.shields.io/badge/Chakra_UI-319795?style=for-the-badge&logo=chakra-ui&logoColor=white)
![React Query](https://img.shields.io/badge/React_Query-FF4154?style=for-the-badge&logo=react-query&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-0055FF?style=for-the-badge&logo=framer&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=for-the-badge&logo=eslint&logoColor=white)
![Prettier](https://img.shields.io/badge/Prettier-F7B93E?style=for-the-badge&logo=prettier&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)

</div>

Веб-додаток для перегляду та управління розкладами поїздів, з сучасним інтерфейсом та розширеними можливостями пошуку.

---

## ✨ Основні функції

<table>
  <tr>
    <td width="50%">
      <h3>🔐 Авторизація</h3>
      <ul>
        <li>Захищений вхід та реєстрація користувачів</li>
        <li>JWT автентифікація</li>
        <li>Валідація форм з Zod</li>
      </ul>
    </td>
    <td width="50%">
      <h3>🔍 Розширений пошук</h3>
      <ul>
        <li>Фільтрація за маршрутом і датою</li>
        <li>Сортування за різними параметрами</li>
        <li>Автозаповнення та підказки</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>📋 Управління розкладами</h3>
      <ul>
        <li>Перегляд, додавання, редагування розкладів</li>
        <li>Оптимістичні оновлення UI</li>
        <li>Видалення записів з підтвердженням</li>
      </ul>
    </td>
    <td width="50%">
      <h3>🎨 Сучасний інтерфейс</h3>
      <ul>
        <li>Адаптивний дизайн для різних пристроїв</li>
        <li>Анімації та переходи</li>
        <li>Темна/світла тема</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>⚙️ Якість коду</h3>
      <ul>
        <li>Строга типізація TypeScript</li>
        <li>Налаштований ESLint та Prettier</li>
        <li>Оптимізований Fast Refresh</li>
      </ul>
    </td>
    <td width="50%">
      <h3>🔄 CI/CD</h3>
      <ul>
        <li>Автоматизоване тестування</li>
        <li>Перевірка якості коду</li>
        <li>Автоматичний деплой</li>
      </ul>
    </td>
  </tr>
</table>

## 🧩 Технології

<details>
<summary><b>Frontend Stack</b></summary>

- **Next.js** - React фреймворк з App Router
- **TypeScript** - Типізована мова програмування
- **Chakra UI** - Компонентна бібліотека з підтримкою тем
- **React Query** - Управління серверним станом та кешування
- **Axios** - HTTP клієнт для API запитів
- **Framer Motion** - Бібліотека для плавних анімацій
- **React Hook Form** - Управління формами та валідація
- **Zod** - Типізована валідація схем даних
- **React Window** - Віртуалізація для ефективного рендерингу списків

</details>

<details>
<summary><b>Інструменти розробки</b></summary>

- **ESLint** - Статичний аналіз коду
- **Prettier** - Форматування коду
- **TypeScript** - Строга типізація
- **GitHub Actions** - CI/CD автоматизація
- **Husky** - Git hooks для контролю якості коду(не встиг додати)
- **lint-staged** - Перевірка змін перед комітом(не встиг додати)

</details>

## 🏗️ Архітектура проекту

```
src/
├── 📁 app/                    # Next.js App Router
│   ├── 🔒 auth/               # Сторінки автентифікації
│   ├── 🔍 search/             # Пошук розкладів
│   ├── 📄 page.tsx            # Головна сторінка
│   ├── 📐 layout.tsx          # Кореневий макет
│   └── 🔌 providers/          # Контекст-провайдери
│
├── 📦 components/             # UI компоненти
│   ├── 🧰 feedback/           # Компоненти відгуку
│   │   ├── LoadingAnimation.tsx
│   │   └── ErrorDisplay.tsx
│   ├── 🔍 search/             # Компоненти пошуку
│   │   ├── Pagination.tsx
│   │   ├── SearchBar.tsx
│   │   └── SearchForm.tsx
│   │
│   ├── 🚂 trains/             # Компоненти поїздів
│   │   ├── BackgroundTrains/  # Анімація фону
│   │   │   └── BackgroundTrains.tsx
│   │   │
│   │   ├── TrainCheduleTable/ # Таблиця розкладу (альтернативна)
│   │   │   ├── components/    # Підкомпоненти таблиці
│   │   │   │   ├── RowRenderer.tsx
│   │   │   │   ├── TableHeader.tsx
│   │   │   │   ├── TableRow.tsx
│   │   │   │   └── SortIcon.tsx
│   │   │   ├── constants/     # Константи для таблиці
│   │   │   └── TrainScheduleTable.tsx
│   │   │
│   │   ├── TrainSheduleTable/ # Основна таблиця розкладу
│   │   │   ├── components/    # Підкомпоненти таблиці
│   │   │   ├── constants/     # Константи та конфігурація
│   │   │   └── interfaces/    # Типи компонентів
│   │   │
│   │   ├── TrainSheduleModal/ # Модальне вікно поїзда
│   │   │   ├── components/    # Підкомпоненти модального вікна
│   │   │   ├── constants/     # Константи модального вікна
│   │   │   └── TrainScheduleModal.tsx
│   │   │
│   │   ├── TrainTable/        # Компонент таблиці
│   │   │
│   │   └── TrainTrack/        # Компонент треку поїзда
│   │       └── TrainTrack.tsx
│   │
│   └── NavBar.tsx             # Компонент навігації
│
├── 🌐 contexts/               # React контексти
│   └── auth/                  # Контексти авторизації
│       ├── AuthContext.ts     # Контекст авторизації
│       ├── AuthProvider.tsx   # Провайдер авторизації
│       └── useAuth.ts         # Хук авторизації
│
├── 🪝 hooks/                  # Кастомні React хуки
│   └── useTrainSearch.ts      # Логіка пошуку і сортування
│
├── 🛠️ libs/                   # Утиліти та хелпери
│   ├── api.ts                 # API функції
│   ├── axios.ts               # Конфігурація Axios
│   └── validation/            # Схеми валідації
│       ├── authSchema.ts      # Схема для авторизації
│       └── trainSheduleSchema.ts # Схема для розкладу
│
├── 🎭 styles/                 # Стилі та теми
│   ├── auth/                  # Стилі для авторизації
│   │   └── inputStyles.ts
│   └── tables/                # Стилі для таблиць
│       └── buttonStyles.ts
│
└── 📋 types/                  # TypeScript типи
    ├── train.ts               # Інтерфейси даних поїздів
    └── api.ts                 # Типи API відповідей
```

## 🚀 Особливості реалізації

### Управління формами та валідація

Форми використовують комбінацію `React Hook Form` та `Zod` для валідації:

```typescript
// Приклад схеми валідації з Zod
const trainScheduleSchema = z.object({
  trainNumber: z.string().min(3, "Номер поїзда повинен мати мінімум 3 символи"),
  departure: z.date(),
  arrival: z.date(),
  origin: z.string().min(2, "Введіть коректну станцію відправлення"),
  destination: z.string().min(2, "Введіть коректну станцію прибуття"),
  // Додаткові поля...
}).refine(data => data.arrival > data.departure, {
  message: "Час прибуття має бути пізніше часу відправлення",
  path: ["arrival"]
});
```

### Оптимізація продуктивності

- Віртуалізація списків для ефективного рендерингу великої кількості даних
- Кешування та оптимістичні оновлення з React Query
- Ефективне управління станом з використанням хуків та контекстів
- Розділення коду і ліниве завантаження для швидшого старту

### Якість коду та інструменти розробки

- **ESLint** з розширеними правилами для TypeScript та React
- **Prettier** для уніфікованого форматування коду
- **CI/CD pipeline** на базі GitHub Actions:
  - Автоматична збірка та тестування
  - Перевірка коду за допомогою лінтерів
  - Автоматичний деплой на хостинг

### Адаптивний дизайн

- Частково адаптивний інтерфейс з використанням Chakra UI
- Частково додана мобільна навігація та оптимізовані під дотик елементи
- Оптимізовані зображення та анімації

### Анімації та переходи

- Плавні переходи між сторінками за допомогою Framer Motion
- Мікроанімації для покращення UX
- Анімовані фони та елементи інтерфейсу

## 🔧 Запуск проекту

1. Клонувати репозиторій:
   ```bash
   git clone https://github.com/username/train-schedule-app.git
   cd train-schedule-app
   ```

2. Встановити залежності:
   ```bash
   npm install
   # або
   yarn install
   ```

3. Запустити локальний сервер:
   ```bash
   npm run dev
   # або
   yarn dev
   ```

4. Відкрити [http://localhost:3000](http://localhost:3000) у браузері
