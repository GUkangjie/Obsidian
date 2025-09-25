**`operator`**
![[Pasted image 20250707104428.png]]
**`sorted`**
从功能上讲和列表的sort没有区别，但它会返回排序后的列表对象，而不是直接修改原来的列表
**time.time()**
```python
import time
start = time.time()
# 你要统计的代码
time.sleep(1.5)
end = time.time()

print(f"耗时：{end - start:.3f} 秒")
```
**`datetime` 模块**
适合用于显示/记录时间戳
```python
from datetime import datetime
start = datetime.now()
# 代码
time.sleep(1.5)
end = datetime.now()

print(f"耗时：{(end - start).total_seconds():.3f} 秒")
```

