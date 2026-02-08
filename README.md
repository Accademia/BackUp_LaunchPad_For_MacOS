

# 备份\还原：启动台的APP分组布局 


<br>



<br>
<br>

---------


# 概要：

<br>

+ 用于备份、还原 启动台（LaunchPad）内的APP分组。
+ 备份路径：数据糊备份到iCloud云盘当中，在icloud盘符下的 BACKUP目录
 
<br>
<br>

---------


# 命令说明：

<br>


```
usercmd_backup_LaunchpadLayout	# 备份
usercmd_restore_LaunchpadLayout	# 还原
```	

<br>
<br>

---------


# 程序下载

<br>

#  [usercmd_backup_LaunchpadLayout](https://cdn.jsdelivr.net/gh/Accademia/BackUp_LaunchPad_For_MacOS/usercmd_backup_LaunchpadLayout)  

> ### https://cdn.jsdelivr.net/gh/Accademia/BackUp_LaunchPad_For_MacOS/usercmd_backup_LaunchpadLayout


<br>

#  [usercmd_restore_LaunchpadLayout](https://cdn.jsdelivr.net/gh/Accademia/BackUp_LaunchPad_For_MacOS/usercmd_restore_LaunchpadLayout)  

> ### https://cdn.jsdelivr.net/gh/Accademia/BackUp_LaunchPad_For_MacOS/usercmd_restore_LaunchpadLayout

<br>
<br>

---------


# 命令路径：(建议的，此命令存放的路径)

<br>


```
/usr/local/bin/usercmd_backup_LaunchpadLayout
/usr/local/bin/usercmd_restore_LaunchpadLayout

```


<br>
<br>

---------


# 保存路径：(备份数据保存在哪里)

<br>

```
/iCloud/产品名-芯片型号-序列号/用户名称/LaunchpadLayout

```
注意：执行保存还原时，路径上的用户名中的空格，会被自动删除。

<br>
<br>

---------


# 使用建议：

<br>


+ 可以将备份命令加到自动任务当中，从而每日自动备份。

<br>
<br>

---------


# 权限：

<br>

+ 如何避免自动备份过程中的密码请求？ 
 请将下面配置改为自己的用户名后（注意，用户名不能有空格）加入到 sudo visudo 中。

```
你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/cp -rf /System/Volumes/Data/private/var/folders/*/0/com.apple.dock.launchpad *

你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/chmod  -R 755 ./com.apple.dock.launchpad

你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/cp -rf */com.apple.dock.launchpad /System/Volumes/Data/private/var/folders/*/0

```

<br>
<br>

---------


# 手动命令

<br>

控制台布局 数据库文件 所在的路径
备份还原本文件夹，即可 备份、还原 控制台布局。注意：在同一个Mac上，即便是不同的用户ID，也可以做到无缝拷贝布局

```
echo $(find $(find /System/Volumes/Data/private/var/folders/ -maxdepth 2 -type d -name "$(basename "$(dirname "$TMPDIR")")" 2>/dev/null) -maxdepth 2 -type d -name "com.apple.dock.launchpad" 2>/dev/null)

```

重启 控制台

```
killall Dock

```

<br>
<br>

---------

   
#  本项目相关的系列工具

<br>

 - ## [UpdateFull_For_MacOS](https://github.com/Accademia/UpdateFull_For_MacOS)  🔥🔥🔥🔥🔥 
   
   > 聚合更新脚本，聚合了市面上所有主流的MacOS APP更新程序，包括 Homebrew 、 Mas 、 Sparkle 、 MacPorts 、 TopGreade 、MacUpdater 等 第三方更新软件。实现 一站式 + 后台静默执行 + 无人值守式 更新 。

 - ## [Migrate_MacApp_To_Homebrew](https://github.com/Accademia/Migrate_MacApp_To_Homebrew)  🔥🔥🔥🔥🔥 
   
   > 扫描本机 App，生成可迁移到 Homebrew 的安装清单。

 - ## [Generate_Sudoers_For_Homebrew](https://github.com/Accademia/Generate_Sudoers_For_Homebrew)  🔥🔥🔥 
   
   > 生成 ，执行Homebrew升级时，所需的 sudoers 免密规则，便于当前脚本时，全自动更新（无人值守式更新）。

 - ## [BackUp_LoginitemsPrivacy_For_MacOS](https://github.com/Accademia/BackUp_LoginitemsPrivacy_For_MacOS)  🔥 
   
   > 备份/还原 登录项与扩展、隐私与安全（TCC）配置。

 - ## [BackUp_LaunchPad_For_MacOS](https://github.com/Accademia/BackUp_LaunchPad_For_MacOS)  🔥 
   
   > 备份/还原 LaunchPad（启动台）布局。

 - ## [Generate_ClashRuleset_For_Homebrew](https://github.com/Accademia/Generate_ClashRuleset_For_Homebrew)  
   
   > 生成用于 Homebrew 下载更新时，所需的 Clash 规则集，提升访问稳定性。



<br>
<br>


---------


# 版权：

<br>

+ 遵从MIT协议
+ 所有代码全部来自于 xAI SuperGrok Think 编写（仅经过微量删减）
