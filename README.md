# МедИнтеграция — REST API на 1С:Предприятие 8.3

Учебный проект REST API интеграции на платформе 1С:Предприятие 8.3.
Симулирует часть функциональности медицинской информационной системы.

## Технологии
- 1С:Предприятие 8.5.1
- 1С:EDT 2025.2.6
- HTTP-сервисы 1С
- IIS
- Postman

## Объекты конфигурации
- Справочники: Клиники, Пациенты, Услуги
- Документ: ЗаказУслуги
- Регистры сведений: ТарифыУслуг, ИсторияСтатусов
- Регистр накопления: ВыполненныеУслуги

## API эндпоинты

| Метод | URL | Описание |
|-------|-----|----------|
| GET | /patients/{id} | Данные пациента |
| GET | /services | Список услуг |
| POST | /orders | Создать заказ |
| GET | /orders | Список заказов |
| GET | /orders/{id} | Заказ по номеру |
| PUT | /orders/{id}/status | Изменить статус |
| GET | /reports/clinic/{id} | Отчёт по клинике |

## Примеры запросов

### Получить пациента
GET http://localhost/med_api/hs/med/patients/000000001

Authorization: Basic Auth

### Создать заказ
POST http://localhost/med_api/hs/med/orders

Content-Type: application/json
{

"clinic": "000000001",

"patient": "000000001",

"service": "000000001",

"quantity": 1,

"comment": "Тестовый заказ"

}

### Изменить статус
PUT http://localhost/med_api/hs/med/orders/000000001/status

Content-Type: application/json
{

"status": "ВРаботе",

"comment": "Пациент записан"

}

## Тестирование
Postman коллекция: `MedIntegration.postman_collection.json`
