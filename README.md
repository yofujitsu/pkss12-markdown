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
sequenceDiagram
    participant User as Пользователь
    participant WebApp as ВебПриложение
    participant API as API Сервер
    participant Database as База данных
    participant SteamAPI as Steam API

    User ->> WebApp: Открывает платформу
    WebApp ->> API: Авторизация через Steam
    API ->> SteamAPI: Запрос данных пользователя
    SteamAPI -->> API: Данные пользователя
    API ->> Database: Сохранение данных
    WebApp -->> User: Успешная авторизация

    User ->> WebApp: Запрашивает статистику героя
    WebApp ->> API: Получить данные героя
    API ->> Database: Проверить данные
    alt Данные в базе есть
        Database -->> API: Вернуть данные
    else Данных нет
        API ->> SteamAPI: Запросить данные героя
        SteamAPI -->> API: Вернуть данные
        API ->> Database: Сохранить данные
    end
    API -->> WebApp: Данные героя
    WebApp -->> User: Показать статистику

quadrantChart
    title Приоритеты функционала Deadlock Tracker
    "Высокая ценность" : [Авторизация, Статистика игроков]
    "Низкая ценность" : [Статистика предметов]
    "Высокие усилия" : [Интеграция с Steam API]
    "Низкие усилия" : [Улучшение интерфейса]
gitGraph
    commit id: "Инициализация проекта"
    branch feature/API
    commit id: "Реализация взаимодействия с Steam API"
    checkout main
    merge feature/API
    branch feature/Frontend
    commit id: "Разработка интерфейса пользователя"
    checkout main
    merge feature/Frontend
    branch feature/Database
    commit id: "Настройка базы данных"
    checkout main
    merge feature/Database
```
