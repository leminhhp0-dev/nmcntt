# BÀI LÀM – ÔN TẬP NGÀY 1

- **Họ tên:Lê Hồng Minh**
- **Lớp:CNTT 1**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):windows**

## Phần A. Tổ chức thư mục bằng GUI

> Phần A được chấm qua kết quả B1 (tên thư mục gốc) và kết quả liệt kê toàn bộ dự án B8 ở Phần B, không cần ghi thêm ở đây.

## Phần B. Thao tác bằng CLI

### Các lệnh đã chạy (B1–B7)

```shell
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng
 pwd
 ls -Recurse
 mv .\lich_hoc.txt .\docs\
 mv .\logo_trung_tam.PNG .\media\
 mv .\anh_lop_hoc.JPG .\media\
 cp .\media\logo_trung_tam.PNG .\archive\
 rm .\temp_201.tmp
 rm .\temp_202.tmp
 cd .\logs\
 ls
 cd ..
 cd .\docs\
 cp ..\media\anh_lop_hoc.JPG ..\archive\
 cd..
```

### Kết quả B1 (pwd)

```text
Path
----
C:\Users\LeMinhHP\Downloads\starter-kit\s...

```

### Kết quả liệt kê toàn bộ dự án – B8 (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
    Directory:
    C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\trung-tam-tieng-anh


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/20/2026  10:36 PM                archive
d-----        10/20/2026  10:01 PM                data
d-----        10/20/2026  10:18 PM                docs
d-----        10/20/2026  10:02 PM                logs
d-----        10/20/2026  10:35 PM                media
------        10/19/2026  10:04 AM             83 .env
-a----        10/19/2026  10:04 AM            902 bai_lam_ngay1.md


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\trung-ta
    m-tieng-anh\archive


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026  10:04 AM          13559 anh_lop_hoc.JPG
-a----        10/19/2026  10:04 AM           5184 logo_trung_tam.PNG


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\trung-ta
    m-tieng-anh\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026  10:04 AM           5070 hoc_vien_khoa_3.xlsx


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\trung-ta
    m-tieng-anh\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026  10:04 AM             67 lich_hoc.txt


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\trung-ta
    m-tieng-anh\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026  10:04 AM           1072 access.log


    Directory: C:\Users\LeMinhHP\Downloads\starter-kit\starter-kit\trung-ta
    m-tieng-anh\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026  10:04 AM          13559 anh_lop_hoc.JPG
-a----        10/19/2026  10:04 AM           5184 logo_trung_tam.PNG

```

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
