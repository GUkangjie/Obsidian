try / except 是用来**兜底处理程序中可能出错的代码**。
我们把**可能出错的代码**写在 try 代码块里，
如果那段代码在运行过程中真的出现了**特定的错误（异常）**，程序就会立刻跳到 except 中，执行我们预设的“出错时的处理方式”，从而**避免程序崩溃**。
正则和match**是经常一起使用的组合**，在 Python 中几乎是标配操作
```python
import re
pattern = r"^\\d+\\.\\d+$"   # 匹配一个浮点数，比如 12.34
text = "12.34"
match = re.match(pattern, text)
if match:
    print("匹配成功")
print("结果是：", match.group())  # 输出匹配到的字符串
else:
    print("匹配失败")
```
input输入获取输入的默认是字符串
文件读写和异常处理
```python
try:
# 放可能出错的代码
可能会出错的语句
except 错误类型:
# 如果出错就执行这块
错误时的处理逻辑
```