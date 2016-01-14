# day01 NSRegularExpression & UIKit Framework & TableviewCell 高度 自适应

今天想记录这三点。

###一：

The NSRegularExpression class is used to represent and apply regular expressions to Unicode strings. An instance of this class is an immutable representation of a compiled regular expression pattern and various option flags. The pattern syntax currently supported is that specified by ICU. The ICU regular expressions are described at 
<http://userguide.icu-project.org/strings/regexp.>

在stackoverflow上介绍了个网站，可以解析自己写的表达式有没有问题[regex101](https://regex101.com/r/rQ5fX9/1)。

用到正则表达式是需要解析出网页源代码上的标题。

###二：

[UIKit Framework](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIKit_Framework/index.html#//apple_ref/doc/uid/TP40006955) apple UIKit Framework Reference

[UIApplicationDelegate Protocol Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplicationDelegate_Protocol/index.html) 

简介：The UIApplicationDelegate protocol defines methods that are called by the singleton UIApplication object in response to important events in the lifetime of your app.

也就是AppDelegate内的内容，Appdelegate里面的方法都是关于app的生命周期的，网页中的这张图能很好的展示

![icon](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplicationDelegate_Protocol/Art/high_level_flow_2x.png)

重要的方法是这几个：

####Launch time:

	application:willFinishLaunchingWithOptions:

	application:didFinishLaunchingWithOptions:

###Transitioning to the foreground—

	applicationDidBecomeActive:

###Transitioning to the background:

	applicationDidEnterBackground:

###Transitioning to the inactive state

	applicationWillResignActive: (Called when leaving the foreground state.)

	applicationWillEnterForeground: (Called when transitioning out of the background state.)

###Termination:

	applicationWillTerminate: (Called only when the app is running. This method is not called if the app is suspended.)

更详细的信息要戳这里：[app programming Guide for iOS](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40007072)
	有关lifeCycle，background等处理的相关策略都有介绍。
###三：

上周正好有人问到每个tableviewCell的高度都不一样的话怎么处理，这么简单的问题当然根本没想明白，这两天看到pocket更新了才想起来，简直不能更蠢，这个博客有对这个方法详细的介绍 [link](http://blog.sunnyxx.com/2015/05/17/cell-height-calculation/)，此篇文章还赠送了一个自动计算cell高度的库，很不错，[FDTemplateLayoutCell](https://github.com/forkingdog/UITableView-FDTemplateLayoutCell)。写完文章后看着敲一遍，就当学习了。

