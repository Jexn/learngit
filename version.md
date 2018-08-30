### 版本发布过程
> 1 . 按git基本操作创建新的文件，git add git commit后提交修改<br/>
> 2 . 然后用git tag <name> 给当前分支打上标签。<br/>
> 3 . git tag -a v1.0 -m 'version v1.0 released' <hash> 其中-a指定标签名，-m指定说明文字。<br/>
> 4 . git push origin v1.0则可以正式发布Releases.文件会打包发布到GitHub。