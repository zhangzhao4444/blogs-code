title: 删除遗忘的 vpn 存储凭据
date: 2015-01-31 11:21:16
updated: 2015-01-31 11:21:16
categories: [Android Framework]
tags: [android]
---

自从入手了 nexus7，公司就不时有人来玩下新系统的新功能。上次好像谁给我设了什么加密的破密码，后面他好像解除掉了，但是不知道为什么每次我进系统设置的 vpn 界面，就弹个什么鸟界面，让我输入什么存储的凭据，我刚开始以为是我设置锁屏的 PIN 码，但是不对。连续输错了3次后，系统提示说存储凭据已被删除，但是还是让我继续输存储凭据的密码，不让我添加、编辑 vpn 。我操，哪个脑残设计的， vpn 和这玩意有关系么，以为是 vpn 帐号的密码，试了好几次也不是。

搞得我差点想去改源码，废了这个脑残的东西（后面知乎上有人说老外用 vpn 的场景一般是公司内部比较隐身的网络，所以需要设置一些加密措施，不像国内一般是翻墙用的）。后面度娘发现，好像这个鸟 keystore 存在：

<pre>
# 当前用户
/data/misc/keystore/user_0/.masterkey
</pre>

NND，哥自己编的系统，root 权限随便玩，二话不说，shell 上去 rm 掉，然后重启，终于可以玩 vpn。蛋蛋疼。


