***规则：
- **以 $ 开头，后➕变量名 （如$name）**
- **必须以字母或者下划线_开始**
- **只能包含字母、数字以及下划线（A-z、0-9 和 _ ）**
- **区分大小写（$y 和 $Y 是两个不同的变量）**
- **不包含空格**
- 
四种变量作用域
`local`  局部作用域---局部变量
`global` 全局作用域---全局变量
函数内访问全局变量需要 `global` 关键字或者使用 `$GLOBALS[index]` 数组
```php
$a=5;
$b=3;

function t1()
{  
    global $a,$b;
    echo $a-$b;  // 输出 2
}

t1();

echo PHP_EOL;

function t2()
{
    echo $GLOBALS['a']-$GLOBALS['b'];  // 输出 2
}

t2();

?>
```
`static` 静态作用域
 每次调用函数时， 该变量将会保留请前函的前被调用的值一次
`parameter` 参数作用域
