# Лабораторная. React: запросы в сеть и маршрутизация

###  [React. Запросы в сеть. Fetch](https://dmitryweiner.github.io/web-lectures/React%20-%20Network.html)
###  [React. Запросы в сеть. React Query](https://dmitryweiner.github.io/web-lectures/React%20-%20Query.html)
###  [React. Маршрутизация](https://dmitryweiner.github.io/web-lectures/React%20-%20Router.html)

---


### Задание по маршрутизации

* Сделать роуты для своих лабораторных по реакту (чтобы все странички с лабами открывались каждая по своему адресу)

либо 

* Сделать роуты для форм из прошлой лабораторной про  [валидацию форм](https://dmitryweiner.github.io/web-lectures/React%20-%20Form%20validation.html).

/login - \<LoginForm /\>

/registration - \<RegistrationForm /\>

/ - \<Home /\>
  
* При вводе несуществующих адресов веб-приложение переходит на /.

---

### Задание по запросам в сеть

* Написать компонент, отображающий форму:
ID:
<inpit style="width: 200px"/>
<button text="Получить данные!"/>

* При нажатии кнопки компонент обращается по адресу https://jsonplaceholder.typicode.com/posts/:id.

* Также компонент обращается по адресу https://jsonplaceholder.typicode.com/users/:userId, где userId получен из предыдущих данных.

* Показать экране: из post - поля title и body, из user - поля name, email.

Опционально:

* Блокировать кнопку сабмита формы во время выполнения запроса
* Показывать спиннер во время выполнения запроса
* Показывать ошибки в случае ошибки запроса (ввод некорректных данных либо не 200 ответ сервера)

---

### Задание по запросам в сеть (опциональное)

* Склонировать [репозиторий](https://github.com/dmitryweiner/mini-chat-server), запустить сервер.

* Из форм, [написанных ранее (логин и регистрация)](https://github.com/goryachkinama/web-lectures/blob/main/src/lab_react_forms.md), отправлять запросы:

* Регистрация: POST /user
```js
{ "nickname": "test", "password": "123" }
```

* Логин: POST /auth
```js
{ "nickname": "test", "password": "123" }
```

* После успешной регистрации перенаправлять на логин. После успешной авторизации перенаправлять на /Home.

---

