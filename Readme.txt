# ————————————————————————
# 备份\还原：启动台的APP分组布局 
# ————————————————————————

概要：

	+ 用于备份、还原 启动台（LaunchPad）内的APP分组。

	+ 备份路径：数据糊备份到iCloud云盘当中，在icloud盘符下的 BACKUP目录
 

备份命令：
	usercmd_backup_DesktopLayout


还原命令：
	usercmd_restore_DesktopLayout


 
建议：

	+ 可以将备份命令加到自动任务当中，从而每日自动备份。


权限：
	+ 如何避免自动备份过程中的密码请求？ 请将下面配置改为自己的用户名后（注意，用户名不能有空格），加入到 sudo visudo 中。


你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/cp -rf /System/Volumes/Data/private/var/folders/*/0/com.apple.dock.launchpad *
你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/chmod  -R 755 ./com.apple.dock.launchpad

你的用户名 ALL=(ALL) NOPASSWD: SETENV: /bin/cp -rf */com.apple.dock.launchpad /System/Volumes/Data/private/var/folders/*/0