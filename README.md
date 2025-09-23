备份\还原：启动台的APP分组布局 



# -------
# 概要：
# -------
	+ 用于备份、还原 启动台（LaunchPad）内的APP分组。
	+ 备份路径：数据糊备份到iCloud云盘当中，在icloud盘符下的 BACKUP目录
 

# -------
# 命令说明：
# -------
	usercmd_backup_DesktopLayout	# 备份
	usercmd_restore_DesktopLayout	# 还原
	
	
# -------
# 命令路径：(建议的，此命令存放的路径)
# -------

 	/usr/local/bin/usercmd_backup_DesktopLayout
	/usr/local/bin/usercmd_restore_DesktopLayout


# -------
# 保存路径：(备份数据保存在哪里)
# -------

	/iCloud/计算机名称/用户名称/DesktopLayout

	# 注意：执行保存还原时，路径上的用户名中的空格，会被自动删除。


# -------
# 使用建议：
# -------

	+ 可以将备份命令加到自动任务当中，从而每日自动备份。


# -------
# 权限：
# -------
	+ 如何避免自动备份过程中的密码请求？ 
	  请将下面配置改为自己的用户名后（注意，用户名不能有空格）加入到 sudo visudo 中。


你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/cp -rf /System/Volumes/Data/private/var/folders/*/0/com.apple.dock.launchpad *

你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/chmod  -R 755 ./com.apple.dock.launchpad

你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/cp -rf */com.apple.dock.launchpad /System/Volumes/Data/private/var/folders/*/0



# -------
# 手动命令
# -------

# 控制台布局 数据库文件 所在的路径
# 备份还原本文件夹，即可 备份、还原 控制台布局。注意：在同一个Mac上，即便是不同的用户ID，也可以做到无缝拷贝布局

echo $(find $(find /System/Volumes/Data/private/var/folders/ -maxdepth 2 -type d -name "$(basename "$(dirname "$TMPDIR")")" 2>/dev/null) -maxdepth 2 -type d -name "com.apple.dock.launchpad" 2>/dev/null)


# 重启 控制台

killall Dock



# -------
# 版权：
# -------
	+ 遵从MIT协议
	+ 所有代码全部来自于 xAI SuperGrok Think 编写（仅经过微量删减）