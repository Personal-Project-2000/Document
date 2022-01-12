<ul>
  <li><a href ="#number01">Đăng ký</a></li>
  <li><a href ="#number02">Đăng nhập</a></li>
  <li><a href ="#number03">Tìm kiếm phòng</a></li>
  <li><a href ="#number04">Xem thông tin cá nhân</a></li>
  <li><a href ="#number05">Thay đổi thông tin cá nhân</a></li>
  <li><a href ="#number06">Cài đặt</a></li>
  <li><a href ="#number07">Tạo phòng</a></li>
  <li><a href ="#number08">Tham gia phòng</a></li>
  <li><a href ="#number09">Đăng Ký</a></li>
  <li><a href ="#number10">Đăng Ký</a></li>
</ul>

<h1 id="number01"> Đăng ký </h1>

Người dùng cần nhập vào khung tài khoản(8 ký tự) và khung mật khẩu(8 ký tự), khung nhập lại mật khẩu -> Bấm nút đăng ký -> máy tự động kiểm tra khung mật khẩu và khung nhập lại mật khẩu có khớp với nhau không, nếu không thì hiện thông báo "Nhập lại mật khẩu đã bị sai", nếu khớp thì -> Api(Registration) kiểm tra tên tài khoản đã tồn tại trên bảng USER, nếu tồn tại thì thông báo "Tài khoản đã tôn tại, hãy chọn 1 tài khoản khác", nếu chưa tồn tại thì tạo thêm dữ liệu vào bảng USER -> Máy chuyển qua Activity đăng nhập.

<h1 id="number02"> Đăng Nhập </h1>

Nhập vào 2 khung tài khoản và mật khẩu -> Máy kiểm tra có trống hay khung nào chưa đủ 8 ký tự, nếu sai thì thông báo "Bạn đã nhập sai, xin nhập lại cho đúng", nếu đúng thì -> Api(SignIn) kiểm tra bảng USER với 2 thông tin tài khoản và mật khẩu xem có không, nếu sai thì báo "Tài khoản hoặc mật khẩu của bạn bị sai", nếu đúng thì trả thông tin của USER về -> Máy chuyển qua Main Activity

<h1 id="number03"> Tìm kiếm phòng </h1>

Bấm vào khung tìm -> Nhập mã phòng hoặc tên chủ phòng theo ra phòng, ngoài việc nhập có thể dùng mic để đọc từ khóa tìm kiếm -> Máy kiểm tra có để trống dữ liệu trong khung tìm kiếm, nếu có thì thông báo "Không có dữ liệu để tìm kiếm", nếu không trống thì -> Api(SearchRoom) kiểm tra mã của các phòng có khớp với key không, nếu có thì trả về danh sanh phòng khớp, nếu không thì tìm kiếm tên chủ phòng, nếu có thì trả về danh sách phòng gần đúng, nếu không thì thông báo "Phòng bạn tìm kiếm hiện không tồn tại".

<h1 id="number04"> Xem thông tin cá nhân </h1>

Bấm vào biểu tượng ☰ -> Chọn thông tin cá nhân -> Api(GetInfo) lấy dữ liệu USER theo <u>TK</u>.

<h1 id="number05"> Thay đổi thông tin cá nhân </h1>

Tên người dùng: Vào mục xem thông tin cá nhân -> Xóa tên củ -> Viết tên mới vào -> Bấm nút lưu -> Api(UpdateInfo) cập nhật lại tên của USER

Hình ảnh: Vào mục xem thông tin cá nhân -> Bấm vào khung ảnh -> Chọn ảnh mới từ máy -> Bấm nút lưu -> Api(UpdateInfo) cập nhật lại tên của USER

Mật khẩu: Vào mục xem thông tin cá nhân -> Bấm vào thay đổi mật khẩu -> Nhập mật khẩu củ và 2 lần mật khẩu mới -> Bấm nút lưu -> Máy kiểm tra 2 lần mật khẩu mới có trùng nhau không, nếu không thì thông báo "Nhập lại mật khẩu đã bị sai", nếu có thì -> Api(ChangePass) kiểm tra mật khẩu có trùng với dữ liệu của bảng USER, nếu không thì thông báo "Mật khẩu củ đã sai", nếu có thì cập nhật lại mật khẩu mới.

<h1 id="number06"> Cài đặt </h1>

BackGround: Bấm vào biểu tượng ☰ -> Chọn cài đặt -> Thay đổi màn hình chế độ sáng hay tối -> Bấm nút lưu -> Api(UpdateSetting) cập nhật lại bảng USER

Ngôn ngữ: Bấm vào biểu tượng ☰ -> Chọn cài đặt -> Bấm vào mũi tên sổ xuống -> Chọn ngôn ngữ mong muốn -> Bấm nút lưu -> Api(UpdateSetting) cập nhật lại bảng USER

<h1 id="number07"> Tạo phòng </h1>

Bấm vào biểu tượng ☰ -> Chọn tạo phòng -> Api(CreateRoom) thêm dữ liệu mới vào bảng ROOM và trả về RoomId cho người tạo -> Gữi RoomId và tên người tạo lên RealTime -> RealTime gửi RoomId và tên người tạo về các người dùng còn lại -> Máy của người dùng còn lại kiểm tra khung tìm kiếm có dữ liệu không, nếu không thì hiện thêm phòng mới với RoomId, nếu có thì kiểm thông tin phòng có giống với từ khóa, nếu giống thì hiện, nếu không giống thì không hiện.

<h1 id="number08"> Tham gia phòng </h1>

Bấm vào phòng mà muốn vào -> Api(CheckPass) kiểm tra phòng có mật khẩu, nếu không thì vào phòng, nếu có thì gửi pass về cho máy -> Nhập pass vào khung -> Máy kiểm tra pass, nếu đúng thì vào phòng, nếu sai thì hiện thông báo "Nhập sai mật khẩu"

Khi vào phòng -> Api(GetPlayer) thêm dữ liệu vào bảng ROOMDETAIL và trả danh sách người(tên, hình, boss) đã tham gia phòng trước -> Gửi TK lên RealTime -> RealTime gửi UserId cho những người đã có trong phòng và gửi số lượng mới của phòng cho những người đang hoạt động còn lại.
