HTML（HyperText Markup Language）即超文本标记语言，是用于创建网页的标准标记语言。以下是HTML基本语法的详细介绍：

### 1. HTML 文档结构
一个基本的 HTML 文档包含以下结构：
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <!-- 这里是网页的可见内容 -->
</body>

</html>
```
- `<!DOCTYPE html>`：声明文档类型为 HTML5。
- `<html>`：HTML 文档的根标签，所有 HTML 元素都包含在其中。`lang="en"` 指定文档语言为英语。
- `<head>`：包含文档的元数据，如字符编码、页面标题等，这些信息通常不会直接显示在页面上。
    - `<meta charset="UTF-8">`：设置文档的字符编码为 UTF - 8。
    - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`：用于响应式网页设计，确保页面在不同设备上正确显示。
    - `<title>`：设置页面的标题，显示在浏览器的标签页上。
- `<body>`：包含页面的可见内容，如文本、图像、链接等。

### 2. HTML 标签
HTML 标签是 HTML 语言的基本组成部分，通常由尖括号包围，大多数标签成对出现，有开始标签和结束标签，少数标签为单标签。

#### 成对标签
```html
<p>这是一个段落。</p>
```
`<p>` 是开始标签，`</p>` 是结束标签，中间的文本就是该段落的内容。

#### 单标签
```html
<br>
```
`<br>` 是换行标签，不需要结束标签。

### 3. 文本标签
- **标题标签**：从 `<h1>` 到 `<h6>` 共六级标题，`<h1>` 表示最高级别的标题，字体最大，重要性也最高。
```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
```
- **段落标签**：`<p>` 用于定义段落。
```html
<p>这是一个段落的内容。</p>
```
- **强调标签**：
    - `<em>`：用于强调文本，通常显示为斜体。
```html
<p>这是 <em>强调</em> 的内容。</p>
```
    - `<strong>`：用于表示重要的文本，通常显示为粗体。
```html
<p>这是 <strong>重要</strong> 的内容。</p>
```

### 4. 列表标签
- **无序列表**：使用 `<ul>` 标签定义，列表项使用 `<li>` 标签。
```html
<ul>
    <li>苹果</li>
    <li>香蕉</li>
    <li>橙子</li>
</ul>
```
- **有序列表**：使用 `<ol>` 标签定义，列表项同样使用 `<li>` 标签。
```html
<ol>
    <li>第一步</li>
    <li>第二步</li>
    <li>第三步</li>
</ol>
```

### 5. 链接标签
使用 `<a>` 标签创建超链接，`href` 属性指定链接的目标地址。
```html
<a href="https://www.example.com">访问示例网站</a>
```
还可以使用 `target="_blank"` 属性让链接在新窗口中打开。
```html
<a href="https://www.example.com" target="_blank">在新窗口打开示例网站</a>
```

### 6. 图像标签
使用 `<img>` 标签插入图像，`src` 属性指定图像的源文件路径，可以是本地路径或网络地址，`alt` 属性用于在图像无法显示时提供替代文本。
```html
<img src="image.jpg" alt="这是一张示例图片">
```

### 7. 表格标签
使用 `<table>` 标签创建表格，`<tr>` 表示表格的行，`<th>` 表示表格的表头单元格，`<td>` 表示表格的数据单元格。
```html
<table border="1">
    <tr>
        <th>姓名</th>
        <th>年龄</th>
    </tr>
    <tr>
        <td>张三</td>
        <td>25</td>
    </tr>
    <tr>
        <td>李四</td>
        <td>30</td>
    </tr>
</table>
```
`border="1"` 属性为表格添加了边框。

### 8. 表单标签
表单用于用户输入数据，常见的表单元素有 `<input>`、`<textarea>`、`<select>` 等，使用 `<form>` 标签包裹这些元素。
```html
<form action="submit.php" method="post">
    <label for="name">姓名：</label>
    <input type="text" id="name" name="name"><br>
    <label for="message">留言：</label>
    <textarea id="message" name="message"></textarea><br>
    <label for="country">国家：</label>
    <select id="country" name="country">
        <option value="china">中国</option>
        <option value="usa">美国</option>
    </select><br>
    <input type="submit" value="提交">
</form>
```
- `action` 属性指定表单数据提交的目标地址。
- `method` 属性指定提交方式，常见的有 `get` 和 `post`。
- `<label>` 标签用于为表单元素提供文本描述，`for` 属性的值要与对应的表单元素的 `id` 属性值相同。
- `<input>` 标签的 `type` 属性可以是 `text`、`password`、`radio`、`checkbox`、`submit` 等。

通过学习这些基本的 HTML 语法，你可以创建出简单的网页。不断实践和尝试不同的标签组合，能让你更熟练地掌握 HTML。 