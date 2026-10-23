# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** Cao Bao Lam
- **Lớp:** CNTT2
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
Get-Location

Get-ChildItem -Force

Move-Item .\nhap_hang.txt .\docs\
Move-Item .\logo* .\media\

Copy-Item .\media\logo* .\backup\

Get-ChildItem -Path . -Filter *.tmp -File |
    Remove-Item

Set-Location .\logs
Get-ChildItem -Force

Set-Location ..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Get-ChildItem -Force -Recurse |
    Select-Object FullName, Mode
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell

Select-String -Path .\logs\shop.log -Pattern "ERROR" |
    ForEach-Object { $_.Line } |
    Set-Content .\logs\daily_report.txt

Get-Content .\logs\daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
(Dán kết quả vào đây – xoá dòng này)

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [ ] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [ ] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [ ] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [ ] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [ ] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Tac gia: Cao Bao Lam
# Ngay tao: 23/10/2026

$logFile = ".\logs\shop.log"
$reportFile = ".\logs\auto_report.txt"
$keyword = "ERROR"

Get-Content $logFile |
    Select-String -Pattern $keyword |
    ForEach-Object { $_.Line } |
    Set-Content $reportFile
```

### Nội dung file logs/auto_report.txt

```text
Get-Content .\logs\auto_report.txt

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
(Get-Content .\logs\shop.log |
    Select-String -Pattern "ERROR").Count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
(Dán kết quả vào đây – xoá dòng này)

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell

"=== TONG HOP LOG ===" |
    Set-Content .\logs\tong_hop.txt


Get-Content .\logs\shop.log |
    Select-String -Pattern "WARNING" |
    ForEach-Object { $_.Line } |
    Add-Content .\logs\tong_hop.txt


(Get-Content .\logs\shop.log |
    Select-String -Pattern "ERROR").Count |
    Add-Content .\logs\tong_hop.txt


Get-Content .\logs\tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
(Dán kết quả vào đây – xoá dòng này)

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
