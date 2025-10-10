**核心功能：**
- 用例发现
- 用例筛选
- 用例执行
- 用例报告
- 第三方插件

```
安装：

pip install pytest
```

使用（创建用例、执行用例）
```python
def test_abc():
	assert 1 = 2
```

**要求：**
1. 创建test_开头的 .py文件
2. 创建test_开头的函数
3. 在函数中使用断言


```
pytest 启动框架执行用例
```

```
pytest -h  查询参数、配置、使用说明
```

**后期学习路线：**
- 参数
- mark
- fixture
- hook