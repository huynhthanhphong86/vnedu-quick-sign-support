# Chính sách quyền riêng tư

Ngày hiệu lực: 17/09/2026

## 1. Phạm vi và đơn vị cung cấp

Chính sách này áp dụng cho tiện ích **Trợ lý Sổ đầu bài - Hỗ trợ vnEdu** (sau đây gọi là “Tiện ích”), do Huỳnh Thanh Phong cung cấp. Tiện ích là sản phẩm độc lập, không phải sản phẩm chính thức, không đại diện, không được tài trợ hoặc bảo chứng bởi VNPT/vnEdu. Google không phải bên bán giấy phép của Tiện ích.

## 2. Dữ liệu được xử lý trên trang vnEdu

Để cung cấp chức năng xem, nhập và ký sổ đầu bài theo yêu cầu của giáo viên, Tiện ích có thể đọc trên trang vnEdu đang đăng nhập:

- tên, mã tài khoản, ảnh đại diện và tên trường của giáo viên;
- năm học, tuần học, phân công giảng dạy, lớp, môn và tiết học;
- tên/mã học sinh và trạng thái vắng có phép, không phép hoặc có mặt;
- tên bài, tiết PPCT, nhận xét và xếp loại tiết học.

Dữ liệu này được xử lý trong trình duyệt. Tiện ích chỉ gửi dữ liệu trở lại hệ thống vnEdu khi giáo viên chủ động yêu cầu lưu. Máy chủ cấp phép của nhà phát triển không nhận tên học sinh, danh sách vắng, lớp, môn, nội dung tiết học hoặc nhận xét.

Tiện ích không đọc mật khẩu vnEdu và không truy cập trực tiếp cookie đăng nhập.

## 3. Dữ liệu tài khoản và giấy phép

Khi người dùng đăng nhập hoặc sử dụng giấy phép, Tiện ích gửi tới `api.phanmemso.vn`:

- địa chỉ email do người dùng chủ động nhập;
- mã cài đặt ngẫu nhiên do Tiện ích tạo ra, tên nền tảng/phiên bản Chrome cơ bản;
- OTP đã nhập để xác minh email;
- mã phiên đăng nhập, trạng thái dùng thử, thời hạn giấy phép và trạng thái thiết bị;
- mã đơn, số tiền, thời điểm và trạng thái thanh toán.

Mục đích là gửi OTP, ngăn lạm dụng dùng thử, giới hạn số thiết bị, tạo đơn thanh toán, kích hoạt và khôi phục giấy phép. Tiện ích không sử dụng tài khoản vnEdu làm mã nhận diện giấy phép.

Máy chủ lưu email, mã cài đặt, phiên đăng nhập, trạng thái dùng thử/giấy phép, đơn hàng và bản ghi giao dịch cần thiết để vận hành dịch vụ. Mật khẩu ngân hàng, thông tin đăng nhập ngân hàng và số thẻ không được Tiện ích hoặc máy chủ của nhà phát triển thu thập.

## 4. Nhà cung cấp dịch vụ

- **Cloudflare** vận hành API và cơ sở dữ liệu giấy phép.
- **Resend** nhận địa chỉ email và nội dung thư cần thiết để gửi OTP hoặc mã khôi phục giấy phép.
- **payOS** nhận thông tin đơn hàng cần thiết như email người mua, số tiền, mô tả và URL kết quả để tạo trang QR thanh toán; payOS gửi kết quả giao dịch về máy chủ qua webhook.
- **vnEdu** nhận dữ liệu sổ đầu bài khi giáo viên yêu cầu lưu bằng phiên đăng nhập hiện tại của giáo viên.

Các nhà cung cấp trên chỉ được sử dụng để thực hiện chức năng mà người dùng yêu cầu. Nhà phát triển không bán dữ liệu người dùng và không sử dụng dữ liệu cho quảng cáo, chấm điểm tín dụng hoặc mục đích không liên quan.

## 5. Lưu trữ cục bộ

Tiện ích có thể lưu trên trình duyệt:

- mã cài đặt ngẫu nhiên, mã phiên giấy phép và trạng thái giấy phép gần nhất;
- tùy chọn giao diện, buổi học mặc định, mẫu nhận xét và dữ liệu đệm cần thiết để tăng tốc sử dụng.

Người dùng có thể xóa dữ liệu giấy phép bằng chức năng đăng xuất trong popup. Việc gỡ Tiện ích sẽ ngăn Tiện ích tiếp tục truy cập trang; một số dữ liệu trang vnEdu lưu bằng `localStorage` có thể cần được xóa riêng trong cài đặt dữ liệu trang của Chrome.

## 6. Thời hạn và bảo mật

OTP có thời hạn ngắn và chỉ dùng một lần. Phiên đăng nhập giấy phép có thời hạn. Mã giấy phép được lưu trên máy chủ dưới dạng băm có khóa bảo vệ; bản rõ chỉ được gửi cho người dùng khi cấp giấy phép. Dữ liệu truyền qua HTTPS.

Dữ liệu tài khoản, giấy phép và giao dịch được giữ trong thời gian cần thiết để vận hành giấy phép, hỗ trợ người dùng, xử lý tranh chấp và đáp ứng nghĩa vụ pháp lý. Người dùng có thể yêu cầu xem xét hoặc xóa dữ liệu không còn cần thiết qua kênh hỗ trợ; một số bản ghi giao dịch có thể phải được giữ theo quy định áp dụng.

## 7. Quyền và lựa chọn của người dùng

Người dùng có thể:

- không nhập email và không kích hoạt dùng thử nếu không muốn dùng dịch vụ cấp phép;
- đăng xuất để xóa phiên giấy phép cục bộ;
- gỡ Tiện ích để chấm dứt quyền truy cập trang;
- yêu cầu hỗ trợ, tra cứu hoặc xóa dữ liệu tài khoản trong phạm vi có thể áp dụng.

Không đăng công khai OTP, mã giấy phép, mã giao dịch, thông tin ngân hàng hoặc dữ liệu học sinh trong GitHub Issues.

## 8. Thay đổi chính sách

Khi cách xử lý dữ liệu thay đổi đáng kể, chính sách này sẽ được cập nhật trước hoặc đồng thời với phiên bản Tiện ích liên quan.

## 9. Liên hệ

- Hỗ trợ công khai, không chứa dữ liệu nhạy cảm: https://github.com/huynhthanhphong86/vnedu-quick-sign-support/issues
- Email riêng tư về tài khoản, thanh toán và yêu cầu dữ liệu: **hotro@phanmemso.vn**
