# Markdown 语法

---

### 标题

- "#" 表示一级标题，也可以用"="表示，写在文字下方
- "##" 表示二级标题吗，也也可以用"-"表示，写在文字下方
- 以此类推，"######" 表示六级标题，最多只有六级

### 分隔线

- "\*\*\*、---"均可以表示分隔线，必须三个及以上

### 字体

- 斜体： "_斜体文本_"
- 粗体："**粗体文本**"
- 粗斜体："**_粗斜体文本_**"
- 文本删除线："~~删除线~~"
- 文本下划线："<u>下划线</u>"
- 文本脚注：文本脚注示例（注意脚本说明一定要换行）[^文件脚注]。

### 列表（无序和有序可以相互嵌套）

- "-、_、+"，均可以表示："_ *表示、+ *表示"
- 数字加"."表示有序列表："[number]. 有序列表"

### 代码块表示

- "```",包裹代码前后

```
这是代码块区域
function(){

}
```

- 文本中包含代码块可以用"`"包裹
- 示例：`（Tab键）`

### 链接

- 链接地址为网址表示 1：[百度地址](http://baidu.com)
- 链接地址网址表示 2：<http://baidu.com>
- 链接地址为图片：![图片](http://static.runoob.com/images/runoob-logo.png)
- 链接地址用变量地址,文末定义网址变量：[百度地址][1]

### 区块使用

- 一个">"表示第一层，两个">"表示第二层，以此类推
- 示例
  > 第一层
  >
  > > 第二层
  > >
  > > > 第三层

### 表格

- "|" 分隔不同单元格
- "-" 分隔表头和其他行
- "-:",右对齐
- ":-",左对齐
- ":-:",居中对齐
  | 表头 1 | 表头 2 |表头 3 |
  | :--------- | ---------: | :---------: |
  | 单元格 11 | 单元格 12 | 单元格 13 |
  | 单元格 21 | 单元格 21 | 单元格 23 |

### 段落（不重要，具体看官网)

- 这是一段文本，段落在 markdown 可以直接，
  使用空格表示换行，也可以在文本的末尾加两个
  空格进行换行

### MarkDown 的其他技巧可以查看官方文档

- markDown 支持直接使用 html 标签，具体看[官网文档](http://markdown.p2hp.com/)

[^文件脚注]: 文本脚注说明

[1]: http://baidu.com
