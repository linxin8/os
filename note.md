# 笔记

## 启动

内核小于100kb

## 内存

分页机制只区分用户级(CPL3)和系统级，系统级可以访问用户级内容，而分段区分4级，不可以跨级访问  
用户物理内存起始地址0x1100000,bitmap 9A1E0,内核物理内存起始地址0x2000000,bitmap 9A000  
用户虚线堆栈：8048000  
i386不支持invlpg指令  
一个扇区512B  

## 段选择子

| 7654321076543 | 2   | 10  |
| ------------- | --- | --- |
| index         | T/I | RPL |

## 分区信息

|      | start lab | sector count | block bltmap | inode bitmap | inode table | block table |
| ---- | --------- | ------------ | ------------ | ------------ | ----------- | ----------- |
| sdb1 | 0x800     | 0x186A1      | 0x802        | 0x818        | 0x81C       | 0xA7C       |
| sdb2 | 0x19000   | 0xEDE0       | 0x19002      | 0x19011      | 0x19012     | 0x19272     |
  
| Device       | Boot | Start  | End    | Sectors | Size  | Id  | Type  |
| ------------ | ---- | ------ | ------ | ------- | ----- | --- | ----- |
| ./hd80M.img1 |      | 2048   | 102048 | 100001  | 48.8M | 83  | Linux |
| /hd80M.img2  |      | 102400 | 163295 | 60896   | 29.8M | 83  | Linux |