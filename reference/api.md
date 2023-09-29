## API для поставщиков

#### Сигнал на обновление прайса
```
POST /api/v1/partner/update
{
    "token": "h39d0f93f9e895b82f1724864b7c186b",
    "url": "https://partner-site.ru/files/price.yaml",
}

200 OK
```


#### Получить статус получения заказов
```
GET /api/v1/partner/state
{
    "token": "h39d0f93f9e895b82f1724864b7c186b",
}

200 OK
{
    "state": "on",
}
```


#### Включить/выключить заказы
```
POST /api/v1/partner/state
{
    "token": "h39d0f93f9e895b82f1724864b7c186b",
    "state": "off",
}

200 OK
```


#### Получить список заказов
```
GET /api/v1/partner/order?token=h39d0f93f9e895b82f1724864b7c186b,

200 OK
{
    "orders": {
        "124": "2023-09-25 14:50:15",
        "139": "2023-09-26 10:06:22"
    }
}
```


#### Получить состав заказа
```
GET /api/v1/partner/order/124/?token=h39d0f93f9e895b82f1724864b7c186b,

200 OK
{
    "id": 124,
    "dt": "2023-09-25 14:50:15",
    "total": "1350",
    "state": "new",
    "items": [
        {
            "id": 5341532,
            "name": "товар1",
            "quantity": 3.000,
            "price": 300.00,
        },
        {
            "id": 5341345,
            "name": "товар4",
            "quantity": 1.000,
            "price": 450.00,
        }
    ]
}
```
