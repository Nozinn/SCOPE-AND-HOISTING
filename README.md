# SCOPE-AND-HOISTING


## Scope (Область видимости)
В JavaScript область видимости определяет, где переменные, функции и объекты могут быть доступны в коде.

### Виды областей видимости:
1. **Глобальная область видимости** – переменные доступны везде в коде.
2. **Область видимости функции** – переменные доступны только внутри функции.
3. **Область видимости блока** (ES6 `let`, `const`) – переменные доступны только внутри блока `{}`.
4. **Лексическая область видимости** – вложенные функции имеют доступ к переменным родительских функций.

#### Пример областей видимости:
```javascript
var globalVar = "Я глобальная";

function testScope() {
    let functionScope = "Я внутри функции";
    if (true) {
        let blockScope = "Я внутри блока";
        console.log(blockScope); // Работает
    }
    // console.log(blockScope); // Ошибка! Вне блока недоступно
}
```

![JavaScript Scope](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-scopes.svg/800px-JavaScript-scopes.svg.png)

---

## Hoisting (Поднятие)
Hoisting – это механизм, при котором объявления переменных и функций перемещаются в начало их области видимости перед выполнением кода.

### Как работает Hoisting?
1. **Переменные `var` поднимаются, но их значения остаются `undefined` до инициализации.**
2. **Переменные `let` и `const` поднимаются, но находятся во "временной мёртвой зоне" (TDZ) до объявления.**
3. **Функции, объявленные через `function`, полностью поднимаются с телом.**

#### Примеры:
##### Переменные `var`:
```javascript
console.log(a); // undefined
var a = 5;
console.log(a); // 5
```

##### Переменные `let` и `const`:
```javascript
console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 10;
```

##### Функции:
```javascript
hello(); // Работает!
function hello() {
    console.log("Привет!");
}
```

##### Функциональные выражения:
```javascript
sayHi(); // TypeError: sayHi is not a function
var sayHi = function() {
    console.log("Привет!");
};
```

![JavaScript Hoisting](https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript_Hoisting.png)

---

## Заключение
- **Используй `let` и `const`**, чтобы избежать неожиданных ошибок с `var`.
- **Понимай лексическую область видимости**, чтобы правильно работать с переменными.
- **Знай про hoisting**, чтобы код выполнялся так, как ты ожидаешь!


