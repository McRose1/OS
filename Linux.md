# Linux 相关
## uname 
- -a 或 --all：显示全部的信息
- -m 或 --machine：显示电脑类型
- -n 或 -nodename：显示在网络上的主机名称
- -r 或 -release：显示操作系统的发行编号
- -s 或 --sysname：显示操作系统名称
- -v：显示操作系统的版本
- --help：显示帮助
- --version：显示版本信息
- who：可以查询当前登录在系统上的登录用户的信息
- who am i：等同于 who -m，只打印执行该命令的登录用户的信息
- whoami：可以查询当前有效用户的名字

## >
重定向符号，通常用于输入输出到文件

用法：./a.out > a.txt

将程序的输出结果存到 txt 文件中

## |
管道符号，用于两个程序之前输入输出的连接

用法：command1|command2

把第一个命令 command1 的执行结果作为 command2 的输入传给 command2

## grep
命令格式：grep [option] pattern file

1. 查找指定进程
ps -ef | grep bash 

2. 查找指定进程个数
ps -ef | grep bash -c

3. 从文件中读取关键字进行搜索
cat test.txt | grep -f test2.txt

从 test.txt 文件中含有从 test2.txt 文件中读取出的关键字的内容行

4. 从文件中读取关键字进行搜索且显示行号
cat test.txt | grep -nf test2.txt

5. 从文件中查找关键字
grep 'linux' test.txt

6. 从多个文件中查找关键字
grep 'linux' test.txt test2.txt

7. 找出以 u 开头的行内容
cat test.txt | grep ^u

8. 找出非 u 开头的行内容
cat test.txt | grep ^[^u]

9. 找出以 hat 结尾的行内容
cat test.txt | grep hat$

10. 显示包含 ed 或者 at 字符的内容行
cat test.txt | grep -E "ed|at"

## chmod
用来修改文件权限

1. 用数字来设定权限：r(读):4(100), w(写):2(010), x(执行):1(001)
实际上是按二进制取 1 的位来设置权限

chmod 777 test.txt：7=111，给 test 拥有者、所属群组、其他人所有权限

2. 用符号设定权限：chmod [ugoa] [+-=] [rwx] dirname/filename
- u：拥有者
- g：所属群组
- o：其他人
- a：所有人
- +：添加权限
- -：移除权限
- =：设定权限

为 test.txt 文件的所有用户添加读权限：chmod a+r test.txt

## inode
一般情况下，文件名和 inode 号码是“一一对应”关系，每个 inode 号码对应一个文件名。但是，Unix/Linux 系统允许多个文件名指向同一个 inode 号码。这意味着，可以用不同的文件名访问同样的内容；对文件内容进行修改，会影响到所有文件名；但是，删除一个文件名，不影响另一个文件名的访问，这种情况被称为“硬链接”（hard link）。

除了硬链接以外，还有一种特殊情况：文件 A 和文件 B 的 inode 号码虽然不一样，但是文件 A 的内容是文件 B 的路径。读取文件 A 时，系统会自动将访问者导向文件 B。因此，无论打开哪一个文件，最终读取的都是文件 B。这时，文件 A 就称为文件 B 的“软链接”（soft link）或者“符号链接”（symbolic link）。这意味着，文件 A 依赖于文件 B 而存在，如果删除了文件 B,打开文件 A 就会报错：“No such file or directory”。

这是软链接和硬链接最大的不同：文件 A 指向文件 B 的文件名，而不是文件 B 的 inode 号码，文件 B 的 inode “链接数” 不会因此发生变化。


































