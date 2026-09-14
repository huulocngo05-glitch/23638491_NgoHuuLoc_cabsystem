# B11. TEST CASE

## 1. XÁC THỰC TÀI KHOẢN

### 1.1. Đăng nhập / Đăng xuất

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-AUTH-001 | Kiểm tra đăng nhập | Đăng nhập với thông tin hợp lệ | Người dùng đã có tài khoản hợp lệ và đang ở màn hình đăng nhập | 1. Mở màn hình đăng nhập.<br>2. Nhập tên đăng nhập.<br>3. Nhập mật khẩu.<br>4. Chọn **Đăng nhập**. | Tài khoản hợp lệ | Hệ thống xác thực thành công, xác định vai trò của người dùng và chuyển đến giao diện phù hợp với quyền được cấp. | High |
| TC-AUTH-002 | Kiểm tra đăng nhập | Đăng nhập với mật khẩu không hợp lệ | Tài khoản tồn tại trên hệ thống | 1. Nhập tên đăng nhập hợp lệ.<br>2. Nhập mật khẩu không đúng.<br>3. Chọn **Đăng nhập**. | Username hợp lệ<br>Password không hợp lệ | Hệ thống thông báo thông tin đăng nhập không chính xác và không cho phép truy cập vào hệ thống. | High |
| TC-AUTH-003 | Kiểm tra đăng nhập | Đăng nhập khi bỏ trống thông tin bắt buộc | Người dùng đang ở màn hình đăng nhập | 1. Để trống tên đăng nhập hoặc mật khẩu.<br>2. Chọn **Đăng nhập**. | Username: rỗng | Hệ thống thông báo trường bắt buộc và không thực hiện xác thực. | Medium |
| TC-AUTH-004 | Kiểm tra phân quyền sau đăng nhập | Người dùng chỉ truy cập chức năng thuộc quyền được cấp | Người dùng đã đăng nhập thành công | 1. Đăng nhập hệ thống.<br>2. Chọn chức năng không thuộc quyền được cấp. | Tài khoản không có quyền quản trị | Hệ thống từ chối truy cập chức năng không được cấp quyền. | High |
| TC-AUTH-005 | Kiểm tra đăng xuất | Đăng xuất sau khi đăng nhập thành công | Người dùng đã đăng nhập | 1. Chọn **Đăng xuất**.<br>2. Xác nhận đăng xuất. | Tài khoản đang đăng nhập | Hệ thống kết thúc phiên đăng nhập và chuyển người dùng về màn hình đăng nhập. | High |

---

# 2. KHÁCH HÀNG

## 2.1. Đăng ký tài khoản

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-CUS-REG-001 | Kiểm tra đăng ký tài khoản | Đăng ký với thông tin hợp lệ | Khách hàng chưa có tài khoản | 1. Chọn **Đăng ký tài khoản**.<br>2. Nhập đầy đủ thông tin yêu cầu.<br>3. Chọn **Đăng ký**. | Thông tin khách hàng hợp lệ | Hệ thống kiểm tra thông tin, tạo tài khoản khách hàng và lưu thông tin vào CSDL. | High |
| TC-CUS-REG-002 | Kiểm tra đăng ký tài khoản | Đăng ký khi thiếu thông tin bắt buộc | Khách hàng đang ở biểu mẫu đăng ký | 1. Bỏ trống một trường bắt buộc.<br>2. Chọn **Đăng ký**. | Một trường bắt buộc rỗng | Hệ thống thông báo thông tin chưa đầy đủ và không tạo tài khoản. | Medium |
| TC-CUS-REG-003 | Kiểm tra đăng ký tài khoản | Đăng ký với thông tin tài khoản đã tồn tại | Thông tin tài khoản đã tồn tại trong hệ thống | 1. Nhập thông tin đã tồn tại.<br>2. Chọn **Đăng ký**. | Thông tin tài khoản đã tồn tại | Hệ thống thông báo tài khoản đã tồn tại và không tạo tài khoản trùng lặp. | High |

---

## 2.2. Quản lý thông tin cá nhân

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-CUS-PRO-001 | Kiểm tra thông tin cá nhân | Hiển thị thông tin cá nhân | Khách hàng đã đăng nhập | 1. Chọn **Quản lý thông tin cá nhân**. | Tài khoản khách hàng hợp lệ | Hệ thống hiển thị thông tin cá nhân hiện tại của khách hàng. | High |
| TC-CUS-PRO-002 | Kiểm tra thông tin cá nhân | Cập nhật thông tin cá nhân hợp lệ | Khách hàng đã đăng nhập | 1. Chọn **Cập nhật**.<br>2. Thay đổi thông tin.<br>3. Chọn **Lưu**. | Thông tin cá nhân hợp lệ | Hệ thống kiểm tra dữ liệu, cập nhật thông tin mới và lưu vào CSDL. | High |
| TC-CUS-PRO-003 | Kiểm tra thông tin cá nhân | Cập nhật với dữ liệu không hợp lệ | Khách hàng đang ở biểu mẫu cập nhật | 1. Nhập dữ liệu không hợp lệ.<br>2. Chọn **Lưu**. | Dữ liệu sai định dạng | Hệ thống thông báo lỗi, không lưu dữ liệu không hợp lệ và yêu cầu khách hàng nhập lại. | Medium |

---

## 2.3. Đặt xe

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-CUS-BOOK-001 | Kiểm tra đặt xe | Tạo yêu cầu đặt xe với thông tin hợp lệ | Khách hàng đã đăng nhập | 1. Chọn **Đặt xe**.<br>2. Nhập điểm đón.<br>3. Nhập điểm đến.<br>4. Chọn loại xe/dịch vụ.<br>5. Gửi yêu cầu đặt xe. | Điểm đón: hợp lệ<br>Điểm đến: hợp lệ<br>Loại xe: hợp lệ | Hệ thống tiếp nhận yêu cầu, tạo yêu cầu đặt xe và lưu thông tin vào CSDL. | High |
| TC-CUS-BOOK-002 | Kiểm tra đặt xe | Đặt xe khi thiếu điểm đón | Khách hàng đã đăng nhập và đang ở màn hình đặt xe | 1. Bỏ trống điểm đón.<br>2. Nhập điểm đến.<br>3. Chọn loại xe.<br>4. Gửi yêu cầu. | Điểm đón: rỗng | Hệ thống thông báo thiếu thông tin điểm đón và không tạo yêu cầu đặt xe. | High |
| TC-CUS-BOOK-003 | Kiểm tra đặt xe | Đặt xe khi thiếu điểm đến | Khách hàng đã đăng nhập và đang ở màn hình đặt xe | 1. Nhập điểm đón.<br>2. Bỏ trống điểm đến.<br>3. Chọn loại xe.<br>4. Gửi yêu cầu. | Điểm đến: rỗng | Hệ thống thông báo thiếu thông tin điểm đến và không tạo yêu cầu đặt xe. | High |
| TC-CUS-BOOK-004 | Kiểm tra đặt xe | Đặt xe với loại xe/dịch vụ hợp lệ | Khách hàng đã đăng nhập | 1. Nhập điểm đón và điểm đến.<br>2. Chọn loại xe/dịch vụ.<br>3. Gửi yêu cầu. | Điểm đón, điểm đến hợp lệ<br>Loại xe/dịch vụ hợp lệ | Hệ thống ghi nhận đúng loại xe/dịch vụ được khách hàng lựa chọn và tạo yêu cầu đặt xe. | High |
| TC-CUS-BOOK-005 | Kiểm tra thông báo đặt xe | Thông báo khi yêu cầu đặt xe được tiếp nhận | Khách hàng đã gửi yêu cầu đặt xe hợp lệ | 1. Gửi yêu cầu đặt xe.<br>2. Chờ hệ thống xử lý yêu cầu. | Yêu cầu đặt xe hợp lệ | Hệ thống gửi thông báo cho khách hàng về việc yêu cầu đặt xe đã được tiếp nhận. | Medium |

---

## 2.4. Theo dõi chuyến đi

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-CUS-TRK-001 | Kiểm tra theo dõi chuyến đi | Xem trạng thái hiện tại của chuyến | Khách hàng đã đăng nhập và có chuyến đang thực hiện | 1. Chọn **Theo dõi chuyến đi**.<br>2. Chọn chuyến đang thực hiện. | Mã chuyến hợp lệ | Hệ thống hiển thị trạng thái hiện tại của chuyến xe. | High |
| TC-CUS-TRK-002 | Kiểm tra theo dõi chuyến đi | Xem thông tin tài xế đã nhận chuyến | Chuyến xe đã được phân công tài xế | 1. Mở thông tin chuyến.<br>2. Xem thông tin tài xế. | Chuyến đã có tài xế | Hệ thống hiển thị thông tin tài xế đã nhận chuyến. | High |
| TC-CUS-TRK-003 | Kiểm tra theo dõi chuyến đi | Xem vị trí hiện tại của tài xế | Chuyến đã được phân công và hệ thống có dữ liệu vị trí | 1. Mở chức năng theo dõi chuyến.<br>2. Xem vị trí tài xế. | Chuyến đang thực hiện | Hệ thống cung cấp vị trí hiện tại của tài xế cho chuyến đang theo dõi. | High |
| TC-CUS-TRK-004 | Kiểm tra theo dõi chuyến đi | Xem thời gian dự kiến tài xế đến | Chuyến đã được phân công tài xế | 1. Mở thông tin chuyến.<br>2. Xem thời gian dự kiến đến. | Chuyến có tài xế | Hệ thống hiển thị thời gian dự kiến tài xế đến theo dữ liệu hệ thống cung cấp. | Medium |
| TC-CUS-TRK-005 | Kiểm tra lịch sử chuyến đi | Xem lịch sử chuyến của tài khoản | Khách hàng đã đăng nhập và có dữ liệu chuyến | 1. Chọn **Theo dõi chuyến đi**.<br>2. Chọn lịch sử chuyến. | Tài khoản có lịch sử chuyến | Hệ thống hiển thị các chuyến thuộc tài khoản khách hàng. | Medium |

---

## 2.5. Thanh toán

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-CUS-PAY-001 | Kiểm tra thanh toán | Hiển thị số tiền cần thanh toán | Chuyến xe đã hoàn thành và hệ thống đã xác định cước | 1. Mở thông tin thanh toán của chuyến. | Chuyến đã hoàn thành | Hệ thống hiển thị số tiền khách hàng phải thanh toán. | High |
| TC-CUS-PAY-002 | Kiểm tra thanh toán tiền mặt | Thanh toán bằng tiền mặt | Chuyến xe đã hoàn thành và có số tiền cần thanh toán | 1. Chọn **Thanh toán**.<br>2. Chọn **Tiền mặt**.<br>3. Xác nhận thanh toán. | Phương thức: Tiền mặt | Hệ thống ghi nhận phương thức thanh toán là tiền mặt và cập nhật kết quả giao dịch. | High |
| TC-CUS-PAY-003 | Kiểm tra thanh toán điện tử | Thanh toán bằng phương thức điện tử | Chuyến xe đã hoàn thành và có số tiền cần thanh toán | 1. Chọn **Thanh toán**.<br>2. Chọn phương thức thanh toán điện tử.<br>3. Thực hiện thanh toán. | Phương thức: Điện tử | Hệ thống gửi yêu cầu thanh toán đến nhà cung cấp, nhận kết quả và lưu giao dịch. | High |
| TC-CUS-PAY-004 | Kiểm tra thanh toán điện tử | Thanh toán điện tử thất bại | Có giao dịch thanh toán điện tử đang được thực hiện | 1. Chọn phương thức thanh toán điện tử.<br>2. Thực hiện thanh toán.<br>3. Nhà cung cấp trả kết quả thất bại. | Giao dịch: Thất bại | Hệ thống ghi nhận giao dịch thất bại và thông báo kết quả cho khách hàng. | High |
| TC-CUS-PAY-005 | Kiểm tra kết quả thanh toán | Hiển thị kết quả thanh toán | Giao dịch đã được xử lý | 1. Hoàn tất thanh toán.<br>2. Xem kết quả giao dịch. | Giao dịch thành công/thất bại | Hệ thống hiển thị đúng kết quả thanh toán và lưu thông tin giao dịch. | High |

---

# 3. TÀI XẾ

## 3.1. Quản lý thông tin cá nhân

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-DRV-PRO-001 | Kiểm tra thông tin cá nhân | Hiển thị thông tin cá nhân | Tài xế đã đăng nhập | 1. Chọn **Quản lý thông tin cá nhân**. | Tài khoản tài xế hợp lệ | Hệ thống hiển thị thông tin cá nhân hiện tại của tài xế. | High |
| TC-DRV-PRO-002 | Kiểm tra thông tin cá nhân | Cập nhật thông tin cá nhân hợp lệ | Tài xế đã đăng nhập | 1. Chọn **Cập nhật**.<br>2. Thay đổi thông tin.<br>3. Chọn **Lưu**. | Thông tin hợp lệ | Hệ thống cập nhật thông tin mới và lưu vào CSDL. | High |
| TC-DRV-PRO-003 | Kiểm tra thông tin cá nhân | Cập nhật thông tin không hợp lệ | Tài xế đang ở biểu mẫu cập nhật | 1. Nhập dữ liệu không hợp lệ.<br>2. Chọn **Lưu**. | Dữ liệu không hợp lệ | Hệ thống thông báo lỗi và không lưu thông tin không hợp lệ. | Medium |

---

## 3.2. Cập nhật trạng thái làm việc

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-DRV-STS-001 | Kiểm tra trạng thái làm việc | Chuyển tài xế sang trạng thái Available | Tài xế đã đăng nhập và không thực hiện chuyến | 1. Chọn **Cập nhật trạng thái làm việc**.<br>2. Chọn **Available**.<br>3. Xác nhận. | Trạng thái: Available | Hệ thống cập nhật tài xế sang trạng thái Available và lưu trạng thái vào CSDL. | High |
| TC-DRV-STS-002 | Kiểm tra trạng thái làm việc | Chuyển tài xế sang trạng thái không sẵn sàng | Tài xế đã đăng nhập và không thực hiện chuyến | 1. Chọn **Cập nhật trạng thái làm việc**.<br>2. Chọn trạng thái không sẵn sàng.<br>3. Xác nhận. | Trạng thái: Không sẵn sàng | Hệ thống cập nhật trạng thái làm việc mới và tài xế không được xem xét phân công chuyến mới. | High |
| TC-DRV-STS-003 | Kiểm tra trạng thái làm việc | Không cho tài xế chuyển sang Available khi đang thực hiện chuyến | Tài xế đang ở trạng thái On Trip | 1. Chọn cập nhật trạng thái.<br>2. Chọn Available.<br>3. Xác nhận. | Current: On Trip<br>New: Available | Hệ thống từ chối cập nhật vì tài xế đang thực hiện chuyến xe. | High |

---

## 3.3. Tiếp nhận chuyến xe

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-DRV-TRP-001 | Kiểm tra tiếp nhận chuyến | Tài xế nhận yêu cầu chuyến phù hợp | Tài xế đang Available và có yêu cầu chuyến phù hợp | 1. Nhận thông báo chuyến mới.<br>2. Xem thông tin chuyến.<br>3. Chọn **Chấp nhận**. | Chuyến phù hợp với tài xế | Hệ thống gán tài xế cho chuyến và chuyển trạng thái tài xế sang On Trip. | High |
| TC-DRV-TRP-002 | Kiểm tra tiếp nhận chuyến | Tài xế từ chối chuyến | Tài xế đang Available và nhận được yêu cầu chuyến | 1. Mở yêu cầu chuyến.<br>2. Chọn **Từ chối**.<br>3. Xác nhận. | Yêu cầu chuyến hợp lệ | Hệ thống ghi nhận tài xế từ chối và tiếp tục tìm tài xế Available khác. | High |
| TC-DRV-TRP-003 | Kiểm tra tiếp nhận chuyến | Tài xế không phản hồi yêu cầu chuyến | Tài xế Available đã nhận thông báo chuyến | 1. Không phản hồi yêu cầu trong thời gian quy định. | Yêu cầu chuyến hợp lệ | Hệ thống xác định tài xế không phản hồi và tiếp tục tìm tài xế Available khác. | High |
| TC-DRV-TRP-004 | Kiểm tra tiếp nhận chuyến | Không cho tài xế không Available nhận chuyến mới | Tài xế đang ở trạng thái không sẵn sàng | 1. Nhận yêu cầu chuyến.<br>2. Thực hiện chấp nhận chuyến. | Driver Status: Không Available | Hệ thống không phân công chuyến cho tài xế không ở trạng thái Available. | High |
| TC-DRV-TRP-005 | Kiểm tra phân công | Không tìm được tài xế phù hợp | Khách hàng đã gửi yêu cầu đặt xe nhưng không có tài xế Available phù hợp | 1. Gửi yêu cầu đặt xe.<br>2. Hệ thống thực hiện tìm tài xế. | Không có tài xế phù hợp | Hệ thống không phân công chuyến và thông báo cho khách hàng không tìm được tài xế phù hợp. | High |

---

## 3.4. Cập nhật trạng thái chuyến xe

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-DRV-TRPSTS-001 | Kiểm tra trạng thái chuyến | Cập nhật sang Đã đến điểm đón | Tài xế đã nhận chuyến | 1. Mở chuyến đang thực hiện.<br>2. Chọn **Đã đến điểm đón**.<br>3. Xác nhận. | Trạng thái mới: Đã đến điểm đón | Hệ thống cập nhật trạng thái chuyến thành Đã đến điểm đón. | High |
| TC-DRV-TRPSTS-002 | Kiểm tra trạng thái chuyến | Cập nhật sang Đã đón khách | Chuyến đang ở trạng thái Đã đến điểm đón | 1. Chọn **Đã đón khách**.<br>2. Xác nhận. | Current: Đã đến điểm đón<br>New: Đã đón khách | Hệ thống cập nhật trạng thái chuyến thành Đã đón khách. | High |
| TC-DRV-TRPSTS-003 | Kiểm tra trạng thái chuyến | Cập nhật sang Đang di chuyển | Chuyến đang ở trạng thái Đã đón khách | 1. Chọn **Đang di chuyển**.<br>2. Xác nhận. | Current: Đã đón khách<br>New: Đang di chuyển | Hệ thống cập nhật trạng thái chuyến thành Đang di chuyển. | High |
| TC-DRV-TRPSTS-004 | Kiểm tra trạng thái chuyến | Cập nhật sang Hoàn thành | Chuyến đang ở trạng thái Đang di chuyển | 1. Chọn **Hoàn thành**.<br>2. Xác nhận. | Current: Đang di chuyển<br>New: Hoàn thành | Hệ thống cập nhật chuyến thành Hoàn thành, làm cơ sở cho bước tính cước và thanh toán. | High |
| TC-DRV-TRPSTS-005 | Kiểm tra quy tắc trạng thái | Cập nhật trạng thái không đúng trình tự | Tài xế đang thực hiện chuyến | 1. Chọn một trạng thái không phù hợp với trạng thái hiện tại.<br>2. Xác nhận. | Ví dụ: Current = Đã đến điểm đón<br>New = Hoàn thành | Hệ thống từ chối cập nhật và thông báo trạng thái không hợp lệ. | High |

---

# 4. NHÂN VIÊN VẬN HÀNH

## 4.1. Quản lý khách hàng

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-OPS-CUS-001 | Kiểm tra quản lý khách hàng | Hiển thị danh sách khách hàng | Nhân viên vận hành đã đăng nhập và có quyền quản lý khách hàng | 1. Chọn **Quản lý khách hàng**. | Không có | Hệ thống hiển thị danh sách khách hàng và thông tin cần thiết để quản lý khách hàng. | High |
| TC-OPS-CUS-002 | Kiểm tra quản lý khách hàng | Xem thông tin khách hàng | Danh sách khách hàng đang được hiển thị | 1. Chọn một khách hàng trong danh sách. | Khách hàng tồn tại | Hệ thống hiển thị thông tin của khách hàng được chọn. | Medium |
| TC-OPS-CUS-003 | Kiểm tra quản lý khách hàng | Cập nhật thông tin khách hàng | Khách hàng đã tồn tại | 1. Chọn khách hàng.<br>2. Chọn **Cập nhật**.<br>3. Chỉnh sửa thông tin.<br>4. Chọn **Lưu**. | Thông tin mới hợp lệ | Hệ thống kiểm tra và cập nhật thông tin khách hàng vào CSDL. | High |

---

## 4.2. Quản lý tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-OPS-DRV-001 | Kiểm tra quản lý tài xế | Hiển thị danh sách tài xế | Nhân viên vận hành đã đăng nhập và có quyền quản lý tài xế | 1. Chọn **Quản lý tài xế**. | Không có | Hệ thống hiển thị danh sách tài xế và trạng thái làm việc của từng tài xế. | High |
| TC-OPS-DRV-002 | Kiểm tra quản lý tài xế | Xem thông tin tài xế | Danh sách tài xế đang hiển thị | 1. Chọn một tài xế. | Tài xế tồn tại | Hệ thống hiển thị thông tin của tài xế được chọn. | Medium |
| TC-OPS-DRV-003 | Kiểm tra quản lý tài xế | Tạo tài khoản cho tài xế | Nhân viên vận hành đã đăng nhập và có quyền quản lý tài xế | 1. Chọn chức năng tạo tài khoản tài xế.<br>2. Nhập thông tin tài xế.<br>3. Xác nhận tạo. | Thông tin tài xế hợp lệ | Hệ thống tạo tài khoản cho tài xế và lưu thông tin vào CSDL. | High |
| TC-OPS-DRV-004 | Kiểm tra quản lý tài xế | Cập nhật thông tin tài xế | Tài xế đã tồn tại | 1. Chọn tài xế.<br>2. Chọn **Cập nhật**.<br>3. Thay đổi thông tin.<br>4. Chọn **Lưu**. | Thông tin mới hợp lệ | Hệ thống cập nhật thông tin tài xế và lưu vào CSDL. | High |

---

## 4.3. Quản lý phương tiện

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-OPS-VEH-001 | Kiểm tra quản lý phương tiện | Hiển thị danh sách phương tiện | Nhân viên vận hành đã đăng nhập và có quyền quản lý phương tiện | 1. Chọn **Quản lý phương tiện**. | Không có | Hệ thống hiển thị danh sách phương tiện phục vụ công tác quản lý. | High |
| TC-OPS-VEH-002 | Kiểm tra quản lý phương tiện | Thêm phương tiện hợp lệ | Nhân viên vận hành có quyền quản lý phương tiện | 1. Chọn **Thêm phương tiện**.<br>2. Nhập thông tin phương tiện.<br>3. Chọn **Lưu**. | Thông tin phương tiện hợp lệ | Hệ thống kiểm tra dữ liệu và lưu phương tiện vào CSDL. | High |
| TC-OPS-VEH-003 | Kiểm tra quản lý phương tiện | Cập nhật thông tin phương tiện | Phương tiện đã tồn tại | 1. Chọn phương tiện.<br>2. Chọn **Cập nhật**.<br>3. Thay đổi thông tin.<br>4. Chọn **Lưu**. | Thông tin phương tiện mới hợp lệ | Hệ thống cập nhật thông tin phương tiện và lưu vào CSDL. | High |
| TC-OPS-VEH-004 | Kiểm tra quản lý phương tiện | Nhập thông tin phương tiện không hợp lệ | Nhân viên đang ở biểu mẫu phương tiện | 1. Nhập dữ liệu không hợp lệ.<br>2. Chọn **Lưu**. | Dữ liệu phương tiện không hợp lệ | Hệ thống thông báo lỗi và không lưu dữ liệu không hợp lệ. | Medium |

---

## 4.4. Giám sát chuyến xe

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-OPS-MON-001 | Kiểm tra giám sát chuyến | Hiển thị danh sách chuyến đang diễn ra | Nhân viên vận hành đã đăng nhập | 1. Chọn **Giám sát chuyến xe**. | Không có | Hệ thống hiển thị danh sách các chuyến đang diễn ra và trạng thái hiện tại của từng chuyến. | High |
| TC-OPS-MON-002 | Kiểm tra giám sát chuyến | Xem trạng thái tài xế | Có tài xế đang hoạt động trên hệ thống | 1. Mở chức năng giám sát.<br>2. Xem trạng thái tài xế. | Tài xế Available/On Trip | Hệ thống hiển thị trạng thái làm việc hiện tại của tài xế. | High |
| TC-OPS-MON-003 | Kiểm tra giám sát chuyến | Theo dõi thay đổi trạng thái chuyến | Có chuyến đang diễn ra | 1. Mở danh sách chuyến.<br>2. Theo dõi một chuyến.<br>3. Tài xế cập nhật trạng thái. | Chuyến đang thực hiện | Hệ thống cập nhật trạng thái chuyến trên giao diện giám sát theo dữ liệu mới. | High |
| TC-OPS-MON-004 | Kiểm tra giám sát chuyến | Không có chuyến đang diễn ra | Không có chuyến đang thực hiện | 1. Chọn **Giám sát chuyến xe**. | Không có chuyến hoạt động | Hệ thống thông báo không có chuyến đang diễn ra. | Medium |

---

## 4.5. Tra cứu chuyến xe và giao dịch

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-OPS-LOOK-001 | Kiểm tra tra cứu chuyến xe | Tra cứu chuyến xe theo thông tin hợp lệ | Nhân viên vận hành đã đăng nhập và có quyền tra cứu | 1. Chọn **Tra cứu chuyến xe và giao dịch**.<br>2. Nhập điều kiện tra cứu.<br>3. Chọn **Tra cứu**. | Thông tin chuyến hợp lệ | Hệ thống hiển thị các chuyến xe phù hợp với điều kiện tra cứu. | High |
| TC-OPS-LOOK-002 | Kiểm tra tra cứu giao dịch | Tra cứu giao dịch thanh toán | Có dữ liệu giao dịch trong hệ thống | 1. Chọn chức năng tra cứu.<br>2. Nhập điều kiện tra cứu giao dịch.<br>3. Chọn **Tra cứu**. | Điều kiện giao dịch hợp lệ | Hệ thống hiển thị các giao dịch phù hợp với điều kiện tra cứu. | High |
| TC-OPS-LOOK-003 | Kiểm tra tra cứu | Không tìm thấy dữ liệu phù hợp | Nhân viên đã nhập điều kiện tra cứu | 1. Nhập điều kiện không có dữ liệu.<br>2. Chọn **Tra cứu**. | Điều kiện không có kết quả | Hệ thống thông báo không tìm thấy dữ liệu phù hợp. | Medium |

---

## 4.6. Xem báo cáo và thống kê

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-OPS-REP-001 | Kiểm tra báo cáo | Hiển thị báo cáo doanh thu | Nhân viên vận hành đã đăng nhập và có quyền xem báo cáo | 1. Chọn **Xem báo cáo và thống kê**.<br>2. Chọn báo cáo doanh thu. | Khoảng thời gian hợp lệ | Hệ thống hiển thị báo cáo doanh thu theo dữ liệu đã ghi nhận. | High |
| TC-OPS-REP-002 | Kiểm tra báo cáo | Xem thống kê số lượng chuyến | Có dữ liệu chuyến xe | 1. Chọn **Xem báo cáo và thống kê**.<br>2. Chọn thống kê số chuyến. | Khoảng thời gian hợp lệ | Hệ thống hiển thị số lượng chuyến tương ứng với dữ liệu trong hệ thống. | High |
| TC-OPS-REP-003 | Kiểm tra báo cáo | Xem tỷ lệ hoàn thành/hủy chuyến | Có dữ liệu chuyến xe với các trạng thái khác nhau | 1. Chọn báo cáo thống kê.<br>2. Chọn thống kê tỷ lệ hoàn thành/hủy. | Dữ liệu chuyến xe | Hệ thống tính toán và hiển thị tỷ lệ hoàn thành/hủy dựa trên dữ liệu thực tế. | Medium |
| TC-OPS-REP-004 | Kiểm tra báo cáo | Xem hiệu quả tài xế | Có dữ liệu hoạt động của tài xế | 1. Chọn báo cáo thống kê.<br>2. Chọn thống kê hiệu quả tài xế. | Dữ liệu tài xế/chuyến | Hệ thống hiển thị thông tin thống kê phục vụ đánh giá hiệu quả tài xế. | Medium |

---

# 5. QUẢN TRỊ VIÊN HỆ THỐNG

## 5.1. Quản lý tài khoản

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-ADM-ACC-001 | Kiểm tra quản lý tài khoản | Hiển thị danh sách tài khoản | Quản trị viên đã đăng nhập và có quyền quản lý tài khoản | 1. Chọn **Quản lý tài khoản**. | Không có | Hệ thống hiển thị danh sách tài khoản và các thông tin phục vụ quản lý tài khoản. | High |
| TC-ADM-ACC-002 | Kiểm tra quản lý tài khoản | Xem thông tin tài khoản | Danh sách tài khoản đang hiển thị | 1. Chọn một tài khoản. | Tài khoản tồn tại | Hệ thống hiển thị thông tin của tài khoản được chọn. | Medium |
| TC-ADM-ACC-003 | Kiểm tra quản lý tài khoản | Cập nhật tài khoản hợp lệ | Tài khoản cần cập nhật đã tồn tại | 1. Chọn tài khoản.<br>2. Chọn **Cập nhật**.<br>3. Thay đổi thông tin.<br>4. Chọn **Lưu**. | Dữ liệu hợp lệ | Hệ thống kiểm tra và cập nhật thông tin tài khoản vào CSDL. | High |
| TC-ADM-ACC-004 | Kiểm tra quản lý tài khoản | Cập nhật tài khoản với dữ liệu không hợp lệ | Quản trị viên đang cập nhật tài khoản | 1. Nhập dữ liệu không hợp lệ.<br>2. Chọn **Lưu**. | Dữ liệu không hợp lệ | Hệ thống thông báo lỗi và không lưu thay đổi. | Medium |

---

## 5.2. Phân quyền người dùng

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-ADM-ROLE-001 | Kiểm tra phân quyền | Hiển thị quyền hiện tại của tài khoản | Quản trị viên đã đăng nhập và tài khoản cần phân quyền tồn tại | 1. Chọn **Phân quyền người dùng**.<br>2. Chọn tài khoản. | Tài khoản hợp lệ | Hệ thống hiển thị vai trò và quyền hiện tại của tài khoản. | High |
| TC-ADM-ROLE-002 | Kiểm tra phân quyền | Cấp quyền cho người dùng | Tài khoản tồn tại và quản trị viên có quyền phân quyền | 1. Chọn tài khoản.<br>2. Chọn quyền cần cấp.<br>3. Xác nhận. | Tài khoản hợp lệ<br>Quyền hợp lệ | Hệ thống cập nhật quyền cho tài khoản và lưu thay đổi vào CSDL. | High |
| TC-ADM-ROLE-003 | Kiểm tra phân quyền | Thay đổi quyền người dùng | Tài khoản đã được cấp quyền | 1. Chọn tài khoản.<br>2. Thay đổi quyền.<br>3. Xác nhận. | Quyền mới hợp lệ | Hệ thống cập nhật quyền mới và người dùng chỉ được truy cập chức năng theo quyền mới. | High |
| TC-ADM-ROLE-004 | Kiểm tra phân quyền | Người dùng không thể truy cập chức năng ngoài quyền | Người dùng đã được phân quyền giới hạn | 1. Đăng nhập bằng tài khoản được phân quyền.<br>2. Truy cập chức năng ngoài quyền. | Tài khoản bị giới hạn quyền | Hệ thống từ chối truy cập và bảo đảm kiểm soát quyền truy cập. | High |

---

## 5.3. Cấu hình hệ thống

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-ADM-CON-001 | Kiểm tra cấu hình hệ thống | Hiển thị thông tin cấu hình | Quản trị viên đã đăng nhập và có quyền cấu hình | 1. Chọn **Cấu hình hệ thống**. | Không có | Hệ thống hiển thị các cấu hình hiện tại của hệ thống. | Medium |
| TC-ADM-CON-002 | Kiểm tra cấu hình hệ thống | Cập nhật cấu hình hợp lệ | Quản trị viên có quyền cấu hình | 1. Chọn cấu hình cần thay đổi.<br>2. Nhập giá trị mới.<br>3. Chọn **Lưu**. | Giá trị cấu hình hợp lệ | Hệ thống kiểm tra, lưu cấu hình mới và áp dụng cấu hình theo quy định. | High |
| TC-ADM-CON-003 | Kiểm tra cấu hình hệ thống | Cập nhật cấu hình không hợp lệ | Quản trị viên đang chỉnh sửa cấu hình | 1. Nhập giá trị không hợp lệ.<br>2. Chọn **Lưu**. | Giá trị không hợp lệ | Hệ thống thông báo lỗi và không lưu cấu hình không hợp lệ. | Medium |

---

## 5.4. Xem nhật ký hệ thống

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-ADM-LOG-001 | Kiểm tra nhật ký hệ thống | Hiển thị danh sách nhật ký | Quản trị viên đã đăng nhập và có quyền xem nhật ký | 1. Chọn **Xem nhật ký hệ thống**. | Không có | Hệ thống hiển thị các thao tác quan trọng đã được ghi nhận trong nhật ký. | High |
| TC-ADM-LOG-002 | Kiểm tra nhật ký hệ thống | Kiểm tra nhật ký sau thao tác quan trọng | Có thực hiện một thao tác quan trọng trên hệ thống | 1. Thực hiện thao tác quan trọng.<br>2. Mở **Xem nhật ký hệ thống**.<br>3. Tìm bản ghi tương ứng. | Thao tác quản trị hợp lệ | Hệ thống có bản ghi thể hiện thao tác đã thực hiện, phục vụ kiểm tra và xử lý sự cố. | High |
| TC-ADM-LOG-003 | Kiểm tra nhật ký hệ thống | Tra cứu nhật ký theo điều kiện | Nhật ký hệ thống có dữ liệu | 1. Chọn điều kiện tra cứu.<br>2. Nhập điều kiện.<br>3. Chọn **Tra cứu**. | Điều kiện tra cứu hợp lệ | Hệ thống hiển thị các bản ghi nhật ký phù hợp với điều kiện. | Medium |
| TC-ADM-LOG-004 | Kiểm tra nhật ký hệ thống | Tra cứu nhật ký không có kết quả | Nhật ký hệ thống đang hoạt động | 1. Nhập điều kiện không có dữ liệu.<br>2. Chọn **Tra cứu**. | Điều kiện không có kết quả | Hệ thống thông báo không tìm thấy bản ghi phù hợp. | Low |
