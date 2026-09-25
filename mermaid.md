## Mermaid

**Mermain** - это сильно упрощенный и далекий аналог **UML** - спец. язык описания блок схем, графиков и диаграмм с их визуализаций.

Блок схемы
#### Базовая структура 1
```mermaid
flowchart LR
    A[Вопрос: Как сдеать список?] --> B["Ответ: - `-` или `*`"]
    A --> C["Пример: \n - Пункт 1 \n"]
```


* flowchart - блок схема
* LR - направление вправо
* A[], B[], C[] - прямоугольник
* --> - стрелка связи
#### Базовая структура 2

#### Полный  синтаксис блок-схем
```mermaid
flowchart TD
    Start([Начало]) --> Input[/Ввести X/]
    Input --> Check{X > 0?}
    Check -- Да --> Calc[Вычислить Y = X * 2]
    Check -- Нет --> Calc2[Вычислить Y = -X]
    Calc --> Output[/Вывести Y/]
    Calc2 --> Output
    Output --> End([Конец])
```

### Диаграмма последовательности
```mermaid
sequenceDiagram
    participant User
    participant API
    participant DB

    User->>API: POST /login
    API->>DB: Проверить учётные данные
    alt Успех
        DB-->>API: OK
        API-->>User: JWT token
    else Ошибка
        DB-->>API: Error
        API-->>User: 401 Unauthorized
    end
```

### Диаграмма класса
```mermaid
classDiagram
    class User {
        -id: int
        +name: string
        +login()
    }
    class Admin {
        +banUser(user: User)
    }
    Admin --|> User : наследование
    User ..> Role : зависимость
```
### Диаграмма Ганта
```mermaid
gantt
    title План проекта
    dateFormat  YYYY-MM-DD
    section Дизайн
        Макет: des1, 2025-10-01, 5d
        Утверждение: des2, after des1, 2d
    section Разработка
        API: dev1, 2025-10-05, 7d
        Frontend: dev2, after dev1, 6d
```

### Граф зависимостей
```mermaid
graph TD
    A[Frontend] --> B[API Gateway]
    B --> C[User Service]
    B --> D[Order Service]
    C --> E[DB Users]
    D --> F[DB Orders]
```
### Диаграмма состояний
```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Processing : start
    Processing --> Done : finish
    Processing --> Error : fail
    Error --> Idle : reset
    Done --> [*]
```
### Юзер Джайрни
```mermaid
timeline
    Title: Путь пользователя
    section Регистрация
        Ввод email: 2025-10-01
        Подтверждение кода: 2025-10-02
    section Покупка
        Выбор товара: 2025-10-03
        Оплата: 2025-10-04
```
### Кастомизация стилей
```mermaid
flowchart LR
    A[Важно] --> B[Обычно]
    style A fill:#f96,stroke:#333,stroke-width:2px
    style B fill:#9f9,stroke:#333
```
### Классы CSS
```mermaid
flowchart LR
    A[Узел 1]:::warn --> B[Узел 2]:::ok
    classDef warn fill:#f96,stroke:#900,color:#fff
    classDef ok fill:#9f9,stroke:#090
```
### Интерактивность

#### Круговая диаграмма
```mermaid
pie
    title ОС на десктопе
    "Windows" : 70
    "MacOS" : 25
    "Linux" : 7
    "Other" : 3
```





























