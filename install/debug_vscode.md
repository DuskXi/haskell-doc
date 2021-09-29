## 如何在VSCode中调试Haskell
---
1. 在左边栏中的资源管理器中右键创建文件: *helloworld.hs*
2. 在上方找到*运行* > *添加配置*
3. 找到配置中的`startup`, 将右边的值改为`${workspaceFolder}/helloworld.hs`（其中两处都需要修改）
4. 在上方找到*运行* > *启动调试*, 或按下F5
5. 在左上方找到如下界面:![image](https://user-images.githubusercontent.com/84715902/135362072-27fcc67f-3793-4b24-8585-ff5af7770f50.png)
6. 如果你是cabal安装的就选择cabal，如果是stack安装的就选择stack
7. 完成选择以后再次按下F5开始调试
