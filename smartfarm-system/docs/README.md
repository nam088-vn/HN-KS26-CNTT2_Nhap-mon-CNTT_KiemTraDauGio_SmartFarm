# Hệ thống Quản trị SmartFarm

## Hướng dẫn chạy script
Mở Terminal, di chuyển vào thư mục script và chạy lệnh:
``` bash
cd scripts/
chmod +x auto_report.sh
./auto_report.sh 
 ```
## Checklist kiểm tra thiết bị
- [x] Kiểm tra kết nối mạng của trạm sensor-03
- [ ] Cập nhật phần mềm hệ thống cho trạm ST01
- [ ] Thay thế bộ nguồn cho trạm bị lỗi
 ## Bảng thông số phần cứng
| Tên thiết bị | Đơn giá  | Loại storage |
| :--- | :--- | :--- |
| Raspberry Pi 4 Model B | 1,500,000 | MicroSD |
| Intel NUC i3 | 6,000,000 | SSD NVMe |
| Orange Pi 5 | 3,000,000 | eMMC |
 ## Phân tích hệ thống
1. Input - Process - Output (Chức năng lọc log):
- Input: File dữ liệu thô log-he-thong.log.
- Process: Dùng lệnh trích xuất để quét file, lọc ra các dòng chứa chuỗi "ERROR" hoặc "CRITICAL" và đếm số lượng.
- Output: File báo cáo bao-cao-su-co.txt chứa danh sách chi tiết và tổng số lỗi.
2. Phân loại tầng DIKW:
(a) Wisdom: Quyết định thay modem trạm sensor-03 trước thứ Sáu.
(b) Data: 2026-10-12 08:15:01 [ERROR] sensor-03 Connection TIMEOUT after 30s
(c) Information: Hôm nay hệ thống ghi nhận 8 sự cố, trong đó 4 sự cố đến từ trạm sensor-03.
(d) Knowledge: Trạm sensor-03 hay mất kết nối vào buổi chiều do sóng yếu, nên cần lắp thêm anten.