# Контрольная неделя 1. Серверная часть приложения

### [Презентация по NodeJS](https://dmitryweiner.github.io/web-lectures/Basic%20-%20Nodejs.html)

### [Презентация по Express](https://dmitryweiner.github.io/web-lectures/Express.html)

### [Презентация по SQLite](https://dmitryweiner.github.io/web-lectures/SQLite.html)

### [Проект с авторизацией](https://github.com/dmitryweiner/express-auth-example/tree/333f5400062315490e7470340d152ea3a671556a)

### Задание

* Определиться с идеей будущего веб-приложения (как варианты: интернет-магазин/сайт услуг/форум/чат/почтовый клиент/органайзер/todolist на максималках/свой вариант).
* Разработать схему БД в соответствии с тематикой, выбранной выше
* Выкачать проект с готовой логинкой (последняя ссылка)
* Переписать форму логина, заиспользовав библиотеку компонент (например, [Ant Design](https://ant.design/components/overview/))
* Доработать базу данных, дописав функции создания и, опционально, заполнения оставшихся таблиц (файл server/db/db.js)
* Продумать схему API (по каким ссылкам и с какими параметрами будем делать запросы на сервер, чтобы получать данные)
* Доработать роуты, добавив в соответствии со схемой API методы для работы с БД (создать файлы в папке routes/ по аналогии с уже имеющимися)
* Подключить новые роуты в index.js
  
* ! Клиент пока не трогаем и фетчи не делаем