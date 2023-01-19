# 1 新特性 总结

![](image/Chapter7_CSS3新特性_总结_001.png)
![](image/Chapter7_CSS3新特性_总结_002.png)


# 2 浏览器私有属性

浏览器私有前缀是为了兼容老版本的写法，比较新版本的浏览器无须添加。

1. 私有前缀
   
   - `-moz-`: 代表firefox浏览器私有属性
   - `-ms-`: 代表ie浏览器私有属性
   - `-webkit-`: 代表safari、chrome私有属性-o-∶代表Opera私有属性

2. 提倡的写法
   
   ```
   -moz-border-radius: 10px;
   -webkit-border-radius: 10px;
   -o-border-radius: 10px;
   border-radius: 10px;
   ```


