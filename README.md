# Multi-user-event-scheduling-service
# Flask framework. Comparison with Django
# Многопользовательский сервис планирования событий

Реализуем сервис для планирования событий.
Сервис должен поддерживать работу нескольких пользователей. Пользователи должны создавать событие, которое доступно остальным пользователям.
У каждого события есть следующие параметры: автор, время начала, время конца, тема и описание.
Каждый пользователь может просматривать все события, которые созданы любыми пользователями.
Каждый пользователь может редактировать, удалять и создавать события, где пользователем является он.
Должна быть реализована страница, на которой есть общий вид всех событий.

В приложении используются:
- Flask в качестве фреймворка для приложения
- celery для обработки очередей 
- PostgreSQL для хранения данных.

Чтобы запустить приложение на локальной машине нужно:
- склонировать этот репозиторий
- перейти в папку репозиторием
- установить зависимости из requirements.txt
- еслли не устоновлен docker, то устанвить
- выполнить в командной строке команду docker-compose up -d

После успешного выполнения команды, на 127.0.0.1:5000 будет доступно приложение со следующими эндпоинтами:

- /create_user -- регистрация нового пользователя
- /login -- форма логина (чтобы залогиниться нужно сначала создать пользователя)
- /schedule, / -- сводка всех существующих событий
- /event -- создание нового события
- /event/<id> -- обновление существующего события, где <id> -- это его идентификатор. Также на эту страницу можно попасть из списка событий. Редактировать можно только "свои" события. 
  
  We implement a service for event scheduling.
The service must support the work of multiple users. Users must create an event that is available to other users.
Each event has the following parameters: author, start time, end time, subject and description.
Each user can view all the events that are created by any user.
Each user can edit, delete and create events where he is the user.
A page should be implemented that has a general view of all events.

The application uses:
- Flask as an application framework
- celery to handle queues
- PostgreSQL for data storage.

To run the application on a local machine you need:
- clone this repository
- go to the folder by the repository
- install dependencies from requirements.txt
- if docker is not installed, then install
- run the command docker-compose up -d on the command line

After successful execution of the command, an application with the following endpoints will be available at 127.0.0.1:5000:

- / create_user - registration of a new user
- / login - login form (to log in, you must first create a user)
- / schedule, / - summary of all existing events
- / event - create a new event
- / event / <id> - updating an existing event, where <id> is its identifier. You can also get to this page from the list of events. You can edit only "your" events.
