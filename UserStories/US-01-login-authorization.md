# US-01 - Đăng nhập và phân quyền

## Epic

Authentication & Authorization

## Actor

- User
- Admin

## User Story

As a user, I want to log in to the system and access functions according to my role, so that I can use the system securely.

## Description

Người dùng đăng nhập vào hệ thống bằng tài khoản và mật khẩu. Sau khi đăng nhập thành công, hệ thống xác định quyền dựa trên role của người dùng.

## Acceptance Criteria

- [ ] Người dùng có thể nhập username/email.
- [ ] Người dùng có thể nhập mật khẩu.
- [ ] Hệ thống kiểm tra thông tin đăng nhập.
- [ ] Đăng nhập thành công nếu thông tin hợp lệ.
- [ ] Hiển thị lỗi nếu thông tin đăng nhập không hợp lệ.
- [ ] Không cho đăng nhập nếu tài khoản bị khóa.
- [ ] Hệ thống xác định đúng role của người dùng.
- [ ] Người dùng chỉ truy cập được các chức năng được phép.

## Priority

High

## Related Requirement

FR-AUTH-01, FR-AUTH-05

## Related Use Case

UC01 - Đăng nhập
