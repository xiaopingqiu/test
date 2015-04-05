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

4. 查看和提交修改
+ 如果对仓库里的文件进行了修改，可以用`git status` 命令来查看哪些文件被修改过了。运行`git status` ，典型的输出如下：
>位于分支 master
>尚未暂存以备提交的变更：
> （使用 "git add <file>..." 更新要提交的内容）
>   （使用 "git checkout -- <file>..." 丢弃工作区的改动）
>
>   	修改:         step1.md
>
>未跟踪的文件:
>  （使用 "git add <file>..." 以包含要提交的内容）
>
>  	.step1.md.swp
>
>修改尚未加入提交（使用 "git add" 和/或 "git commit -a"）

注意，这里从输出的信息可以看到，有一个文件`step1.md`被修改了，但未提交到仓库。此外，还有一个文件未被本仓库跟踪，`.step1.md.swp`，这是我用`vim`编辑文本过程中产生的swap文件，不需要被跟踪，所以不管这个。

+ 用`git diff` 命令来查看具体哪里被修改了。
`git diff step1.md`
典型的输出如下：
>diff --git a/step1.md b/step1.md
>index f85f9c4..112ed56 100644
>--- a/step1.md
>+++ b/step1.md
>@@ -5,4 +5,23 @@
> 2. 创建一个新的版本库
>  在需要创建版本库的目录下运行`git init`，就完成了创建，该目录下会出现
>   
>  +3. 把文件添加到版本库
>  ++ 先用`git add`命令将文件添加到仓库
>  + `git add step1.md`
>  + 若执行成功，则没有任何返回信息，没有消息就是好消息。
>  ++ 然后用`git commit` 命令将文件提交到仓库
>  +`git commit step1.md -m "comments"`
>  +注意后面的`-m "comments"` 是对本次提交的一个说明，方便以后查看修改记
>  + 执行成功以后，会返回类似如下的信息：
>  + > [master （root-commit） d83e152] add global config and create a ne
>  +>  1 file changed, 8 insertions(+)
>    +>     create mode 100644 step1.md
>    +
>    +注意，`git commit`可以一次提交多个文件，示例如下：
>    +```
>    +git add file1
>    +git add file2
>    +git add file3
>    +git commit -m "add 3 files"
>    +```

注意到这里运行`git diff` 其实就是调用了linux的`diff`命令。返回的格式自然也就跟`diff`一样了。

+ 跟添加新文件一样，用`git add`来提交修改过的文件
`git add step1.md`
然后再运行`git status`，会发现输出有了一点变化：
>位于分支 master
>要提交的变更：
>  （使用 "git reset HEAD <file>..." 撤出暂存区）
>
>  	修改:         step1.md
>

这里输出的意思是告诉我们`step1.md`的修改将被提交到`master`分支

+ 同样的，运行`git commit`命令提交修改到仓库
提交完成后，再运行`git status`, 典型的输出如下：
>位于分支 master
>无文件要提交，干净的工作区

dfdhgjhgjhfjgh
