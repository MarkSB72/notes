## 一、 创建新的WinForm项目
![[Pasted image 20251113222351.png]]

## 二、下载ReoGrid源码
这里我们使用3.3版本的源码来进行移植
![[Pasted image 20251113222451.png]]

链接在这：[[[GitHub - unvell/ReoGrid at v3.3.0](https://github.com/unvell/ReoGrid/tree/v3.3.0)]]

## 三、拷贝需要的代码
下载3.3版本的代码，并解压之后，目录结构是下面这个样子的
![[Pasted image 20251113222813.png]]
我们需要拷贝ReoGrid目录里面的代码到我们刚刚创建的WinForm工程里面
除了Android iOS Test WPF这几个目录不用拷贝之外，其他的全拷贝
拷贝完之后我们的项目，目录结构如下图所示
![[Pasted image 20251113223114.png]]
然后是ReoGrid的CSharp文件，和我们刚刚拷贝的目录在同一层
![[Pasted image 20251113223213.png]]

## 四、修改WinForm工程的命名空间
为了简化移植流程，我们修改工程的命名空间和ReoGrid官方的一样
右键项目，然后点击Properties，打开我们的工程属性
![[Pasted image 20251113223559.png]]

然后在Application中修改我们的命名空间为**unvell.ReoGrid**，然后Ctrl + S保存设置
![[Pasted image 20251113223735.png]]

## 五、将ReoGrid包含进项目
在Solution Explorer中，将我们刚刚复制过来的文件包含进我们的项目
![[Pasted image 20251113223950.png]]
CSharp文件也要包含进来
![[Pasted image 20251113224027.png]]

如果在Solution Explorer中没有看见我们新增的文件，可以点这两个按钮
![[Pasted image 20251113224120.png]]

## 六、添加宏定义
ReoGrid使用了条件编译，不仅可以编译成WinForm控件，还可以编译成其他平台如WPF的空间，不过这里仅演示WinForm的编译。
要为工程添加宏定义，需要在项目属性的Build界面里面进行添加
![[Pasted image 20251113224408.png]]

然后Ctrl + S保存

## 七、开始编译
在做好上述准备之后，我们可以开始我们第一步的编译
![[Pasted image 20251113224549.png]]
如果遇到due to its being in the Internet or Restricted zone or having the mark of the web on the file. Remove the mark of the web if you want to process these files.
之类的问题，说明该文件被Windows系统给锁定了，需要右键该文件，选择属性，之后手动解除锁定
![[Pasted image 20251113224747.png]]

## 八、解决报错
### 1. ZipArchive找不到
![[Pasted image 20251113224828.png]]
这个需要我们手动添加系统的引用，在Solution Explorer里右键我们项目下面的Reference
![[Pasted image 20251113224937.png]]
选择Add Reference
在Reference Manager界面找到我们所需要的这两个选项，勾选之后，点击OK
![[Pasted image 20251113225218.png]]
然后工程里面关于ZipArchive的错误就不见了
![[Pasted image 20251113225254.png]]

### 2. Formula 命名空间找不到
![[Pasted image 20251113225337.png]]
这个错误，需要我们添加一个宏定义**FORMULA**
![[Pasted image 20251113225433.png]]
Ctrl + S保存
这个报错也不见了
### 3. Resource  does not contain ...
![[Pasted image 20251113225601.png]]
这个问题需要把ReoGrid3.3目录里的Properties文件夹，复制，覆盖我们工程的Properties文件夹

### 4. NumberDataFormatter ... does not contain ...
![[Pasted image 20251113225832.png]]
这个问题需要我们添加一个宏定义 **LANG_JP**
我猜应该是添加小日本鬼子的支持，估计是英语学的不好吧
![[Pasted image 20251113230024.png]]


### 5. DateTimeFormat ... does not exist
![[Pasted image 20251113230124.png]]
刚刚复制过来的Properties里面有一些文件还没有被包含进项目，这里我们把相应缺失的文件包含进来即可
![[Pasted image 20251113230343.png]]

## 九、编译运行
至此，编译成功
![[Pasted image 20251113230424.png]]
然后在我们的Form1里面添加ReoGrid控件
![[Pasted image 20251113230537.png]]

点击运行
![[Pasted image 20251113230602.png]]

大功告成！

## 十、编译成动态库供其他项目使用
我们也可以把刚刚移植成功的ReoGrid编译成一个动态库，供其他项目使用，这样就不需要拷贝我们创建的这个项目，在这个项目基础上去进行其他项目的开发
在项目属性的Application选项里，把Output type从**Windows Application**修改成**Class Library**
![[Pasted image 20251113230900.png]]
保存之后，点击编译即可生成动态库
![[Pasted image 20251113231003.png]]
这样只需拷贝这个动态库，就可以让其他项目也使用ReoGrid这个表格控件啦！