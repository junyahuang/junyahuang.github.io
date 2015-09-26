---
layout: post
title: 用最快捷的方式搭建个人博客
date: 2015-09-24
categories: blog
tags: [博客]
description: 利用Github以及Fork大法搭建个人博客


---




## 前言



为什么要创建博客



如今微博微信朋友圈泛滥成灾，短小精悍便于书写，也便于与人交流的社交软件使长文章渐渐退出大众的视野，表示尚留几分，占据统治地位的依然是各类鸡汤文。再加上网民阅读耐心下降，一些人更产生一种“文章太长不看”的习惯。这些因素使博客衰退，更使个人博客成为苍茫大海中的孤岛，只能孤芳自赏————

那又怎么样呢？

————别无他意，只为了取悦自己。

能在自己的地盘上驰骋，也不需要纠结无用的访量，可以自由的修改，可以尽情的欣赏自我，足够了。

我于2015年9月开始探索个人博客的搭建方法，尝试了若干方法，最终发现[博主陈素封](cnfeat.com)的文章，选用了她推荐的——**以github以及Jekyll为核心**的构造方式，不必对那两个英文发怂，因为说白了这真是一种简单到丧心病狂无以伦比的方法，这也是我选用这个方法的主要原因，**适用于一切初学者**。但容我于下文一一向诸位看官解析。


适用人群——包括但不仅限于

- 博客初学者
- 对代码完全没有概念的文科生
- 喜欢折腾的同学
- 码农

- - -



## 正文

- 操作系统 ： Mac OS X
- 用户名：junya（以下涉及到用户名的位置均用junya代替）
- 必要软件：github客户端


###第零步   
####————购买一个属于你的域名



- 没有域名怎会有个人博客，可以购买域名的地方有很多，个人推荐**godaddy**，安全可靠还支持支付宝，但网站为**全英文**，英文有压力的同学稍微会比较难受。

购买域名步骤如下:

- 首先打开[**godaddy**](https://www.godaddy.com),搜索你想要的域名，SEARCH DOMAIN,如果搜到了可用的，CONTINUES TO CART, 之后会推荐你购买额外服务，无视即可，拉到尾页继续CONTINUES TO CART

![]http://7xlzhh.com1.z0.glb.clouddn.com/9-24博客1.png

![]http://7xlzhh.com1.z0.glb.clouddn.com/9-24博客2.png

- 默认为租五年，改为一年或两年即可。proceed to checkout

- ps,此时可以在网上搜索godaddy的优惠码，种类丰富，寻一个填入code区域，有时会优惠不少

![]http://7xlzhh.com1.z0.glb.clouddn.com/9-24博客3.png

- 新用户则注册，填写资料后注意地区选择CHINA，否则不可使用支付宝支付，注册后使用支付宝付费即可。



- 这样你就可以获得只属于你的域名了（虽然是有租期的）



###第一步
####了解Github

**github**
https://github.com/

github是全球最大的源代码托管平台，提供一个免费的仓库，免费用户和收费用户的区别在于能否创建私人仓库，但是作为小型博主，我们不需要在意这些细节，免费用户即可，这便是一个免费的不限流量服务器。

加上github提供github pages功能，可以使用jekyll搭建静态博客站点，两者搭配几乎完美。

 


####注册Github账号

注册过程并不困难，但要注意注册时**不要使用带大写字母的用户名**，会出现乱七八糟的奇妙错误现象——至少我是如此。




###配置SSH keys

- 配置ssh keys的原因是使本地git与远程github关联————总之是一件很重要的事
 
- 本文使用mac系统，windows系统请参阅beiyuu的[《使用Github Pages建独立博客》](http://beiyuu.com/github-pages/)
- 注：本文亦是参考此博客书写

####检查本地ssh key

打开终端（默认位于应用程序-实用工具中），输入如下代码：

          ^$ cd ~/.ssh 检查本机的ssh密钥
          
 如果此时提示：No such file or directory，说明本机没有ssh，可以直接看第三部
 
####备份和移除本地SSH

 
        $ ls
        config  id_rsa  id_rsa.pub  known_hosts
        $ mkdir key_backup
        $ cp id_rsa* key_backup
        $ rm id_rsa*
        
        
####生成新的SSH key

      $ ssh-keygen -t rsa -C "邮件地址@xxxx.com"
      
      注意区分大小写，-C必须大写，
      邮件地址处填入你注册github时的邮箱   

      
      
 **然后回车**，会跳出如下文字
      
      
      Generating public/private rsa key pair.
      Enter file in which to save the key (/Users/
      your_user_directory/.ssh/id_rsa):
      
      <此处是文件路径名，保持默认就好，所以记住文件位置后，直接点回车>
      
      
      
 **然后系统会要求你输入一个密码（用于以后SSH验证）**
 
 
    Enter passphrase (empty for no passphrase):<输入加密串>
    Enter same passphrase again:<再次输入加密串>
      
注意：输入密码的适合没有*字样，不管打多少字符都只会显示一个 * ，所以直接输入就行，系统会记录的

最后如果看到一大串类似这样的界面，便是成功设置SSH key

![](http://cnfeat.qiniudn.com/11.png)


###添加新生成的SSH key到Github界面


- 设置完SSH key后，还要提交到Github上，以完成SSH链接的设置

- 按着刚刚记录下来的位置，找到并打开.ssh\id_rsa.pub文件，此文件内容伪刚刚生成的密钥。如果看不到这个文件，**你需要设置显示隐藏文件**，windows用户可以在文件夹选项设置，mac用户需要在终端处输出显示隐藏文件的代码，[代码查询]（http://sspai.com/26273）

- 登陆github系统。点击右上角的用户图标--->Settings--->SSH keys---> add SSH keys

- 把之前密钥复制到key文本框中，title随意输入（比如我的是mac）





###测试

可以在终端输入如下命令，看看设置是否成功，git@github.com部分是固定的，不要更改





     $ ssh -T git@github.com

如果是下面的反馈：

    The authenticity of host 'github.com (207.97.227.239)' can't be established.
    
    RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
    
    Are you sure you want to continue connecting (yes/no)?

输入yes，然后会看到：

    Hi xxxx! You've successfully authenticated, but GitHub does not provide shell access.



###设置用户信息

现在你已经可以通过SSH链接到GitHub了，还有一些个人信息需要完善的。

Git会根据用户的名字和邮箱来记录提交。GitHub也是用这些信息来做权限的处理，输入下面的代码进行个人信息的设置，把名称和邮箱替换成你自己的，名字必须是你的真名，而不是GitHub的昵称。

    $ git config --global user.name "xxxx"//用户名
    $ git config --global user.email  "xxxx@xxxx.com"//填写自己的邮箱
    
    
    
   
###SSH Key配置成功

本机已成功连接到github。

恭喜你完成了最重要的一步。



##Fork 他人博客


###寻找到合适的博客源

什么？你想独自打造只属于你的博客？

那样好麻烦啊，因为我压根没这么干，因为这种时候只需要**复制粘贴**

[Jekyll-powered blogs and Source](https://github.com/jekyll/jekyll/wiki/Sites)

这里是一些使用Jekyll的博客，你看谁的最顺眼，copy下来并加以改造就可以了。

[Michael Rose's github](https://github.com/mmistakes)

这是我收集到的大神博客，你也可以copy这里的

[Shihya.com](https://shihya.com)

当然还有我的，点博客下发的小喵图标就可以找到我的github

###修改github数据

- 在你喜欢的博客源github页面处，点击右上角的fork

![]http://7xlzhh.com1.z0.glb.clouddn.com/9-24博客5.png

- 回到你自己的仓库，将" xxxx.github.io " ，改为"你的用户名.github.io"（例如我的用户名是junyahuang，便改为junyahuang.github.io）

![]http://7xlzhh.com1.z0.glb.clouddn.com/9-24博客4.png

- 此时"你的用户名.github.io"便可以访问了

- 设置DNS，会在下文贴出来

- 回到之前github的页面，找到"CNAME"文件，将文件中的网址改为你之前申请的域名，这样你的域名就可以连接github pages了（如下图，将我的sinhya.com改为你的域名）

![]http://7xlzhh.com1.z0.glb.clouddn.com/9-24博客6.png

- 这个博客从此属于你，你可以任意修改


###DNS设置（图片内容来自cnfeat.com）


此处推荐使用DNSpod

注册[DNSpod](www.dnspod.cn)，添加域名，如下图设置。（每个人的设置可能会不同）

![](http://cnfeat.qiniudn.com/15.png)



其中A的两条记录指向的ip地址是github Pages的提供的ip

- 192.30.252.153
- 192.30.252.154

如博客不能登录，有可能是github更改了空间服务的ip地址，记得及时到在[GitHub Pages](https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider/)查看最新的ip即可

指定的记录是你在github注册的仓库。

###去Godaddy修改DNS地址

更改godaddy的Nameservers为DNSpod的NameServers。

![](http://cnfeat.qiniudn.com/16.png)

1、点击「My Account」，管理我的域名。

![](http://cnfeat.qiniudn.com/17.jpg)


2、点击域名。

![](http://cnfeat.qiniudn.com/18.jpg)



3、将godaddy的Nameservers更改成f1g1ns1.dnspod.net和f1g1ns2.dnspod.net


![](http://cnfeat.qiniudn.com/19.jpg)



##博客创建完毕

没错，你没看错，你的博客已经创建完毕了，


接下来就是把博客私人化了。关于这个内容我之后有空会补充说明。


