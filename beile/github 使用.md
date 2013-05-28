# Git & Github 使用指南
## Git 的起源？  
> Git 诞生于一个极富纷争大举创新的年代。Linux 内核开源项目有着为数众广的参与者。绝大多数的 Linux 内核维护工作都花在了提交补丁和保存归档的繁琐事务上（1991－2002年间）。到 2002 年，整个项目组开始启用分布式版本控制系统 BitKeeper 来管理和维护代码。  
然而，到 2005 年的时候，开发 BitKeeper 的商业公司同 Linux 内核开源社区的合作关系结束，他们决定收回免费使用 BitKeeper 的权力。这就迫使 Linux 开源社区（特别是 Linux 的缔造者 Linus Torvalds ）不得不吸取教训。只有开发一套属于自己的版本控制系统才不至于重蹈覆辙。  
Git 是 Linux Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的分布式版本控制软件，它不同于Subversion、CVS这样的集中式版本控制系统。在集中式版本控制系统中只有一个仓库（repository），许多个工作目录（working copy），而像Git这样的分布式版本控制系统中（其他主要的分布式版本控制系统还有BitKeeper、Mercurial、GNU Arch、Bazaar、Darcs、SVK、Monotone等），每一个工作目录都包含一个完整仓库，它们可以支持离线工作，本地提交可以稍后提交到服务器上。分布式系统理论上也比集中式的单服务器系统更健壮，单服务器系统一旦服务器出现问题整个系统就不能运行了，分布式系统通常不会因为一两个节点而受到影响。  

## Git 的特点  
* 分布式  
* 直接记录快照，而非差异比较  
* 近乎所有操作都是本地执行  
* 时刻保持数据完整性  

## Git 的安装（Mac下） 
推荐使用 homebrew (mac下的包管理器，类似于 yum 等) 安装:   
		
		$ brew install git

检查是否安装成功：
	
		$ git --version  

## Git 的使用 
通过 `git --help` 可以查看到所有 git 命令：
  		
  		$ git --help
  		
## Github 简介  

> GitHub 是一个用于使用Git版本控制系统项目的共享虚拟主机服务。它由GitHub公司（曾称Logical Awesome）的开发者Chris Wanstrath、PJ Hyett和Tom Preston-Werner使用Ruby on Rails编写而成。  

[Github 网站](https://github.com/)


## Github 使用 

下面通过一个简单示例来介绍下 Github 网站的使用，在 Github 中，fork 是比较常用的操作，当我们需要修改别人的项目代码的时候，我们需要首先通过 fork 功能将项目 fork 到自己的资源库中。  

![fork](http://s5.mogujie.cn/pic/130524/2r6z_kqywut2mnjbhms2ugfjeg5sckzsew_523x94.jpg)  

fork 完后，在你自己的目录下就生成了该资源库，例如我的资源库是这样的。  
		
		https://github.com/LeezQ/front-end-practice  

然后我们需要通过 Git 命令将资源库下载到本地。

![git clone](http://s6.mogujie.cn/pic/130524/2r6z_kqyumstynjbdiq2ugfjeg5sckzsew_931x89.jpg)  

通过 Git clone 到本地有三种方式，分别是 `HTTP`、`SSH`、`Git Read-Only`，推荐使用 `SSH` 方式，不过这种方式需要在自己机器上生成一个密钥。你也可以通过 HTTP 方式。命令如下。 
		
		// 创建一个目录，管理你的 git 资源库，名字随意
		$mkdir git-repo 
		
		// 进入到目录中
		$cd git-repo
		
		// 使用 git clone 命令将资源库挂载到本地
		$git clone https://github.com/LeezQ/front-end-practice.git
		
		// 进入 front-end-practice 目录
		$cd front-end-practice
		
		// 使用 git pull 获取最新代码  
		$git pull
		
		// 创建你的目录和文件，以下 yournamedir 指代你创建
		$mkdir yournamedir
		$cd yournamedir
		$touch demo.html
		
		// 提交你的代码  
		$git add yournamedir
		$git commit -m'my demo' yournamedir
		
		// 本地完成操作后，需要 push 到服务器上，git push
		$git push

代码提交后，在你的 github 网站那边就能看到你所提交的代码，然后我们需要将自己改动的东西 pull request 到主库中，点击`Pull Request`按钮

![pull request](http://s4.mogujie.cn/pic/130524/2r6z_kqytcn3cnjbf6wkugfjeg5sckzsew_957x77.jpg)

填写相关信息，然后点击提交即可：

![Send pull request](http://s8.mogujie.cn/pic/130524/2r6z_kqytat2bnjbfiq2ugfjeg5sckzsew_698x425.jpg)  

最后由项目创建人接受你的 pull request 即可在主资源库那边看到你的代码。


