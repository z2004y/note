以下为你提供几个使用 `requests` 库的典型案例，并进行详细分析。

### 案例一：爬取网页内容
#### 需求描述
爬取百度首页的 HTML 内容。
#### 代码示例
```python
import requests

# 定义要请求的 URL
url = 'https://www.baidu.com'

try:
    # 发送 GET 请求
    response = requests.get(url)
    # 检查响应状态码
    response.raise_for_status()
    # 设置响应的编码
    response.encoding = response.apparent_encoding
    # 打印网页内容
    print(response.text)
except requests.exceptions.HTTPError as http_err:
    print(f'HTTP 错误发生: {http_err}')
except requests.exceptions.RequestException as req_err:
    print(f'请求发生错误: {req_err}')
```
#### 代码分析
1. **导入库**：`import requests` 导入 `requests` 库，以便后续使用其功能。
2. **定义 URL**：指定要爬取的网页 URL，这里是百度首页。
3. **发送请求**：使用 `requests.get(url)` 发送 GET 请求，并将响应对象赋值给 `response`。
4. **状态码检查**：`response.raise_for_status()` 用于检查响应的状态码，如果状态码不是 200，会抛出 `HTTPError` 异常。
5. **编码设置**：`response.encoding = response.apparent_encoding` 根据网页内容自动检测并设置正确的编码，避免中文等字符显示乱码。
6. **获取内容**：`response.text` 获取响应的文本内容并打印。
7. **异常处理**：使用 `try-except` 语句捕获可能出现的 `HTTPError` 和其他请求异常，并打印相应的错误信息。

### 案例二：带参数的 GET 请求获取豆瓣电影信息
#### 需求描述
通过豆瓣电影的 API，获取指定标签和数量的电影信息。
#### 代码示例
```python
import requests

# 定义 API URL
url = 'https://movie.douban.com/j/search_subjects'

# 定义请求参数
params = {
    'type': 'movie',
    'tag': '热门',
    'sort': 'recommend',
    'page_limit': 10,
    'page_start': 0
}

try:
    # 发送带参数的 GET 请求
    response = requests.get(url, params=params)
    # 检查状态码
    response.raise_for_status()
    # 解析 JSON 数据
    data = response.json()
    # 打印电影标题
    for movie in data['subjects']:
        print(movie['title'])
except requests.exceptions.HTTPError as http_err:
    print(f'HTTP 错误发生: {http_err}')
except requests.exceptions.RequestException as req_err:
    print(f'请求发生错误: {req_err}')
```
#### 代码分析
1. **定义 URL 和参数**：确定豆瓣电影 API 的 URL，并使用字典 `params` 定义请求参数，包括电影类型、标签、排序方式、每页数量和起始页码等。
2. **发送请求**：`requests.get(url, params=params)` 发送带参数的 GET 请求，`requests` 会自动将参数添加到 URL 中。
3. **状态码检查**：同样使用 `response.raise_for_status()` 检查响应状态。
4. **解析 JSON 数据**：`response.json()` 将响应的 JSON 数据解析为 Python 字典或列表，方便后续处理。
5. **数据处理**：遍历解析后的数据，提取并打印电影的标题。
6. **异常处理**：捕获并处理可能出现的请求异常。

### 案例三：发送 POST 请求模拟登录
#### 需求描述
模拟用户登录一个简单的网站，通过 POST 请求提交用户名和密码。
#### 代码示例
```python
import requests

# 定义登录 URL
login_url = 'https://example.com/login'

# 定义登录数据
login_data = {
    'username': 'testuser',
    'password': 'testpass'
}

try:
    # 发送 POST 请求
    response = requests.post(login_url, data=login_data)
    # 检查状态码
    response.raise_for_status()
    # 打印登录结果
    print(response.text)
except requests.exceptions.HTTPError as http_err:
    print(f'HTTP 错误发生: {http_err}')
except requests.exceptions.RequestException as req_err:
    print(f'请求发生错误: {req_err}')
```
#### 代码分析
1. **定义 URL 和数据**：确定登录页面的 URL，并使用字典 `login_data` 定义要提交的用户名和密码。
2. **发送请求**：`requests.post(login_url, data=login_data)` 发送 POST 请求，将登录数据提交到服务器。
3. **状态码检查**：使用 `response.raise_for_status()` 确保请求成功。
4. **获取结果**：`response.text` 获取服务器返回的登录结果并打印。
5. **异常处理**：处理可能的请求异常。

### 案例四：使用会话对象保持登录状态
#### 需求描述
在登录一个网站后，使用会话对象保持登录状态，继续访问需要登录权限的页面。
#### 代码示例
```python
import requests

# 创建会话对象
session = requests.Session()

# 定义登录 URL 和数据
login_url = 'https://example.com/login'
login_data = {
    'username': 'testuser',
    'password': 'testpass'
}

try:
    # 发送登录请求
    login_response = session.post(login_url, data=login_data)
    # 检查登录状态码
    login_response.raise_for_status()

    # 定义需要登录权限的页面 URL
    protected_url = 'https://example.com/protected'
    # 使用会话对象访问受保护页面
    protected_response = session.get(protected_url)
    # 检查访问状态码
    protected_response.raise_for_status()
    # 打印受保护页面内容
    print(protected_response.text)
except requests.exceptions.HTTPError as http_err:
    print(f'HTTP 错误发生: {http_err}')
except requests.exceptions.RequestException as req_err:
    print(f'请求发生错误: {req_err}')
```
#### 代码分析
1. **创建会话对象**：`requests.Session()` 创建一个会话对象 `session`，用于在多个请求之间保持会话状态。
2. **发送登录请求**：使用会话对象的 `post` 方法发送登录请求，提交用户名和密码。
3. **检查登录状态**：确保登录请求成功。
4. **访问受保护页面**：使用同一个会话对象的 `get` 方法访问需要登录权限的页面，由于会话状态已保持，服务器会识别用户的登录身份。
5. **检查访问状态**：确保访问受保护页面的请求成功。
6. **获取内容**：打印受保护页面的内容。
7. **异常处理**：捕获并处理请求过程中可能出现的异常。 