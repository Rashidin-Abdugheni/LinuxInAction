 

* 所用的是ubuntu16系统的服务器。
###1. 先查看某个软件有没有安装：
###### 参考：
```
https://www.unixmen.com/linux-basics-check-package-installed-not-ubuntu/
```
1）先查看已经安装的所有软件列表
```
dpkg --get-selections
```
![image.png](https://upload-images.jianshu.io/upload_images/23394760-5a07b3529d142990.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2）也可以查某个指定软件有没有安装过：
比如查询Firefox有没有安装过：
```
dpkg -s firefox
```
会看到：installed，即安装过！
![image.png](https://upload-images.jianshu.io/upload_images/23394760-c03010eb0b9fca35.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3）同样查看一下prokka有没有安装过：直接输入prokka就可以看到
```
prokka
```
![image.png](https://upload-images.jianshu.io/upload_images/23394760-4278999c625278cf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
即：此前安装过!
---
### 2. 进行单菌基因组的注释：
1)首先在wincp下在自建的一个文件夹下放入单菌拼接基因组：
![image.png](https://upload-images.jianshu.io/upload_images/23394760-27e39f7fa651a1f3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2）复制路径：
![image.png](https://upload-images.jianshu.io/upload_images/23394760-47b72600a589523b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

所以读取路径可以指定了！输出路径指定，但是"不用创建"具体输出文件!
#### 注意 ：其中，40这个文件不要创建！不然会报错！
* #### 报错代码为：
```
prokka /media/dell/data3/RXD/Prokka/B1669N-40.genome.fasta --outdir /media/dell/data3/RXD/Annotation/ --prefix goldbacteria --kingdom Bacteria
```
* ##### 输出报错信息为：
![image.png](https://upload-images.jianshu.io/upload_images/23394760-318b3e272f060ed1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

---
* ##### 正确代码为：
```
/media/dell/data3/RXD/Prokka/B1669N-40.genome.fasta --outdir /media/dell/data3/RXD/Annotation/40 --prefix goldbacteria --kingdom Bacteria 
```
 * #####注意：运行结束后，到40这个文件的上级目录进行refresh，才会看到注释结果！
![image.png](https://upload-images.jianshu.io/upload_images/23394760-dc9596f58765b0ca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后具体文件内容如下：
![image.png](https://upload-images.jianshu.io/upload_images/23394760-07e2242143eaf91c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* ##### 如果想看prokka帮助文件，则只需要输入：
```
prokka -h
```
即可看到：

![image.png](https://upload-images.jianshu.io/upload_images/23394760-05f8632b805aa966.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)