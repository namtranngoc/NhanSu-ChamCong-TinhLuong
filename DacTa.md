# ĐẶC TẢ USE CASE
## Hệ thống quản lý nhân sự, chấm công và tính lương

---

# 1. Tổng quan

Tài liệu này mô tả chi tiết các Use Case chính của hệ thống quản lý nhân sự, chấm công và tính lương.

## 1.1. Danh sách Actor

| Actor | Mô tả |
|---|---|
| Admin | Quản lý tài khoản và phân quyền |
| HR | Quản lý thông tin nhân sự và chấm công |
| Nhân viên | Chấm công, nghỉ phép, tăng ca và xem lương |
| Quản lý | Duyệt nghỉ phép và tăng ca |
| Kế toán | Tính và quản lý bảng lương |

---

# 2. UC01 - Đăng nhập

## Thông tin chung

- **Mã:** UC01
- **Tên:** Đăng nhập
- **Actor:** Admin, HR, Quản lý, Kế toán, Nhân viên
- **Mục tiêu:** Cho phép người dùng truy cập hệ thống.
- **Tiền điều kiện:** Người dùng đã có tài khoản.
- **Hậu điều kiện:** Người dùng đăng nhập thành công và được chuyển đến giao diện phù hợp với quyền.

## Luồng chính

1. Người dùng mở màn hình đăng nhập.
2. Người dùng nhập username/email.
3. Người dùng nhập mật khẩu.
4. Người dùng nhấn nút "Đăng nhập".
5. Hệ thống kiểm tra thông tin đăng nhập.
6. Hệ thống xác định quyền của người dùng.
7. Hệ thống tạo phiên đăng nhập.
8. Hệ thống chuyển người dùng đến trang chính.

## Luồng ngoại lệ

- **E1:** Username/email hoặc mật khẩu không chính xác.
  - Hệ thống hiển thị thông báo lỗi.

- **E2:** Tài khoản bị khóa.
  - Hệ thống từ chối đăng nhập và thông báo tài khoản đã bị khóa.

- **E3:** Người dùng bỏ trống username/email hoặc mật khẩu.
  - Hệ thống yêu cầu nhập đầy đủ thông tin.

---

# 3. UC02 - Đăng xuất

## Thông tin chung

- **Mã:** UC02
- **Tên:** Đăng xuất
- **Actor:** Admin, HR, Quản lý, Kế toán, Nhân viên
- **Mục tiêu:** Kết thúc phiên làm việc của người dùng.
- **Tiền điều kiện:** Người dùng đã đăng nhập.
- **Hậu điều kiện:** Phiên đăng nhập được kết thúc.

## Luồng chính

1. Người dùng chọn chức năng "Đăng xuất".
2. Hệ thống kết thúc phiên đăng nhập.
3. Hệ thống chuyển người dùng về màn hình đăng nhập.

---

# 4. UC03 - Đổi mật khẩu

## Thông tin chung

- **Mã:** UC03
- **Tên:** Đổi mật khẩu
- **Actor:** Tất cả người dùng
- **Mục tiêu:** Cho phép người dùng thay đổi mật khẩu.
- **Tiền điều kiện:** Người dùng đã đăng nhập.
- **Hậu điều kiện:** Mật khẩu mới được lưu thành công.

## Luồng chính

1. Người dùng chọn "Đổi mật khẩu".
2. Hệ thống hiển thị biểu mẫu đổi mật khẩu.
3. Người dùng nhập mật khẩu hiện tại.
4. Người dùng nhập mật khẩu mới.
5. Người dùng nhập lại mật khẩu mới.
6. Người dùng nhấn "Lưu".
7. Hệ thống kiểm tra mật khẩu hiện tại.
8. Hệ thống kiểm tra mật khẩu mới.
9. Hệ thống cập nhật mật khẩu.
10. Hệ thống thông báo đổi mật khẩu thành công.

## Luồng ngoại lệ

- **E1:** Mật khẩu hiện tại không chính xác.
- **E2:** Mật khẩu mới không đáp ứng yêu cầu bảo mật.
- **E3:** Mật khẩu xác nhận không trùng khớp.

---

# 5. UC04 - Quản lý tài khoản

## Thông tin chung

- **Mã:** UC04
- **Tên:** Quản lý tài khoản
- **Actor:** Admin
- **Mục tiêu:** Quản lý tài khoản người dùng.
- **Tiền điều kiện:** Admin đã đăng nhập.
- **Hậu điều kiện:** Thông tin tài khoản được thêm, sửa hoặc cập nhật trạng thái.

## Chức năng

- Xem danh sách tài khoản.
- Thêm tài khoản.
- Sửa tài khoản.
- Khóa tài khoản.
- Mở khóa tài khoản.
- Tìm kiếm tài khoản.

## Luồng chính - Thêm tài khoản

1. Admin chọn "Quản lý tài khoản".
2. Hệ thống hiển thị danh sách tài khoản.
3. Admin chọn "Thêm tài khoản".
4. Nhập username/email.
5. Chọn nhân viên tương ứng.
6. Chọn vai trò.
7. Nhập mật khẩu.
8. Nhấn "Lưu".
9. Hệ thống kiểm tra dữ liệu.
10. Hệ thống tạo tài khoản.
11. Hệ thống thông báo thành công.

## Luồng ngoại lệ

- Username/email đã tồn tại.
- Không tìm thấy nhân viên.
- Thiếu thông tin bắt buộc.

---

# 6. UC05 - Phân quyền

## Thông tin chung

- **Mã:** UC05
- **Tên:** Phân quyền
- **Actor:** Admin
- **Mục tiêu:** Xác định quyền truy cập của từng người dùng.
- **Tiền điều kiện:** Admin đã đăng nhập.
- **Hậu điều kiện:** Vai trò của tài khoản được cập nhật.

## Vai trò

- Admin
- HR
- Quản lý
- Kế toán
- Nhân viên

## Luồng chính

1. Admin chọn "Phân quyền".
2. Hệ thống hiển thị danh sách tài khoản.
3. Admin chọn tài khoản.
4. Admin chọn vai trò.
5. Admin nhấn "Lưu".
6. Hệ thống cập nhật vai trò.
7. Hệ thống áp dụng quyền tương ứng.

## Luồng ngoại lệ

- Tài khoản không tồn tại.
- Vai trò không hợp lệ.

---

# 7. UC06 - Quản lý nhân viên

## Thông tin chung

- **Mã:** UC06
- **Tên:** Quản lý nhân viên
- **Actor:** HR
- **Mục tiêu:** Quản lý hồ sơ nhân viên.
- **Tiền điều kiện:** HR đã đăng nhập.
- **Hậu điều kiện:** Hồ sơ nhân viên được tạo hoặc cập nhật.

## Thông tin nhân viên

- Mã nhân viên
- Họ tên
- Ngày sinh
- Giới tính
- Số điện thoại
- Email
- Địa chỉ
- Phòng ban
- Chức vụ
- Ngày vào làm
- Trạng thái làm việc

## Luồng chính - Thêm nhân viên

1. HR chọn "Quản lý nhân viên".
2. Chọn "Thêm nhân viên".
3. Nhập thông tin nhân viên.
4. Nhấn "Lưu".
5. Hệ thống kiểm tra dữ liệu.
6. Hệ thống kiểm tra mã nhân viên có bị trùng không.
7. Hệ thống lưu thông tin.
8. Hệ thống thông báo thành công.

## Luồng ngoại lệ

- Mã nhân viên đã tồn tại.
- Thiếu thông tin bắt buộc.
- Email không đúng định dạng.
- Phòng ban không tồn tại.
- Chức vụ không tồn tại.

## Chức năng phụ

- Xem nhân viên.
- Tìm kiếm nhân viên.
- Sửa nhân viên.
- Ngừng hoạt động nhân viên.

---

# 8. UC07 - Quản lý phòng ban

## Thông tin chung

- **Mã:** UC07
- **Tên:** Quản lý phòng ban
- **Actor:** HR
- **Mục tiêu:** Quản lý danh sách phòng ban.
- **Tiền điều kiện:** HR đã đăng nhập.
- **Hậu điều kiện:** Phòng ban được thêm, sửa hoặc cập nhật.

## Luồng chính

1. HR chọn "Quản lý phòng ban".
2. Hệ thống hiển thị danh sách phòng ban.
3. HR chọn "Thêm phòng ban".
4. Nhập mã phòng ban.
5. Nhập tên phòng ban.
6. Nhấn "Lưu".
7. Hệ thống kiểm tra dữ liệu.
8. Hệ thống lưu phòng ban.

## Luồng ngoại lệ

- Mã phòng ban bị trùng.
- Tên phòng ban bị bỏ trống.
- Không cho phép xóa phòng ban đang có nhân viên nếu chưa xử lý nhân viên thuộc phòng ban đó.

---

# 9. UC08 - Quản lý chức vụ

## Thông tin chung

- **Mã:** UC08
- **Tên:** Quản lý chức vụ
- **Actor:** HR
- **Mục tiêu:** Quản lý chức vụ của nhân viên.
- **Tiền điều kiện:** HR đã đăng nhập.
- **Hậu điều kiện:** Chức vụ được thêm hoặc cập nhật.

## Luồng chính

1. HR chọn "Quản lý chức vụ".
2. Hệ thống hiển thị danh sách chức vụ.
3. HR chọn "Thêm chức vụ".
4. Nhập mã chức vụ.
5. Nhập tên chức vụ.
6. Nhấn "Lưu".
7. Hệ thống kiểm tra dữ liệu.
8. Hệ thống lưu chức vụ.

## Luồng ngoại lệ

- Mã chức vụ bị trùng.
- Tên chức vụ bị bỏ trống.

---

# 10. UC09 - Quản lý hợp đồng

## Thông tin chung

- **Mã:** UC09
- **Tên:** Quản lý hợp đồng
- **Actor:** HR
- **Mục tiêu:** Quản lý hợp đồng lao động của nhân viên.
- **Tiền điều kiện:** Nhân viên đã tồn tại.
- **Hậu điều kiện:** Hợp đồng được lưu vào hệ thống.

## Thông tin hợp đồng

- Mã hợp đồng
- Nhân viên
- Loại hợp đồng
- Ngày bắt đầu
- Ngày kết thúc
- Mức lương cơ bản
- Trạng thái hợp đồng

## Luồng chính

1. HR chọn nhân viên.
2. Chọn "Hợp đồng".
3. Chọn "Thêm hợp đồng".
4. Nhập thông tin hợp đồng.
5. Nhấn "Lưu".
6. Hệ thống kiểm tra dữ liệu.
7. Hệ thống lưu hợp đồng.

## Luồng ngoại lệ

- Ngày kết thúc nhỏ hơn ngày bắt đầu.
- Nhân viên không tồn tại.
- Thiếu thông tin bắt buộc.

---

# 11. UC10 - Chấm công

## Thông tin chung

- **Mã:** UC10
- **Tên:** Chấm công
- **Actor:** Nhân viên
- **Mục tiêu:** Ghi nhận thời gian bắt đầu và kết thúc làm việc.
- **Tiền điều kiện:** Nhân viên đã đăng nhập.
- **Hậu điều kiện:** Dữ liệu chấm công được lưu.

## Luồng chính

1. Nhân viên đăng nhập.
2. Chọn "Chấm công".
3. Hệ thống hiển thị trạng thái chấm công.
4. Nhân viên chọn "Check-in".
5. Hệ thống lấy thời gian hiện tại.
6. Hệ thống lưu giờ vào.
7. Khi kết thúc ca, nhân viên chọn "Check-out".
8. Hệ thống lấy thời gian hiện tại.
9. Hệ thống lưu giờ ra.
10. Hệ thống cập nhật bản ghi chấm công.

## Luồng ngoại lệ

### E1 - Check-in lần hai

- Nhân viên đã Check-in nhưng chưa Check-out.
- Hệ thống không cho phép Check-in lần nữa.

### E2 - Check-out trước Check-in

- Nhân viên chưa Check-in.
- Hệ thống không cho phép Check-out.

### E3 - Lỗi lưu dữ liệu

- Hệ thống không thể lưu dữ liệu.
- Hệ thống hiển thị thông báo lỗi.

## Dữ liệu chấm công

- Mã chấm công
- Mã nhân viên
- Ngày
- Giờ vào
- Giờ ra
- Tổng thời gian
- Trạng thái

---

# 12. UC11 - Xem lịch sử chấm công

## Thông tin chung

- **Mã:** UC11
- **Tên:** Xem lịch sử chấm công
- **Actor:** Nhân viên
- **Mục tiêu:** Cho phép nhân viên kiểm tra dữ liệu chấm công.
- **Tiền điều kiện:** Nhân viên đã đăng nhập.
- **Hậu điều kiện:** Lịch sử chấm công được hiển thị.

## Luồng chính

1. Nhân viên chọn "Lịch sử chấm công".
2. Hệ thống hiển thị dữ liệu chấm công.
3. Nhân viên chọn khoảng thời gian.
4. Hệ thống lọc dữ liệu.
5. Hệ thống hiển thị kết quả.

## Thông tin hiển thị

- Ngày
- Giờ vào
- Giờ ra
- Tổng thời gian
- Đi trễ
- Về sớm
- Trạng thái

---

# 13. UC12 - Điều chỉnh chấm công

## Thông tin chung

- **Mã:** UC12
- **Tên:** Điều chỉnh chấm công
- **Actor:** HR
- **Mục tiêu:** Điều chỉnh dữ liệu chấm công khi có sai sót.
- **Tiền điều kiện:** HR đã đăng nhập.
- **Hậu điều kiện:** Bản ghi chấm công được cập nhật.

## Luồng chính

1. HR chọn "Quản lý chấm công".
2. Tìm kiếm nhân viên.
3. Chọn ngày cần điều chỉnh.
4. Hệ thống hiển thị bản ghi.
5. HR chỉnh sửa giờ vào/ra.
6. HR nhập lý do điều chỉnh.
7. Nhấn "Lưu".
8. Hệ thống kiểm tra dữ liệu.
9. Hệ thống cập nhật bản ghi.
10. Hệ thống lưu thông tin người điều chỉnh.

## Luồng ngoại lệ

- Không tìm thấy bản ghi.
- Giờ ra nhỏ hơn giờ vào.
- Không nhập lý do điều chỉnh.
- Dữ liệu không hợp lệ.

---

# 14. UC13 - Gửi yêu cầu nghỉ phép

## Thông tin chung

- **Mã:** UC13
- **Tên:** Gửi yêu cầu nghỉ phép
- **Actor:** Nhân viên
- **Mục tiêu:** Cho phép nhân viên gửi yêu cầu nghỉ phép.
- **Tiền điều kiện:** Nhân viên đã đăng nhập.
- **Hậu điều kiện:** Yêu cầu được tạo với trạng thái "Chờ duyệt".

## Luồng chính

1. Nhân viên chọn "Nghỉ phép".
2. Chọn "Tạo yêu cầu".
3. Chọn loại nghỉ.
4. Chọn ngày bắt đầu.
5. Chọn ngày kết thúc.
6. Nhập lý do.
7. Nhấn "Gửi".
8. Hệ thống kiểm tra số ngày phép.
9. Hệ thống tạo yêu cầu.
10. Trạng thái yêu cầu = "Chờ duyệt".

## Luồng ngoại lệ

- Không đủ ngày phép.
- Ngày kết thúc trước ngày bắt đầu.
- Thời gian nghỉ bị trùng.
- Thiếu lý do.

---

# 15. UC14 - Duyệt nghỉ phép

## Thông tin chung

- **Mã:** UC14
- **Tên:** Duyệt nghỉ phép
- **Actor:** Quản lý
- **Mục tiêu:** Duyệt hoặc từ chối yêu cầu nghỉ phép.
- **Tiền điều kiện:** Có yêu cầu nghỉ phép đang chờ duyệt.
- **Hậu điều kiện:** Yêu cầu chuyển sang "Đã duyệt" hoặc "Từ chối".

## Luồng chính

1. Quản lý chọn "Danh sách nghỉ phép".
2. Hệ thống hiển thị các yêu cầu thuộc phạm vi quản lý.
3. Quản lý chọn một yêu cầu.
4. Hệ thống hiển thị thông tin.
5. Quản lý chọn "Duyệt".
6. Hệ thống cập nhật trạng thái.
7. Hệ thống cập nhật số ngày phép.
8. Hệ thống thông báo cho nhân viên.

## Luồng từ chối

1. Quản lý chọn "Từ chối".
2. Nhập lý do từ chối.
3. Hệ thống cập nhật trạng thái = "Từ chối".
4. Hệ thống lưu lý do.
5. Nhân viên xem được kết quả.

---

# 16. UC15 - Xem lịch sử nghỉ phép

## Thông tin chung

- **Mã:** UC15
- **Tên:** Xem lịch sử nghỉ phép
- **Actor:** Nhân viên
- **Mục tiêu:** Theo dõi lịch sử nghỉ phép và số ngày phép còn lại.
- **Tiền điều kiện:** Nhân viên đã đăng nhập.
- **Hậu điều kiện:** Lịch sử nghỉ phép được hiển thị.

## Luồng chính

1. Nhân viên chọn "Nghỉ phép".
2. Chọn "Lịch sử".
3. Hệ thống hiển thị danh sách yêu cầu.
4. Hệ thống hiển thị số ngày phép còn lại.

## Thông tin hiển thị

- Loại nghỉ
- Ngày bắt đầu
- Ngày kết thúc
- Số ngày nghỉ
- Lý do
- Trạng thái
- Ngày gửi yêu cầu

---

# 17. UC16 - Đăng ký tăng ca

## Thông tin chung

- **Mã:** UC16
- **Tên:** Đăng ký tăng ca
- **Actor:** Nhân viên
- **Mục tiêu:** Đăng ký thời gian làm thêm.
- **Tiền điều kiện:** Nhân viên đã đăng nhập.
- **Hậu điều kiện:** Yêu cầu tăng ca được tạo.

## Luồng chính

1. Nhân viên chọn "Tăng ca".
2. Chọn "Đăng ký tăng ca".
3. Chọn ngày.
4. Nhập giờ bắt đầu.
5. Nhập giờ kết thúc.
6. Nhập lý do.
7. Nhấn "Gửi".
8. Hệ thống kiểm tra dữ liệu.
9. Hệ thống tạo yêu cầu.
10. Trạng thái = "Chờ duyệt".

## Luồng ngoại lệ

- Thời gian kết thúc nhỏ hơn hoặc bằng thời gian bắt đầu.
- Trùng yêu cầu tăng ca.
- Thiếu thông tin.

---

# 18. UC17 - Duyệt tăng ca

## Thông tin chung

- **Mã:** UC17
- **Tên:** Duyệt tăng ca
- **Actor:** Quản lý
- **Mục tiêu:** Duyệt hoặc từ chối yêu cầu tăng ca.
- **Tiền điều kiện:** Có yêu cầu tăng ca.
- **Hậu điều kiện:** Yêu cầu được duyệt hoặc từ chối.

## Luồng chính

1. Quản lý chọn "Danh sách tăng ca".
2. Hệ thống hiển thị yêu cầu.
3. Quản lý chọn yêu cầu.
4. Kiểm tra thông tin.
5. Chọn "Duyệt".
6. Hệ thống cập nhật trạng thái.
7. Số giờ tăng ca được sử dụng khi tính lương.

## Luồng từ chối

1. Quản lý chọn "Từ chối".
2. Nhập lý do.
3. Hệ thống cập nhật trạng thái.
4. Hệ thống lưu lý do từ chối.

---

# 19. UC18 - Quản lý phụ cấp

## Thông tin chung

- **Mã:** UC18
- **Tên:** Quản lý phụ cấp
- **Actor:** Kế toán
- **Mục tiêu:** Quản lý các khoản phụ cấp của nhân viên.
- **Tiền điều kiện:** Kế toán đã đăng nhập.
- **Hậu điều kiện:** Phụ cấp được lưu và sử dụng khi tính lương.

## Luồng chính

1. Kế toán chọn "Phụ cấp".
2. Chọn nhân viên.
3. Chọn loại phụ cấp.
4. Nhập số tiền.
5. Chọn thời gian áp dụng.
6. Nhấn "Lưu".
7. Hệ thống kiểm tra dữ liệu.
8. Hệ thống lưu phụ cấp.

## Luồng ngoại lệ

- Số tiền không hợp lệ.
- Nhân viên không tồn tại.
- Thiếu thông tin.

---

# 20. UC19 - Quản lý thưởng

## Thông tin chung

- **Mã:** UC19
- **Tên:** Quản lý thưởng
- **Actor:** Kế toán
- **Mục tiêu:** Quản lý tiền thưởng của nhân viên.
- **Tiền điều kiện:** Kế toán đã đăng nhập.
- **Hậu điều kiện:** Khoản thưởng được lưu.

## Luồng chính

1. Kế toán chọn "Thưởng".
2. Chọn nhân viên.
3. Nhập số tiền thưởng.
4. Nhập lý do.
5. Chọn tháng áp dụng.
6. Nhấn "Lưu".
7. Hệ thống lưu khoản thưởng.

## Luồng ngoại lệ

- Số tiền không hợp lệ.
- Nhân viên không tồn tại.
- Thiếu lý do.

---

# 21. UC20 - Quản lý khấu trừ

## Thông tin chung

- **Mã:** UC20
- **Tên:** Quản lý khấu trừ
- **Actor:** Kế toán
- **Mục tiêu:** Quản lý các khoản khấu trừ vào lương.
- **Tiền điều kiện:** Kế toán đã đăng nhập.
- **Hậu điều kiện:** Khoản khấu trừ được lưu.

## Luồng chính

1. Kế toán chọn "Khấu trừ".
2. Chọn nhân viên.
3. Chọn loại khấu trừ.
4. Nhập số tiền.
5. Nhập lý do.
6. Chọn tháng áp dụng.
7. Nhấn "Lưu".
8. Hệ thống kiểm tra dữ liệu.
9. Hệ thống lưu khoản khấu trừ.

---

# 22. UC21 - Tính lương

## Thông tin chung

- **Mã:** UC21
- **Tên:** Tính lương
- **Actor:** Kế toán
- **Mục tiêu:** Tự động tính lương hàng tháng.
- **Tiền điều kiện:** Dữ liệu nhân viên và chấm công đã có.
- **Hậu điều kiện:** Bảng lương được tạo.

## Luồng chính

1. Kế toán chọn "Tính lương".
2. Chọn tháng cần tính.
3. Hệ thống lấy danh sách nhân viên.
4. Hệ thống lấy mức lương cơ bản.
5. Hệ thống lấy dữ liệu chấm công.
6. Hệ thống lấy dữ liệu tăng ca đã được duyệt.
7. Hệ thống lấy phụ cấp.
8. Hệ thống lấy thưởng.
9. Hệ thống lấy các khoản khấu trừ.
10. Hệ thống tính lương cho từng nhân viên.
11. Hệ thống hiển thị bảng lương.
12. Kế toán kiểm tra.
13. Kế toán lưu bảng lương.

## Công thức tính

### Tổng thu nhập

Tổng thu nhập
= Lương cơ bản
+ Tiền tăng ca
+ Phụ cấp
+ Thưởng
