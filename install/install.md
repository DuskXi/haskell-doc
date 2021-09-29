
## 安装Haskell环境:

#### 第一步: 提升操作权限到root权限

1. 执行`sudo su root`
2. 输入密码回车

---
#### 第二步: 安装Haskell

1. 更新apt镜像: 执行`apt update`
2. 安装haskell环境: 执行`apt install -y ghc haskell-stack`

#### 第三步: 测试

执行: `echo "main = do {putStrLn \"helloworld\"}" >> test.hs && ghc -o test test.hs && echo -e "\033[31m 执行
结果: \033[0m"  && ./test && rm test test.hs test.hi test.o`

看到helloworld输出就代表haskell环境可以使用

## VSCode调试配置

#### 第一步: 安装VSCode 

#### 第二步: 设置语言(有需要的话)

1. 打开VSCode
2. ctrl+shift+p
3. 输入lanuage
4. 点击Configure Display Language
5. 点击zh-cn，如果没有则点击最后一个选项进行安装

#### 第三步: 在VSCode中打开wsl

在软件的左边栏中找到"远程资源管理器"，其中找到WSL并且连接

#### 第四步: 安装插件

1. 按下快捷键: `ctrl+shift+x`
2. 输入*haskell*
3. 安装以下插件:

![image](https://user-images.githubusercontent.com/84715902/135286983-c11374ff-6305-419e-a295-d93743b8a6e8.png)

![image](https://user-images.githubusercontent.com/84715902/135287031-adf7efa0-321b-486f-be48-d46cc6c18298.png)

![image](https://user-images.githubusercontent.com/84715902/135287062-989a41f6-6856-4c18-a616-9e2d574ffe60.png)

#### 第五步: 

##### 先提权

1. 执行`sudo su root`
2. 输入密码回车

然后使用*stack*或者*cabal*进行安装

##### 依次执行:
  
`stack update`

`stack install haskell-dap ghci-dap haskell-debug-adapter`

如果出现超时等报错则stack在wsl上翻车

改为使用cabal

##### 安装cabal: 

1. `apt -y install haskell-cabal`

##### 使用cabal安装调试器（如果stack没有出错就不用走这边）

1. `cabal update`
2. `cabal install ghci-dap haskell-debug-adapter-0.0.34.0`

#### 最后关于path环境

由于有可能因为安装软件的地方没有加入环境导致bug

应该执行以下步骤（root权限下）

`echo "export PATH=\"~/.local/bin/:$PATH\""`

`echo "export PATH=\"~/.stack/bin/:$PATH\""`

重启
