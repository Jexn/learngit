## git学习过程中遇到的错误
### git push origin master遇到的错误
<code>
$ git push origin master
To github.com:Jexn/learngit.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:Jexn/learngit.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
</code><br>

如果遇到此错误，说明远程仓库有什么修改你本地没有，需要你先合并远程仓库，然后再做修改：<br>
<code>
git pull origin master
</code><br>
然后就可以正常使用提交命令：<br>
<code>git push origin master</code>