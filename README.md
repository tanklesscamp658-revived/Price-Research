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

### Nếu muốn hiện giá ngay trong bảng (giai đoạn 2)

Cần thêm một backend nhỏ đứng giữa để cào dữ liệu hộ, vì GitHub Pages không
chạy được server. Có thể dùng miễn phí:

- Cloudflare Workers / Workers KV
- Vercel Serverless Functions
- GitHub Actions chạy định kỳ (phù hợp nếu bạn chỉ cần theo dõi giá của một
  danh sách sản phẩm cố định, không phải tìm kiếm tự do)

Nếu bạn muốn, mình có thể dựng tiếp phần này ở bước sau.

## Cách đưa lên GitHub Pages

1. Tạo một repository mới trên GitHub (ví dụ: `tra-gia-san-pham`).
2. Tải file `index.html` này lên repo (kéo-thả trên GitHub web, hoặc qua Git).
3. Vào **Settings → Pages**.
4. Ở mục **Branch**, chọn `main` (hoặc nhánh bạn vừa đẩy code lên) và thư mục
   `/ (root)`, rồi bấm **Save**.
5. Đợi khoảng 1 phút, GitHub sẽ cấp cho bạn một đường link dạng:
   `https://<tên-tài-khoản>.github.io/<tên-repo>/`
6. Mở link đó lên là dùng được ngay, trên điện thoại cũng xem được bình thường.

Mỗi lần bạn sửa `index.html` và đẩy (push) lên GitHub, trang sẽ tự cập nhật
sau khoảng 1 phút, không cần làm lại bước Pages.
