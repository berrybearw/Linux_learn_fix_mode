# Linux_learn_fix_mode
emergency mode 維護模式介紹

FAQ
---
1. pquota 寫成 pgouta 無法正常開機

💡 搜尋看 journal 日誌 錯誤訊息

檢查看 /boot

如沒有 /boot 可以嘗試看

建立 mkdir /boot 

查看 /boot mount 型態 : mount | grep boot

![image](https://user-images.githubusercontent.com/96226780/202836277-6fb4d0a3-597e-44f0-9bb4-fd60eeede8fb.png)

執行 : mount -t xfs /dev/sda1 /boot

grep -r 'pguota'

發現是 /boot/grub2 檔案 grub.conf , grubenv 

把 pguota 改成 pquota 

接著存檔後重啟

