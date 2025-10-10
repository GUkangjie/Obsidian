```python
安装：
pip install requests
```

向接口发送请求：
1. [向接口发送请求] + pytest -> 接口自动化
2. [控制浏览器] + pytest -> WEB自动化
3. [控制手机App] + pytest -> App自动化

```python
import requests

requests.request()  #基本用法、统一用法
```
示例：
```python
resp = requests.request(
	method = 'get',                 #http请求方法，必填
	url = "http://www.baidu.com",   #接口地址，必填
	data = {"a":1,"b":2},           #接口参数，选填，类型有多种
	
)
print(resp.status_code) #整数
print(resp.headers)     #字典
print(resp.test)        #字符串
print(resp.json())      #JSON
```
##### 常见场景：
 1. **表单参数**
主要用在Web项目：
- 参数只能是字符串
- 请求头中包含form
- requests请求：
	- 如果data参数是一个字典，则自动将其识别为表单，并自动添加请求头
```python
user_info = {
	"username":"gukangjie",
	"password":"123456"
}
def test_api_form():
	resp = requests.request(
		method = "post",
		url = "http://api.fbi.com:9225/rest_v1/login/with_from",
		data = user_info,
)
assert resp.status_code == 200
```

2. **json参数**
	主要用在各类项目中：
		1. 参数类型很多：字符串、数字、布尔值、空值、数组
		2. 请求头中包含json
		3. requests技巧：
					如果传递json参数，自动识别为json参数类型，自动添加请求头
```python
user_info = {
	"username":"gukangjie",
	"password":"123456"
}
def test_api_json():
	resp = requests.request(
		method = "post",
		url = "http://api.fbi.com:9225/rest_v1/login/with_json",
		json = user_info,
)
assert resp.status_code == 200
```
3 . **文件上传**
	主要用在各类项目中：
		1. 上传方式：
			1. body直传
			2. 表单
		2. 请求头说明使用哪种方式
		3. requests技巧：
					如果传递files参数，自动识别为表单文件上传，自动添加请求头
```python
def test_file_upload():
	path = r"E:\Pyproject\file.txt"
	f = open(path,'r')
	
	resp = requests.request(
		method = "post",
		url = "http://api.fbi.com:9225/rest_v1/upload/one_file",
		files = {'file':f}
)
assert resp.status_code == 200
```
4 . **接口关联**
==核心：数据的传递----变量（媒介）==
如何从上一个响应中提取变量：
- re
- jsonpath：json接口
- xpath

流程：
	- 请求第一个接口，得到响应
	- 从响应中提取数据，创建变量
	- 在第二个接口中，使用变量
```python
user_info = {
	"username":"gukangjie",
	"password":"123456"
}
def test_token():
	resp = requests.request(
		method = 'post',
		url = "http://api.fbi.com:9225/rest_v1/login/with_from",
		data = use_info
	)
assert resp.status_code == 200

print(resp.text)       #返回token 身份凭证

#变量提取 

token = jsonpath.jsonpath(resp.json(),"$.token")[0]

resp = requests.request(
	method = 'get',
	url ='http://api.fbi.com:9225/rest_v1/auth/token_with_header',
	header = {"token": token}
)
assert resp.status_code == 200
```
5 . **数据驱动测试**
数据驱动测试 = 参数化测试 + 数据文件（csv、json、yaml、excel、mysql）
