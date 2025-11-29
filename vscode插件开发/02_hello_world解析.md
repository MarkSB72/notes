上一节我们在命令行创建了一个hello world工程，并且在VSCode中成功运行了起来，提示输出了Hello World
这个Hello World来源于我们的工程目录下的这个文件
![](attachments/Pasted%20image%2020251129184733.png)
在这里，这个文件描述了当插件激活时，向VSCode注册一个命令，这个命令的功能就是显示一个提示信息，Hello World from hello_world
我们修改这里框起来的字符串，为Hello VSCode
![](attachments/Pasted%20image%2020251129184856.png)

然后重新按F5运行，并调用Hello World命令
![](attachments/Pasted%20image%2020251129184940.png)
可以看到这里真的修改成为我们自定义的字符串了

但是注意到我们命令的别名是Hello World，这个字符串在哪里呢
![](attachments/Pasted%20image%2020251129185307.png)
在工程目录下的package.json文件里面，描述了我们的插件提供的命令
![](attachments/Pasted%20image%2020251129185346.png)
这个contributes是一个很重要的一个东西
这里就描述了我们的hello world程序

注意到这里有一个main的属性，描述了插件的主程序
![](attachments/Pasted%20image%2020251129185527.png)
但是我们好像写的ts文件，怎么这会编程extension.js，JavaScript了。可能是由于转换了，目前学的还是很浅，只能猜测

依葫芦画瓢，在这个contributes里面添加一个新的命令
![](attachments/Pasted%20image%2020251129185722.png)

但是先不给它注册对应的命令看看是什么效果
![](attachments/Pasted%20image%2020251129185804.png)
提示找不到命令了

同样依葫芦画瓢，在extension.ts里面添加say hello 命令
![](attachments/Pasted%20image%2020251129185911.png)
复制粘贴，大功告成。再次运行
![](attachments/Pasted%20image%2020251129185933.png)
这次没有报错，并且成功提示了Say Hello了



