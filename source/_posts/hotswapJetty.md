---
title: hotswapJetty
date: 2018-02-02 17:13:47
tags: [basic]
---
### 前言
```markdown
  只是热部署, 热加载没成功
```
### 尝试
* 原来用的jRebel 在spring 内置tomcat 用 velocity 没毛病, 现在用了 wf +jetty + velocity 
* 按道理来讲jRebel 是默认支持 class 和 velocity 及 静态资源的热部署的
![image.png](http://upload-images.jianshu.io/upload_images/4832809-1e43964882d40101.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 结果现在 html 上修改不能热加载
* 感觉问题应该出在 html 修改后 重新velocity模板解析这
![image.png](http://upload-images.jianshu.io/upload_images/4832809-b8ea105e6fada580.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
<!----more--->
2. <servlet>
		<servlet-name>default</servlet-name>
		<init-param>
			<param-name>useFileMappedBuffer</param-name>
			<param-value>false</param-value>
		</init-param>
	</servlet>
没成功只是解决的文件锁定
### 继续尝试, 打算 用tomcat 作为外部容器, idea 管理, 看看能不能成功
* 下载tomcat
![image.png](http://upload-images.jianshu.io/upload_images/4832809-8df120fccc747204.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
很小啊![image.png](http://upload-images.jianshu.io/upload_images/4832809-1cae5b1b9612b5e7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-f2a0823e0dc30a71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
按照网上的设置了下
![image.png](http://upload-images.jianshu.io/upload_images/4832809-cc0c05e624c17b93.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
tomcat, 热部署成功
* 看看jetty runner 插件, 作为planB
![image.png](http://upload-images.jianshu.io/upload_images/4832809-30e76f1914434ea3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 查看 tnetstat -ano | grep 8080 接口使用情况
* ntskill [进程号]
* 想到能不能是jRebal 和Tomcat 有冲突 尝试一下
![image.png](http://upload-images.jianshu.io/upload_images/4832809-71dd605eaeb173ed.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 最好放弃热加载, 设置了下热部署
![image.png](http://upload-images.jianshu.io/upload_images/4832809-1bbe47d8a97127ae.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ctrl+F9 build 项目部署
![image.png](http://upload-images.jianshu.io/upload_images/4832809-910621c86b10714b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 静态资源不知道为什么必须重新部署后才会生效, 先打个标记
* 尝试解决 静态资源问题, 使其直接生效, 不需要重新部署
在你的 pom.xml 文件中添加如下配置，reload 的可选值 ：[automatic|manual]
<reload>automatic</reload>
<scanIntervalSeconds>1</scanIntervalSeconds>
http://blog.csdn.net/wangshuai6707/article/details/78466815
快捷键Ctrl + Alt + S打开设置面板，勾选Build project automatically选项：
![image.png](http://upload-images.jianshu.io/upload_images/4832809-83c0521875d0e38a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-a20ae9793523330f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
jetty 热加载 , 没成功, 但是, html好像终于纳入管理了, 我 启用下jRebal 试一下
* 不成功, 静态资源依然不成功,依旧不成功

### 新电脑 重新来
* 先配置下![image.png](http://upload-images.jianshu.io/upload_images/4832809-2a79764cb138cb56.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
http://www.mincoder.com/article/2365.shtml
自动编译?![image.png](http://upload-images.jianshu.io/upload_images/4832809-41001b959de5a3dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

ctrl , 作为临时快捷键
debug 找到了缓存代码, 也是醉了, 那就关闭它试一下
![](http://upload-images.jianshu.io/upload_images/4832809-5e58dd63fa13c0ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
package org.apache.velocity.runtime.resource;
velocity 默认 cache false