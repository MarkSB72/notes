ReoGrid3.0移植到WPF的过程和WinForm的过程一样，区别在于以下几个方面
# 区别
### 1. 创建WPF工程
### 2. 宏定义 为 WPF FORMULA LANG_JP
![](attachments/Pasted%20image%2020251115144915.png)
### 3. 需要额外添加一个引用
![](attachments/Pasted%20image%2020251115145008.png)
### 4. 额外安装一个库
![](attachments/Pasted%20image%2020251115145044.png)
注意这里的版本要和创建项目时使用的.Net Framework版本一致，不然会安装不了

然后在报错的地方添加相应的using就好了

### 5. 运行效果
![](attachments/Pasted%20image%2020251115145215.png)
最后就可以得到一个可以随窗口大小变化的表格控件了