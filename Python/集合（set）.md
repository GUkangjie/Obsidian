==**特性**==
1. **无序性**：一个集合中的元素之间是无序的。
2. **互异性**：一个集合中，任何两个元素都不相同，即元素在集合中只能出现一次。
3. **确定性**：给定一个集合和一个任意元素，该元素要么属这个集合，要么不属于
==通过 `in` `not in` 来确定在不在集合内==
**集合的成员运算在性能上要优于列表的成员运算**
**<span style="background:#b1ffff">创建集合</span>**：set
集合元素是无序的，因此集合中的每个元素打印的位置都具有不确定性
```python
set1 = {'Python', 'C++', 'Java', 'Kotlin', 'Swift'}
for elem in set1:
    print(elem)
```
集合的运算符
<mark class="hltr-purple">通过`issubset`和`issuperset`来判断集合之间的关系</mark>
**判断一个集合是不是另一个集合的超集：issuperset**
**判断一个集合是不是另一个集合的子集：issubset**
**判断两个集合有没有相同的元素：isdisjoint**
![[Pasted image 20250627101422.png]]
添加元素：set.add()
删除元素：set.discard()  set.remove()
`remove`方法在元素不存在时会引发`KeyError`错误,所以上面的代码中我们先通过成员运算判断元素是否在集合中。
清空元素：set.clear()
###### **<font color="#ff0000">不可变集合</font>**
有一种不可变类型的集合，名字叫`frozenset`（不能添加和删除元素）

