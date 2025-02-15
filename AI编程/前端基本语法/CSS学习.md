CSS（Cascading Style Sheets）即层叠样式表，用于为 HTML 文档添加样式，使网页更加美观和吸引人。以下是 CSS 基本语法的详细介绍：

### 1. CSS 引入方式
在 HTML 中引入 CSS 有三种常见的方式：

#### 内联样式
直接在 HTML 标签的 `style` 属性中添加 CSS 样式。
```html
<p style="color: red; font-size: 16px;">这是一个使用内联样式的段落。</p>
```

#### 内部样式表
在 HTML 文件的 `<head>` 标签内使用 `<style>` 标签定义 CSS 样式。
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Internal CSS</title>
    <style>
        p {
            color: blue;
            font-size: 18px;
        }
    </style>
</head>

<body>
    <p>这是一个使用内部样式表的段落。</p>
</body>

</html>
```

#### 外部样式表
将 CSS 代码写在一个独立的 `.css` 文件中，然后在 HTML 文件的 `<head>` 标签内使用 `<link>` 标签引入。
**index.html**
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>External CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <p>这是一个使用外部样式表的段落。</p>
</body>

</html>
```
**styles.css**
```css
p {
    color: green;
    font-size: 20px;
}
```

### 2. CSS 基本语法结构
CSS 规则由选择器和声明块组成，声明块包含一个或多个声明，每个声明由属性和值组成，用冒号分隔，多个声明之间用分号分隔。
```css
selector {
    property1: value1;
    property2: value2;
}
```
- **选择器（Selector）**：用于选择要应用样式的 HTML 元素。
- **声明块（Declaration Block）**：用花括号 `{}` 包围，包含一个或多个声明。
- **声明（Declaration）**：由属性和值组成，定义了要应用的样式。

### 3. 选择器

#### 元素选择器
通过 HTML 元素的名称来选择元素。
```css
h1 {
    color: purple;
}
```
上述代码会将所有 `<h1>` 元素的文本颜色设置为紫色。

#### 类选择器
通过元素的 `class` 属性来选择元素，类名前面需要加上点号 `.`。
```html
<p class="highlight">这是一个有高亮样式的段落。</p>
```
```css
.highlight {
    background-color: yellow;
}
```

#### ID 选择器
通过元素的 `id` 属性来选择元素，ID 名前面需要加上井号 `#`。每个 HTML 元素的 `id` 属性值必须是唯一的。
```html
<p id="special">这是一个有特殊样式的段落。</p>
```
```css
#special {
    font-weight: bold;
}
```

#### 组合选择器
可以将多个选择器组合使用，以更精确地选择元素。
```css
/* 选择所有 class 为 "article" 的 div 元素中的 p 元素 */
div.article p {
    font-size: 14px;
}
```

### 4. 常用属性和值

#### 文本属性
- **color**：设置文本颜色。
```css
p {
    color: red;
}
```
- **font-size**：设置字体大小。
```css
h2 {
    font-size: 24px;
}
```
- **font-family**：设置字体族。
```css
body {
    font-family: Arial, sans-serif;
}
```
- **text-align**：设置文本对齐方式。
```css
p {
    text-align: center;
}
```

#### 背景属性
- **background-color**：设置背景颜色。
```css
div {
    background-color: lightgray;
}
```
- **background-image**：设置背景图像。
```css
body {
    background-image: url('background.jpg');
}
```

#### 盒模型属性
- **width** 和 **height**：设置元素的宽度和高度。
```css
div {
    width: 200px;
    height: 150px;
}
```
- **padding**：设置元素内容与边框之间的间距。
```css
p {
    padding: 10px;
}
```
- **border**：设置元素的边框。
```css
div {
    border: 1px solid black;
}
```
- **margin**：设置元素与其他元素之间的间距。
```css
h3 {
    margin: 20px;
}
```

### 5. 伪类和伪元素

#### 伪类
用于选择处于特定状态的元素，例如链接的不同状态。
```css
/* 未访问的链接 */
a:link {
    color: blue;
}
/* 已访问的链接 */
a:visited {
    color: purple;
}
/* 鼠标悬停在链接上 */
a:hover {
    color: red;
}
/* 激活的链接（鼠标按下时） */
a:active {
    color: green;
}
```

#### 伪元素
用于选择元素的特定部分，例如段落的首字母。
```css
p::first-letter {
    font-size: 24px;
    font-weight: bold;
}
```

### 6. 层叠和优先级
当多个 CSS 规则应用于同一个元素时，会根据层叠和优先级规则来确定最终应用的样式。一般来说，优先级从高到低依次为：内联样式 > ID 选择器 > 类选择器 > 元素选择器。

通过学习这些 CSS 基本语法，你可以为 HTML 页面添加基本的样式。不断实践和尝试不同的属性和选择器组合，能让你更熟练地掌握 CSS。 