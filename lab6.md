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

- - ![This is a class diagram](https://www.planttext.com/api/plantuml/png/Z5H1Ri8m4Bpd5HQd8C47SgYGe0SEbP1QgUV5NaAAuuri1mbLVLaFVLA_q0tO9Y558WU2PcTdnhjMVhz_5iw3zMsjCwd1EV5SDvfEYE8p4_pC1GPWhGhnwcrbob0mKECD14fPTEu6tO8vhCsE1h0G9Vfeja8FbNRvj4Z-WTGs2Zn6i2CSgLBPLnRYlbKrIh0gnVK16CMzUuxEe10h_Wt0dbhhtiaUaAcLyG6MUx0bBadXpK6aHMwEIVAnqQpdCHl9p_vHvdD6lS4Waic38kTXNGGS7A_jepbku6H9woKPtxtHXe4AqLYIlDD0o8UY4hHiDGVZSbVQQGAVzclGNafoZ_BGrUF_WV4PIGji0l3u0g6crlYXUSDrttVkXLROaAl6rMicInye_GiOAB56utbni0M7QIXyTvTftdbpuL-3JLD2ranNT3vFjxiGaorgCgKJdYPzojDzTswooB9uH1VMBIJxkqasNb-d56MviNNtQN4GJ8ixO-u2ZUe-2rds1m00__y30000)
 
### 4. Biểu đồ trạng thái: Timecard

- - ![This is a class diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bUqLgo2hgwTWbzgEHSGWzcUUG55-Ub5gSN52bOAIiv5gOabgGeXcRcfoOb5AKfSID8WrQ45AK3v591I21D9AKmEf2uuiGoY2iH0KWCH1wa0keNB8JKl1UGk00000F__0m00)
 
### 5. Gợi ý cho các lớp khác

- Lớp Employee

- Thuộc tính:

- employeeId, name, address, bankInfo, paymentMethod.

- Phương thức:

- getEmployeeDetails(), updateEmployee().

- Lớp PayrollController

- Phương thức:

- processPayroll(): Xử lý toàn bộ lương.

- calculatePay(): Tính toán lương.

- generatePaycheck(): Tạo phiếu lương.

- Lớp Paycheck

- Thuộc tính:

- paycheckId, employeeId, amount.

- Phương thức:

- printPaycheck(), depositPaycheck().

- Lớp Commission

- Thuộc tính:

- commissionId, employeeId, projectId, commissionRate.

- Phương thức:

- calculateCommission().
