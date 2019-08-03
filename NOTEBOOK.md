本文档是使用markdown记录的工作学习中的随笔,内容会比较杂乱.但是也有可能会出一些有深度的  
内容出来.
___
Linux
===

### tar 
```text
tar [选项...] [FILE]...
-c, --create               创建一个新归档
-x, --extract, --get       从归档中解出文件
-f, --file=ARCHIVE         使用归档文件或 ARCHIVE 设备
-t, --list                 列出归档内容
-C, --directory=DIR        改变至目录 DIR
    --add-file=FILE        添加指定的 FILE 至归档(如果名字以'.'开始会很有用的)
Examples:
  tar -cf archive.tar foo bar  # 创建包含foo,bar两个文件的archive.tar.
  tar -tvf archive.tar         # 详细展示archive.tar包中的所有文件.
  tar -xf archive.tar          # 提取所有的archive.tar包中的文件.
```

### ls
```text
ls [选项]... [文件]...
```


### find
```text
find [-H] [-L] [-P] [-O level] [-D debug_options] [路径...] [表达式]
默认路径为当前目录;默认表达式为 -print
表达式可能由下列成份组成：操作符、选项、测试表达式以及动作：
操作符(优先级递减；未做任何指定时默认使用 -and):
      ( EXPR )   ! EXPR   -not EXPR   EXPR1 -a EXPR2   EXPR1 -and EXPR2
      EXPR1 -o EXPR2   EXPR1 -or EXPR2   EXPR1 , EXPR2
位置选项(总是真): 
      -day_start   -follow   -regex_type
普通选项(总是真，在其它表达式前指定):
      -depth  --help  -maxdepth LEVELS  -mindepth LEVELS  -mount  
      -noleaf  --version  -xdev  -ignore_readdir_race  
      -noignore_readdir_race
测试表达式(N可以是 +N 或-N 或 N):
      -amin N  -anewer 文件  -atime N  -cmin  -cnewer 文件  -ctime N  
      -empty  -false  -fstype 类型  -gid N  -group 名称  -ilname 匹配模式
      -iname 匹配模式  -inum N  -ipath 匹配模式  -iregex 匹配模式  -links N
      -lname 匹配模式  -mmin N  -mtime N  -name 匹配模式  -newer 文件 
      -nouser -nogroup  -path 匹配模式  -perm [-/]MODE  -regex 匹配模式
      -readable -writable -executable -wholename 匹配模式 -size N[bcwkMG]
      -true -type [bcdpflsD]  -uid N  -used N -user NAME  
      -xtype [bcdpfls]  -context 文本
动作:
      -delete  -print0  -printf FORMAT  -fprintf FILE FORMAT  -print
      -fprint0 FILE  -fprint FILE  -ls  -fls FILE  -prune  -quit
      -exec COMMAND ;  -exec COMMAND {} + -ok COMMAND ;
      -execdir COMMAND ;  -execdir COMMAND {} + -okdir COMMAND ;

对-D选项提供的参数(debug_options):
exec, opt, rates, search, stat, time, tree, all, help
```

### tail
```text
tail [选项]... [文件]...
-f, --follow[={name|descriptor}]     追踪打开的文件
```
如果希望即时追查一个文件的有效名称而非描述内容(例如循环日志)，可以使用--follow=name选  
项，它会使tail定期追踪打开给定名称的文件，以确认它是否被删除或被其它某些程序重新创建.  
如果要打开的文件名并不存在,或之后才会创建可以使用--follow=descriptor选项, 它会不断尝  
试打开文件直到文件被创建,而不是报错.

### top
```text
top -hv | -bcEHiOSs1 -d secs -n max -u|U user -p pid(s) -o field -w [cols]
-n                  刷新次数
-d                  刷新间隔
-p                  指定pid
top内部指令
t CPU状态展示  m 内存状态展示 d,s 设定时间间隔(0.1分度)  k 杀死进程 r 设置优先级
C 移动显示的内容(使用上下左右home end键) 1 显示更多cpu
```
### kill
```text
kill [-s 信号声明 | -n 信号编号 | -信号声明] 进程号 | 任务声明 ... 或 kill -l [信号声明]
kill -9 9987 kill -KILL 9987
```

### ps
```text
ps [options]
ps aux 显示所有用户(u),的所有tty(a), 非tty(x) 
ps -A f 显示所有进程, 并显示依赖关系
ps -AF  显示所有进程, 以完整的格式
```
- 技巧  
有-的命令可以联写只要后面没有参数.有参数需要放在最后, 
没有-的命令放在一起.

### lsof
```text
lsof [-?abhKlnNoOPRtUvVX] [+|-c c] [+|-d s] [+D D] [+|-E] [+|-e s] [+|-f[gG]]
[-F [f]] [-g [s]] [-i [i]] [+|-L [l]] [+m [m]] [+|-M] [-o [o]] [-p s]
[+|-r [t]] [-s [p:s]] [-S [t]] [-T [t]] [-u s] [+|-w] [-x [fl]] [--] [names]
lsof -i :8080 查找端口号为8080的套接子文件. 在网络调试中十分又用
```

### crontab
```text
crontab [-u user] file
crontab [ -u user ] [ -i ] { -e | -l | -r }
crontab -e 编辑定时任务脚本
0 5 * * 1 tar -zcf /var/backups/home.tgz /home/ 每隔一周对home作一次备份
分 时 日 月 周  命令 的形式给出时间格式. 使用'*'表示每一个, 使用'*/n'表示每隔n个
```

Python
===
### SQLAlachemy

### Flask

### Django

### Celery

Docker
===

MySQL
===

MongoDB
===

Redis
===

Nginx
===

Pipelines
===

