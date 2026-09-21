# Лабораторная работа №1

Приложение на Ruby on Rails с несколькими текстовыми страницами и проверкой работоспособности (health check).

## Описание

Минимальное Rails-приложение без базы данных и представлений (views) — ответы отдаются
напрямую из контроллера через `render html:`. Приложение демонстрирует базовую маршрутизацию
Rails и поддержку не-ASCII (UTF-8) текста.

## Структура проекта

Ниже — файлы и каталоги, значимые именно для этой лабораторной работы (остальное — стандартный
скелет, сгенерированный `rails new`):

```
hello_app/
├── app/
│   └── controllers/
│       └── application_controller.rb   # экшены hello и goodbye
├── config/
│   └── routes.rb                       # маршруты приложения
├── bin/
│   ├── rails                           # запуск rails-команд
│   └── dev                             # запуск dev-сервера
├── Gemfile                             # зависимости (Rails 8.1, Puma, SQLite и др.)
└── README.md
```

## Маршруты

| Метод | Путь       | Экшен                       | Ответ                  |
|-------|------------|------------------------------|-------------------------|
| GET   | `/`        | `application#hello`          | `¡Hola, mundo!`         |
| GET   | `/goodbye` | `application#goodbye`        | `goodbye, world!`       |
| GET   | `/up`      | `rails/health#show`          | 200, если приложение живо (health check), иначе 500 |

Маршруты определены в [`config/routes.rb`](config/routes.rb), логика экшенов — в
[`app/controllers/application_controller.rb`](app/controllers/application_controller.rb).

## Требования

* Ruby 3.4.10 (см. [`.ruby-version`](.ruby-version))
* Bundler

## Запуск

```bash
bundle install
bin/rails server
```

Приложение будет доступно на [http://localhost:3000](http://localhost:3000).

Проверка работоспособности: [http://localhost:3000/up](http://localhost:3000/up).

## Автор

Святослав
