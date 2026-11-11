# BÀI LÀM – HACKATHON 02

- **Mã đề:** 08
- **Họ tên:** Vo_Xuan_Thinh
- **Lớp:** CNTT2
- **Link repository:** https://github.com/HCM-KS26-CNTT2-IT108-VXT/HCM_KS26_CNTT2_IT108_Hackathon02.git
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
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

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text

   Directory: D:\Hoc_Tap_PTIT\Year_one\HK_1_2026-2027\IT-108\Test_cuoi_ki\starter-kit\Phong_Thu_Am_Website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   1:54 PM                backup
d-----        11/11/2026   1:42 PM                data
d-----        11/11/2026   1:50 PM                docs
d-----        11/11/2026   1:37 PM                evidence
d-----        11/11/2026   1:43 PM                logs
d-----        11/11/2026   1:32 PM                web
------         11/3/2026   7:08 AM             74 .env
-a----         11/3/2026   7:08 AM           2409 bai_lam.md


    Directory: D:\Hoc_Tap_PTIT\Year_one\HK_1_2026-2027\IT-108\Test_cuoi_ki\starter-kit\Phong_Thu_Am_Website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:08 AM           6136 Lich_Thu_Thang_8.xlsx


    Directory: D:\Hoc_Tap_PTIT\Year_one\HK_1_2026-2027\IT-108\Test_cuoi_ki\starter-kit\Phong_Thu_Am_Website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:08 AM           6136 Lich_Thu_Thang_8.xlsx


    Directory: D:\Hoc_Tap_PTIT\Year_one\HK_1_2026-2027\IT-108\Test_cuoi_ki\starter-kit\Phong_Thu_Am_Website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:08 AM            157 Quy_Trinh_Thu_Am.txt


    Directory: D:\Hoc_Tap_PTIT\Year_one\HK_1_2026-2027\IT-108\Test_cuoi_ki\starter-kit\Phong_Thu_Am_Website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:08 AM            992 Studio.log


    Directory: D:\Hoc_Tap_PTIT\Year_one\HK_1_2026-2027\IT-108\Test_cuoi_ki\starter-kit\Phong_Thu_Am_Website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   1:32 PM                images
------         11/3/2026   7:08 AM            586 app.js
------         11/3/2026   7:08 AM            514 index.html
------         11/3/2026   7:08 AM            460 style.css


    Directory: D:\Hoc_Tap_PTIT\Year_one\HK_1_2026-2027\IT-108\Test_cuoi_ki\starter-kit\Phong_Thu_Am_Website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:08 AM           3097 logo-soundlab.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
get-content ./logs/Studio.log | select-string "status=500" >> logs/loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-08-28 08:25:34 POST /api/dat-lich status=500
2026-08-28 08:34:07 POST /api/thanh-toan status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
(get-content ./logs/Studio.log | select-string "status=404").count >> logs/loi_500.txt

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
 .\Tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text

=== BAO CAO SU CO WEBSITE ===

2026-08-28 08:16:01 GET /tin-tuc status=404
2026-08-28 08:47:51 GET /san-pham-cu status=404
2026-08-28 08:58:24 GET /images/phong-thu-2.jpg status=404
2026-08-28 09:00:35 GET /images/phong-thu-2.jpg status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** 
- **Expected:** 
- **Actual:** 
- **Log:** 

### Câu tìm kiếm Google

```text
(Ghi câu tìm kiếm vào đây – xoá dòng này)

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/lich_thu_thang_8.xlsx`, không cần ghi vào đây.
