
# 1 Width 和Height
在 CSS 中，width 和 height 指的是内容区域的宽度和高度。
增加内边距、边框和外边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸。

可以分成两种情况：

1.  传统模式宽度计算: `box-sizing：content-box` 
    1.  盒子大小为  CSS中设置的 width + padding + border （以前默认的）
2.  CSS3盒子模型: `box-sizing: border-box` 
    1.  盒子大小为 CSS中设置的宽度width，里面包含了 border 和 padding
    2.  如果盒子模型我们改为了 box-sizing： border-box ，那padding 和 border就不会撑大盒子了（前提 padding 和 border 不会超过 width 宽度）

详细见: 
obsidian://open?vault=HTML5_CSS3_HeiMaPink_YZHNote&file=CSS%2FChapter2_%E9%80%89%E6%8B%A9%E5%99%A8_%E5%AD%97%E4%BD%93%E6%96%87%E6%9C%AC%E5%B1%9E%E6%80%A7%2FChapter2_02_%E5%AD%97%E4%BD%93%E6%96%87%E6%9C%AC%E5%B1%9E%E6%80%A7_%E9%AB%98%E5%BA%A6%E5%92%8C%E5%AE%BD%E5%BA%A6