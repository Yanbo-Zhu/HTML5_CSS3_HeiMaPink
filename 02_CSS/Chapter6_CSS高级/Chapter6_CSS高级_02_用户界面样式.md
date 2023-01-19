# 1 总结

所谓的界面样式，就是更改一些用户操作样式，以便提高更好的用户体验。

- 更改用户的鼠标样式

| 属性   | 用途            | 用途                                    |
| ---- | ------------- | ------------------------------------- |
| 鼠标样式 | 更改鼠标样式cursor  | 样式很多，重点记住 pointer                     |

# 2 鼠标样式 cursor

-设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形状

```css
cursor: default | pointer | move | text | not-allowed;
```

| 属性值         | 描述    |
| ----------- | ----- |
| default     | 小白，默认 |
| pointer     | 小手    |
| move        | 移动    |
| text        | 文本    |
| not-allowed | 禁止    |

```css
<ul>  
  <li style="cursor:default">我是小白</li>  
  <li style="cursor:pointer">我是小手</li>  
  <li style="cursor:move">我是移动</li>  
  <li style="cursor:text">我是文本</li>  
  <li style="cursor:not-allowed">我是文本</li>  
</ul>
```



