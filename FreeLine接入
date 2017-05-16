FreeLine实现Android的秒级编译

一、使用步骤

1.安装plugin:
![plugIN](http://upload-images.jianshu.io/upload_images/1458573-e17e241b295dfe61.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
安装完后AS上就有一个freeline的编译按钮了。
![](http://upload-images.jianshu.io/upload_images/1458573-428f0b9a7af5b20b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2.配置Project以及Module的gradle
````
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.antfortune.freeline:gradle:0.8.3'
    }
}
````
````
 apply plugin: 'com.antfortune.freeline'

 android {
     ...
 }
freeline {
    hack true
    productFlavor 'zroTest'
}

````


4.使用gradle初始化一下freeLine

最后，在命令行执行以下命令来下载 freeline 的 python 和二进制依赖。
*Windows[CMD]: gradlew initFreeline
*Linux/Mac: ./gradlew initFreeline
> 对于国内的用户来说，如果你的下载的时候速度很慢，你也可以加上参数，执行gradlew initFreeline -Pmirror，这样就会从国内镜像地址来下载。

然后就可以愉快的玩耍了！例如，我这次修改了Java代码之后，重新编译下，耗时如下：
![](http://upload-images.jianshu.io/upload_images/1458573-011e5793f951305a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3秒即可重新编译安装新的app到手机上！！！
比Instant Run稳定且更快！！！

温馨提示：

1.初次安装可能耗时比较久，因为其实FreeLine也是基于增量更新的机制。

2.adb断开连接后，重连之后的再次编译，等价于初次安装

二、常见问题

1.编译时找不到文件：freeline_project_description.json

按照提示：执行./gradlew checkBeforeCleanBuild，然后它就自动帮你生成了一个project_description.json文件


### 参考目录
http://www.jianshu.com/p/46418dd38218

https://github.com/alibaba/freeline/blob/master/README-zh.md

### 额外
 如果要只在Debug编译引入库，两种方式：
1. 使用放射调用类；和   zroTestCompile 'com.facebook.stetho:stetho:1.5.0'
2. 使用  空包方式:    releaseCompile 'com.antfortune.freeline:runtime-no-op:0.8.3'




