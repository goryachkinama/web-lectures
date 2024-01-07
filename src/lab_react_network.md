# Лабораторная. React: запросы в сеть и маршрутизация

###  [React. Запросы в сеть. Fetch](https://dmitryweiner.github.io/web-lectures/React%20-%20Network.html)
###  [React. Запросы в сеть. React Query](https://dmitryweiner.github.io/web-lectures/React%20-%20Query.html)
###  [React. Маршрутизация](https://dmitryweiner.github.io/web-lectures/React%20-%20Router.html)

---

### Задача 1

* Написать компонент, отображающий форму:
ID: <inpit width="200px"/><button text="Получить данные!"/>

* При нажатии кнопки компонент обращается по адресу https://jsonplaceholder.typicode.com/posts/:id.

* Также компонент обращается по адресу https://jsonplaceholder.typicode.com/users/:userId, где userId получен из предыдущих данных.

* Показать экране: из post - поля title и body, из user - поля name, email.

---

### Задача 2

* Склонировать [репозиторий](https://github.com/dmitryweiner/mini-chat-server), запустить сервер.

* Из форм, [написанных ранее (логин и регистрация)](https://dmitryweiner.github.io/web-lectures/React%20-%20Form%20validation.html), отправлять запросы:

* Регистрация: POST /user
```js
{ "nickname": "test", "password": "123" }
```

* Логин: POST /auth
```js
{ "nickname": "test", "password": "123" }
```

* После успешной регистрации перенаправлять на логин. После успешной авторизации перенаправлять на / (Home).

---

### Задача 3

* Сделать роуты для [лабораторной](https://github.com/dmitryweiner/web-lectures/blob/main/laba.md):
** /login - <LoginForm />
** /registration - <RegistrationForm />
** / - <Home />

* Формы можно взять из предыдущей лекции про [валидацию форм](https://dmitryweiner.github.io/web-lectures/React%20-%20Form%20validation.html).
* При вводе на форме логина значений admin/123 веб-приложение переходит на /.
