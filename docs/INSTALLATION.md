# Cài đặt Paste

[← Quay lại trang chính](../README.md)

## Yêu cầu

- macOS 14 Sonoma hoặc mới hơn.
- Máy Mac dùng Apple Silicon: M1, M2, M3, M4 hoặc mới hơn.
- Khoảng 20 MB dung lượng trống cho ứng dụng; lịch sử clipboard sử dụng thêm
  dung lượng tùy nội dung bạn sao chép.

## Cài đặt

1. Tải
   [Paste-1.2.5-arm64.dmg](https://github.com/ugotuan/paste-releases/releases/download/v1.2.5/Paste-1.2.5-arm64.dmg).
2. Nhấp đúp file vừa tải để mở disk image.
3. Kéo **Paste.app** vào shortcut **Applications**.
4. Eject disk image Paste.
5. Mở **Applications → Paste**.

## Nếu macOS chặn lần mở đầu tiên

Bản thử nghiệm hiện tại được ký ad-hoc và chưa notarize bằng Apple Developer
ID, vì vậy Gatekeeper có thể hiển thị cảnh báo.

Thử theo thứ tự:

1. Mở Finder → **Applications**.
2. Giữ `Control`, nhấp **Paste**, chọn **Open**.
3. Chọn **Open** lần nữa trong hộp thoại xác nhận.

Nếu nút Open chưa xuất hiện:

1. Mở **System Settings → Privacy & Security**.
2. Kéo xuống phần Security.
3. Tìm thông báo Paste vừa bị chặn và chọn **Open Anyway**.
4. Xác nhận bằng Touch ID hoặc mật khẩu macOS nếu được yêu cầu.

Chỉ tải Paste từ repo chính thức:
`https://github.com/ugotuan/paste-releases`.

## Thiết lập lần đầu

### Khởi động cùng macOS

Paste mặc định đăng ký chạy sau khi đăng nhập. Bạn có thể tắt tại
**Paste → Settings → General → Mở Paste khi đăng nhập**.

Nếu macOS yêu cầu phê duyệt Login Item, Paste sẽ hiển thị nút mở đúng trang
System Settings.

### Đổi phím tắt

Phím mặc định là `⌘⇧V`. Để thay đổi:

1. Mở **Paste → Settings → General**.
2. Tại **Phím tắt**, bấm vào tổ hợp hiện tại.
3. Nhấn tổ hợp mới có ít nhất một trong các phím `⌘`, `⌥` hoặc `⌃`.

### Accessibility

Paste chỉ cần Accessibility khi bạn dùng **Dán ngay**, vì macOS yêu cầu quyền
để ứng dụng gửi tổ hợp `⌘V` tới ứng dụng khác.

Lần đầu sử dụng, Paste sẽ yêu cầu quyền qua hộp thoại của macOS. Bạn cũng có thể
mở **Paste → Cài đặt → Chung → Dán ngay** để xem trạng thái và yêu cầu cấp quyền.
Sau khi bật Paste trong **System Settings → Privacy & Security →
Accessibility**, quay lại Paste và thử thao tác dán lần nữa.

Nếu chưa cấp quyền, Paste vẫn chép mục đã chọn vào clipboard nhưng không thể tự
gửi `⌘V`; bạn vẫn có thể dán thủ công.

Bạn không cần cấp quyền này để:

- Lưu lịch sử clipboard.
- Tìm kiếm và xem nội dung.
- Sao chép một mục trở lại clipboard.
- Sử dụng phím tắt mở Paste.

## Cập nhật

Paste kiểm tra cập nhật lúc `00:00` và `12:00` theo giờ địa phương. Bạn cũng có
thể chọn **Paste → Kiểm tra cập nhật…**.

Khi có phiên bản mới, Sparkle tải file cập nhật, kiểm tra chữ ký EdDSA rồi mới
tiến hành thay ứng dụng.

## Gỡ cài đặt

1. Thoát Paste.
2. Xóa `/Applications/Paste.app`.

Thao tác trên không xóa lịch sử. Để xóa cả dữ liệu, xem
[Xóa dữ liệu](PRIVACY.md#xóa-dữ-liệu).
