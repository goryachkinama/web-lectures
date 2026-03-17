# Замыкания в JS

```js
function createIncrementFunc() {
    let counter = 0;
    return () => {
        console.log(counter);
        counter++;
    }
}

// мгновенный вызов
(createIncrementFunc())()

function createIncrementFunc() {
    let counter = 0;
    return () => {
        console.log(counter);
        counter++;
    }
}

const counter1 = createIncrementFunc();
const counter2 = createIncrementFunc();
counter1(); // 0
counter1(); // 1
counter1(); // 2

counter2(); // 0



const createIncrementFunc = (param1) => (param2) => {
 let counter = param1
 return () => {
        console.log(counter);
        counter = counter + param2;
    }
}

const counter1 = createIncrementFunc(3);
const counter2 = createIncrementFunc(40);

const counter11 = counter1(30);
const counter22 = counter2(40);

counter11(); // 3
counter11(); // 33
counter11(); // 63
counter11(); // 93

counter22(); // 40
counter22(); // 80
counter22(); // 120

const createIncrementFunc = (param1) => (param2) => {
 let counter = param1
 return () => {
        console.log(counter);
        counter = counter + param2;
    }
}

const counter1 = createIncrementFunc(3)(30);
const counter2 = createIncrementFunc(40)(40);

```
