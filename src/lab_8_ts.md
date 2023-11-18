# Лабораторная работа 8. TypeScript

* [Упражнения](https://typescript-exercises.github.io/#exercise=1&file=%2Findex.ts).

* [Ещё упражнения](https://exercism.org/tracks/typescript/exercises).
---

### Задача 1

Избавиться от `unknown`, описать актуальный интерфейс:

```ts
export type User = unknown;

export const users: unknown[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    }
];

export function logPerson(user: unknown) {
    console.log(` - ${user.name}, ${user.age}`);
}

console.log('Users:');
users.forEach(logPerson);
```
---


### Задача 2

Переписать todo-list на Typescript

---
