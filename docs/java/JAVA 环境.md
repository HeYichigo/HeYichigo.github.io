# ***JAVA 环境***    

本次项目开发需要两个JAVA环境，原因会在后文解释。  

JDK下载过慢的话可以采用国内镜像：
> https://mirrors.tuna.tsinghua.edu.cn/AdoptOpenJDK/  

使用方法可以参考 > [这里](https://zhuanlan.zhihu.com/p/111022749)  

    请安装hotspot版本的JDK

**MAC** 的JAVA配置可以参考 > [这里](https://blog.csdn.net/vvv_110/article/details/72897142)  

## ***JAVA 11***  

需要下载 ***Java11*** 的JDK并配置在环境中。  

需要配置的环境变量为 

     JAVA_HOME / CLASSPATH / PATH 

## ***JAVA 8***  

仅需要下载 ***Java8*** 的JDK并解压，不需要配置环境变量。  

---
# ***MAVEN 环境***  

**MAC** 的Maven配置可以参考 > [这里](https://wangxin1248.github.io/life/2020/02/mac-install-maven.html)  

***MAVEN*** 选择 3.6.3 版本，配置阿里镜像提高下载速度。  

MAVEN的repo可以不做配置。   

``` xml
<!-- 在mirrors节点下添加如下代码 -->
<mirror>
    <id>nexus-aliyun</id>
    <mirrorOf>central</mirrorOf>
    <name>Nexus aliyun</name>
    <url>http://maven.aliyun.com/nexus/content/groups/public</url>
</mirror>
```

需要配置的环境变量为 

     MAVEN_HOME / PATH 

---
#  ***IDE选择***    

使用 ***VScode*** 进行开发  

1.在 ***VScode*** 中安装如下插件：  

 > + Java Extension Pack  
 > + Lombok Annotations Support for VS Code
 > + Spring Boot Tools


    Java Extension Pack 会安装多个插件，其中 Language Support for Java(TM) by Red Hat 需要Java_11作为运行环境，项目运行需要Java_8作为运行环境，所以需要在PC中拥有两个环境。  

2.在 ***VScode*** 中选择 File -> Preferences -> Settings .  

3.在 **Settings** 页面右上角点击 **打开Json**，并在打开的 ***Settings.json*** 文件中加入如下内容，注意替换path路径。    

```json
    "java.configuration.runtimes": [
    {
        "name": "JavaSE-1.8",
        "path": "/JAVA_ENV/jdk8u272-b10",
        "default": true
    },
    {
        "name": "JavaSE-11",
        "path": "/JAVA_ENV/jdk-11.0.9+11",
    },
    ],
    "java.home": "/JAVA_ENV/jdk-11.0.9+11",
    "java.configuration.maven.userSettings": "/JAVA_ENV/apache-maven-3.6.3/conf/settings.xml"
```
---
# 载入项目

最好为github/git配置ssh密钥，以提高clone速度。  

配置方法[在这里](https://docs.github.com/cn/free-pro-team@latest/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)，文档中包含win和mac的配置方式。    

之后可以clone项目  

```bash
git clone git@github.ibm.com:QA-Team/QA-Server.git
```
vscode打开项目文件夹，右下角弹出的窗口都点确认或者允许（这一步的选择没太大关系）。  

在vscode的terminal中运行mvn命令  

```bash
mvn package
```

运行mvn命令时一定要注意当前运行时所在的路径，路径一定是在QA-Server之下。  

之后可以按**F5**运行一下，如果package时没出现问题，基本就可以运行成功。  

**至此项目配置结束。**