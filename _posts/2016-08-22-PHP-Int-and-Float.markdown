
---
layout:     post
title:      "PHP数值比较"
date:       2016-08-22
author:     "Sim"
catalog: false
tags:
    - PHP
---

由于对PHP没有系统的学习，在某段程序中，发现一个奇怪的问题，就是无论怎么改，'3.0 == 3'的这个条件始终不成立。原因是因为，PHP是一种强类型的语言，3.0属于浮点数，3是整形，3.0只是无限接近于3，而不会等于3，所以无论是使用'=='还是'==='，结果都是false。另外，'=='只会比较数值，而'==='是首先比较类型再比较值，两者要注意区分。
所以，要想比较一个整形数值和浮点数的话，可以将整形数值通过'number_format()'函数转化为浮点数

```php
$num = 3;
if (number_format($num, 2) == 3.0) {
	echo 'Equal';
}

// Equal
```


