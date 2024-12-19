# go-calc

## Описание

go-calc — это HTTP-сервис, предназначенный для выполнения арифметических вычислений. Он принимает математические выражения в виде строк, обрабатывает их и возвращает результаты. Проект написан на языке Go и может быть интегрирован с другими сервисами или использоваться как самостоятельный API.

## Функции
- **Обработка арифметических выражений**: поддерживаются операции сложения, вычитания, умножения и деления.
- **JSON API**: простой интерфейс для взаимодействия через POST-запросы.
- **Обработка ошибок**: корректная обработка некорректных выражений, деления на ноль и других возможных проблем.
- **Тестирование**: проект включает готовые тесты для проверки правильности работы.

### Требования
- Go версии 1.18 и выше.
- Установленный Git.
- Доступ в интернет для загрузки зависимостей.

### Установка
1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/Roman56-boop/go-calc.git
   cd go-calc
Установите зависимости:
go mod tidy
Запуск
В режиме разработчика
Запустите сервер:

go run cmd/go-calc/main.go
Сервер будет доступен по адресу: http://localhost:8080/api/v1/calculate.

В режиме пользователя
Соберите бинарный файл:

go build -o go-calc cmd/go-calc/main.go
Запустите его:

./ go-calc
API
POST /calculate
Принимает математическое выражение и возвращает результат.

Пример запроса

{ "expression": "3 + 2 * (1 + 4)" }
Пример ответа

{ "result": 13 }
Ошибки
Если выражение некорректно, сервер возвращает:

HTTP 400 Internal Server Error:

{ "error": "Internal server error" }
Тестирование
Для запуска тестов используйте:

go test -v ./...
Тесты проверяют корректность вычислений, обработку ошибок и работу API.

Пример использования
Вот пример, как отправить запрос к API с помощью curl:

curl -X POST http://localhost:8080/calculate \
-H "Content-Type: application/json" \
-d '{"expression": "5 * (2 + 3)"}'
Ответ:

{ "result": 25 }
