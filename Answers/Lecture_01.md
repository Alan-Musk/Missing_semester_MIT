Q1 本课程需要使用类Unix shell，例如 Bash 或 ZSH。如果您在 Linux 或者 MacOS 上面完成本课程的练习，则不需要做任何特殊的操作。如果您使用的是 Windows，则您不应该使用 cmd 或是 Powershell；您可以使用[Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/)或者是 Linux 虚拟机。使用echo $SHELL命令可以查看您的 shell 是否满足要求。如果打印结果为/bin/bash或/usr/bin/zsh则是可以的。

Q2 在 /tmp 下新建一个名为 missing 的文件夹。
A2 :
```shell
mkdir missing
```

Q3 用 man 查看程序 touch 的使用手册
A3 :
```shell
man touch
```

Q4 用 touch 在 missing 文件夹中新建一个叫 semester 的文件
A4 :
```shell
touch semester
```

Q5 将以下内容一行一行地写入 semester 文件：
```shell
#!/bin/sh
curl --head --silent https://missing.csail.mit.edu
```

Q6 尝试执行这个文件。例如，将该脚本的路径（./semester）输入到您的shell中并回车。如果程序无法执行，请使用 ls 命令来获取信息并理解其不能执行的原因。
A6 :
```shell
sh ./semester
```

Q7 查看 chmod 的手册(例如，使用 man chmod 命令)
A7 :
```
man chmod
```

Q8 使用 chmod 命令改变权限，使 ./semester 能够成功执行，不要使用 sh semester 来执行该程序。您的 shell 是如何知晓这个文件需要使用 sh 来解析呢？更多信息请参考：shebang
A8 :
```shell
chmod ugo+x semester
./semester
```

Q9 使用 | 和 > ，将 semester 文件输出的最后更改日期信息，写入主目录下的 last-modified.txt 的文件中
A9 :
```shell
./semester | grep -i 'last-modified' > last-modified.txt
```

Q10 写一段命令来从 /sys 中获取笔记本的电量信息，或者台式机 CPU 的温度。注意：macOS 并没有 sysfs，所以 Mac 用户可以跳过这一题。