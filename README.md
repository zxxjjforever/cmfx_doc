# ThinkCMF文档

ThinkCMF是一款基于ThinkPHP+MySQL开发的中文内容管理框架。ThinkCMF提出灵活的应用机制，框架自身提供基础的管理功能，而开发者可以根据自身的需求以应用的形式进行扩展。每个应用都能独立的完成自己的任务，也可通过系统调用其他应用进行协同工作。在这种运行机制下，开发商城应用的用户无需关心开发SNS应用时如何工作的，但他们之间又可通过系统本身进行协调，大大的降低了开发成本和沟通成本。



此项目用于编写ThinkCMF完全开发手册，我们希望通过git,让更多对CMF感兴趣的朋友参与开发文档的完善。本文档使用MD格式文档编写，方便生成pdf,epub,mobi及html的发行版。我们会定期生成相应的格式。



在线阅读：[ThinkCMF文档](http://www.thinkcmf.com/docs/cmfx)





## 参加步骤

1. 在GitHub上 `fork` 到自己的仓库，如 `your_username/cmfx_doc`，然后 `clone` 到本地，并设置用户信息。

```bash

$ git clone git@github.com:your_username/cmfx_doc.git

$ cd cmfx_doc

$ git config user.name "yourname"

$ git config user.email "your email"

```

* 修改代码后提交，并推送到自己的仓库。

```bash

$ #do some change on the content

$ git commit -am "Fix issue #1: change helo to hello"

$ git push

```

* 在 GitHub 网站上提交 pull request。

* 定期使用项目仓库内容更新自己仓库内容。

```bash

$ git remote add upstream https://github.com/your_username/cmfx_doc

$ git fetch upstream

$ git checkout master

$ git rebase upstream/master

$ git push -f origin master

```
