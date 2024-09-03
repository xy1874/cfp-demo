---
# comments: true
---

# 实验原理

## 1. 字体及链接

无缩进

<!-- &emsp;是全角空格，相当于4个英文空格 -->
&emsp;&emsp;添加空格缩进

&emsp;&emsp;默认字体

&emsp;&emsp;*斜体*

&emsp;&emsp;**粗体**

&emsp;&emsp;^^下划线^^

&emsp;&emsp;~~删除线~~

&emsp;&emsp;更改字体<font color=orange>颜色</font>

&emsp;&emsp;使用Markdown原生语法添加的超链接（当前标签页打开）：[Bing搜素引擎](https://cn.bing.com)。

&emsp;&emsp;使用内嵌HTML添加的超链接（新标签页打开）：<a href="https://cn.bing.com/" target="_blank">Bing搜索引擎</a>。


## 2. 图表

### 2.1 图片示例

&emsp;&emsp;使用Markdown原生语法添加的图片：

![图片描述](assets/3-1.png)  <!-- 可以是本地图片或网络图片 -->

&emsp;&emsp;使用内嵌HTML添加的图片（支持居中、调节大小等）：

<center><img src="../assets/3-1.png" width = 150></center>
<center>图3-1 XXXXX</center>

!!! tip "提示框 :bulb:"
    &emsp;&emsp;使用Markdown原生语法添加图片时，使用的是图片相对于当前`.md`文件的路径。  
    &emsp;&emsp;使用内嵌HTML添加图片时，使用的是`site`文件夹下，图片相对于当前`.md`文件所生成的`.html`文件的路径，故需在图片路径前添加`../`。

    &emsp;&emsp;PS：更多关于提示框使用方法，请参考<a href="https://squidfunk.github.io/mkdocs-material/reference/admonitions/" target="_blank">Material for MkDocs/References/Admonitions</a>。

### 2.2 表格示例

&emsp;&emsp;表格示例：

<center>        <!-- 设置表格居中 -->
<center>表3-1 XXXXX</center>

| 表头1 | 表头2 | 表头3 |
| :-: | :- | -: |
| 本列居中 | 本列左对齐 | 本列右对齐 |
| ... | ... | ... |

</center>       <!-- 设置表格居中 -->



## 3. 代码及公式

### 3.1 代码示例

&emsp;&emsp;代码块示例：

``` C
int main(void)
{
    return 0;
}
```

&emsp;&emsp;行内代码示例：主函数的返回类型是`int`，参数是`void`。

### 3.2 公式示例

&emsp;&emsp;公式块示例：

$$
\sum_{i=1}^n a_i=0
$$

&emsp;&emsp;行内公式示例：$ \sum_{i=1}^n a_i=0 $.

&emsp;&emsp;关于数学公式的编写，请参考<a href="https://blog.csdn.net/wzk4869/article/details/126863936" target="_blank">此博客</a>。
