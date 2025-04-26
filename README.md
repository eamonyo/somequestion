# somequestion
日常遇到问题以及解决

vmware linux共享文件夹不显示
sudo vmhgfs-fuse .host:/ /mnt/hgfs/ -o allow_other -o uid=1000
vmhgfs-fuse：VMware提供的用于挂载虚拟机共享文件夹的工具。
.host:/：表示共享文件夹在虚拟机中的挂载点。
/mnt/hgfs/：指定共享文件夹在宿主机上的挂载点。
-o allow_other：允许其他用户访问挂载的文件系统。
-o uid=1000：设置挂载文件系统的用户ID为1000。这通常用于确保挂载的文件系统以特定的用户身份运行，1000通常是普通用户的UID。
