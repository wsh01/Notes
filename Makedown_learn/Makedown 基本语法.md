# Makedown语法
---
注意事项
* 新建一个文件, 命名为 test.md, 注意后缀一定要是 .md!!! 这样表明它是一个 Markdown 文件. 所有笔记文件都应该以 .md 作为后缀.
* 先后顺序按下快捷键 Ctrl + K, V, 开启预览窗口.
* [教程地址]（https://zhuanlan.zhihu.com/p/366596107）
* 数学公式用到再学
  
  ---
# 一级标题  
```语法：# 一级标题```
## 二级标题
```语法：## 二级标题```
### 三级标题
```语法：###三级标题```

---
``` 分割线 语法：--- ```

---

**重点加粗**
```命令：**重点加粗**```

---
*斜体*
```命令：*斜体*```

---
~~删除线~~
```命令：~~删除线~~```v

---
列表：

* 无序列表
  * 嵌套无序列表
  *  嵌套无序列表
  *  嵌套3
* 有序列表
  * 嵌套1
    * 再嵌套  
      * 继续嵌套
```
语法：
* 无序列表
  * 嵌套无序列表
  *  嵌套无序列表
  *  嵌套3
* 有序列表
  * 嵌套1
    * 再嵌套  
      * 继续嵌套
 ```     
 ---
>引用别人的话
>就这样写
```
语法：
>引用别人的话
>就这样写
```
---
这是行内代码语法。

代码块语法：

``` python
print ("Hellow, World")
```

``` C++
#inclode<iostream>
using namespace std;
int main(void)
{
    printf("Hellow Markdown");
    return 0;
}
```



---
[github地址]（https://github.com/HKUST-Aerial-Robotics/GVINS）

```
语法：
[超链接名称](链接地址)
```

---
表格：

|表头|表头|
|----|----|
|内容|内容|
|内容|内容|
```
语法：
|表头|表头|
|----|----|
|内容|内容|
|内容|内容|
```
---
注释：
<!-- 你看不见我 -->
```
语法：
<!-- 你看不见我 -->
```
---
===高亮===
```
语法：
===高亮===
```
---
图片插入
![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v2789a7fa429304f029c9044ede4149a9e.png)

按下快捷键 Ctrl + Alt + V,

就能把图片自动保存到当前目录下, 并以正确的格式粘贴到当前的 Markdown 文件中.

如果你需要上传到图床, 便于在互联网中分享的话, 也可以用 Better Markdown & Latex Shortcuts 中的功能, 按下快捷键 Shift + Ctrl + Alt + V, 就可以上传到图床并自动以正确格式粘贴到当前 Markdown 文件中.

---
数学公式(Latex语法)：
单位圆 $x^2+y^2=1$

公式块
$$
\begin{cases}
x=\rho\cos\theta \\
y=\rho\sin\theta \\
\end{cases}
$$


较小的行内行分数 $\frac{1}{2}$

展示型的分式 $\displaystyle\frac{x+1}{x-1}$

开平方 $\sqrt{2}$

---

# 插件增加的快捷键
## 1.Makedown 语法
&emsp;1.```Ctrl+B```**当前有选中的文本时**，将文本加粗
&emsp;2.```Ctrl + I```**当前有选中文本时**, 将文本变为斜体
&emsp;3.```Ctrl + M``` 进入数学公式模式 (加入美元符)
## 2.图片粘贴
&emsp;1.```Ctrl + Alt + V``` 粘贴剪贴板图片 (本地)
&emsp;1.```Ctrl + Alt + V``` 粘贴剪贴板图片 (图床)

---
## 文字缩进语法```&emsp;```
---
提交到GitHub
注意提交信息，windows下提交时跳出的编辑器是给你写描述信息的，
![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v25c2fb9651be546e5bf99422e2eb2e520.png)要不然会出现下列情况（rename the file就是提交的信息）
![](https://pic3.58cdn.com.cn/nowater/webim/big/n_v2795e2ee29cbd4b6591f7eda24141667d.png)