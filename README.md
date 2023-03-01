# Github 仓库管理规范

## Commit

每次提交的commit应该遵循以下形式

```
<type> <block>
---
* <subject>:
    <details>
* <subject>:
    <details>
```
其中`<type>`表示此次更新的主题/类别，`<block>`表示修改的函数、文件或影响的范围，`<subject>`表示修改的文件位置，`<details>`表示修改细节。一个简单的示例如下

```
Add `say_hello()`
---
* src/hello.py:
    line 1119 to 1121: add `say_hello` function
* src/utils.py:
    line    2 to    3: revised import
```

### Type

`<type>`是每次commit的最重要部分，需要首字母大写，仅限于从下面中选择此次更新的种类

+ `Initial` 第一次创建一个**库**
+ `Dump` 将**库**进行一次大版本更新
+ `Revert` 将**库**回退到上一个版本
+ `Update` 更新**文字文档**
+ `Add` 增加**代码**
+ `Delete` 删除**代码**
+ `Feat` 增加新的**函数**
+ `Remove` 移除特定**函数**
+ `Move` 移动**代码**或**函数**
+ `Modify` 修改**代码**或**函数**
+ `Improve` 优化**代码**或**函数**的性能
+ `Refactor` 修改**文件夹**的结构分布
+ `Fix` 修复影响程序运行的**问题**
+ `Close` 关闭某个相关的**问题**

### Block

`<block>`中填写操作的目标类型，大致分为

+ `repo` 库，在第一次引用和大型更新时用到，用\*\*加粗
+ `docs` 文字文档，包括README.md和其它文档（如yaml或html等），注明扩展名即可
+ `file` 代码，指包括了多个函数的文件，注明扩展名即可
+ `func` 函数，需要用双反引号\`注明
+ `tree` 文件夹下的整体结构，用结构树形式表示
+ `issue` 问题，用#开头+问题编号

### Subjet & Details

`<subject>` 是修改的具体位置，`<details>`是该文件夹下的具体修改细节。这两个部分特别详细要求，有必要的时候进行说明即可，标注行号等一般以修改后的结果为准。缩进一般取4格为准
