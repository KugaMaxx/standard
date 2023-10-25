# Github 仓库管理规范

## Commit

每次提交的commit应该遵循以下形式

```
[<type>]: <block>
---
* <subject>: (<description>)
    + <details> 
* <subject>: (<description>)
    + <details>
```
其中`<type>`表示此次更新的主题/类别，`<block>`表示修改的函数、文件的原因，`<subject>`表示修改的文件位置，`<details>`表示修改细节。一个简单的示例如下

```
[Feat]: add `say_hello()`
---
* src/__init__.py: a description can be inserted here

* src/hello.py: a function to print "hello, world"
    + line   58 to   68: add `say_hello()` to welcome
    + line  123 to  156: remove `say_bye()` when shutdown
    + line 1138 to 1164: reformat the code style

* src/utils.py:
    + line  412 to  456: revised import of some load function and delete some trash lines to make 
    more easy to follow
    + line  632 to  634: this line is a placeholder, do not delete this
```

### Type

`<type>`是每次commit的最重要部分，需要首字母大写，仅限于从下面中选择此次更新的种类

+ `mst` 迭代到最新**版本**
+ `docs` 创建或修复**文档**
+ `feat` 新增**函数**或**功能**
+ `fix` 修复**错误**
+ `style` 重构代码**风格**或**结构**
+ `chore` 无法分类的**杂项**

<!-- + `Initial` 第一次创建一个**库**
+ `Release` 将**库**进行一次大版本更新
+ `Revert` 将**库**回退到上一个版本
+ `Update` 更新**文字文档**
+ `Add` 增加**代码**或**函数**或**参数**
+ `Remove` 删除**代码**或**函数**或**参数**
+ `Move` 移动**代码**或**函数**或**参数**
+ `Modify` 修改**代码**或**函数**或**参数**
+ `Improve` 优化**代码**或**函数**的性能
+ `Refactor` 修改**文件夹**的结构分布
+ `Fix` 修复影响程序运行的**问题**
+ `Close` 关闭某个相关的**问题** -->

### Block

`<block>`中填写操作的目标类型，大致分为

+ `repo` 库，在第一次引用和大型更新时用到，用v+版本号表示
+ `docs` 文字文档，包括README.md和其它文档（如yaml或html等），注明扩展名即可
+ `file` 代码，指包括了多个函数的文件，注明扩展名即可
+ `func` 函数，需要用双反引号 \` 注明
+ `param` 参数，用双反引号 \` + template:Any 的格式标明参数支持类型
+ `tree` 文件夹下的整体结构，用结构树形式表示
+ `issue` 问题，用#开头+问题编号或注明错误原因（如Warning, Error等，首字母大写）

### Subjet & Details

`<subject>` 是修改的具体位置。`<details>`是该文件夹下的具体修改细节，段首4个缩进，标注行号后一般只接60个字符，然后换行并加上4字缩进，行号一般以修改后的结果为准。
