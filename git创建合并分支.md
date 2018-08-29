首先，创建dev分支，然后切换到dev分支：<br>
<code>git checkout -b dev</code><br>
git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：<br>
<code>$ git branch dev</code><br>
<code>$ git checkout dev</code><br>
<code>switch to branch 'dev'<code><br>

然后,用git branch命令查看当前分支:<br>
<code>$ git branch</code><br>
* dev<br>
  master<br>

git branch命令会列出所有的分支，*标注的为当前分支<br>

我们就可以在dev分支上正常提交，比如对readme.txt做个修改，加上一行：<br>

<code>Creating a new branch is quick.</code>
然后提交：
<code>$ git add readme.txt</code><br> 
<code>$ git commit -m "branch test"</code><br>
<code>[dev b17d20e] branch test</code>
<code> 1 file changed, 1 insertion(+)<code>
现在，dev分支的工作完成，我们就可以切换回master分支：<br>
<code>
$ git checkout master
Switched to branch 'master'</code>
切换回master分支后，再查看一个readme.txt文件，刚才添加的内容不见了！因为那个提交是在dev分支上，而master分支此刻的提交点并没有变：

现在，我们把dev分支的工作成果合并到master分支上：

$ git merge dev
Updating d46f35e..b17d20e
Fast-forward
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
git merge命令用于合并指定分支到当前分支。合并后，再查看readme.txt的内容，就可以看到，和dev分支的最新提交是完全一样的。

注意到上面的Fast-forward信息，Git告诉我们，这次合并是“快进模式”，也就是直接把master指向dev的当前提交，所以合并速度非常快。

当然，也不是每次合并都能Fast-forward，我们后面会讲其他方式的合并。

合并完成后，就可以放心地删除dev分支了：

$ git branch -d dev
Deleted branch dev (was b17d20e).
删除后，查看branch，就只剩下master分支了：

$ git branch
* master
因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在master分支上工作效果是一样的，但过程更安全。

## 小结
Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

内容来自廖雪峰git教程