# react-native
一个为了练手的react-native项目
#window下项目环境配置
一、安装 Java sdk 配置好环境变量  （版本为1.8，太高的版本Android tools不支持）

    （必须注意：安装的时候文件目录不能有空格或其他特殊字符）

    变量名：JAVA_HOME

    变量值：C:\Java\jdk-10

二、安装 Android sdk  tools （android-sdk_r24.4.1-windows.zip）

    （下载地址：http://www.androiddevtools.cn/）

    问题：如果双击SDK Manager 启动不了，需要一些配置

    右键编辑tools目录下的android.bat

    修改：rem Check we have a valid Java.exe in the path.

        set java_exe=
        call lib\find_java.bat
        if not defined java_exe goto :EOF

    改为：rem Check we have a valid Java.exe in the path.
        set java_exe="C:\Java\jdk-10\bin\java.exe"
            set jar_path=lib\sdkmanager.jar;lib\swtmenubar.jar

    启动SDK Manager，选择安装

    1、Tools 选择三项  Android SDK Tools ，Android SDK Platform-tools，Android SDK Build-tools

    2、API  任意选择一个，一般选择最新的

    3、Extras 全选

    4、Android SDK在线更新镜像服务器来下载安装，启动 Android SDK Manager ，打开主界面，依次选择『Tools』、『Options...』，弹出『Android SDK Manager - Settings』窗口

        大连东软信息学院镜像服务器地址:mirrors.neusoft.edu.cn 端口：80

    5、检测是否配置成功。打开命令行窗口，输入adb

    问题：安装好依赖包后，打开SDK manager 失败，显示错误：Failed to execute tools\android.bat:, error 2

    解决方法：

    1.找到sdk目录下的temp文件夹，它是用来暂存数据的。

    2.temp文件夹里找到tools_r24.1.2-windows.zip，或者其他的tools_r***-windows.zip（建议选最新的），解压它得到一个tools文件夹。

    3.将刚解压的tools文件夹内容（里面有android.bat）全部复制到本身的tools文件夹，即sdk/tools，可以了。

    问题：'adb' 不是内部或外部命令，也不是可运行的程序 或批处理文件。 这个命令是测试Android SDK是否安装成功的。

    解决方法：

    1、找到SDK目录，在其子目录platform-tools中找到adb.exe这个程序，将其复制到tools目录下。

    2、配置系统环境变量

    （1）ANDROID_HOME：Android SDK Manager的位置

    变量名：ANDROID_HOME
    变量值：E:\android-sdk_r24.4.1-windows\android-sdk-windows

    （2）PATH： %ANDROID_HOME%\tools;%ANDROID_HOME%\platform-tools

    path路径添加上：%ANDROID_HOME%\tools;%ANDROID_HOME%\platform-tools

三、react-native 安装

    npm install -g react-native-cli
    初始化项目：react-native init  项目名称

四、Android 模拟器  夜神模拟器  Genymotion（建议选择个人免费版，强烈推荐使用！）

    1.连接：命令行cmd运行 adb connect 127.0.0.1:62001 

五、整个项目的运行方法

   （1）、android
        1、运行包管理器，项目根目录下运行命令：react-native start
        2、连接到夜神模拟器，a：打开夜神，b：cmd 连接：react-native start
        3、运行android项目，项目根目录下运行打包命令：react-native run-android debug
        4、修改修改调试服务器地址，开启远程服务。点击模拟器的摇动按钮，在对话框的DevSettings选项中，填入本机的IP地址和ReactNative默认的8081端口号  
        5、点击模拟器摇动按钮，选择reload


    运行ios：   react-native run-ios
    运行Android：  react-native run-android

    





