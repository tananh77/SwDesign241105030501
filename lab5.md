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
- - ![This is a class diagram](https://www.planttext.com/api/plantuml/png/Z9BDIiD058NtynINxFi2BgHOYmWMGjCNc4w7P6pcJaWcXI2kNRXqBLX1X89emLMpw2BGzyWJ-0hUYVMdZOApc-5yvvmxCs_bkfjPdjfSnopXOif32PxFYzJ4CGH5PgNsu881BM5qOb2Y1Q-lazWKKWuu4g3fBCZ7sLRDC-WFWdrafBGKF9ti2aUzbf32suR-RpBNqK-Da5ccCDm3saJFQAr8Qd1Nsgumb8b9RSjp6B1BncWsw7GENG8Sa6kE8OXwzP20ZQfNsX0865Nt23DLBT1ZDEGVnAGkdo5MTNcL4rsNjmf2nH7YwauJJUV2O_-Y8yE136umz9XJDaG3dDJbauAYMkGEUtH172EmfffJjwtKE-8u_NnkWaRajHGGENDqdOnBknQHnuPRmayLlP9CPqh8XZb5I0XOhNE8Do-RkQlI-nARSodiztyvvfQFUVP1dj4unS_hewmbDFsw4YVkRx9t0000__y30000)

### 3. Mô tả chi tiết từng hệ thống con
3.1 EmployeeManagementSubsystem (EMS)
- Chức năng:

- Quản lý hồ sơ nhân viên, bao gồm tên, địa chỉ, số tài khoản, và thông tin liên quan đến lương.

- Cung cấp thông tin cho các hệ thống con khác để xử lý tính toán.

- Các lớp chính:

- Employee: Định nghĩa các thuộc tính và phương thức để lưu trữ và truy xuất thông tin nhân viên.

- EmployeeController: Điều phối thao tác thêm, sửa, và xóa nhân viên.
3.2 TimecardSubsystem (TCS)

- Chức năng:

- Ghi nhận thời gian làm việc hàng ngày của nhân viên.

- Tích hợp với hệ thống quản lý dự án để lấy thông tin mã công việc.

- Các lớp chính:

- Timecard: Lưu thông tin thời gian làm việc, số giờ, và mã công việc.

- TimecardController: Điều phối việc nhập và chỉnh sửa thông tin thẻ thời gian.

3.3 PaymentSubsystem (PS)

- Chức năng:

- Quản lý phương thức thanh toán (chuyển khoản hoặc tiền mặt).

- Tích hợp với hệ thống ngân hàng để thực hiện giao dịch.

- Các lớp chính:

- Payment: Chứa thông tin thanh toán như số tiền và phương thức.

- BankInterface: Kết nối với hệ thống ngân hàng.

3.4 PayrollProcessingSubsystem (PPS)

- Chức năng:

- Tính toán lương dựa trên thời gian làm việc, hoa hồng, và các khấu trừ.

- Các lớp chính:

- PayrollProcessor: Thực hiện tính toán và lưu trữ lương.

- PayrollController: Điều phối các thao tác xử lý lương.

3.5 CommissionSubsystem (CS)

- Chức năng:

- Theo dõi và tính toán hoa hồng của nhân viên theo dự án.

- Lấy thông tin từ hệ thống quản lý dự án.

- Các lớp chính:

- Commission: Chứa thông tin hoa hồng theo dự án.

- CommissionController: Điều phối việc tính toán hoa hồng.

3.6 ReportingSubsystem (RS)

- Chức năng:

- Tạo phiếu lương và báo cáo liên quan.

- Gửi yêu cầu in phiếu lương qua PrintService.

- Các lớp chính:

- Report: Định nghĩa cấu trúc phiếu lương và báo cáo.

- PrintController: Kết nối với dịch vụ in.
