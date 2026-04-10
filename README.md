Вот красивое и профессиональное README для вашего HabitTracker проекта:

```markdown
<div align="center">
  
  <img src="app/src/main/res/drawable/ic_launcher_foreground.png" width="120" height="120" alt="App Icon">
  
  # 🎯 HabitTracker
  
  **Приложение для отслеживания привычек с системой ежедневных задач и статистикой**
  
  [![Kotlin](https://img.shields.io/badge/Kotlin-2.0.0-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)](https://kotlinlang.org/)
  [![Compose](https://img.shields.io/badge/Jetpack%20Compose-2024.09.00-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white)](https://developer.android.com/jetpack/compose)
  [![Material3](https://img.shields.io/badge/Material%20Design-3-757575?style=for-the-badge&logo=materialdesign&logoColor=white)](https://m3.material.io/)
  
</div>

---

## 📱 О проекте

**HabitTracker** — это современное Android-приложение для формирования полезных привычек. Оно помогает пользователям отслеживать ежедневные задачи, анализировать прогресс и поддерживать мотивацию через систему стриков (непрерывных серий выполнений).

### ✨ Основные возможности

| Возможность | Описание |
|-------------|----------|
| ✅ **Управление задачами** | Создание, редактирование и удаление задач с приоритетами |
| 📊 **Статистика** | Визуализация прогресса по дням с процентами выполнения |
| 🔥 **Система стриков** | Отслеживание текущей и максимальной серии выполнений |
| 📅 **Ежедневные цели** | Автоматическое обновление задач каждый день |
| 🎨 **Material Design 3** | Современный интерфейс с динамическими цветами |
| 📈 **Аналитика** | Детальная статистика выполнения по каждому дню |

---

## 🏗️ Архитектура

Проект построен на **Clean Architecture** с разделением на слои:

```
┌─────────────────────────────────────────────────────┐
│                   Presentation Layer                 │
│  (Compose UI, ViewModels, Navigation)               │
├─────────────────────────────────────────────────────┤
│                     Domain Layer                     │
│  (Use Cases, Entities, Repository Interfaces)       │
├─────────────────────────────────────────────────────┤
│                      Data Layer                      │
│  (Repository Implementations, Local Database)       │
└─────────────────────────────────────────────────────┘
```

### 🛠️ Технологический стек

- **Язык**: Kotlin
- **UI**: Jetpack Compose + Material 3
- **DI**: Dagger Hilt
- **БД**: Room (SQLite)
- **Асинхронность**: Kotlin Coroutines + Flow
- **Навигация**: Compose Navigation
- **Архитектура**: MVVM + Clean Architecture
- **Минимальная версия**: Android 8.0 (API 26)
- **Target SDK**: Android 14 (API 34)

---

## 📸 Скриншоты

<div align="center">
  
| Главный экран | Статистика | Детали дня |
|:-------------:|:----------:|:----------:|
| ![Главный экран](screenshots/home_screen.png) | ![Статистика](screenshots/statistics_screen.png) | ![Детали](screenshots/details_dialog.png) |

</div>

---

## 🚀 Установка и запуск

### Требования
- Android Studio Hedgehog | 2023.1.1 или новее
- JDK 17
- Android SDK API 34+

### Шаги для установки

1. **Клонируйте репозиторий**
   ```bash
   git clone https://github.com/yourusername/HabitTracker.git
   cd HabitTracker
   ```

2. **Откройте проект в Android Studio**
   - File → Open → выберите папку проекта

3. **Соберите проект**
   ```bash
   ./gradlew build
   ```

4. **Запустите приложение**
   - Подключите устройство или запустите эмулятор
   - Нажмите `Run` (зелёная стрелка)

---

## 📁 Структура проекта

```
app/src/main/java/com/example/habittracker/
├── data/
│   ├── local/
│   │   ├── daos/           # Room DAO интерфейсы
│   │   ├── entities/       # Room сущности
│   │   ├── mappers/        # Мапперы Entity ↔ Domain
│   │   └── helpers/        # Вспомогательные классы
│   └── TaskRepositoryImpl.kt
├── domain/
│   ├── models/             # Domain модели
│   ├── TaskRepository.kt   # Интерфейс репозитория
│   └── WorkWithTime.kt     # Утилиты для работы с датами
├── presentation/
│   ├── navigation/         # Навигация
│   ├── view/               # Compose UI компоненты
│   │   ├── components/     # Переиспользуемые компоненты
│   │   └── screens/        # Экраны приложения
│   └── viewmodels/         # ViewModels
└── di/                     # Dagger Hilt модули
```

---

## 🎯 Основные функции в коде

### Создание задачи
```kotlin
viewModel.addTask(
    title = "Утренняя зарядка",
    description = "15 минут упражнений",
    priority = TaskPriority.HIGH
)
```

### Выполнение задачи
```kotlin
viewModel.completeTask(taskId)
// Автоматически обновляет стрик и статистику
```

### Получение статистики
```kotlin
val currentStreak = viewModel.currentStrick.value  // Текущая серия
val maxStreak = viewModel.maxStrick.value          // Максимальная серия
```

---

## 🔄 Работа с данными

Приложение использует **Room Database** с тремя основными таблицами:

1. **tasks** — задачи пользователя
2. **days** — ежедневная статистика
3. **max_streak** — максимальная серия

Данные автоматически синхронизируются между локальным состоянием и базой данных через корутины.

---

## 🤝 Вклад в проект

1. Форкните репозиторий
2. Создайте ветку для фичи (`git checkout -b feature/AmazingFeature`)
3. Зафиксируйте изменения (`git commit -m 'Add some AmazingFeature'`)
4. Запушьте ветку (`git push origin feature/AmazingFeature`)
5. Откройте Pull Request

---

## 📄 Лицензия

Распространяется под лицензией MIT. Смотрите файл `LICENSE` для подробностей.

---

## 📧 Контакты

Разработчик: [Ваше Имя](https://github.com/yourusername)

- GitHub: [@yourusername](https://github.com/yourusername)
- Telegram: [@yourusername](https://t.me/yourusername)

---

<div align="center">
  
  **⭐ Не забудьте поставить звезду, если проект оказался полезным! ⭐**
  
  Made with ❤️ and Kotlin
  
</div>
```

