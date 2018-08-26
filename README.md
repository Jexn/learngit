##git学习过程

###创建git远程仓库，链接远程仓库过程

* 第一步，创建本地密钥，看看用户主目录下有没有.ssh目录，而且该目录下有没有id_rsa和id_rsa.pub文件。如果没有，则输入
<code>ssh-keygen -t rsa -C 'youremail@example.com'</code>
创建自己的私钥和公钥。id_rsa是私钥，id_rsa.pub是公钥。
* 第二步，登陆Github，进入Settings -- SSH and GPG keys -- New SSH key，输入id_rsa.pub的内容。
* 第三步，Create a new repository创建自己的仓库，记录自己仓库的ssh链接
* 第四步，在本地bash上输入命令：
    <code>git remote add origin git@github.com:Jexn/learngit.git</code>
    链接到GitHub远程仓库。
* 第五步，把本地master推送到github,注意：未成master的目录无法进行推送，可以用<code>git init</code>转换成master。
    <code>git push -u origin master</code>推送本地项目到远程仓库
* 从现在起，可以通过<code>git push origin master</code>提交修改了

##SSH警告
* 当你第一次使用git的clone或者push命令连接到GitHub时，会得到一个警告：
<code>
    The authenticity of host 'github.com (xx.xx.xx.xx)' can't be      stablished.
    RSA key fingerprint is xx.xx.xx.xx.xx.
    Are you sure you want to continue connecting (yes/no)?
</code>
    这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入yes回车即可。
    Git会输出一个警告，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：
    <code>
    Warning: Permanently added 'github.com' (RSA) to the list of known hosts
    </code>
    这个警告只会出现一次，后面的操作就不会有任何警告了。
    如果你实在担心有人冒充GitHub服务器，输入yes前可以对照GitHub的RSA Key的指纹信息是否与SSH连接给出的一致。