**服务端脚本语言**
##### 规则：
- php代码以 ****<?php 开始，以 ?> 结尾***
- PHP中的每行代码都必须以分号 **; 结尾
- 在浏览器输出文本的基础指令：**echo 和 print**
##### echo 和 print 和 var_dump 区别？
echo 输出的速度比 print 快

| 语句       | 是否可用于表达式 | 返回值 | 适用场景     |
| -------- | -------- | --- | -------- |
| echo     | 否        | 无   | 输出提示或字符串 |
| print    | ✅        | 1   | 表达式中输出   |
| var_dump | 不推荐      | 无   | 调试查看值与类型 |
单行注释
多行注释
文档注释： `/** ... */`
```php
<?php
/**
 * 打印问候语
 *
 * @param string $name 用户名
 * @return string 返回问候语
 */
function sayHello($name) {
    return "Hello, $name!";
}

echo "hello,wolrd!";

//这是单行注释
# 这也是单行注释
/*
这是多行注释
*/

?>
```







