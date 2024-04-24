### 同时安装多个node版本

https://blog.csdn.net/l_ymttt/article/details/119598032

同一电脑上安装不同版本的nodejs，需要借助nvm工具。使用的时候，nvm use切换不同版本的nodejs。

nvm官方文档：https://github.com/nvm-sh/nvm
nvm工具下载：https://github.com/coreybutler/nvm-windows/releases/tag/1.1.9

步骤：

### 1.卸载已安装的node

### 2.双击nvm-setup.exe，下一步下一步即可。（包含nvm的安装地址和nodejs的安装地址，最好是默认到c盘，自定义需要配置系统和环境变量）

### 3.检查安装版本即可。nvm已经自动设置了环境变量。

查看nvm语法：nvm -v

### 4.安装nodejs

安装语法：

```bash
nvm install 16.17.0
```

查看当前node版本：node-v

### 5.nvm常用命令

nvm on ： 打开node.js版本控制
nvm off ： 关闭node.js版本控制
nvm list ： 查看已经安装的版本
nvm list available ： 查看网络可以安装的版本
nvm install ‘版本号’ ：安装指定版本node.js
nvm uninstall ’ ’ ： 卸载指定版本号
nvm use ’ ’ ： 切换指定的node版本
nvm version ： 查看当前的版本

### 6.使用nvm

```bash
javanvm use 14.19.1
Now using node v14.19.1 (64-bit)
node -v
v14.19.1
```

```bash
nvm use 16.14.2
Now using node v16.14.2 (64-bit)
node -v
v16.14.2
```



### 7.卸载nvm

1.先删除你当初所安装的nvm的文件夹即可。
2.文件夹内右键 此电脑 – 点击属性 – 找到高级系统设置 – 环境变量。
3.删除用户变量 和 系统变量中名为 NVM_HOME 和 NVM_SYMLINK 两个变量。其他的不要改。
4.用户变量和系统变量中path中的 %NVM_HOME%;%NVM_SYMLINK% 两个属性，其他的不要改。