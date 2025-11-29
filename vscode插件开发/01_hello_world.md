vscode的插件工程要用命令行来创建，并且是使用的Node.js
在目录下使用命令行来创建vscode插件工程
```shell
npx --package yo --package generator-code -- yo code
```

![](attachments/Pasted%20image%2020251129183817.png)
使用TypeScript来编写插件
![](attachments/Pasted%20image%2020251129183933.png)
编写项目描述信息
![](attachments/Pasted%20image%2020251129184007.png)
并用npm来管理包
![](attachments/Pasted%20image%2020251129184027.png)
然后进入到工程目录，用VSCode来打开
![](attachments/Pasted%20image%2020251129184116.png)
打开之后如下图所示
![](attachments/Pasted%20image%2020251129184132.png)
左边就是我们的插件工程目录了，按F5来进行运行，会打开一个新的VSCode窗口
![](attachments/Pasted%20image%2020251129184215.png)
我们使用Ctrl + Shift + P 来打开命令板，然后输入Hello 可以看到有一个Hello World的命令
![](attachments/Pasted%20image%2020251129184306.png)
运行它，会在右下角提示一个Hello World的信息
![](attachments/Pasted%20image%2020251129184343.png)






