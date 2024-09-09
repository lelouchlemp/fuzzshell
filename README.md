# fuzzshell 

![image-20240726143653735](https://s2.loli.net/2024/07/26/IWk2m1xzDrMptYg.png)

## 视频教程
视频教程: https://youtu.be/LAFNWY7c_9E 



## 使用步骤
1.第一行为输入命令，文件地址，或者其他数据

2.第二行为黑名单，用 "," 隔开如： flag,eval,cat,system ，然后点击黑名单，会清除输出中存在黑名单的数据

3.然后点击去重。

4.点击复制后导入到burpsuite进行fuzz



## 功能说明

- 命令混淆： 对linux命令进行简单的混淆
- 读文件+混淆： 不需要输入命令，输入文件的地址即可如/flag (或者/f* /f???)
- 读文件：只输出一些能查看文件的命令不进行混淆
- php读文件：题目环境存在include()文件包含的情况下使用
- php代码执行：题目环境中存在eval()等情况下使用
- 八进制编码：
- 十六进制编码：
- IP编码：ipv4地址编码，SSRF使用
- 沙箱逃逸：参考https://github.com/Macr0phag3/parselmouth，在第一栏输入`__import__('os').popen('cat /flag').read()` 第二栏输入黑名单  `__,os,pop,system` 点击输出自动绕WAF
- SSTI：参考https://github.com/Marven11/Fenjing ，在第一栏输入 `cat /flag` 第二栏输入  `_,os,{{,}},eavl,subprocess` 点击输出自动绕WAF
