# 说明

主要用于练习linux下C和C++

# Git相关操作

## 上传到分支

1. 增加远程地址

   ```
   git remote add origin https://github.com/9DemonFox/Linux-Advanced-Environment-System.git
   ```

2. 和远程分支关联, 如果远程有该分支，需要当前与其关联

```
git branch --set-upstream-to origin/google
```

3. 如果远程没有该分支，需要从本地推送

   ```bash
   $ git checkout -b name #(创建并且切换到分支)  
   $ git push origin GCC-practice:GCC-practice  
   Username for 'https://github.com': 9DemonFox  
   Password for 'https://9DemonFox@github.com':
   ```

# GCC 练习

## 1. dynamic_link

1. 使用 ldd ./test查看链接库链接情况
2. 
    ```
    all: libhello.so test
    
    libhello.so:hello.c 
        gcc -fPIC -shared -o libhello.so hello.c 
    # 生成动态链接库
    
    test:test.c
        gcc -o test test.c -L. libhello.so \ 
        -Wl,-rpath=./ # 设定链接库路径 优先搜索-rpath的命令
    ```
# UESTC 
# 互联网络程序设计

# 动态插桩的污点分析

## 项目说明 
参考docs 软件安全分析大作业.doc

## 启动方法
1. 下载tool工具
2. 将此文件夹放入/source/tools目录下
3. > sh runexample.sh 1

## 参考
1. [pin手册](https://software.intel.com/sites/landingpage/pintool/docs/98189/Pin/html/index.html)
2. [Taint analysis and pattern matching with Pin](http://shell-storm.org/blog/Taint-analysis-and-pattern-matching-with-Pin/)
3. 朱正欣. (2015). 二进制程序的动态符号化污点分析. (Doctoral dissertation).
4. https://github.com/mxmssh/tvc
