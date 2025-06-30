<mark style="background: #FF5582A6;">学习website：</mark>
[https://www.runoob.com/python3/python3-data-type.html](https://www.runoob.com/python3/python3-data-type.html)
https://github.com/jackfrued/Python-100-Days/blob/master/
<mark style="background: #FF5582A6;">查看python版本：</mark>
    `python —version`
<span style="background:#fdbfff"><font color="#ff0000">python注释</font></span>
<font color="#fac08f">多行注释 """...""" 要缩进，放在函数最前面，不影响代码结构</font>
```python
  """"
  #内嵌注释  
  """
```
<span style="background:rgba(240, 167, 216, 0.55)">Hash：</span>
哈希是一种通过把数据（比如字符串、对象）转换为一个固定长度的数字（哈希值）的方法，目的是为了快速定位和查找数据。它常用于字典、集合、哈希表等数据结构中。像 Python 的 dict、set 本质上就是基于哈希实现的，查找效率非常高，接近 O(1)
我理解就是：<mark class="hltr-red">通过索引快速找到对应的内容</mark>
<mark style="background: #FF5582A6;">python常用内置数据结构</mark>：
列表
元组
字符串
字典
集合
列表推导式----场景
<font color="#ff0000">**[表达式 for 变量 in 可迭代对象 if 条件]**</font>
[保留或筛选数据项]----提取句子中的字母
[做一些变换]---列表中所有数平方
[排序、过滤数据]---过滤掉小于0点数
字典推导式
<font color="#ff0000">**{key: value for key, value in dict.items() if 条件}**</font>
[对原字典过滤]---选出符合条件的键值对
[重新构造字典]---把一个列表展位字典
[映射转换]---把键值都进行某种处理

| 数据结构        | 可变性   | 是否有序    | 是否可重复  | 主要特点               |     |
| ----------- | ----- | ------- | ------ | ------------------ | --- |
| `list`（列表）  | ✅ 可变  | ✅ 有序    | ✅ 可重复  | 支持增删改查、切片、排序等操作    |     |
| `tuple`（元组） | ❌ 不可变 | ✅ 有序    | ✅ 可重复  | 占用内存少，可作字典键、不可变集合  |     |
| `dict`（字典）  | ✅ 可变  | ✅（3.7+） | ❌ 键唯一  | 通过 key 快速查值，灵活映射结构 |     |
| `set`（集合）   | ✅ 可变  | ❌ 无序    | ❌ 自动去重 | 集合运算（交并差），元素唯一     |     |
| `str`（字符串）  | ❌ 不可变 | ✅ 有序    | ✅ 可重复  | 支持切片、查找、替换、格式化     |     |
**<font color="#ff0000">可变能改内容，有序能找位置</font>**