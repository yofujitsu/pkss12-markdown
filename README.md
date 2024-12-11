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
   commit id: "Set up CI/CD pipeline"
   commit id: "Create API Gateway project"

   branch feature-user-service
   commit id: "Implement UserService"
   commit id: "Write Unit Tests for UserService"
   merge develop id: "Merge UserService to develop"

   branch feature-frontend-auth
   commit id: "Develop Frontend Authentication Module"
   merge develop id: "Merge Frontend Auth Module to develop"

   branch feature-stats-service
   commit id: "Implement StatsService"
   commit id: "Write Integration Tests for StatsService"
   merge develop id: "Merge StatsService to develop"

   branch feature-steam-service
   commit id: "Develop SteamService"
   commit id: "Integrate with External Steam API"
   merge develop id: "Merge SteamService to develop"

   branch feature-frontend-ui
   commit id: "Enhance Frontend UI (Responsive Design)"
   commit id: "Display User Stats on Frontend"
   merge develop id: "Merge Frontend UI enhancements to develop"

   branch feature-db-optimization
   commit id: "Improve Database Schema for Performance"
   merge develop id: "Merge DB optimization to develop"

   branch staging
   commit id: "Deploy to Staging Environment"
   branch main
   merge staging id: "Merge Staging to Main"
   commit id: "Release version 1.0"

   branch hotfix-fix-frontend-bug
   commit id: "Fix critical bug in frontend"
   merge main id: "Merge Hotfix to Main"
   merge develop id: "Merge Hotfix to Develop"
```
