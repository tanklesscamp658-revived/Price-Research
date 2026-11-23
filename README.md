# Tra giá sản phẩm

Trang tĩnh (1 file HTML, không cần cài đặt gì) giúp người dùng gõ tên sản phẩm
rồi bấm thẳng tới trang tìm kiếm của:

- Nhà thuốc Long Châu
- Pharmacity
- Nhà thuốc An Khang
- Website chính hãng của nhà sản xuất (qua tìm kiếm Google)

## Vì sao không hiện giá ngay trong bảng?

Các trang trên **chặn truy cập dữ liệu chéo domain (CORS)** và hiển thị giá
bằng JavaScript phía máy chủ riêng của họ. Một trang tĩnh host trên GitHub
Pages (không có server) không thể đọc được dữ liệu đó trong thời gian thực.
Giải pháp ở đây dùng link tìm kiếm trỏ thẳng (deep link) tới từng site, nên
giá bạn thấy luôn là giá thật, mới nhất — chỉ mất thêm một cú click.

