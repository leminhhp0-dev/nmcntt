## 1. Khối code Python
```python
DRY_THRESHOLD = 35
def control_pump(moisture_level):
    if moisture_level < DRY_THRESHOLD:
        print("Đất khô - bật máy bơm")
    else:
        print("Đất đủ ẩm - tắt máy bơm")
moisture_level = 25
control_pump(moisture_level)
```
## 4. Bảng so sánh cảm biến
| Tiêu chí | Cảm biến cũ | Cảm biến mới |
|:---:|:---:|:---:|
| Nguyên lý | Điện trở | Điện dung |
| Độ bền | Dễ bị ăn mòn hơn | Thường bền hơn |
| Chi phí | Thấp | Cao hơn |
| Bảo trì | Thường xuyên hơn | Ít hơn tùy loại |
## 5. Danh sách kiểm tra
- [ ] Kiểm tra model cảm biến
- [ ] Kiểm tra nguồn điện
- [ ] Kết nối cảm biến đúng sơ đồ
- [ ] Kiểm tra giá trị độ ẩm
- [ ] Kiểm tra mạch điều khiển máy bơm
- [ ] Thử nghiệm hệ thống an toàn
