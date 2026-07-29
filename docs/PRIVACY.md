# Quyền riêng tư & dữ liệu

[← Quay lại trang chính](../README.md)

Paste được thiết kế theo nguyên tắc local-first: clipboard thuộc về bạn và mặc
định chỉ tồn tại trên máy của bạn.

## Paste lưu gì?

Tùy nội dung được sao chép, Paste có thể lưu:

- Văn bản và rich text.
- Liên kết, source code và mã màu.
- Ảnh.
- Danh sách đường dẫn của tệp được sao chép.
- Tên và bundle identifier của ứng dụng nguồn.
- Thời gian sao chép, số lần sử dụng, trạng thái yêu thích và pinboard.

Với clipboard chứa tệp, Paste lưu danh sách đường dẫn tới tệp gốc, không nhân
bản toàn bộ nội dung tệp vào kho dữ liệu.

## Dữ liệu nằm ở đâu?

```text
~/Library/Application Support/Paste/
```

Dữ liệu được chia theo loại nội dung và mỗi mục có một UUID riêng.

## Mã hóa

- Metadata và payload được mã hóa xác thực bằng AES-256-GCM.
- Khóa 256-bit được tạo ngẫu nhiên trên máy.
- Khóa được lưu trong macOS Keychain với nhãn **Paste Clipboard Data Key**.
- Khóa không nằm chung với thư mục dữ liệu clipboard.

Không xóa khóa Paste trong Keychain nếu bạn vẫn cần đọc lịch sử đã mã hóa.

## Kết nối mạng

Paste không đồng bộ lịch sử clipboard lên máy chủ và không tích hợp quảng cáo,
analytics hoặc telemetry.

Ứng dụng kết nối GitHub để:

- Đọc feed cập nhật công khai `appcast.xml`.
- Tải DMG của phiên bản mới khi người dùng đồng ý cập nhật.

GitHub có thể ghi nhận thông tin mạng tiêu chuẩn của một lượt tải theo chính
sách của GitHub. Nội dung clipboard không được gửi kèm yêu cầu cập nhật.

## Ứng dụng bị loại trừ

Paste có thể ngừng đọc clipboard khi một ứng dụng nhạy cảm đang hoạt động. Danh
sách mặc định bao gồm các trình quản lý mật khẩu phổ biến và có thể thay đổi
tại **Settings → Riêng tư**.

Việc loại trừ dựa trên bundle identifier của ứng dụng đang ở foreground.

## Chính sách lưu giữ

Bạn có thể chọn tự động giữ dữ liệu trong:

- 3 ngày, 1 tuần hoặc 1 tháng.
- 3 tháng, 6 tháng hoặc 1 năm.
- Vĩnh viễn.

Mục yêu thích không bị dọn tự động. Tuổi dữ liệu dựa trên hoạt động sao
chép/dán gần nhất.

## Xóa dữ liệu

### Xóa trong ứng dụng

- Chọn một hoặc nhiều mục rồi nhấn nút thùng rác.
- Nhấn `⌘A` để chọn toàn bộ kết quả đang hiển thị.
- Vào **Settings → Lưu trữ → Xóa toàn bộ…** để xóa toàn bộ lịch sử.

Paste luôn yêu cầu xác nhận trước khi xóa theo nhóm hoặc xóa toàn bộ.

### Xóa thủ công hoàn toàn

1. Thoát Paste.
2. Xóa thư mục:

   ```text
   ~/Library/Application Support/Paste/
   ```

3. Mở **Keychain Access**.
4. Tìm **Paste Clipboard Data Key** và chỉ xóa nếu bạn chắc chắn không cần phục
   hồi lịch sử cũ.

Xóa khóa Keychain là không thể hoàn tác: dữ liệu đã mã hóa bằng khóa đó sẽ
không thể đọc lại.

## Nhập dữ liệu Raycast

Importer làm việc trên một bản sao database Clipboard History của Raycast,
không sửa database gốc. Nội dung sau khi nhập được mã hóa bằng khóa của Paste
giống như các mục clipboard mới.

## Câu hỏi bảo mật

Nếu phát hiện vấn đề liên quan tới quyền riêng tư hoặc tính toàn vẹn của bản
phát hành, không đăng nội dung clipboard hay khóa bí mật vào issue công khai.
Hãy liên hệ chủ repository qua hồ sơ GitHub:
[ugotuan](https://github.com/ugotuan).
