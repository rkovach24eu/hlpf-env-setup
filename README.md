## Student
- Name: Роман Ковач
- Group: 232/2

## Практичне заняття №2 — NestJS + PostgreSQL + Redis

## Структура репозиторію
```
.
├── src/               # NestJS source code
├── Dockerfile
├── docker-compose.yml
├── .env.example       # шаблон змінних оточення
└── README.md
```

## Запуск проекту
```bash
cp .env.example .env   # налаштувати значення
docker compose up --build
```
## Перевірка сервісів
```text
NAME                        IMAGE                COMMAND                  SERVICE    CREATED          STATUS                    PORTS
hlpf-env-setup-app-1        hlpf-env-setup-app   "docker-entrypoint.s…"   app        12 minutes ago   Up 10 minutes             0.0.0.0:3000->3000/tcp, [::]:3000->3000/tcp
hlpf-env-setup-postgres-1   postgres:16-alpine   "docker-entrypoint.s…"   postgres   22 minutes ago   Up 22 minutes (healthy)   0.0.0.0:5432->5432/tcp, [::]:5432->5432/tcp
hlpf-env-setup-redis-1      redis:7-alpine       "docker-entrypoint.s…"   redis      22 minutes ago   Up 22 minutes (healthy)   0.0.0.0:6379->6379/tcp, [::]:6379->6379/tcp
```

## Перевірка PostgreSQL
```text
                                                      List of databases
   Name    |  Owner   | Encoding | Locale Provider |  Collate   |   Ctype    | ICU Locale | ICU Rules |   Access privileges
-----------+----------+----------+-----------------+------------+------------+------------+-----------+-----------------------
 nestdb    | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           |
 postgres  | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           |
 template0 | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/nestuser          +
           |          |          |                 |            |            |            |           | nestuser=CTc/nestuser
 template1 | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/nestuser          +
           |          |          |                 |            |            |            |           | nestuser=CTc/nestuser
(4 rows)
```
## Перевірка Redis
```text
PONG
```
## Перевірка застосунку
```text
Hello World!
```
## Логи NestJS (фрагмент)
```text
app-1  | [Nest] 29  - 03/22/2026, 5:09:24 PM     LOG [NestFactory] Starting Nest application...
app-1  | [Nest] 29  - 03/22/2026, 5:09:24 PM     LOG [InstanceLoader] TypeOrmModule dependencies initialized +129ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:24 PM     LOG [InstanceLoader] ConfigHostModule dependencies initialized +1ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:24 PM     LOG [InstanceLoader] AppModule dependencies initialized +0ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:24 PM     LOG [InstanceLoader] ConfigModule dependencies initialized +0ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:25 PM     LOG [InstanceLoader] CacheModule dependencies initialized +28ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:25 PM     LOG [InstanceLoader] TypeOrmCoreModule dependencies initialized +72ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:25 PM     LOG [RoutesResolver] AppController {/}: +10ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:25 PM     LOG [RouterExplorer] Mapped {/, GET} route +9ms
app-1  | [Nest] 29  - 03/22/2026, 5:09:25 PM     LOG [NestApplication] Nest application successfully started +5ms
```