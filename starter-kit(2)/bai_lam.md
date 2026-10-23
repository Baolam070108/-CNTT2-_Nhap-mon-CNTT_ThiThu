# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** Cao Bao Lam
- **Lớp:**CNTT2 
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
get-childitem -force -recurse
mv .\nhap_hang.txt .\docs\
mv .\logo_van_phong_pham.png .\media\
copy-item .\media\logo_van_phong_pham.png .\backup\
rm .\temp_131.tmp
dir logs


```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory: C:\Users\Admin\Downloads\starter-kit(3)\starter-kit\van-phon
    g-pham-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/23/2026   8:54 AM                backup
d-----        10/23/2026   8:40 AM                data
d-----        10/23/2026   8:47 AM                docs
d-----        10/23/2026   8:40 AM                logs
d-----        10/23/2026   8:47 AM                media
------        10/19/2026   9:41 AM             78 .env
-a----        10/23/2026   8:54 AM           2390 bai_lam.md


    Directory: C:\Users\Admin\Downloads\starter-kit(3)\starter-kit\van-phon
    g-pham-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png


    Directory: C:\Users\Admin\Downloads\starter-kit(3)\starter-kit\van-phon
    g-pham-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6105 don_ban_thang_10.xlsx


    Directory: C:\Users\Admin\Downloads\starter-kit(3)\starter-kit\van-phon
    g-pham-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM             51 nhap_hang.txt


    Directory: C:\Users\Admin\Downloads\starter-kit(3)\starter-kit\van-phon
    g-pham-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           1053 shop.log


    Directory: C:\Users\Admin\Downloads\starter-kit(3)\starter-kit\van-phon
    g-pham-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
get-content .\logs\shop.log | select-string "ERROR" | out-file .\logs\daily_report.txt -append

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [X] Heading 1: tên dự án
- [X] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [X] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [X] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [X] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [X] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\auto_report.ps1

```

### Nội dung file logs/auto_report.txt

```text
# Script: auto_report.ps1
# Tac gia: Lê Hồng Quân
# Ngay tao: 23/10/2026
 
Write-Host "Dang loc log..."
 
"=== BAO CAO LOI ===" > logs/auto_report.txt 
Get-Content logs/shop.log | Select-String "ERROR" >> logs/auto_report.txt 
 
Write-Host "Hoan thanh!"

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
(get-content .\logs\shop.log | select-string "ERROR").count

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
6

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"===TONG HOP LOG===" > .\logs\tong_hop.txt
get-content .\logs\shop.log | select-string "WARNING" >> .\logs\tong_hop.txt
(get-content .\logs\shop.log | select-string "ERROR").count >>.\logs\tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
===TONG HOP LOG===

2025-10-28 08:51:28 [WARNING] Thoi gian tai trang cham
2025-10-28 08:54:28 [WARNING] Anh san pham dung luong lon
2025-10-28 08:57:28 [WARNING] Thoi gian tai trang cham


6

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
