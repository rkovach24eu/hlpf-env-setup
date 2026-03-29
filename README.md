## Student
- Name: Роман Ковач
- Group: 232/2

## Практичне заняття №3 — CRUD REST API для MiniShop

### Структура репозиторію
```text
.
├── src/
│   ├── categories/
│   │   ├── category.entity.ts
│   │   ├── categories.module.ts
│   │   ├── categories.service.ts
│   │   └── categories.controller.ts
│   ├── products/
│   │   ├── product.entity.ts
│   │   ├── products.module.ts
│   │   ├── products.service.ts
│   │   └── products.controller.ts
│   ├── migrations/
│   │   ├── 1700000001-CreateTables.ts
│   │   └── 1774807888365-AddIsActiveToProducts.ts
│   ├── data-source.ts
│   └── app.module.ts
├── Dockerfile
├── docker-compose.yml
└── README.md
```

### Запуск проекту
```bash
cp .env.example .env
docker compose up --build
```

### API Endpoints
| Method | URL | Опис |
|--------|-----|------|
| GET | /api/categories | Список категорій |
| GET | /api/categories/:id | Одна категорія |
| POST | /api/categories | Створити категорію |
| PATCH | /api/categories/:id | Оновити категорію |
| DELETE | /api/categories/:id | Видалити категорію |
| GET | /api/products | Список продуктів |
| GET | /api/products/:id | Один продукт |
| POST | /api/products | Створити продукт |
| PATCH | /api/products/:id | Оновити продукт |
| DELETE | /api/products/:id | Видалити продукт |

### Перевірка міграцій
```text
              List of relations
 Schema |    Name    | Type  |  Owner
--------+------------+-------+----------
 public | categories | table | nestuser
 public | migrations | table | nestuser
 public | products   | table | nestuser
(3 rows)
```

### Тест створення категорії
```text
id name        description         createdAt
-- ----        -----------         ---------
 2 Electronics Gadgets and devices 2026-03-29T18:25:21.060Z
```

### Тест створення продукту
```text
id          : 1
name        : iPhone 15
description :
price       : 999,99
stock       : 50
isActive    : True
category    : @{id=3}
createdAt   : 2026-03-29T18:57:24.577Z
updatedAt   : 2026-03-29T18:57:24.577Z
```

### Тест отримання продуктів
```text
id          : 1
name        : iPhone 15
description :
price       : 999.99
stock       : 50
isActive    : True
createdAt   : 2026-03-29T18:57:24.577Z
updatedAt   : 2026-03-29T18:57:24.577Z

id          : 2
name        : USB Cable
description :
price       : 9.99
stock       : 200
isActive    : True
category    :
createdAt   : 2026-03-29T18:57:39.307Z
updatedAt   : 2026-03-29T18:57:39.307Z
```

### Тест 404
```text
{"message":"Product #999 not found","error":"Not Found","statusCode":404}
```