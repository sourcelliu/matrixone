# **FIND_IN_SET()**

## **函数说明**

- str 为要查询的字符串
- strList 为字段名，参数以“,”分隔，如(1,2,6,8)
- 查询字段(strList)中包含的结果，返回结果 NULL 或记录。

如果字符串 *str* 在由 N 个子字符串组成的字符串列表 *strlist* 中，则返回值的范围在 *1* 到 *N* 之间。一个字符串列表就是由 *‘,’* 符号分开的子字符串组成。如果第一个参数是常量字符串，第二个参数是 ``SET`` 类型的列，那么 ``FIND_IN_SET()``函数将优化为使用位运算。如果 *str* 不在 *strlist* 中或者 *strlist* 是空字符串，则返回 *0*。如果任一参数为 *NULL* 则返回 ``NULL``。如果第一个参数包含逗号 ``(,)`` 字符，此函数将无法正常运行。

## **函数语法**

```
> FIND_IN_SET(str,strlist)
```

## **参数释义**

|  参数   | 说明  |
|  ----  | ----  |
| str | 必要参数。CHAR和VARCHAR类型都支持。|
| strlist | 必要参数。|

## **示例**

```SQL
select find_in_set('b','a,b,c,d');
+-------------------------+
| find_in_set(b, a,b,c,d) |
+-------------------------+
|                       2 |
+-------------------------+
```