# MyNote

### 远程仓库与本地仓库的联系    *个人见解*

当我们对本地空仓库进行存放数据时，仓库会默认创建master分支，此时若需要将本地仓库push到github，

需要先将仓库里的文件git add到本地仓库里，检查状态，直到不再有未完成操作，保证不遗漏数据，然后执行连接语句，例：

```
$ git remote add origin https://github.com/wangleihd/h5class.git
```
进行连接，注意此时仅仅是预连接，信息是先保存在.git目录下的，config文件里的。

但是通过

```
$ git branch -av
```

还是可以看到会有一个远程连接的分支，这个分支是github仓库的master分支

然后我们就可以通过

```
$ git push origin master

```

来进行仓库的push操作，将本地数据push到你的github仓库里。当然这只是push到master分支，你也可以通过

```
$ git push origin branch-name
```

这个语句push到其他分支

当我们需要github 仓库里的东西时，那么我们可以通过

```
$ git clone url
```

url可以是  https://github.com/jsliker/Course-Design.git

来将远程的仓库clone到本地，当然若服务器上的git已经更新了, 而我们需要将服务器的源码与本地源进行同步进时, 可以使用以下代码

```

$ git pull
```


## 注意

不要在本地建立仓库后，直接与远程仓库进行连接，因为本地仓库没有文件，所以没有创建master分支也就无法连接。

**创建仓库后只有仓库里有文件，才会自动创建master分支**


作者就是因为初学，犯了这个低级错误，刚开始就将建立连接的remote命令执行在刚创建的空仓库中，
结果查询分支时就显示无分支，这可急坏当时的我了......以为犯了什么严重错误，后通过网络，才知道是怎么回事。

我们可以认为本地仓库和远程仓库之间的关系其实可以理解为两种操作

要么是将本地仓库push到远程仓库，要么是将远程仓库clone到本地，在进行pull操作
