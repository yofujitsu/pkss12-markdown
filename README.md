# Deadlock Tracker Documentation

## Описание проекта

Deadlock Tracker — это веб-платформа для отслеживания игровой статистики популярной игры **Deadlock**. Пользователи могут просматривать:
- Статистику матчей.
- Детальную статистику героев, предметов и сборок.
- Статистику других игроков.
- Свою собственную статистику (доступно только для авторизованных пользователей).

Система интегрируется с **Steam API** для получения данных и сохраняет обработанную информацию в базе данных для последующего отображения.

---

## Структура функциональных возможностей

```mermaid
mindmap
  root((Deadlock Tracker))
    Статистика
      Матчи
      Герои
      Игроки
      Предметы
    Пользователь
      Авторизация
      Просмотр своей статистики
    Технологии
      API-интеграция
      Веб-интерфейс
        База данных
```
## Путешествие пользователя Deadlock Tracker
```mermaid
journey
  section Посещение сайта
    Пользователь: Переходит на главную страницу: 5: Удобно
  section Авторизация
    Пользователь: Вводит данные Steam: 4: Ожидаемо
    Система: Получает данные пользователя: 5: Быстро
  section Работа со статистикой
    Пользователь: Открывает статистику героя: 5: Информативно
    Система: Запрашивает данные с API: 4: Быстро
    Пользователь: Смотрит собственные данные: 5: Полезно
```
## Приоритеты функционала
```mermaid
graph TD
    A[Приоритеты функционала] -->|Высокая ценность| B[Авторизация]
    A -->|Высокая ценность| C[Статистика игроков]
    A -->|Низкая ценность| D[Статистика предметов]
    A -->|Высокие усилия| E[Интеграция с Steam API]
    A -->|Низкие усилия| F[Улучшение интерфейса]
```
## История разработки

## Git Graph for Deadlock Statistics Tracker System

```mermaid
gitGraph
   commit id: "Initialize project"
   branch develop
   checkout develop
   commit id: "Set up CI/CD pipeline"
   commit id: "Create API Gateway project"

   branch feature/frontend
   checkout feature/frontend
   commit id: "Implement frontend UI"
   commit id: "Add user authentication"
   checkout develop
   merge feature/frontend id: "Merge frontend to develop"

   branch feature/user-service
   checkout feature/user-service
   commit id: "Develop UserService"
   commit id: "Implement user authentication logic"
   checkout develop
   merge feature/user-service id: "Merge UserService to develop"

   branch feature/stats-service
   checkout feature/stats-service
   commit id: "Develop StatsService"
   commit id: "Add game stats processing"
   checkout develop
   merge feature/stats-service id: "Merge StatsService to develop"

   branch feature/steam-service
   checkout feature/steam-service
   commit id: "Develop SteamService"
   commit id: "Integrate with external Steam API"
   checkout develop
   merge feature/steam-service id: "Merge SteamService to develop"

   branch feature/database
   checkout feature/database
   commit id: "Design database schema"
   commit id: "Optimize queries for performance"
   checkout develop
   merge feature/database id: "Merge database updates to develop"

   branch staging
   checkout staging
   commit id: "Deploy to Staging Environment"
   branch main
   checkout main
   merge staging id: "Release version 1.0

```
