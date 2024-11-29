### 1. Các hệ thống con trong Payroll System
 Dựa trên tài liệu và các ca sử dụng chính trong hệ thống, các hệ thống con được xác định bao gồm:

1. EmployeeManagementSubsystem

- Quản lý thông tin nhân viên như thêm, chỉnh sửa, và xóa.

- Lưu trữ các thông tin cần thiết như tài khoản ngân hàng, địa chỉ, và loại hợp đồng.

2. TimecardSubsystem

- Ghi nhận và quản lý dữ liệu thời gian làm việc.

-  Tích hợp với hệ thống quản lý dự án để lấy mã công việc.

3. PaymentSubsystem

- Xử lý thanh toán, bao gồm các giao dịch qua ngân hàng hoặc tiền mặt.

- Gửi thông tin giao dịch đến hệ thống ngân hàng.

4. PayrollProcessingSubsystem

- Tính toán lương dựa trên thời gian làm việc, hoa hồng, và các khoản khấu trừ.

- Tích hợp với các hệ thống con khác để xử lý dữ liệu.

5. CommissionSubsystem

- Theo dõi và quản lý hoa hồng của nhân viên theo dự án.

- Lấy dữ liệu từ hệ thống quản lý dự án.

6. ReportingSubsystem

- Tạo báo cáo và phiếu lương.
  
- Gửi yêu cầu in phiếu lương.

###  2. Mô hình kiến trúc hệ thống con
Dưới đây là biểu đồ UML Component Diagram thể hiện các hệ thống con và mối quan hệ của chúng.
