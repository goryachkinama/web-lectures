
### Переполнение контейнера и [overflow](https://htmlbook.ru/css/overflow)

Свойство overflow управляет отображением содержания блочного элемента, если оно целиком не помещается и выходит за область заданных размеров. 

* Значения:
  * **visible**: отображается все содержание элемента, даже за пределами установленной высоты и ширины.
  * **hidden**: отображается только область внутри элемента, остальное будет скрыто.
  * **scroll**: всегда добавляются полосы прокрутки.
  * **auto**: полосы прокрутки добавляются только при необходимости.

overflow-x управляет отображением содержания блочного элемента по горизонтали
overflow-y - по вертикали

---

### Как обрезать текст и добавить многоточие

Если текст целиком не помещается и выходит за область заданных размеров, можно (и нужно) обрезать его и добавить многоточие:

```html
<style>
   div {
    overflow: hidden; /* Обрезаем текст*/
    white-space: nowrap; /* Отменяем переносы текста на следующие строки*/
    text-overflow: ellipsis; /* Добавляем многоточие при обрезке*/
   } 
</style>
```

---

### Добавление [псевдоэлемента](https://htmlbook.ru/css/cat/pseudoelement)

Псевдоэлемент, который используется для вывода желаемого текста после содержимого элемента, к которому он добавляется. Псевдоэлемент ::after работает совместно со свойством content.

Для `::after` характерны следующие особенности:

* При добавлении `::after` к блочному элементу,
  значение свойства `display` может быть только: `block`, `inline`, `none`, `marker`.
  Все остальные значения будут трактоваться как `block`.
* При добавлении `::after` к встроенному элементу, `display` ограничен значениями `inline` и none. Все остальные будут восприниматься как `inline`.

<h4>Синтаксис</h4>

```html
элемент::after { content: "текст" }
```

<h4>Пример</h4>
  
  <div style="color: gray">html <span style="font-size: 200%">✔</span></div>
  <div style="color: gray">css <span style="font-size: 200%">✔</span></div>
  <div style="color: gray">js <span style="font-size: 200%">✔</span></div>
  
```html
<html>
 <head>
  <meta charset="utf-8">
  <title>Список дел</title>
  <style>
    div::after {
      content: "✔"; /* Добавляемый текст: любые символы обязательно в кавычках */ 
      font-size: 200%; /* Размер шрифта */ 
      padding: 2px;
    }
  </style>
 </head>
 <body>
  <div>html</div>
  <div>css</div>
  <div>js</div>
 </body>
</html>
```

---

### [Псевдоклассы](https://htmlbook.ru/css/cat/pseudoclass) для ссылок

При верстке ссылок и кнопок необходимо продумать их поведени и соответствующие цвета, которые задаются с помощью псевдоклассов:

* Значения для ссылок:
  * [**:hover**](https://htmlbook.ru/css/hover): стиль элемента при наведении на него курсора мыши, но при этом элемент еще не активирован, иными словами кнопка мыши не нажата.
  * [**:active**](https://htmlbook.ru/css/active): стиль для активной ссылки, когда на нее нажали.
  * [**:visited**](https://htmlbook.ru/css/visited): ссылки, уже посещённые пользователем.

* Значения для элементов форм:
  * [**:focus**](https://htmlbook.ru/css/focus) определяет стиль для элемента получающего фокус. Например, текстовое поле формы, в которое устанавливается курсор.
  * [**:disabled**](https://htmlbook.ru/css/disabled) используется для применения стиля к заблокированным элементам форм. Такие элементы не могут получить фокус, быть нажатыми или активированы, в текстовых полях нельзя набирать текст.
  * [**:checked**](https://htmlbook.ru/css/checked) применяется к элементам интерфейса, таким как переключатели (checkbox) и флажки (radio), когда они находятся в положение «включено». Переключение элементов в такое состояние происходит с помощью атрибута checked тега `<input>` или пользователем. 
 

---
### Послойное отображение элементов и [z-index](https://htmlbook.ru/css/z-index)

* Для наложения друг на друга позиционированных элементов веб-страницы в определенном порядке.
* Имитирует измерение, перпендикулярное экрану, т.е. по z-оси. 
* Работает только для элементов, у которых значение position задано как absolute, fixed или relative.
* Принимает целые числа (положительные, отрицательные и ноль). 
* Чем больше значение, тем выше находится "слой" с элементом. 
* При равном значении z-index, на переднем плане находится тот элемент, который в коде HTML описан ниже.

<h4>Синтаксис</h4>
```html
z-index: число | auto | inherit
```

<h4>Пример</h4>
```html
<html>
 <head>
  <meta charset="utf-8">
  <title>z-index</title>
  <style>
   #layer1, #layer2, #layer3, #layer4 {
    position: relative; /* Относительное позиционирование */
   } 
   #layer1, #layer3 {
    font-size: 50px; /* Размер шрифта в пикселах */
    color: #000080; /* Синий цвет текста */
   }
   #layer2, #layer4 {
    top: -55px; /* Сдвигаем текст вверх */
    left: 5px; /* Сдвигаем текст вправо */
    color: #ffa500; /* Оранжевый цвет текста */
    font-size:70px;  /* Размер шрифта в пикселах */
   }
   #layer1 { z-index: 2; }
   #layer2 { z-index: 1; }
   #layer3 { z-index: 3; }
   #layer4 { z-index: 4; }
  </style>
 </head>
 <body>
  <p>Слой 1 наверху</p>
  <div id="layer1">Слой 1</div>
  <div id="layer2">Слой 2</div> 
  <p>Слой 4 наверху</p>
  <div id="layer3">Слой 3</div>
  <div id="layer4">Слой 4</div> 
 </body>
</html>
```

---
### Как добавить шрифты

Шрифты удобнее всего брать у [Google Fonts](fonts.google.com)

* Алгоритм:
  * Ищем шрифт, доступный на заданном языке и начертании.
  * Переходим на него.
  * Убеждаемся, что он подойдет и кликаем на синюю кнопку "Get font".
  * Кликаем на синюю кнопку "Get embed code" (чтобы использовать его на странице без скачивания).
  * Копируем весь html ниже надписи "Embed code in the <head> of your html".
  * Добавляем на страницу в блок `head`

```html 
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&family=SN+Pro:ital,wght@0,200..900;1,200..900&display=swap" rel="stylesheet">
```

Добавляется сюда:

```html
<html>
 <head>
  <meta charset="utf-8">
  <title>Список дел</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?   family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&family=SN+Pro:ital,wght@0,200..900;1,200..900&display=swap" rel="stylesheet">
 </head>
 <body>
  ...
 </body>
</html>
```

---

