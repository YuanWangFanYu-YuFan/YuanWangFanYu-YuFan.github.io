# java string

构造函数

```java
String()
```

> 创建空字符串

```java
String(byte[] bytes)
```

> 通过字节数组来创建字符串，（默认解码器是根据java虚拟机的设置来的？utf-8？）

```java
String(byte[] bytes,Charset charset)
```

> 使用charset所指定的解码器来解析字节数组所对应的字符，并创建字符串

```java
String(byte[] bytes, int offset, int length)
```

> 用默认的解码器解析指定的   子！字节数组，生成对应的字符串

```java
String(byte[] bytes, int offset, int length, Charset charset)
```

> 用charset指定的解码器解析指定的   子！字节数组，生成对应的字符串

```java
String(byte[] bytes, int offset, int length, String charsetName)
```

> 用解析器名称（字符串，charsetname）指定的解析器解析指定的子字节数组，并生成新字符串

```java
String(byte[] bytes, String charsetName)
```

> 用解析器名称（字符串，charsetname）指定的解码器解析字节数组，并创建字符串

```java
String(char[] value)
```

> 用字符数组创建字符串

```java
String(char[] value, int offset, int count)
```

> 用字符数组的子数组创建字符串

```java
String(int[] codePoints, int offset, int count)
```

> 用unicode码点数组的子数组创建的字符串
>
> unicod码点：unicode中一个字符对应的唯一数字标识

```java
String(String original)
String(StringBuffer buffer)
String(StringBuilder builder)
```

> 对几种不同的字符串类型创建新的字符串对象（第一行，对自己也是，不过这叫复制）

> 总结
>
> string构造函数能传入字节数组，字符数组，整数数组和String，StringBuffer，StringBuilder类型
>
> offset		下标起始点
>
> count		元素个数
>
> 字节数组传参：
>
> Charset charset			表示一个解析器对象
>
> String charsetName	表示一个解析器名称



方法

```java
length()
```

> 返回类型：int
>
> 作用：返回字符串长度

```java
isEmpty()
```

> 返回类型：boolean
>
> 作用：判断字符串是否为空（length是否返回的是0），是->true

```java
charAt(int index)
```

> 返回类型：char
>
> 作用：返回指定索引对应的值
>
> error：如果参数小于0或大于字符串长度，抛出IndexOutOfBoundsException

```java
codePointAt(int index)
```

> 返回类型：int
>
> 作用：返回指定索引对应的unicode码点
>
> error：如果参数小于0或大于字符串长度，抛出IndexOutOfBoundsException
>
> ~~此处存在一些疑问，以及不全， 用删除线标记~~



扩展知识点：



~~unicode代理对~~

~~高代理（High Surrogate）：码点范围是 `U+D800` 到 `U+DBFF`。~~

~~低代理（Low Surrogate）：码点范围是 `U+DC00` 到 `U+DFFF`。~~

~~通过组合一个高代理和一个低代理，可以表示一个补充字符~~

~~假设我们要表示一个补充字符，例如笑脸表情符号 😊，它的 Unicode 码点是 U+1F60A。~~

~~高代理：~~
~~计算高代理：(0x1F60A - 0x10000) / 0x400 + 0xD800 = 0xD83D~~

~~低代理：~~
~~计算低代理：(0x1F60A - 0x10000) % 0x400 + 0xDC00 = 0xDE0A~~