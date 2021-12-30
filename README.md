# GCP-Troubleshooting

## VM 硬碟空間塞滿 無法進SSH解決辦法
1. 停止VM
2. 編輯VM -> 增加硬碟空間 -> 儲存
3. 編輯VM -> boot disk -> 按下右邊的X移除掉
4. 開新VM
5. 編輯新VM -> 其他磁碟 -> 連接現有磁碟 -> 選剛剛移除的硬碟
6. SSH 進新 VM -> 下 lsblk 秀出硬碟分配狀態 
7. 找到要增加空間的硬碟 例如 sdb1 -> 下 sudo growpart /dev/sdb 1
8. 最後編輯 VM 把硬碟掛載回原 VM
