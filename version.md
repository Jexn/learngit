### 版本发布过程
1. 按git基本操作创建新的文件，git add git commit后提交修改<br/>
2. 然后用git tag <name> 给当前分支打上标签。<br/>
3. git push origin v1.0则可以正式发布Releases.文件会打包发布到GitHub。

### 版本发布问题
1. git tag -a v1.0 -m 'version v1.0 released' <nameID> 其中-a指定标签名，-m指定说明文字。该命令可以指定历史commit版本号。<br/> 
2. git push origin <version num>并不会把仓库的修改一起提交到远程仓库，修改后的文件只会出现在Release上。如果想要同步提交到远程仓库还是得git push origin master