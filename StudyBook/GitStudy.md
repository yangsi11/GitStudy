

GitStudy

### 一、先学会安装

网站地址:https://blog.csdn.net/mukes/article/details/115693833





### 二、注册Github,并且创建Repository



​	![image-20240404215058187](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404215058187.png)

![image-20240404215148312](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404215148312.png)

点击创建项目即可

### 三、Git绑定你的Github的项目邮箱,账户(用于识别)



**绑定邮箱和名字**

```bash
git config --global user.name "yangtianfei"
git config --global user.emil "2918514049@qq.com"
```



### 四、为Github账户设置SSH key

```bash
ssh-keygen -t rsa -C "2918514049@qq.com"
//执行后一直回车即可
```

第三步：获取ssh key公钥内容（id_rsa.pub）

```
cd ~/.ssh
cat id_rsa.pub
```





**全部用默认三次回车就可以了**



### 五、Github账号上添加公钥

![image-20240404220723652](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404220723652.png)

![image-20240404220734999](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404220734999.png)

![image-20240404220749460](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404220749460.png)

**复制进去添加就行**





最后验证是否添加成功

```bash
ssh -T git@github.com
```

验证登入成功

![image-20240404220953513](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404220953513.png)



克隆github上的代码

```bash
git clone "地址"
```



### 六、初始化Git,创建文件,并且上传

#### 1.初始化 git init

```bash
git init	
```

![image-20240404221437375](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404221437375.png)

#### 2. 输入 `git add .` 将项目添加到暂存区

- 注意： **.** 前面有空格，代表添加所有文件。

- 若添加单个文件输入：`git add xxxx.xx`（xxxx.xx为文件名）

	```bash
	git add .
	```

	

![image-20240404221735611](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404221735611.png)

#### 3.输入 `git commit -m "注释内容"` 将项目提交到Git仓库

```bash
git commit -m "注释内容"	
```

![image-20240404221823994](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404221823994.png)

#### 4.创建分支`git branch -M main`

```bash
git branch -M main
```

![image-20240404222001358](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404222001358.png)

#### 5.输入：`git remote add origin https://github.com/xxxxx/test.git`，和远程仓库连接

```bash
git remote add origin git@github.com:yangsi11/GitStudy.git
```

#### 6.将本地项目推送到远程仓库

![image-20240404225201349](C:\Users\梅玉飞\AppData\Roaming\Typora\typora-user-images\image-20240404225201349.png)

```bash
git push -u origin main
```









# 总结报错

报错一定是要在创建的.git下面的文件进行操作

