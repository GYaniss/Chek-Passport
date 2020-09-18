# CHEK_PASSPORT
ASP.Net Core 3.1

Реализовать ПО (использую технологии .NET или .NETCore), получающее бизнес данные (результат проверки паспортных данных) в асинхронном режиме. 
Сервис ведомства отвечает на запрос в синхронном режиме (т.е., присылает результат проверки в ответе на запрос).

REST Web API (http://localhost/api/passport/ser/nom) 
Кеширование web запросов в MemoryCache обеспечивает снятие задержек между медленным сторонним web-api и клиентами.

Не применимо в реальности:

1)Не обеспечивается защита персональных данных: хранение данных и передача от сервера к клиенту.

2)Перезапуск процесса web сервиса ASP.NET Core (сервера) - удаляет все запросы из локального кеша.

3)Отсутствует возможность масштабирования при увеличении нагрузки - текущая производительность определяется существующим ПО и железом из за локальности кеша.

Решение:
1) JSON Web Tokens
2) БД Redis
3) Переход на микросервисную архитектуру - контейнерзация в Docer: Сервер регистрации клиентов(SSL ON), Сервер кэша Redis, Сервера REST Web API (SSL Off), Kubernetes 


