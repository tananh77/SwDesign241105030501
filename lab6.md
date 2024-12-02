### 1. Quy trình thiết kế lớp
1.1 Xác định các lớp chính

- Dựa trên các ca sử dụng và hệ thống con đã thiết kế:

- Employee

- Timecard

- Paycheck

- PayrollController

- Payment

- Commission

- Project

- BankSystem

-PrintService

### 2. Ví dụ chi tiết: Lớp Timecard (Ca sử dụng Maintain Timecard)

- Thuộc tính

- timecardId: Mã định danh duy nhất cho Timecard.

- employeeId: Mã nhân viên liên kết.

- date: Ngày làm việc.

- hoursWorked: Số giờ làm việc trong ngày.

- chargeCode: Mã công việc liên kết (từ hệ thống quản lý dự án).

- Phương thức

- createTimecard(employeeId: String, date: Date, hoursWorked: int, chargeCode: String): Timecard

- Tạo một Timecard mới.

- updateTimecard(hoursWorked: int, chargeCode: String): void

- Cập nhật số giờ làm việc hoặc mã công việc.

- saveTimecard(): void

- Lưu thông tin Timecard vào cơ sở dữ liệu.

- Quan hệ

- Kết hợp: Timecard liên kết với Employee qua employeeId.

- Phụ thuộc: Sử dụng dữ liệu từ ProjectManagementDatabase để lấy chargeCode.

### 3. Biểu đồ lớp UML
