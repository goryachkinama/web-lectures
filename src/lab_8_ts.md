# Лабораторная работа 8. TypeScript

### [Презентация TypeScript](https://dmitryweiner.github.io/web-lectures/Basic%20-%20TypeScript.html) 
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

### Задача 3

Даны несколько заготовленных типов. При помощи них "собран" тип Student.
Соберите типы Teacher и Director из имеющихся типов. Для проверки используйте
переменные в самом низу. Можно определять новые типы.
    
Teacher имеет идентификатор, имя, уровень скила и словарь из его курсов.
В словаре курсов Teacher-а по ключу id курса лежит объект с идентификатором курса,
названием и ролью учителя.

Director имеет идентификатор, имя, словарь студентов и словарь учителей. Словарь
студентов по id студента содержит объект с идентификатором и именем студента.
Словарь учителей по id учителя содержит объект с идентификатором, именем, уровнем
и оценкой учителя

```ts
type User = {
    id: string;
    name: string;
}

type Course = {
    id: number;
    title: string;
}

type WithRate = {
    rate: 1 | 2 | 3 | 4 | 5;
}

type WithStudentRole = {
    role: "student"
}

type WithTeacherRole = {
    role: "teacher"
}

type WithLevel = {
    level: "junior" | "middle" | "senior"
}
/* --- */

type StudentCourse = Course & WithStudentRole & WithRate & WithLevel
type Student = User & { courses: { [id: number]: StudentCourse } }

type Teacher = User

type Director = User;

/*--  Проверка  --*/
const s1: Student = {
    id: "s1",
    name: "s1",
    courses: {
        [1]: {
            id: 1,
            title: "First",
            rate: 5,
            role: "student",
            level: "middle"
        }
    },
}

const t1: Teacher = {
    id: "t1",
    name: "t1",
    level: "junior",
    courses: {
        [5]: {
            id: 5,
            title: "Fifth",
            role: "teacher"
        },
        [1]: {
            ...s1.courses[1],
            role: "teacher"
        }
    }
}

const d1: Director = {
    id: "d1",
    name: "d1",
    students: {
        ["s1"]: s1,
        ["s2"]: {
            id: "s2",
            name: "s2"
        }
    },
    teachers: {
        ["t1"]: {
            ...t1,
            rate: 3,
        },
        ["t2"]: {
            id: "t2",
            name: "t2",
            level: "senior",
            rate: 5
        }
    }
}
```

---

### Задача 2

Переписать todo-list на Typescript

---

* [Упражнения](https://typescript-exercises.github.io/#exercise=1&file=%2Findex.ts).

* [Ещё упражнения](https://exercism.org/tracks/typescript/exercises).

