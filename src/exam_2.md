# Задачи для экзамена

Для решения каждой задачи надо написать компонент на React.js и тесты к нему. Писать легче всего
в проекте, созданном с помощью create-react-app.

Писать компонент надо в функциональном стиле с использованием хуков.

### 1. Лайк
Компонент отображает чёрное сердечко 🖤. Когда на него кликнули дважды (задержка <= 800 ms),
сердечко становится красным ❤️. По техническим причинам нельзя пользоваться встроенным событием
```onDoubleClick```.

### 2. Обратный отсчёт
При отображении компонент показывает 10. Через секунду число сменяется на 9. И так до 0. На нуле
отсчёт останавливается.

### 3. Обратная строка
Компоненту в пропсы передали строку. Он её отображает в обратном порядке:
```jsx
<Component text="❤!тевирП" />
```
Отображается:
```Привет!❤```

**Внимание!** В переданной строке могут быть символы юникода, эмодзи.

### 4. Градусник
Компоненту передаётся текущая температура в градусах Цельсия. Если значение < 0, температура отображается
синим шрифтом, если > 0 &mdash; красным.
```jsx
<Component temperature={-20} />
```
![7-1](src/assets/exam/7-1.png)
```jsx
<Component temperature={36.6} />
```
![7-2](src/assets/exam/7-2.png)

### 5. Счётчик
Реализовать счётчик нажатий на кнопку:

![9](src/assets/exam/9.png)

Нажатий на кнопку: 42.

### 6. Селектбокс
Компоненту на вход передаётся:
* массив опций для отображения;
* коллбэк, который следует вызвать, когда в селектбоксе что-то выбрали, 
  передав в качестве аргумента выбранную опцию;
* дефолтное значение.
```jsx
<Selectbox 
  options={[1, 2, 3]} 
  onSelect={value => console.log(value)}
  defaultValue={2}
/>
```

![11](src/assets/exam/11.png)
