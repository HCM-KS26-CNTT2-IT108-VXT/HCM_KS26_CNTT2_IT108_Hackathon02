# SoundLab-Phòng thu âm
website **đặt lịch** *phòng thu âm*
|Thư Mục|Nội Dung|
|--|--|
|docs| Tài liệu bàn giao|
|data| Bảng tính lịch thu âm|
|logs| log truy cập wedsite|
```

pwd
get-childitem -force
move-Item ./Quy_Trinh_Thu_Am.txt ./docs/
New-Item -Itemtype directory -p "backup"
copy-Item ./data/Lich_Thu_Thang_8.xlsx ./backup
remove-Item ./*.tmp
cd ./logs
get-childitem
cd ..
get-childitem -r -force

```
- [x] sắp xếp thư mục dự án
- [ ] upload dự án lên github
> Không Upload File.env lên GitHub