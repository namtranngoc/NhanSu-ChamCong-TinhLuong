# USER STORIES
## Hệ thống quản lý nhân sự, chấm công và tính lương

**Phiên bản:** 1.0  
**Trạng thái:** Draft

---

# 1. Tổng quan

Tài liệu này mô tả các User Story của hệ thống quản lý nhân sự, chấm công và tính lương.

User Story được viết theo cấu trúc:

> As a [Actor], I want [Goal], so that [Benefit].

Mỗi User Story bao gồm:

- ID
- Epic
- Actor
- User Story
- Acceptance Criteria
- Priority
- Related Use Case
- Related Requirement

---

# 2. Danh sách Epic

| Epic | Tên |
|---|---|
| EP01 | Authentication & Authorization |
| EP02 | Employee Management |
| EP03 | Attendance Management |
| EP04 | Leave Management |
| EP05 | Overtime Management |
| EP06 | Payroll Management |
| EP07 | Reporting |

---

# 3. EP01 - Authentication & Authorization

## US-AUTH-01 - Đăng nhập

**Actor:** Người dùng

**User Story:**

> As a user, I want to log in to the system using my username/email and password, so that I can access the functions allowed for my role.

### Acceptance Criteria

- [ ] Người dùng có thể nhập username/email.
- [ ] Người dùng có thể nhập mật khẩu.
- [ ] Hệ thống kiểm tra thông tin đăng nhập.
- [ ] Đăng nhập thành công nếu thông tin hợp lệ.
- [ ] Hiển thị thông báo lỗi nếu thông tin không hợp lệ.
- [ ] Không cho đăng nhập nếu tài khoản bị khóa.
- [ ] Hệ thống xác định đúng role của người dùng sau khi đăng nhập.

**Priority:** High

**Use Case:** UC01

**Requirement:** FR-AUTH-01

---

## US-AUTH-02 - Đăng xuất

**Actor:** Người dùng

**User Story:**

> As a user, I want to log out of the system, so that my account session is terminated.

### Acceptance Criteria

- [ ] Có chức năng Đăng xuất.
- [ ] Người dùng có thể đăng xuất.
- [ ] Session/token đăng nhập được kết thúc.
- [ ] Người dùng được chuyển về trang đăng nhập.

**Priority:** High

**Use Case:** UC02

**Requirement:** FR-AUTH-02

---

## US-AUTH-03 - Đổi mật khẩu

**Actor:** Người dùng

**User Story:**

> As a user, I want to change my password, so that I can protect my account.

### Acceptance Criteria

- [ ] Nhập mật khẩu hiện tại.
- [ ] Nhập mật khẩu mới.
- [ ] Nhập lại mật khẩu mới.
- [ ] Mật khẩu hiện tại phải chính xác.
- [ ] Mật khẩu mới phải đáp ứng chính sách bảo mật.
- [ ] Mật khẩu xác nhận phải trùng mật khẩu mới.
- [ ] Hiển thị thông báo khi đổi mật khẩu thành công.

**Priority:** Medium

**Use Case:** UC03

**Requirement:** FR-AUTH-03

---

## US-AUTH-04 - Quản lý tài khoản

**Actor:** Admin

**User Story:**

> As an admin, I want to manage user accounts, so that I can control access to the system.

### Acceptance Criteria

- [ ] Admin có thể xem danh sách tài khoản.
- [ ] Admin có thể tạo tài khoản.
- [ ] Admin có thể cập nhật tài khoản.
- [ ] Admin có thể khóa tài khoản.
- [ ] Admin có thể mở khóa tài khoản.
- [ ] Admin có thể tìm kiếm tài khoản.
- [ ] Username/email không được trùng.

**Priority:** High

**Use Case:** UC04

**Requirement:** FR-AUTH-04

---

## US-AUTH-05 - Phân quyền

**Actor:** Admin

**User Story:**

> As an admin, I want to assign roles to users, so that each user can access only authorized functions.

### Acceptance Criteria

- [ ] Admin có thể xem role của tài khoản.
- [ ] Admin có thể thay đổi role.
- [ ] Hệ thống hỗ trợ role ADMIN.
- [ ] Hệ thống hỗ trợ role HR.
- [ ] Hệ thống hỗ trợ role MANAGER.
- [ ] Hệ thống hỗ trợ role ACCOUNTANT.
- [ ] Hệ thống hỗ trợ role EMPLOYEE.
- [ ] Backend phải kiểm tra quyền khi truy cập API.

**Priority:** High

**Use Case:** UC05

**Requirement:** FR-AUTH-05

---

# 4. EP02 - Employee Management

## US-EMP-01 - Thêm nhân viên

**Actor:** HR

**User Story:**

> As an HR, I want to add a new employee, so that the employee can be managed in the system.

### Acceptance Criteria

- [ ] HR có thể mở chức năng thêm nhân viên.
- [ ] HR nhập các thông tin bắt buộc.
- [ ] Mã nhân viên không được trùng.
- [ ] Email phải đúng định dạng.
- [ ] Hệ thống lưu nhân viên thành công.
- [ ] Nhân viên mới có trạng thái ACTIVE.

**Priority:** High

**Use Case:** UC06

**Requirement:** FR-EMP-01

---

## US-EMP-02 - Xem danh sách nhân viên

**Actor:** HR

**User Story:**

> As an HR, I want to view the employee list, so that I can manage employee information.

### Acceptance Criteria

- [ ] Hiển thị danh sách nhân viên.
- [ ] Hiển thị mã nhân viên.
- [ ] Hiển thị họ tên.
- [ ] Hiển thị phòng ban.
- [ ] Hiển thị chức vụ.
- [ ] Hiển thị trạng thái.
- [ ] Có chức năng tìm kiếm.
- [ ] Có phân trang.

**Priority:** High

**Use Case:** UC06

**Requirement:** FR-EMP-01

---

## US-EMP-03 - Cập nhật nhân viên

**Actor:** HR

**User Story:**

> As an HR, I want to update employee information, so that employee data remains accurate.

### Acceptance Criteria

- [ ] HR có thể chọn nhân viên.
- [ ] Hệ thống hiển thị thông tin hiện tại.
- [ ] HR có thể chỉnh sửa thông tin.
- [ ] Hệ thống kiểm tra dữ liệu.
- [ ] Hệ thống lưu thông tin sau khi cập nhật.

**Priority:** High

**Use Case:** UC06

**Requirement:** FR-EMP-01

---

## US-EMP-04 - Quản lý phòng ban

**Actor:** HR

**User Story:**

> As an HR, I want to manage departments, so that employees can be organized by department.

### Acceptance Criteria

- [ ] Thêm phòng ban.
- [ ] Xem danh sách phòng ban.
- [ ] Cập nhật phòng ban.
- [ ] Tìm kiếm phòng ban.
- [ ] Mã phòng ban không được trùng.
- [ ] Không xóa phòng ban đang có nhân viên nếu chưa xử lý nhân viên.

**Priority:** High

**Use Case:** UC07

**Requirement:** FR-EMP-02

---

## US-EMP-05 - Quản lý chức vụ

**Actor:** HR

**User Story:**

> As an HR, I want to manage positions, so that employees can be assigned appropriate positions.

### Acceptance Criteria

- [ ] Thêm chức vụ.
- [ ] Xem chức vụ.
- [ ] Cập nhật chức vụ.
- [ ] Tìm kiếm chức vụ.
- [ ] Mã chức vụ không được trùng.

**Priority:** Medium

**Use Case:** UC08

**Requirement:** FR-EMP-03

---

## US-EMP-06 - Quản lý hợp đồng

**Actor:** HR

**User Story:**

> As an HR, I want to manage employee contracts, so that I can track employment information.

### Acceptance Criteria

- [ ] Tạo hợp đồng.
- [ ] Chọn nhân viên.
- [ ] Chọn loại hợp đồng.
- [ ] Nhập ngày bắt đầu.
- [ ] Nhập ngày kết thúc.
- [ ] Nhập mức lương cơ bản.
- [ ] Ngày kết thúc không được nhỏ hơn ngày bắt đầu.
- [ ] Có thể xem lịch sử hợp đồng.

**Priority:** High

**Use Case:** UC09

**Requirement:** FR-EMP-04

---

# 5. EP03 - Attendance Management

## US-ATT-01 - Check-in

**Actor:** Nhân viên

**User Story:**

> As an employee, I want to check in when I start working, so that my working start time is recorded.

### Acceptance Criteria

- [ ] Nhân viên phải đăng nhập.
- [ ] Có chức năng Check-in.
- [ ] Hệ thống tự lấy thời gian hiện tại.
- [ ] Hệ thống lưu ngày và giờ Check-in.
- [ ] Không cho Check-in lần hai khi chưa Check-out.
- [ ] Hiển thị trạng thái đã Check-in.

**Priority:** High

**Use Case:** UC10

**Requirement:** FR-ATT-01

---

## US-ATT-02 - Check-out

**Actor:** Nhân viên

**User Story:**

> As an employee, I want to check out when I finish working, so that my working end time is recorded.

### Acceptance Criteria

- [ ] Nhân viên phải Check-in trước.
- [ ] Có chức năng Check-out.
- [ ] Hệ thống tự lấy thời gian hiện tại.
- [ ] Hệ thống lưu giờ Check-out.
- [ ] Hệ thống tính thời gian làm việc.
- [ ] Không cho Check-out nếu chưa Check-in.

**Priority:** High

**Use Case:** UC10

**Requirement:** FR-ATT-02

---

## US-ATT-03 - Xem lịch sử chấm công

**Actor:** Nhân viên

**User Story:**

> As an employee, I want to view my attendance history, so that I can check my working records.

### Acceptance Criteria

- [ ] Xem danh sách chấm công.
- [ ] Xem ngày.
- [ ] Xem giờ vào.
- [ ] Xem giờ ra.
- [ ] Xem tổng thời gian làm việc.
- [ ] Có thể lọc theo khoảng thời gian.
- [ ] Chỉ được xem dữ liệu của chính mình.

**Priority:** High

**Use Case:** UC11

**Requirement:** FR-ATT-03

---

## US-ATT-04 - Điều chỉnh chấm công

**Actor:** HR

**User Story:**

> As an HR, I want to adjust attendance records, so that incorrect attendance data can be corrected.

### Acceptance Criteria

- [ ] HR có thể tìm nhân viên.
- [ ] HR có thể chọn ngày.
- [ ] HR có thể sửa giờ vào.
- [ ] HR có thể sửa giờ ra.
- [ ] Bắt buộc nhập lý do điều chỉnh.
- [ ] Lưu người thực hiện.
- [ ] Lưu thời gian điều chỉnh.
- [ ] Giờ ra không được nhỏ hơn giờ vào.

**Priority:** High

**Use Case:** UC12

**Requirement:** FR-ATT-04

---

# 6. EP04 - Leave Management

## US-LEAVE-01 - Gửi yêu cầu nghỉ phép

**Actor:** Nhân viên

**User Story:**

> As an employee, I want to submit a leave request, so that I can request time off from work.

### Acceptance Criteria

- [ ] Chọn loại nghỉ.
- [ ] Chọn ngày bắt đầu.
- [ ] Chọn ngày kết thúc.
- [ ] Nhập lý do.
- [ ] Hệ thống tính số ngày nghỉ.
- [ ] Hệ thống kiểm tra số ngày phép còn lại.
- [ ] Yêu cầu được tạo với trạng thái PENDING.

**Priority:** High

**Use Case:** UC13

**Requirement:** FR-LEAVE-01

---

## US-LEAVE-02 - Duyệt nghỉ phép

**Actor:** Quản lý

**User Story:**

> As a manager, I want to approve leave requests, so that employee leave can be managed.

### Acceptance Criteria

- [ ] Quản lý xem được yêu cầu của nhân viên thuộc phạm vi quản lý.
- [ ] Có thể xem chi tiết yêu cầu.
- [ ] Có chức năng Duyệt.
- [ ] Trạng thái chuyển từ PENDING sang APPROVED.
- [ ] Số ngày phép được cập nhật.
- [ ] Nhân viên xem được kết quả.

**Priority:** High

**Use Case:** UC14

**Requirement:** FR-LEAVE-02

---

## US-LEAVE-03 - Từ chối nghỉ phép

**Actor:** Quản lý

**User Story:**

> As a manager, I want to reject leave requests, so that inappropriate requests can be denied.

### Acceptance Criteria

- [ ] Quản lý chọn yêu cầu.
- [ ] Có chức năng Từ chối.
- [ ] Bắt buộc nhập lý do từ chối.
- [ ] Trạng thái chuyển từ PENDING sang REJECTED.
- [ ] Nhân viên xem được lý do từ chối.

**Priority:** High

**Use Case:** UC14

**Requirement:** FR-LEAVE-03

---

## US-LEAVE-04 - Xem lịch sử nghỉ phép

**Actor:** Nhân viên

**User Story:**

> As an employee, I want to view my leave history, so that I can track my leave requests.

### Acceptance Criteria

- [ ] Xem danh sách yêu cầu nghỉ.
- [ ] Xem loại nghỉ.
- [ ] Xem ngày bắt đầu.
- [ ] Xem ngày kết thúc.
- [ ] Xem số ngày nghỉ.
- [ ] Xem trạng thái.
- [ ] Xem số ngày phép còn lại.

**Priority:** Medium

**Use Case:** UC15

**Requirement:** FR-LEAVE-04

---

# 7. EP05 - Overtime Management

## US-OT-01 - Đăng ký tăng ca

**Actor:** Nhân viên

**User Story:**

> As an employee, I want to submit an overtime request, so that my overtime work can be recorded and approved.

### Acceptance Criteria

- [ ] Chọn ngày tăng ca.
- [ ] Nhập giờ bắt đầu.
- [ ] Nhập giờ kết thúc.
- [ ] Nhập lý do.
- [ ] Giờ kết thúc phải lớn hơn giờ bắt đầu.
- [ ] Trạng thái ban đầu là PENDING.

**Priority:** High

**Use Case:** UC16

**Requirement:** FR-OT-01

---

## US-OT-02 - Duyệt tăng ca

**Actor:** Quản lý

**User Story:**

> As a manager, I want to approve overtime requests, so that approved overtime can be included in payroll.

### Acceptance Criteria

- [ ] Quản lý xem danh sách yêu cầu.
- [ ] Có thể xem chi tiết.
- [ ] Có chức năng Duyệt.
- [ ] Trạng thái chuyển thành APPROVED.
- [ ] Số giờ tăng ca được sử dụng khi tính lương.

**Priority:** High

**Use Case:** UC17

**Requirement:** FR-OT-02

---

## US-OT-03 - Từ chối tăng ca

**Actor:** Quản lý

**User Story:**

> As a manager, I want to reject overtime requests, so that unapproved overtime is not included in payroll.

### Acceptance Criteria

- [ ] Quản lý chọn yêu cầu.
- [ ] Có chức năng Từ chối.
- [ ] Bắt buộc nhập lý do.
- [ ] Trạng thái chuyển thành REJECTED.
- [ ] Nhân viên xem được lý do.

**Priority:** High

**Use Case:** UC17

**Requirement:** FR-OT-03

---

# 8. EP06 - Payroll Management

## US-PAY-01 - Quản lý phụ cấp

**Actor:** Kế toán

**User Story:**

> As an accountant, I want to manage employee allowances, so that allowances can be included in payroll.

### Acceptance Criteria

- [ ] Chọn nhân viên.
- [ ] Chọn loại phụ cấp.
- [ ] Nhập số tiền.
- [ ] Chọn kỳ áp dụng.
- [ ] Có thể cập nhật phụ cấp.
- [ ] Có thể ngừng áp dụng phụ cấp.

**Priority:** High

**Use Case:** UC18

**Requirement:** FR-PAY-01

---

## US-PAY-02 - Quản lý thưởng

**Actor:** Kế toán

**User Story:**

> As an accountant, I want to manage employee bonuses, so that bonuses can be included in payroll.

### Acceptance Criteria

- [ ] Chọn nhân viên.
- [ ] Nhập số tiền thưởng.
- [ ] Nhập lý do.
- [ ] Chọn kỳ lương.
- [ ] Hệ thống lưu khoản thưởng.
- [ ] Số tiền phải hợp lệ.

**Priority:** Medium

**Use Case:** UC19

**Requirement:** FR-PAY-02

---

## US-PAY-03 - Quản lý khấu trừ

**Actor:** Kế toán

**User Story:**

> As an accountant, I want to manage employee deductions, so that deductions can be included in payroll calculations.

### Acceptance Criteria

- [ ] Chọn nhân viên.
- [ ] Chọn loại khấu trừ.
- [ ] Nhập số tiền.
- [ ] Nhập lý do.
- [ ] Chọn kỳ lương.
- [ ] Hệ thống lưu khoản khấu trừ.

**Priority:** High

**Use Case:** UC20

**Requirement:** FR-PAY-03

---

## US-PAY-04 - Tính lương

**Actor:** Kế toán

**User Story:**

> As an accountant, I want to calculate employee salaries, so that I can generate payroll for a specific period.

### Acceptance Criteria

- [ ] Kế toán chọn kỳ lương.
- [ ] Hệ thống lấy lương cơ bản.
- [ ] Hệ thống lấy dữ liệu chấm công.
- [ ] Hệ thống lấy tăng ca đã được duyệt.
- [ ] Hệ thống lấy phụ cấp.
- [ ] Hệ thống lấy thưởng.
- [ ] Hệ thống lấy khấu trừ.
- [ ] Hệ thống tính tổng thu nhập.
- [ ] Hệ thống tính lương thực nhận.
- [ ] Không tạo bảng lương trùng.
- [ ] Kế toán có thể kiểm tra kết quả trước khi chốt.

### Công thức

Tổng thu nhập
= Lương cơ bản
+ Tiền tăng ca
+ Phụ cấp
+ Thưởng
