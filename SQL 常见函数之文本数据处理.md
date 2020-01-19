# SQL 常见函数之文本数据处理

## 字符函数用于字符数据的处理

+ 返回第一个字符的ASCII编码和返回ASCII编码n对应的字符
ASCII和char函数是互为反运算

```sql
SELECT ASCII('SQL'), CHAR(83) from dual;
```

+ 拼接字符串
连接操作用于将两个或者多个字符串拼接到一起，CONCAT函数是执行连接操作的标准，Oracle只能操作两个字符，其他可以使用多个,concat_ws可使用分隔符将字符连起来，Oracle没有concat_ws函数

```sql
select concat('1','2','3') from dual;
select concat_ws('-','S','Q','L') from dual;
```

+ 返回字符串的小写形式
LOWER 函数将字符转换为小写，UPPER 函数将字符转换为大写

```sql
select upper('hello sql'),lower('HELLO SQL') from dual;
```

+ 字符串长度
字符串的长度可以按照两种方式进行计算：字符数量和字节数量
对应的函数时charlength和octetlenght函数

```sql
SELECT char_length('笔记本') 字符长度,octet_length('笔记本') 字节长度 from dual;
```

![1PVFtx.png](https://s2.ax1x.com/2020/01/20/1PVFtx.png)
oracle使用length和lengthhb函数计算字符和字节数量

+ 返回字符串从位置n开始的m个字符
SUBSTRING函数或者SUBSTR函数用于返回字符串中的子串

```sql
select substr('MySQLWorkbench',4,2) from dual;
```

字符的序号要从1开始,第4个字符Q开始,往后数2个字符:QL

+ 截断字符

TRIM函数删除字符串开头和结尾的指定字符串,如果不指定就是空白字符

```sql
select trim('#' from '#S-Q-L#') 删除指定字符,trim('   hello word   ') 删除空白字符  from dual;
```

![1PVs3T.png](https://s2.ax1x.com/2020/01/20/1PVs3T.png)

ltrim和rtrim是只删除字符串左边和右边的字符

+ 查找与替换
instr函数返回指定字符串出现的位置,**没有找到返回0**,replace函数用于替换字符串中的子串,instr和substr函数组合使用

```sql
select instr('MySQL Workbench','b') 查询字符串,replace('MySQL Workbench','ben','BEN') 替换字符串 from dual;
```
