##### **php数据类型有：**
- string  字符串
- integer 整型
- float  浮点型
- boolean 布尔型
- array  数组
- ==object  对象==
- ==null  空值==
- ==resource 资源类型==

> ==object==
> 对象是 **类（class）实例化出来的东西**。  
> 类是模板，对象是根据模板创建出来的“实际物体
```php
class Cat {
    public $name;

    public function meow() {
        echo $this->name . "：喵～";
    }
}

// 创建对象
$myCat = new Cat();
$myCat->name = "小花";
$myCat->meow();  // 输出：小花：喵～

```
**理解对象的三个组成：**
属性：$name
方法：meow
$this：对象本身

> ==resource==
`resource` 表示**由外部系统创建的资源句柄**，它不是一个真正的数据，而是**指向外部资源的“指针”或“连接通道”**。
常见资源数据类型有打开文件、数据库连接、图形画布区域等，将其它类型的值转换为资源没有意义。
用法：
```
get_resource_type(resource $handle): string
```

