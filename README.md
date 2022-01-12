<ul>
  <li><a href ="#number01">Đăng ký</a></li>
  <li><a href ="#number02">Đăng nhập</a></li>
  <li><a href ="#number03">Tìm kiếm phòng</a></li>
  <li><a href ="#number04">Xem thông tin cá nhân</a></li>
  <li><a href ="#number05">Thay đổi thông tin cá nhân</a></li>
  <li><a href ="#number06">Cài đặt</a></li>
  <li><a href ="#number07">Tạo phòng</a></li>
  <li><a href ="#number08">Tham gia phòng</a></li>
  <li><a href ="#number09">Tìm kiếm bạn trong phòng</a></li>
  <li><a href ="#number10">Cài đặt phòng</a></li>
  <li><a href ="#number11">Đuổi</a></li>
  <li><a href ="#number12">Xem lịch sử</a></li>
  <li><a href ="#number13">Bầu chọn trưởng làng</a></li>
  <li><a href ="#number14">Nhường trưởng làng</a></li>
  <li><a href ="#number15">Bắt đầu và Sẳn sàng</a></li>
  <li><a href ="#number16">Cài đặt phòng</a></li>
  <li><a href ="#number17">Cài đặt phòng</a></li>
  <li><a href ="#number18">Cài đặt phòng</a></li>
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

Khi vào phòng -> Api(GetRoom) cập nhật thêm SL vào bảng ROOM và thêm dữ liệu vào bảng ROOMDETAIL và bao gồm thông tin bảng ROOM (PASS, TIME_VOTE, TIME_ADVOCATE) và danh sách người(NAME, IMG, BOSS) đã tham gia phòng trước -> Gửi TK lên RealTime -> RealTime gửi UserId cho những người đã có trong phòng và gửi số lượng mới của phòng cho những người đang hoạt động còn lại.

<h1 id="number09"> Tìm kiếm bạn trong phòng </h1>

Nhập tên muốn tìm kiếm vào khung tìm kiếm -> Máy tìm kiếm những tên gần giống với từ khóa

<h1 id="number10"> Cài đặt phòng </h1>

Bấm vào biểu tượng ☰ -> Chọn cài đặt -> Thay đổi mật khẩu, nếu không muốn mật khẩu thì để trống, thay đổi thời gian bầu chọn, thời gian biện hộ -> Bấm nút lưu -> Api(UpdateRoom) cập nhật lại bảng ROOM -> Gửi pass, thời gian bầu chọn, thời gian biện hộ lên RealTime -> RealTime gửi lại tất cả người đang trong phòng.

<h1 id="number11"> Đuổi </h1>

Bấm vào biểu tượng ☰ -> Chọn kick -> Máy cho hiện danh sách tất cả người đang trong phòng -> Bấm kick vào ai thì -> Api(DelPlayer) xóa dữ liệu người đó ra khỏi ROOMDETAIL

<h1 id="number12"> Xem lịch sử </h1>

Bấm vào biểu tượng ☰ ở MainActivity -> Chọn lịch sử -> Api(GetHistoryList) lấy dữ liệu  (HISTORYID, SL, TIME)

Muốn xem chi tiết lịch sử -> Bấm vào lịch sử muốn xem -> Api(GetHistory) láy dữ liệu (START_TIME, END_TIME, STORYES[START_TIME, END_TIME, CONTENT]) và danh sách người đã chơi (TÊN, HÌNH, BAI, WIN)

<h1 id="number13"> Bầu chọn trưởng làng </h1>

Nếu có trên 7 người chơi thì Activity Vote trưởng làng được hiện ra -> Mỗi người chọn một người -> Gửi TK chọn lên RealTime -> RealTime sau khi nhận đủ số lượng phiếu hoặc hết thời gian thì bắt đầu tổng hợp người có phiếu cao nhất -> Trả về cho các người chơi, ai là được bầu sẽ hiện icon Trưởng Làng, mọi người còn lại sẽ thấy người đó trong danh sách có icon Trưởng Làng.

<h1 id="number14"> Nhường trưởng làng </h1>

Nếu trưởng làng bị chết thì hiện ra Activity chọn trưởng làng -> Gửi TK chọn lên RealTime -> RealTime trả về cho các người chơi, ai là được bầu sẽ hiện icon Trưởng Làng, mọi người còn lại sẽ thấy người đó trong danh sách có icon Trưởng Làng.

<h1 id="number15"> Bắt đầu và Sẳn sàng </h1>

Khi bấm sẵn sàng thì -> Api(Ready) cập nhật tình trạng sẳn sàng của người chơi vào bảng ROOMDETAIL -> gửi TK lên RealTime -> RealTime trả về những người chơi còn lại -> Máy của chủ phòng kiểm tra số lượng người sẵn sàng bằng số lượng người chơi thì hiện nút START.

khi bấm START -> Api(Start) cập nhật tình trạng phòng vào bảng ROOM -> Gửi lệnh bắt đầu lên RealTime -> Tùy thuộc vòa số lượng người chơi RealTime tự động phân chia bài cho mỗi người -> Gửi bài về cho mỗi người -> Máy của m0ỗi người chuyển qua Player Activity, nếu dữ liệu nhận về là phù thủy thì có 2 icon bình thuốc hiện lên.
