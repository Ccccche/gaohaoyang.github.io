---
layout: post
title:  "学习flutter笔记"
date:   2019-03-28
categories: 技术
tags: flutter
---

* content
{:toc}

## 特性

### 注释
- 每向类添加summary的时候使用大片注释的时候，该注释可以在外部通过**dartdoc**导出

```

   ///这是一个summary

``` 
### 关键字

- 定义常量的时候不用显示声明变量类型,final类型只能被设置一次，const是常量（隐式常量）

```

final name1 = "张三";
//final String name1 = "张三";

const name2 = "李四";
//const String name2 = "李四";

```

- const还可以创建一个常量值，声明创建常量值的构造函数；换言之就是const可以创建一个空的，不可变的变量类型

```

final finalList = const []; //finalList一直是一个空的不可变的列表

const constList = const []; //constList是一个编译时常量的空的不可变列表


```

- 字符串在单引号中添加单引号必须在前面加\

```

'this\'s a test';

```

- 字符串连接的时候如果是连续添加多个单引号或者双引号时候不允许出现空格，并且可以不用在每个引号变量之间使用+连接

```

String connectionStr = '字符串''没有加号的''连接';
print(connectionStr);//字符串没有加号的连接

```

- 使用三引号可以一次添加多行字符串
 
 ```
    String connectionString = '''
        这是用单引号创建的
        多行字符串。
        同理双引号也可以。
    ''';
    print(connectionString);
    /*  这是用单引号创建的
        多行字符串。
        同理双引号也可以。
        */

 ```

- 当声明正则表表达式的时候，在字符串添加r可以避免\被吞。

- 可以在字符串中使用$+变量名称，可以直接在字符串中添加变量值。（类似js的特性了）

 ```

    var height = 48.0;
    print('当前标题高度是$height');//当前标题高度是48.0

 ```
- 可以直接打印list中的值，**这点和c#不太一样，c#必须要使用循环**

- ..连级符号，即在同一个对象上连续进行操作
 ```
    String a = (new StringBuffer()
                ..write('test1 ')
                ..write('test2'))
            .toString();

    print(a);
    //test1 test2
 ```

- ~/是除法的取商，/是除法的取真实值，%是除法的取模