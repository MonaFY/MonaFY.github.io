@[TOC](linux下shell脚本实现文件的批量处理)
## 说明：
在使用linux虚拟机处理数据的过程中，由于需要处理的文件量较大，并且有大量重复的操作，为了省时省力，发现可以使用shell脚本一次处理大量的文件。
# 1、shell文件创建
命令行输入`touch XXX.sh`
# 2、文件编辑

命令行输入`vi XXX.sh`
点击 <kbd>i</kbd> 进入编辑模式
输入shell脚本，以下代码以文件复制为例
```
#!/bin/bash

echo "copy file"
for ((i=226; i<228; i++))
do
cp /home//Documents/$i.nii /home/fsluser/Documents/R/$i
done

```
### 注意：
 1. `#!/bin/bash`是必要的，告诉系统这个脚本使用哪一种 Shell脚本
 2. 使用了C语言类型的for语句依次对文件进行处理
 3. `cp /home//Documents/$i.nii /home/fsluser/Documents/R/$i`是文件复制的命令行代码,同理可替换成其他命令
 
 点击<kbd>esc</kbd>退出编辑，输入`：wq`回到终端。
# 3、执行shell文件

命令行输入`sh XXX.sh`
# 4、停止正在执行shell文件
当shell脚本正在执行时，若想强行终止，可按如下操作：

命令行输入：`ps -ef | grep XXX文件名`
找到进程对应的进程代码(如下图中进程代码为8630)
![](https://img-blog.csdnimg.cn/2019042514310971.png)
命令行输入：`kill -9 XXX进程代码`
强制终止进程

**更多shell教程，请参考: [shell教程|菜鸟教程](http://www.runoob.com/linux/linux-shell.html).**
