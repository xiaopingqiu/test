1. 两个全局设置
` git config --global user.name "xpaiu"`
` git config --global user.email "q.giskard@gmail.com"`

2. 创建一个新的版本库
在需要创建版本库的目录下运行`git init`，就完成了创建，该目录下会出现一个`.git`隐藏目录。

3. 把文件添加到版本库
+ 先用`git add`命令将文件添加到仓库
 `git add step1.md`
 若执行成功，则没有任何返回信息，没有消息就是好消息。
+ 然后用`git commit` 命令将文件提交到仓库
`git commit step1.md -m "comments"`
注意后面的`-m "comments"` 是对本次提交的一个说明，方便以后查看修改记录。
 执行成功以后，会返回类似如下的信息：
 > [master （root-commit） d83e152] add global config and create a new repository
>  1 file changed, 8 insertions(+)
>     create mode 100644 step1.md

注意，`git commit`可以一次提交多个文件，示例如下：
```
git add file1
git add file2
git add file3
git commit -m "add 3 files"
```

