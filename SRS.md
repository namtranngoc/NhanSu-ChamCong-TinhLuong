# SOFTWARE REQUIREMENTS SPECIFICATION (SRS)

## Hệ thống quản lý nhân sự, chấm công và tính lương

**Phiên bản:** 1.0  
**Ngày:** 2026-10-03  
**Trạng thái:** Draft

---

# 1. GIỚI THIỆU

## 1.1. Mục đích

Tài liệu Software Requirements Specification (SRS) mô tả các yêu cầu chức năng và phi chức năng của hệ thống quản lý nhân sự, chấm công và tính lương.

Tài liệu được sử dụng làm cơ sở cho:

- Phân tích hệ thống.
- Thiết kế cơ sở dữ liệu.
- Thiết kế API.
- Phát triển Backend.
- Phát triển Frontend.
- Kiểm thử phần mềm.
- Nghiệm thu hệ thống.

---

## 1.2. Mục tiêu hệ thống

Hệ thống nhằm hỗ trợ doanh nghiệp quản lý tập trung các nghiệp vụ:

- Quản lý tài khoản và phân quyền.
- Quản lý thông tin nhân viên.
- Quản lý phòng ban và chức vụ.
- Quản lý hợp đồng lao động.
- Quản lý chấm công.
- Quản lý nghỉ phép.
- Quản lý tăng ca.
- Quản lý phụ cấp.
- Quản lý thưởng.
- Quản lý khấu trừ.
- Tính lương.
- Quản lý bảng lương.
- Báo cáo và thống kê.

Hệ thống giúp giảm thao tác thủ công, hạn chế sai sót trong quá trình quản lý nhân sự và tính lương.

---

# 2. PHẠM VI HỆ THỐNG

## 2.1. Phạm vi chức năng

Hệ thống bao gồm các module:

### Authentication & Authorization

- Đăng nhập.
- Đăng xuất.
- Đổi mật khẩu.
- Quản lý tài khoản.
- Phân quyền.

### Employee Management

- Quản lý nhân viên.
- Quản lý phòng ban.
- Quản lý chức vụ.
- Quản lý hợp đồng.

### Attendance Management

- Check-in.
- Check-out.
- Xem lịch sử chấm công.
- Điều chỉnh chấm công.

### Leave Management

- Tạo yêu cầu nghỉ phép.
- Duyệt nghỉ phép.
- Từ chối nghỉ phép.
- Xem lịch sử nghỉ phép.
- Quản lý ngày phép.

### Overtime Management

- Đăng ký tăng ca.
- Duyệt tăng ca.
- Từ chối tăng ca.
- Theo dõi giờ tăng ca.

### Payroll Management

- Quản lý phụ cấp.
- Quản lý thưởng.
- Quản lý khấu trừ.
- Tính lương.
- Kiểm tra bảng lương.
- Chốt bảng lương.
- Xem phiếu lương.

### Reporting

- Báo cáo nhân sự.
- Báo cáo chấm công.
- Báo cáo lương.

---

## 2.2. Ngoài phạm vi

Phiên bản hiện tại không bao gồm:

- Tuyển dụng trực tuyến.
- Đào tạo nhân viên.
- Đánh giá hiệu suất chuyên sâu.
- Quản lý tài sản doanh nghiệp.
- Kế toán tổng thể.
- Chuyển lương trực tiếp qua ngân hàng.
- Tích hợp thiết bị chấm công vật lý.
- Ứng dụng mobile native.

---

# 3. ACTORS

## 3.1. Admin

Admin quản lý tài khoản và quyền truy cập hệ thống.

Quyền chính:

- Đăng nhập.
- Đăng xuất.
- Đổi mật khẩu.
- Quản lý tài khoản.
- Phân quyền.

---

## 3.2. HR

HR chịu trách nhiệm quản lý thông tin nhân sự.

Quyền chính:

- Quản lý nhân viên.
- Quản lý phòng ban.
- Quản lý chức vụ.
- Quản lý hợp đồng.
- Xem và điều chỉnh chấm công.
- Xem báo cáo nhân sự.
- Xem báo cáo chấm công.

---

## 3.3. Nhân viên

Nhân viên sử dụng hệ thống để quản lý các thông tin cá nhân và nghiệp vụ của mình.

Quyền chính:

- Đăng nhập.
- Đăng xuất.
- Đổi mật khẩu.
- Xem thông tin cá nhân.
- Check-in.
- Check-out.
- Xem lịch sử chấm công.
- Gửi yêu cầu nghỉ phép.
- Xem lịch sử nghỉ phép.
- Đăng ký tăng ca.
- Xem trạng thái tăng ca.
- Xem phiếu lương.

---

## 3.4. Quản lý

Quản lý chịu trách nhiệm kiểm tra và phê duyệt các yêu cầu của nhân viên thuộc phạm vi quản lý.

Quyền chính:

- Xem nhân viên thuộc bộ phận.
- Xem chấm công.
- Duyệt nghỉ phép.
- Từ chối nghỉ phép.
- Duyệt tăng ca.
- Từ chối tăng ca.
- Xem báo cáo.

---

## 3.5. Kế toán

Kế toán chịu trách nhiệm xử lý nghiệp vụ tiền lương.

Quyền chính:

- Quản lý phụ cấp.
- Quản lý thưởng.
- Quản lý khấu trừ.
- Tính lương.
- Kiểm tra bảng lương.
- Chốt bảng lương.
- Xem báo cáo lương.

---

# 4. YÊU CẦU CHỨC NĂNG

# 4.1. Authentication

## FR-AUTH-01 - Đăng nhập

Hệ thống phải cho phép người dùng đăng nhập bằng username/email và mật khẩu.

### Điều kiện

- Tài khoản tồn tại.
- Tài khoản đang hoạt động.

### Kết quả

- Đăng nhập thành công.
- Hệ thống xác định role.
- Hệ thống cấp phiên đăng nhập/token.
- Người dùng được chuyển đến giao diện phù hợp.

---

## FR-AUTH-02 - Đăng xuất

Hệ thống phải cho phép người dùng kết thúc phiên đăng nhập.

### Kết quả

- Token/session bị vô hiệu hóa hoặc hết hiệu lực.
- Người dùng được chuyển về trang đăng nhập.

---

## FR-AUTH-03 - Đổi mật khẩu

Hệ thống phải cho phép người dùng thay đổi mật khẩu.

### Yêu cầu

- Nhập mật khẩu hiện tại.
- Nhập mật khẩu mới.
- Xác nhận mật khẩu mới.
- Mật khẩu mới phải đáp ứng chính sách bảo mật.

---

## FR-AUTH-04 - Quản lý tài khoản

Admin có thể:

- Xem danh sách tài khoản.
- Tạo tài khoản.
- Cập nhật tài khoản.
- Khóa tài khoản.
- Mở khóa tài khoản.
- Tìm kiếm tài khoản.

Username/email phải là duy nhất.

---

## FR-AUTH-05 - Phân quyền

Hệ thống phải hỗ trợ các role:

- ADMIN
- HR
- MANAGER
- ACCOUNTANT
- EMPLOYEE

Người dùng chỉ được phép thực hiện chức năng mà role của họ được cấp quyền.

---

# 4.2. Employee Management

## FR-EMP-01 - Quản lý nhân viên

HR có thể:

- Thêm nhân viên.
- Xem nhân viên.
- Sửa nhân viên.
- Tìm kiếm nhân viên.
- Lọc nhân viên.
- Ngừng hoạt động nhân viên.

### Thông tin nhân viên

- Employee ID
- Họ tên
- Ngày sinh
- Giới tính
- Số điện thoại
- Email
- Địa chỉ
- Phòng ban
- Chức vụ
- Ngày vào làm
- Trạng thái

Employee ID phải là duy nhất.

---

## FR-EMP-02 - Quản lý phòng ban

HR có thể:

- Thêm phòng ban.
- Xem phòng ban.
- Sửa phòng ban.
- Tìm kiếm phòng ban.
- Xóa/ngừng hoạt động phòng ban.

Mã phòng ban phải là duy nhất.

Không được xóa phòng ban đang có nhân viên nếu chưa xử lý nhân viên thuộc phòng ban đó.

---

## FR-EMP-03 - Quản lý chức vụ

HR có thể:

- Thêm chức vụ.
- Xem chức vụ.
- Sửa chức vụ.
- Tìm kiếm chức vụ.
- Xóa/ngừng hoạt động chức vụ.

Mã chức vụ phải là duy nhất.

---

## FR-EMP-04 - Quản lý hợp đồng

HR có thể:

- Tạo hợp đồng.
- Xem hợp đồng.
- Cập nhật hợp đồng.
- Xem lịch sử hợp đồng.

### Thông tin hợp đồng

- Contract ID
- Employee ID
- Loại hợp đồng
- Ngày bắt đầu
- Ngày kết thúc
- Mức lương cơ bản
- Trạng thái

Ngày kết thúc không được nhỏ hơn ngày bắt đầu.

---

# 4.3. Attendance Management

## FR-ATT-01 - Check-in

Nhân viên có thể Check-in để ghi nhận thời gian bắt đầu làm việc.

### Yêu cầu

- Hệ thống tự động lấy thời gian hiện tại.
- Lưu ngày.
- Lưu giờ vào.
- Gắn bản ghi với nhân viên.

Không cho phép Check-in lần thứ hai khi phiên chấm công hiện tại chưa Check-out.

---

## FR-ATT-02 - Check-out

Nhân viên có thể Check-out để ghi nhận thời gian kết thúc làm việc.

### Yêu cầu

- Nhân viên phải Check-in trước.
- Hệ thống tự động lấy thời gian hiện tại.
- Lưu giờ ra.
- Tính thời gian làm việc.

Không cho phép Check-out nếu chưa Check-in.

---

## FR-ATT-03 - Xem lịch sử chấm công

Nhân viên có thể xem lịch sử chấm công của chính mình.

Thông tin bao gồm:

- Ngày.
- Giờ vào.
- Giờ ra.
- Tổng thời gian.
- Đi trễ.
- Về sớm.
- Trạng thái.

Có thể lọc theo khoảng thời gian.

---

## FR-ATT-04 - Điều chỉnh chấm công

HR có thể điều chỉnh dữ liệu chấm công.

### Yêu cầu

- Chọn nhân viên.
- Chọn ngày.
- Sửa giờ vào/ra.
- Nhập lý do.
- Lưu người thực hiện.
- Lưu thời gian điều chỉnh.

Giờ ra không được nhỏ hơn giờ vào.

---

# 4.4. Leave Management

## FR-LEAVE-01 - Gửi yêu cầu nghỉ phép

Nhân viên có thể gửi yêu cầu nghỉ phép.

### Thông tin

- Loại nghỉ.
- Ngày bắt đầu.
- Ngày kết thúc.
- Số ngày nghỉ.
- Lý do.
