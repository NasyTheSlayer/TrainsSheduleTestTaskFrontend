# 🚄 Train Schedule App

<div align="center">

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Chakra UI](https://img.shields.io/badge/Chakra_UI-319795?style=for-the-badge&logo=chakra-ui&logoColor=white)
![React Query](https://img.shields.io/badge/React_Query-FF4154?style=for-the-badge&logo=react-query&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-0055FF?style=for-the-badge&logo=framer&logoColor=white)

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
│   ├── 🧰 ui/                 # Базові елементи
│   │   ├── LoadingAnimation.tsx
│   │   └── ErrorDisplay.tsx
│   ├── 🚂 trains/             # Компоненти поїздів
│   │   ├── TrainScheduleTable.tsx
│   │   └── BackgroundTrains/
│   └── 📝 TrainScheduleModal.tsx
│
├── 🌐 contexts/               # React контексти
│   └── AuthContext.tsx        # Стан автентифікації
│
├── 🪝 hooks/                  # Кастомні React хуки
│   └── useTrainSearch.ts      # Логіка пошуку і сортування
│
├── 🛠️ lib/                    # Утиліти та хелпери
│   ├── api.ts                 # API функції
│   └── axios.ts               # Конфігурація Axios
│
├── 🎭 styles/                 # Стилі та теми
│   └── buttonStyles.ts        # Стилі кнопок
│
└── 📋 types/                  # TypeScript типи
    └── train.ts               # Інтерфейси даних поїздів
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

### Адаптивний дизайн

- Повністю адаптивний інтерфейс з використанням Chakra UI
- Мобільна навігація та оптимізовані під дотик елементи
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

## 📱 Скріншоти

<div align="center">
<i>Скріншоти будуть додані найближчим часом</i>
</div>
