JavaScript 是一种广泛用于网页开发的脚本语言，以下是对 JavaScript 基本语法的详细介绍，帮助你入门学习。

### 1. 引入 JavaScript
在 HTML 文件中引入 JavaScript 有两种常见方式：

#### 内部脚本
在 HTML 文件的 `<script>` 标签内直接编写 JavaScript 代码。
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Internal Script</title>
</head>

<body>
    <script>
        // 在这里编写 JavaScript 代码
        console.log('Hello, World!');
    </script>
</body>

</html>
```

#### 外部脚本
将 JavaScript 代码写在一个独立的 `.js` 文件中，然后在 HTML 文件中使用 `<script>` 标签引入。
**index.html**
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>External Script</title>
</head>

<body>
    <script src="script.js"></script>
</body>

</html>
```
**script.js**
```javascript
console.log('Hello, World!');
```

### 2. 变量和数据类型

#### 变量声明
在 JavaScript 中，可以使用 `var`、`let` 和 `const` 来声明变量。
```javascript
// 使用 var 声明变量
var message = 'Hello';
// 使用 let 声明变量
let age = 25;
// 使用 const 声明常量
const PI = 3.14;
```
**注意**：`var` 具有函数作用域，`let` 和 `const` 具有块级作用域。`const` 声明的常量一旦赋值就不能再重新赋值。

#### 数据类型
JavaScript 有以下几种基本数据类型：
- **数字（Number）**：包括整数和浮点数。
```javascript
let num1 = 10;
let num2 = 3.14;
```
- **字符串（String）**：表示文本数据。
```javascript
let str1 = 'Hello';
let str2 = "World";
```
- **布尔值（Boolean）**：只有两个值 `true` 和 `false`。
```javascript
let isStudent = true;
```
- **空值（Null）**：表示一个空对象指针。
```javascript
let empty = null;
```
- **未定义（Undefined）**：变量已声明但未赋值时为 `undefined`。
```javascript
let variable;
console.log(variable); // 输出: undefined
```
- **Symbol**：ES6 引入的一种原始数据类型，表示独一无二的值。
```javascript
const sym = Symbol('description');
```

### 3. 函数
函数是一段可重复使用的代码块。

#### 函数声明
```javascript
function add(a, b) {
    return a + b;
}

let result = add(3, 5);
console.log(result); // 输出: 8
```

#### 函数表达式
```javascript
const multiply = function(a, b) {
    return a * b;
};

let product = multiply(4, 6);
console.log(product); // 输出: 24
```

#### 箭头函数
ES6 引入的简洁函数语法。
```javascript
const divide = (a, b) => a / b;

let quotient = divide(10, 2);
console.log(quotient); // 输出: 5
```

### 4. 条件语句
用于根据不同条件执行不同的代码块。

#### if-else 语句
```javascript
let num = 15;
if (num > 10) {
    console.log('Number is greater than 10');
} else {
    console.log('Number is less than or equal to 10');
}
```

#### switch 语句
```javascript
let day = 3;
switch (day) {
    case 1:
        console.log('Monday');
        break;
    case 2:
        console.log('Tuesday');
        break;
    case 3:
        console.log('Wednesday');
        break;
    default:
        console.log('Other day');
}
```

### 5. 循环语句
用于重复执行一段代码。

#### for 循环
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

#### while 循环
```javascript
let j = 0;
while (j < 5) {
    console.log(j);
    j++;
}
```

#### do-while 循环
```javascript
let k = 0;
do {
    console.log(k);
    k++;
} while (k < 5);
```

### 6. 数组
数组是用于存储多个值的有序列表。

```javascript
let fruits = ['apple', 'banana', 'cherry'];

// 访问数组元素
console.log(fruits[0]); // 输出: apple

// 修改数组元素
fruits[1] = 'grape';
console.log(fruits); // 输出: ['apple', 'grape', 'cherry']

// 数组长度
console.log(fruits.length); // 输出: 3
```

### 7. 对象
对象是无序的数据集合，由键值对组成。

```javascript
let person = {
    name: 'John',
    age: 30,
    isMarried: true
};

// 访问对象属性
console.log(person.name); // 输出: John

// 修改对象属性
person.age = 31;
console.log(person.age); // 输出: 31
```

通过以上这些基本语法的学习，你可以开始编写一些简单的 JavaScript 程序了。不断练习和实践是掌握 JavaScript 的关键。 