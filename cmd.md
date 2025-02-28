node版本管理，先安装n
sudo npm i -g n

查看已安装的node版本
n ls

切换node版本
sudo n
选择一个版本回车即可

安装指定版本node
sudo n install x.x.0

因为gitbook-cli依赖graceful-fs，这依赖不更新了，高版本node不支持，需要注释掉statFix函数：
sudo vi /usr/local/lib/node_modules/gitbook-cli/node_modules/npm/node_modules/graceful-fs/polyfills.js
//fs.stat = statFix(fs.stat)
//fs.fstat = statFix(fs.fstat)
//fs.lstat = statFix(fs.lstat)

安装gitbook依赖
sudo gitbool install

启动gitbook服务
sudo gitbook serve

在SUMMARY.md里定义的文件链接，不能是包含在.gitignore里的。