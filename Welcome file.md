# BÀI LÀM – HACKATHON 01

- **Mã đề:** 03
- **Họ tên:**  Vũ Cao Minh
- **Lớp:** CNTT6
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
Get-ChildItem -Force
Move-Item lich_tap.txt docs/
Move-Item logo_phong_gym.png media/
Copy-Item media/logo_phong_gym.png backup/
Remove-Item temp_103.tmp
cd logs
Get-ChildItem
cd ..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/15/2026   8:13 AM                backup
d-----        10/15/2026   8:15 AM                data
d-----        10/15/2026   8:13 AM                docs
d-----        10/15/2026   8:16 AM                gym_website
d-----        10/15/2026   8:23 AM                logs
d-----        10/15/2026   8:13 AM                media

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-Content logs/member.log | Select-String "ERROR" > logs\daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-10-14 08:30:15 [ERROR] Connection timeout to database server. 
2026-10-14 09:12:44 [ERROR] Failed to authenticate user session ID #4092.

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [ ] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [ ] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [ ] Blockquote nhắc không upload `.env`

# Gym Website Management System
*Dự án phát triển hệ thống quản lý phòng tập gym* với các tính năng **quản lý hội viên**,**lịch tập** và **báo cáo tự động**

| Thư mục | Nội dung |
| :--- | :--- |
| Docs | Lưu trữ tài liệu học tập
| Media | Lưu trữ hình ảnh logo phòng gym |
| Data | Lưu trữ dữ liệu đăng ký hội viên 
| Logs | Lưu trữ nhật ký hệ thống |

## Task List
- [x] Học thuộc câu lệnh 
- [x] Lưu trữ tốt

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Script: auto_report.ps1
# Tac gia: Vu Cao Minh
# Ngay Tao: 15-10-2026
Write-Host "Dang loc log "
"=== BAO CAO LOI ===" > logs/auto_report.txt
Get-Content logs/member.log | Select-String "ERROR" >> logs/auto_report.txt
Write-Hose "Hoan thanh!"

```

### Kết quả hiển thị

```text
(Dán kết quả vào đây – xoá dòng này)

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
(Get-Content logs/member.log | Select-String "ERROR") .Count

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
12

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"=== TONG HOP LOG ===" > logs/tong_hop.txt
Get-Content logs/member.log | Select-String "WARNING" >> logs/tong_hop.txt
(Get-Content logs/member.log | Select-String "ERROR") .Count >> logs/tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
(Dán kết quả vào đây – xoá dòng này)

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/dang_ky_thang_11.xlsx`, không cần ghi vào đây.
