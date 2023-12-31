# Домашнее задание к занятию «Микросервисы: принципы» - `Мальцев Виктор`

---

Задача 1: API Gateway

Предложите решение для обеспечения реализации API Gateway. Составьте сравнительную таблицу возможностей различных программных решений. На основе таблицы сделайте выбор решения.

Решение должно соответствовать следующим требованиям:
1. маршрутизация запросов к нужному сервису на основе конфигурации,
2. возможность проверки аутентификационной информации в запросах,
3. обеспечение терминации HTTPS.

Обоснуйте свой выбор.

Ответ:
 
Для создания API Gateway в микросервисной архитектуре можyj рассмотреть несколько решений, таких как Kong, Apigee, AWS API Gateway, и Nginx. 
Cравнение основных характеристик этих решений и на их основе можно сделать выбор.

1. Kong:

    Маршрутизация: Поддерживает сложные правила маршрутизации и перенаправления.
    Аутентификация: Поддерживает различные методы, включая OAuth 2.0, Basic Auth, JWT, и другие.
    Терминация HTTPS: Поддерживается.

2. Apigee (от Google):

    Маршрутизация: Эффективная маршрутизация с поддержкой API версионирования.
    Аутентификация: Предлагает обширные возможности для аутентификации и авторизации.
    Терминация HTTPS: Поддерживается, с дополнительными функциями безопасности.

3. AWS API Gateway:

    Маршрутизация: Тесно интегрируется с другими сервисами AWS, предоставляя гибкую маршрутизацию.
    Аутентификация: Интеграция с AWS Identity and Access Management (IAM) и Cognito для аутентификации.
    Терминация HTTPS: Автоматически поддерживается.

4. Nginx:

    Маршрутизация: Высокопроизводительная и настраиваемая маршрутизация.
    Аутентификация: Может быть настроен для работы с различными методами аутентификации.
    Терминация HTTPS: Поддерживается, с возможностью настройки.

На основе этих данных выбор зависит от потребностей организации:

1. Если нужен мощный, гибко настраиваемый API Gateway и инфраструктура уже развернута в облаке AWS, AWS API Gateway может быть лучшим выбором.
2. Для более общего решения с широким спектром плагинов и настроек, Kong является отличным выбором.
3. Если компания ищет решение с дополнительными функциями управления API и аналитики, Apigee может быть подходящим вариантом.
4. Для сценариев, требующих высокой производительности и гибкости на уровне веб-сервера, Nginx может быть лучшим решением.

Выбор должен учитывать такие факторы, как интеграция с существующей инфраструктурой, специфические требования к безопасности, масштабируемость и управление конфигурацией.

---

Задача 2: Брокер сообщений

Составьте таблицу возможностей различных брокеров сообщений. На основе таблицы сделайте обоснованный выбор решения.

Решение должно соответствовать следующим требованиям:

    поддержка кластеризации для обеспечения надёжности,
    хранение сообщений на диске в процессе доставки,
    высокая скорость работы,
    поддержка различных форматов сообщений,
    разделение прав доступа к различным потокам сообщений,
    простота эксплуатации.

Обоснуйте свой выбор.

Ответ:

Для выбора брокера сообщений, который соответствует требованиям, можно рассмотреть следующие популярные решения: Apache Kafka, RabbitMQ, ActiveMQ, и Amazon SQS. 
Сравнительная таблица их возможностей:

1. Apache Kafka:

    Кластеризация: Отличная поддержка с использованием ZooKeeper.
    Хранение сообщений: Сообщения хранятся на диске с возможностью настройки времени хранения.
    Скорость работы: Высокопроизводительный, особенно в системах с большими объемами данных.
    Форматы сообщений: Поддерживает различные форматы через сериализацию.
    Разделение прав доступа: Поддерживает разделение через ACL.
    Простота эксплуатации: Требует определенного уровня знаний для управления и мониторинга.

2. RabbitMQ:

    Кластеризация: Поддерживается, но может быть сложнее в настройке по сравнению с Kafka.
    Хранение сообщений: Поддерживает хранение сообщений на диске.
    Скорость работы: Хорошая производительность, особенно в системах с меньшими объемами данных.
    Форматы сообщений: Гибкая поддержка различных форматов.
    Разделение прав доступа: Поддерживается.
    Простота эксплуатации: Дружелюбнее для новых пользователей.

3. ActiveMQ:

    Кластеризация: Поддерживается, но может быть менее производительной.
    Хранение сообщений: Поддерживает устойчивое хранение сообщений.
    Скорость работы: Ниже, чем у Kafka и RabbitMQ.
    Форматы сообщений: Поддерживает множество форматов.
    Разделение прав доступа: Поддерживается.
    Простота эксплуатации: Сравнительно прост в использовании.

4. Amazon SQS:

    Кластеризация: Управляется AWS, высокая надежность без необходимости ручной настройки.
    Хранение сообщений: Гарантируется доставка, но с некоторыми ограничениями по времени хранения.
    Скорость работы: Хорошая, но может быть ограничена сетевыми задержками.
    Форматы сообщений: Поддерживает различные форматы, но с некоторыми ограничениями.
    Разделение прав доступа: Интегрируется с IAM для управления доступом.
    Простота эксплуатации: Очень прост в настройке и использовании, особенно в экосистеме AWS.

Выбор зависит от специфических требований системы. Если нужен высокопроизводительный брокер с отличной поддержкой кластеризации и хранением больших объемов данных, Apache Kafka является отличным выбором. Для более простой системы с меньшими требованиями к производительности, RabbitMQ или ActiveMQ могут быть более подходящими. Если  инфраструктура уже находится на AWS, Amazon SQS может предложить наиболее удобное решение с минимальными затратами на настройку и обслуживание.

---

Задача 3: API Gateway * (необязательная)
Есть три сервиса:
minio

хранит загруженные файлы в бакете images,
S3 протокол,
uploader

принимает файл, если картинка сжимает и загружает его в minio,
POST /v1/upload,
security

регистрация пользователя POST /v1/user,
получение информации о пользователе GET /v1/user,
логин пользователя POST /v1/token,
проверка токена GET /v1/token/validation.
Необходимо воспользоваться любым балансировщиком и сделать API Gateway:
POST /v1/register

Анонимный доступ.
Запрос направляется в сервис security POST /v1/user.
POST /v1/token

Анонимный доступ.
Запрос направляется в сервис security POST /v1/token.
GET /v1/user

Проверка токена. Токен ожидается в заголовке Authorization. Токен проверяется через вызов сервиса security GET /v1/token/validation/.
Запрос направляется в сервис security GET /v1/user.
POST /v1/upload

Проверка токена. Токен ожидается в заголовке Authorization. Токен проверяется через вызов сервиса security GET /v1/token/validation/.
Запрос направляется в сервис uploader POST /v1/upload.
GET /v1/user/{image}

Проверка токена. Токен ожидается в заголовке Authorization. Токен проверяется через вызов сервиса security GET /v1/token/validation/.
Запрос направляется в сервис minio GET /images/{image}.
Ожидаемый результат
Результатом выполнения задачи должен быть docker compose файл, запустив который можно локально выполнить следующие команды с успешным результатом. Предполагается, что для реализации API Gateway будет написан конфиг для NGinx или другого балансировщика нагрузки, который будет запущен как сервис через docker-compose и будет обеспечивать балансировку и проверку аутентификации входящих запросов. Авторизация curl -X POST -H 'Content-Type: application/json' -d '{"login":"bob", "password":"qwe123"}' http://localhost/token

Загрузка файла

curl -X POST -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJib2IifQ.hiMVLmssoTsy1MqbmIoviDeFPvo-nCd92d4UFiN2O2I' -H 'Content-Type: octet/stream' --data-binary @yourfilename.jpg http://localhost/upload

Получение файла curl -X GET http://localhost/images/4e6df220-295e-4231-82bc-45e4b1484430.jpg

Ответ:

Кофигурационный файл nginx

```
events {
    worker_connections 1024;
}

http {
    server {
        listen 8080;

        location /token {
            proxy_pass http://security:3000/v1/token;
        }

        location /register {
            proxy_pass http://security:3000/v1/user;
        }

        location /user {
            auth_request /token/validation;
            proxy_pass http://security:3000/v1/user;
        }

        location /upload {
            auth_request /token/validation;
            proxy_pass http://uploader:3000/v1/upload;
        }

        location /user/(.+) {
            auth_request /token/validation;
            proxy_pass http://minio:9000/images/$1;
        }

        location = /token/validation {
            internal;
            proxy_pass http://security:3000/v1/token/validation;
            proxy_pass_request_body off;
            proxy_set_header Content-Length "";
            proxy_set_header X-Original-URI $request_uri;
        }
    }
}

```


