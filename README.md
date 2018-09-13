# BigData-Environment-Setup
配置Hadoop，Hive，Zookeeper，HBase方法总结
本机已经搭建Linux环境，安装secureCRT，Notepa++
## Hadoop搭建：

### 文件上传，解压：

* 打开虚拟机，打开终端。
* 在终端中输入命令 `rz` ，从本地上传配置文件（最好自己新建一个文件夹存放所有压缩包文件）。
![](ScreenShoot/rz.png)
* 选择 `hadoop-2.7.1.tar.gz`，`eclipse-jee-mars-2-linux-gtk-x86_64.tar.gz`，`apache-hive-2.1.1-bin.tar.gz` 上传（一般点击OK后会自动上传，如果没有则在输入一次命令 `rz` 就会启动上传）

![](ScreenShoot/sendFile.png)

* 等待上传完成，输入命令 `ll` 查看文件夹内所有文件：
![](ScreenShoot/allFile.png)
* 确认上传成功后， `cd ..` 退回根目录

* 新建一个hadoop的文件夹用来存放文件 `mkdir hadoop`
![](ScreenShoot/newDocument.png)
* `cd hadoop` 进入Hadoop文件夹，新建一个hHadoopTemFile文件夹用来存放之后需要处理的csv文件， `mkdir hadoopTemFile` 。
![](ScreenShoot/HadoopTmpFile.png)
* 返回存放压缩包的文件夹 `cd /software/` ,解压所有的压缩包文件,解压命令 `tar -zxf 文件名`。
![](ScreenShoot/tarFile.png)
* 将解压好的文件重命名 `mv hadoop-2.7.1 hadoop` ，并且移动到之前创建的hadoop文件夹中 `mv hadoop /hadoop/`。
* 在hadoop文件夹下查看所有文件，可以看到hadoop解压后的文件内容。
![](ScreenShoot/hadoopFile.png)

### 环境变量修改：

* 输入命令 `vim /etc/profile` 打开系统环境变量文件。
![](ScreenShoot/profile.png)
* 执行插入命令（键盘I键）。
* 在文件中添加hadoop的环境变量 `export HADOOP_HOME=/hadoop/hadoop ` （地址为你存放hadoop文件的地址）。
* 在 PATH 之后添加 `:$HADOOP_HOME/bin `。
![](ScreenShoot/path.png)
* 按下esc，输入命令 `:wq` 后回车，保存并退出profile文件。
* 输入命令 `source /etc/profile ` 读取并执行更新后的profile文件。
* 输入命令 `hadoop` ，如果成功配置环境变量，就会输出相关信息如下图。
![](ScreenShoot/hadoopInfo.png)

