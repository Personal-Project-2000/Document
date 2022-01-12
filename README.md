<ul>
  <li><a href ="#number01">01/ Đăng ký</a></li>
  <li><a href ="#number02">02/ Đăng nhập</a></li>
  <li><a href ="#number03">03/ Tìm kiếm phòng</a></li>
  <li><a href ="#number04">04/ Xem thông tin cá nhân</a></li>
  <li><a href ="#number05">05/ Thay đổi thông tin cá nhân</a></li>
  <li><a href ="#number06">06/ Cài đặt</a></li>
  <li><a href ="#number07">07/ Tạo phòng</a></li>
  <li><a href ="#number08">08/ Tham gia phòng</a></li>
  <li><a href ="#number09">09/ Tìm kiếm bạn trong phòng</a></li>
  <li><a href ="#number10">10/ Cài đặt phòng</a></li>
  <li><a href ="#number11">11/ Đuổi</a></li>
  <li><a href ="#number12">12/ Xem lịch sử</a></li>
  <li><a href ="#number13">13/ Bầu chọn trưởng làng</a></li>
  <li><a href ="#number14">14/ Nhường trưởng làng</a></li>
  <li><a href ="#number15">15/ Bắt đầu và Sẳn sàng</a></li>
  <li><a href ="#number16">16/ Trò chơi</a></li>
  <li><a href ="#number17">17/ Viết chuyện</a></li>
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

Chia sẽ câu chuyện cho người khác đọc -> Bấm nút chia sẽ -> Chọn app chia sẽ

Tìm kiếm: Nhập hoặc dùng mic để điền từ khóa tìm kiếm là tên 1 người trong câu chuyện hay tên câu chuyện bạn đã đặt -> Api(SearchHistory) tìm kiếm truy tìm theo tên câu chuyên có không có thì tìm tên nhân vật, nếu có là trả dữ liệu gần giống với từ khóa, nếu không thì hiện thông báo "Câu chuyện tìm kiếm hiện không tồn tại".

<h1 id="number13"> Bầu chọn trưởng làng </h1>

Nếu có trên 7 người chơi thì Activity Vote trưởng làng được hiện ra -> Mỗi người chọn một người -> Gửi TK chọn lên RealTime -> RealTime sau khi nhận đủ số lượng phiếu hoặc hết thời gian thì bắt đầu tổng hợp người có phiếu cao nhất -> Trả về cho các người chơi, ai là được bầu sẽ hiện icon Trưởng Làng, mọi người còn lại sẽ thấy người đó trong danh sách có icon Trưởng Làng.

<h1 id="number14"> Nhường trưởng làng </h1>

Nếu trưởng làng bị chết thì hiện ra Activity chọn trưởng làng -> Gửi TK chọn lên RealTime -> RealTime trả về cho các người chơi, ai là được bầu sẽ hiện icon Trưởng Làng, mọi người còn lại sẽ thấy người đó trong danh sách có icon Trưởng Làng.

<h1 id="number15"> Bắt đầu và Sẳn sàng </h1>

Khi bấm sẵn sàng thì -> Api(Ready) cập nhật tình trạng sẳn sàng của người chơi vào bảng ROOMDETAIL -> gửi TK lên RealTime -> RealTime trả về những người chơi còn lại -> Máy của chủ phòng kiểm tra số lượng người sẵn sàng bằng số lượng người chơi thì hiện nút START.

khi bấm START -> Api(Start) cập nhật tình trạng phòng vào bảng ROOM -> Gửi lệnh bắt đầu lên RealTime -> Tùy thuộc vòa số lượng người chơi RealTime tự động phân chia bài cho mỗi người -> Gửi bài về cho mỗi người -> Máy của mỗi người chuyển qua Player Activity, nếu dữ liệu nhận về là phù thủy thì có 2 icon bình thuốc hiện lên.

<h1 id="number16"> Trò chơi </h5>

Chờ đợi 5s trước khi bắt đầu, để RealTime gữi mỗi người 1 lá bài.

Nếu bài là Sói, khi được gọi thì chọn 1 người trong danh sách không phải sói để giết hoặc bỏ qua, nếu chọn thì -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa TK về RealTime -> RealTime sẽ kiểm tra số người bị chết nhìu người muốn giết -> Lưu lại vào mảng những người vừa chết -> Gọi con bài tiếp theo.

Nếu bài là Sói Trắng, cứ 2 đêm sẽ được gọi riêng để giết 1 sói trong đám sói hoặc bỏ qua, nếu chọn thì -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa TK về RealTime -> RealTime thêm TK đó vào mảng người vừa chết.

Nếu bài là Tiên Tri, khi được gọi thì bạn 1 người trong danh sách hoặc bỏ qua, nếu chọn thì -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa TK về RealTime -> RealTime sẽ trả dữ liệu về, nếu đúng thì thông báo "Bạn đã đoán đúng", nếu sai thì thông báo "Bạn đã đoán sai" -> Gọi con bài tiếp theo.

Nếu bài là Thợ Săn, khi được gọi thì chọn 1 người trong danh sách để giết hoặc bỏ qua, nếu chọn thì -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa TK về RealTime -> RealTime lưu TK đó vào mảng những người vừa chết -> Gọi con bài tiếp theo.

Nếu bài là Cupid, Chọn 2 người trong danh sách -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa 2 TK về RealTime -> RealTime sẽ lưu 2 TK vào mảng tình yêu -> RealTime gửi dữ liệu về 2 TK -> Máy sẽ hiện icon trái tim -> Gọi con bài tiếp theo.

Nếu bài là Phù thủy -> Máy kiểm tra bình cứu đã dùng chưa, nếu chưa thì -> RealTime sẽ đưa danh sách người vừa chết về và hiện thông báo "Bạn có muốn cứu ai không" -> Bấm chọn 1 người hoặc bỏ qua, nếu chọn thì -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa TK về RealTime -> RealTime xóa TK ra khỏi mảng người vừa chết -> Máy kiểm tra bình giết đã dùng chưa, Nếu chưa thì -> Máy hiện thông báo "Bạn có muốn giết ai không" -> Bạn chọn 1 người trong danh sách hoặc bỏ qua, nếu chọn thì -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa TK về RealTime -> RealTime thêm TK vào mảng người vừa chết.

Nếu bài là Bảo vệ -> Chọn 1 người trong danh sách để bảo vệ -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Máy lưu lại tài khoản đã bảo vệ để đêm sau kh được bảo vệ tiếp, đưa TK về RealTime -> Nếu TK nằm trong danh sách mới chết thì xóa TK đó khỏi mảng.

Nếu bài là Thói Sáo -> Chọn 2 người trong danh sách -> Máy sẽ hiện lên thông báo "Bạn muốn chọn ...." -> Đưa 2 TK về RealTime -> RealTime thêm vào mảng thổi sáo -> RealTime gửi thông báo đến những người trong mảng -> Máy hiện icon cây sáo.

Nếu bài là nữa người, nữa sói -> Qua 1 đêm là bị sói cắn -> RealTime sửa dữ liệu TK thành sói.

Khi trời sáng, RealTime công bố những người trong danh sách mới bị chết -> RealTime thêm những TK này vào mảng đã chết, xóa dữ liệu mảng vừa chết

Khi mọi người chọn lựa người để treo cổ -> Đưa TK về RealTime -> Nếu thời gian đã hết hoặc mọi người đã chọn, RealTime tính người có nhìu phiếu nhất -> Trả TK đó về cho mọi người trong phòng

Người bị treo cổ biện hộ, những người còn lại đồng ý giết hay không -> Phiếu đưa về RealTime -> RealTime tính toán (bài Trưởng Làng sẽ tính là 2 phiếu) xem phiếu nào nhìu hơn, nếu đồng ý nhìu hơn thì TK đó vào mảng đã chết, còn không thì thông báo "... bạn được sống"

Nếu Trường Làng bị chết thì Trưởng Làng sẽ chọn 1 người trong danh sách sống để tiếp tục -> Đưu TK lên RealTime -> RealTime đưa về cho mọi người -> Máy được chọn sẽ hiện icon Trưởng Làng.

Nếu là Thợ Săn bị chết thì người là mà thợ săn đã bắn thì bị chết theo.

Nếu 1 trong 2 người đang yêu mà bị treo cổ thì đồng thời người lại cũng phải chết.

Đến buổi sáng nào RealTime tính toán số phiếu sói bằng dân làng gửi tất cả máy sói đã chiến thắng, nếu còn 2 người yêu thì hiện 2 TK chiến thắng, tất cả bị thôi niêm thì TK thổi sáo thắng, chỉ có sói chết hết thì dân làng chiến thắng.

<h1 id="number17"> Viết chuyện</h1>

Cupid (Chỉ đêm đầu tiên) -> 2 người yêu nhau (Chỉ đêm đầu tiên) -> Bảo vệ -> Sói -> Tiên Tri -> Phù Thủy -> Thổi sáo -> Những người bị thôi miên -> Già Làng (Chỉ đêm đầu tiên) -> Thợ Săn (Chỉ đêm đầu tiên).

Ở một ngôi làng nọ rất yêu bình, bỗng nhiên xuất hiện 1 bầy sói giả dân làng, cứ mỗi đêm chúng lại giết 1 dân làng.

Đêm đầu tiên

Hôm nay thần tình yêu(D) rất vui vẻ nên đã ban tình yêu tốt đẹp đến 2 bạn trẻ là F và H. Bắt đầu hoàng hôn buôn xuống anh Bảo Vệ(E) hôm nay bỗng dưng cảm thấy 1 điều bất an nên đã sang nhà chị D để bảo vệ chị, khi màn đêm vừa bầy sói(A, B, C) vào buổi sáng nhìn thấy chị D ngọt thịt qua vì thế đêm nay chúng đã quyết xơi chị D nhưng xui sao bọn sói lại không biết nên đã bị anh Bảo Vệ làm cho một trận, cùng lúc đó bà L đã dùng khả năng tiên đoán của bản thân mình chị D xem chị có phải là sói không, nhưng chị D không phải là sói và điều đó đã giúp bà L tin tưởng hơn vào chị D. Ông F dùng khả năng cảm nhận cảm thấy đêm nay không có người chết nên ông ta không dùng bình thuốc, nhưng ông ta lại nghi ngờ anh A là sói nên ông đã cho 1 bình thuốc độc vào nhà anh ấy.
