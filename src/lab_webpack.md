# Лабораторная 7. Настройка инфраструктуры. Сборка проекта и установка зависимостей

### [NodeJS](https://dmitryweiner.github.io/web-lectures/Basic%20-%20Nodejs.html)
### [NPM](https://dmitryweiner.github.io/web-lectures/Basic%20-%20NPM.html#/)
### [Webpack](https://dmitryweiner.github.io/web-lectures/Basic%20-%20Webpack.html#/)

---

### Задание по проекту TODO-list:

0. Открыть в своей TODO-list как проект (можно выполнить нижеперечисленные шаги на пустом проекте, но позже придется переносить в него все файлы из TODO-list)
1. Проверить и установить, если требуется NodeJS (проверить через "node -v" в терминале IDE)
2. Сгенерить/создать package.json ("npm init -y")
3. Поставить и удалить библиотеку lodash ("npm i lodash", "npm un lodash"): убедиться, что работает установка библиотек
4. Поставить Webpack и создать webpack.config.js
5. Особое внимание к структуре проекта (!) Файлы js, css,и html нужно складывать четко соблюдая дерево папок из примера.
   Если что-то не будет совпадать, Webpack не отработает
7. В package.json прописать скрипты для старта и сборки проекта:
  "start": "webpack-dev-server --config webpack.config.js",
  "build": "webpack --config webpack.config.js"
8. Убедиться, что скрипты работают ("npm run start", "npm run build"), проект стартует на http://localhost:8080
9. В файле .gitignore указать игнорируемые при коммите папки

Опционально:

* Сделать разные Webpack-конфиги для продакшена и для разработки
* Настроить минификацию JS и CSS
* При запуске веб-сервера открывать окно браузера
* [Задание по NodeJS](lab_nodejs.md)
* [Задание по NPM](lab_npm.md)
