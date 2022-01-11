# Đăng Ký

Người dùng cần nhập vào khung tài khoản(8 ký tự) và khung mật khẩu(8 ký tự), khung nhập lại mật khẩu -> Bấm nút đăng ký -> máy tự động kiểm tra khung mật khẩu và khung nhập lại mật khẩu có khớp với nhau không, nếu không thì hiện thông báo "Nhập lại mật khẩu đã bị sai", nếu khớp thì -> Api(Registration) kiểm tra tên tài khoản đã tồn tại trên bảng USER, nếu tồn tại thì thông báo "Tài khoản đã tôn tại, hãy chọn 1 tài khoản khác", nếu chưa tồn tại thì tạo thêm dữ liệu vào bảng USER -> máy chuyển qua Activity đăng nhập.

# Đăng Nhập

Nhập vào 2 khung tài khoản và mật khẩu -> máy kiểm tra có trống hay khung nào chưa đủ 8 ký tự, nếu sai thì thông báo "Bạn đã nhập sai, xin nhập lại cho đúng", nếu đúng thì -> Api(SignIn) kiểm tra bảng USER với 2 thông tin tài khoản và mật khẩu xem có không, nếu sai thì báo "Tài khoản hoặc mật khẩu của bạn bị sai", nếu đúng thì trả thông tin của USER về -> máy chuyển qua Main Activity
