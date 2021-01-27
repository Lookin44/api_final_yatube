## api_final
Проект представляет собой API сервис для проекта YaTube

## Установка

Клонируйте проект на локальную машину:
```
Git clone https://github.com/lookin44/api_final_yatube.git
```

Перейти в корневую директорию проекта и активировать виртуальное окружение 
```
$ source venv/Scripts/activate
```

Установить requirements

```
$ pip install requirements.txt
```

Запуск сервера разработчика
 
```
$ python manage.py runserver
```

## Примеры использования
1. Получение токена:
Отправте POST-запрос на http://localhost:8000/api/v1/token/
Response:
```
[
    {
        "username": "Ваш username",
        "password": "Ваш пароль"
    }   
]
```

В ответ Вы получите 
```
{
        "refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTU4NzEyODUzNSwianRpIjoiNzRmMDhkOGEwODQ4NGEzYjgyZmM4MDRhMTQ3ZTEyZmIiLCJ1c2VyX2lkIjoxfQ.GW7Obcvy2TWgsEI5lqSx9BC1mxk0WnsywBHrXScs7bI",
        "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTg3MDQyNDM1LCJqdGkiOiI5ZmNjMWE5YTM5NDQ0Y2Q4OWJlOGFlOGRlYWQxNDE0ZSIsInVzZXJfaWQiOjF9.ZkEdzDN5pNgYToDRJq1CKHjIglK1ir1fhnfcXkmziuk"
}
```
где access - это сам токен. В следующих запросах передайте его в headers в формате
```
[
    {
        "Authorization": "Bearer yJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTg3MDQyNDM1LCJqdGkiOiI5ZmNjMWE5YTM5NDQ0Y2Q4OWJlOGFlOGRlYWQxNDE0ZSIsInVzZXJfaWQiOjF9.ZkEdzDN5pNgYToDRJq1CKHjIglK1ir1fhnfcXkmziuk",
    }   
]
```

2. Обработка запросов:
 * Обработка GET:
Отправте GET-запрос для получения полного списка постов на http://localhost:8000/api/v1/posts/

 * Обработка POST:
Отправте POST-запрос на http://localhost:8000/api/v1/posts/ для создания нового поста. В тело запроса передайте:
Response:
```
[
    {
        "text": "Текст поста",
    }   
]
```

