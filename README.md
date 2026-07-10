# MK Solar

MK Solar là thẻ Lovelace toàn màn hình dành cho Home Assistant, hiển thị điện mặt trời, lưới điện, tải, pin lưu trữ, thời tiết và lịch sử năng lượng.

Đây là bản phân phối công khai đã được làm sạch. Kho không chứa tài khoản, mật khẩu, token, địa chỉ mạng nội bộ, cấu hình thiết bị riêng hoặc định danh camera của hệ thống phát triển.

## Cài đặt bằng HACS

1. Vào **HACS → Frontend → Custom repositories**.
2. Thêm `https://github.com/quanghaupro/MK-solar` với loại **Dashboard**.
3. Cài đặt **MK Solar** và tải lại trình duyệt.
4. Tạo một dashboard ở chế độ **Panel (1 card)**.

## Cài đặt thủ công

Sao chép `mk-solar.js` và thư mục `sky` vào:

```text
/config/www/community/MK-solar/
```

Thêm tài nguyên Lovelace:

```text
/local/community/MK-solar/mk-solar.js
```

Loại tài nguyên: `JavaScript Module`.

Khi cài thủ công, đặt `background_path` thành `/local/community/MK-solar/sky`.

## Cấu hình tối thiểu

```yaml
type: custom:casa-luna
title: MK SOLAR
language: vi
background_path: /hacsfiles/MK-solar/sky
weather_entity: weather.home
pv1_power: sensor.example_pv1_power
pv2_power: sensor.example_pv2_power
grid_active_power: sensor.example_grid_power
consump: sensor.example_load_power
battery_soc: sensor.example_battery_soc
battery_power: sensor.example_battery_power
today_pv: sensor.example_pv_energy_today
grid_import_today: sensor.example_grid_import_today
```

Thay các thực thể `sensor.example_*` bằng thực thể của hệ thống của bạn. Không đưa mật khẩu, token hoặc URL chứa thông tin đăng nhập vào YAML dashboard.

## Chức năng

- Luồng năng lượng PV, lưới, tải và pin.
- Phân biệt trạng thái sạc, xả và chờ.
- Biểu đồ năng lượng ngày/tháng.
- Ảnh nền WebP tự đổi theo thời tiết và thời gian.
- Tự co theo Chrome, máy tính bảng và điện thoại.
- Trình chỉnh sửa trực quan trong Home Assistant.

## Quyền riêng tư

Gói phát hành chỉ chứa mã giao diện và ảnh nền. Các script triển khai nội bộ, dữ liệu Home Assistant, nhật ký, khóa truy cập và cấu hình thiết bị riêng không thuộc kho này.

