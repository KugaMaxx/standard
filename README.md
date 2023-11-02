# Github 仓库管理规范

## Commit

参考[标准commit规范](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)，每次提交的commit应该遵循以下形式

```
<type>($<scope>): <summary>

---
<details>

  - <subject>: (<description>)
    * <modification> 

  - <subject>: (<description>)
    * <modification>

---
<footer>
```

其中`<type>`表示此次更新的主题/类别，`<scope>`表示此次更新的范围，`<summary>`表示此次更新的简短描述，`<details>`表示此次更新的详细细节。一个简单的示例如下

```
feat($main): add `say_hello()`

---
More detailed explanatory text, if necessary. Wrap it to about 80 characters 
or so. In some contexts, the first line is treated as the subject of the 
commit and the rest of the text as the body. The dash line separating 
the summary from the body is critical (unless you omit the body entirely); 
various tools like `log`, `shortlog` and `rebase` can get confused if you run
the two together.

Further paragraphs come after blank lines.

  - src/__init__.py: a description can be inserted here

  - src/hello.py: a function to print "hello, world"
    * line   58 to   68: add `say_hello()` to welcome
    * line  123 to  156: remove `say_bye()` when shutdown
    * line 1138 to 1164: reformat the code style

  - src/utils.py:
    * line  412 to  456: revised import of some load function and delete some 
    trash lines to make more easy to follow
    * line  632 to  634: this line is a placeholder, do not delete this

---
BREAKING CHANGE: isolate scope bindings definition has changed.

  To migrate the code follow the example below:

  - Before:

    scope: {
      myAttr: 'attribute',
      myBind: 'bind',
      myExpression: 'expression',
      myEval: 'evaluate',
      myAccessor: 'accessor'
    }

  - After:

    scope: {
      myAttr: '@',
      myBind: '@',
      myExpression: '&'
    }

  The removed `inject` wasn't generaly useful for directives so there should be no code using it.

Resolves: #123
See also: #456, #789
```

### Type

`<type>`是每次commit的最重要部分，需要首字母大写，仅限于从下面中选择此次更新的种类

+ `mst` 迭代到最新**版本**
+ `fix` 修复**错误**
+ `feat` 新增**函数**或**功能**
+ `docs` 创建或修复**文档**
+ `style` 重构代码**风格**
+ `refactor` 重构代码**结构**
+ `perf` 提升项目**性能**
+ `test` 增加项目**测试**
+ `chore` 无法分类的**杂项**

### Scope

`<scope>`用于说明 commit 影响的范围，比如可视化、文件读写、样例或问题等。
+ `$` 抽象的**功能**或**模块**
+ `&` 具体的**文件**或**类**
+ `%` 引入项目外的**功能**
+ `#` 解决的**问题**
+ `!` 重要或破坏性的**更改**
+ `*` **无法归类**的提交

### Summary

`<summary>`中如果出现了被操作目标的具体类型，需要按照如下标识区分类型

+ `repo` 库，在第一次引用和大型更新时用到，用v+版本号表示
+ `docs` 文字文档，包括README.md和其它文档（如yaml或html等），注明扩展名即可
+ `file` 代码，指包括了多个函数的文件，注明扩展名即可
+ `func` 函数，需要用双反引号 \` 注明
+ `param` 参数，用双反引号 \` + template:Any 的格式标明参数支持类型
+ `tree` 文件夹下的整体结构，用结构树形式表示
+ `issue` 问题，用#开头+问题编号或注明错误原因（如Warning, Error等，首字母大写）

### Subjet & Details

`<subject>` 是修改的具体位置。`<details>`是该文件夹下的具体修改细节，段首4个缩进，标注行号后一般只接60个字符，然后换行并加上4字缩进，行号一般以修改后的结果为准。
