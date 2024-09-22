# Front-end

## HTML

## CSS

[CSS Crash Course](https://zhsh.info/css-crash-course/)

## JavaScript

### 变量

- var
- 驼峰命名法

### 数据类型

- number
- string
- bool
- null
- undefined

### 运算符

| Operator type          | Individual operators                    |
| ---------------------- | --------------------------------------- |
| member                 | . []                                    |
| call / create instance | () new                                  |
| negation/increment     | ! ~ - + ++ -- typeof void delete        |
| multiply/divide        | * / %                                   |
| addition/subtraction   | + -                                     |
| bitwise shift          | << >> >>>                               |
| relational             | < <= > >= in instanceof                 |
| equality               | == != === !==                           |
| bitwise-and            | &                                       |
| bitwise-xor            | ^                                       |
| bitwise-or             | \|                                      |
| logical-and            | &&                                      |
| logical-or             | \|\|                                    |
| conditional            | ?:                                      |
| assignment             | = += -= *= /= %= <<= >>= >>>= &= ^= \|= |
| comma                  | ,                                       |

### 语句

- 判断语句

```javascript
// if 语句
if (condition) {
    // 代码块
} else if (anotherCondition) {
    // 代码块
} else {
    // 代码块
}

// switch 语句
switch (expression) {
    case value1:
        // 代码块
        break;
    case value2:
        // 代码块
        break;
    default:
        // 默认代码块
}

// 三元运算符
let result = condition ? valueIfTrue : valueIfFalse;
```

- 循环语句

```javascript
// for 循环
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// while 循环
let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}

// do...while 循环
let j = 0;
do {
    console.log(j);
    j++;
} while (j < 5);

// for...of 循环（用于可迭代对象）
for (let item of iterable) {
    console.log(item);
}

// for...in 循环（用于对象属性）
for (let key in object) {
    if (object.hasOwnProperty(key)) {
        console.log(key, object[key]);
    }
}
```

### 函数

```javascript
// 函数声明
function greet(name) {
    return `Hello, ${name}!`;
}

// 函数表达式
const greet = function(name) {
    return `Hello, ${name}!`;
};

// 箭头函数
const greet = (name) => `Hello, ${name}!`;

// 默认参数
function greet(name = 'Guest') {
    return `Hello, ${name}!`;
}

// 剩余参数
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

// 立即执行函数表达式 (IIFE)
(function() {
    console.log('This function is executed immediately');
})();

// 闭包
function outer() {
    let count = 0;
    return function() {
        return ++count;
    };
}
const increment = outer();
console.log(increment()); // 1
console.log(increment()); // 2
```

### 数组

```javascript
// 创建数组
let fruits = ['apple', 'banana', 'orange'];

// 访问元素
console.log(fruits[0]); // 'apple'

// 添加/删除元素
fruits.push('mango');   // 末尾添加
fruits.pop();           // 末尾删除
fruits.unshift('grape'); // 开头添加
fruits.shift();         // 开头删除

// 数组方法
fruits.forEach(fruit => console.log(fruit));
let longFruits = fruits.filter(fruit => fruit.length > 5);
let fruitLengths = fruits.map(fruit => fruit.length);
let totalLength = fruits.reduce((total, fruit) => total + fruit.length, 0);

// 数组展开
let moreFruits = ['kiwi', 'pear'];
let allFruits = [...fruits, ...moreFruits];

// 解构赋值
let [first, second, ...rest] = fruits;
```

### 对象

```javascript
// 创建对象
let person = {
    name: 'John',
    age: 30,
    greet: function() {
        console.log(`Hello, I'm ${this.name}`);
    }
};

// 访问属性
console.log(person.name);
console.log(person['age']);

// 添加/修改属性
person.job = 'Developer';
person['salary'] = 50000;

// 方法简写
let calculator = {
    add(a, b) {
        return a + b;
    },
    subtract(a, b) {
        return a - b;
    }
};

// 对象展开
let employee = { ...person, company: 'ABC Corp' };

// 解构赋值
let { name, age, job = 'Unknown' } = person;

// Object.keys(), Object.values(), Object.entries()
console.log(Object.keys(person));
console.log(Object.values(person));
console.log(Object.entries(person));

// 对象冻结和封装
Object.freeze(person); // 无法修改
Object.seal(person);   // 可以修改现有属性，但不能添加新属性

// Getter 和 Setter
let account = {
    balance: 1000,
    get formattedBalance() {
        return `$${this.balance.toFixed(2)}`;
    },
    set deposit(amount) {
        this.balance += amount;
    }
};
```

### DOM

- document.getElementById()
  - textContent
- document.getElementsByTagName()
- document.querySelectorAll(), querySelector()
  - previousElementSibling
  - nextElementSibling
  - parentNode

### 样式处理

- .style
  - width
  - height
  - backgroundColor
  - className

### 文本处理

- innerHTML
- textContent

### 事件处理

- [事件介绍](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Building_blocks/Events)
- [事件处理程序](https://tsejx.github.io/javascript-guidebook/document-object-model/events/event-handlers-or-listener/)

事件添加方法:

- onclick = function(){}
- addEventListener('', function(){})

### 定时器

- setTimeout()
- setInterval()

## ES6
