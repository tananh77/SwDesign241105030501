### 1. Quy trình thiết kế các ca sử dụng
- Xác định danh sách ca sử dụng: Dựa trên các yêu cầu hệ thống và kết quả phân tích, xác định các chức năng chính của hệ thống. Các chức năng này sẽ được chuyển thành các ca sử dụng.
 
- Mô tả ca sử dụng: Với mỗi ca sử dụng, mô tả các thành phần sau:

- Tên ca sử dụng.

- Diễn viên tham gia (Actors): Ai hoặc hệ thống nào sẽ thực hiện hoặc tương tác với ca sử dụng.

- Mô tả mục đích: Ca sử dụng giúp giải quyết vấn đề gì.

- Luồng chính (Main Flow): Các bước chi tiết để thực hiện ca sử dụng.

- Luồng phụ (Alternative Flow) (nếu có): Các trường hợp ngoại lệ hoặc cách xử lý khác với luồng chính.

- Tạo biểu đồ ca sử dụng (Use Case Diagram): Sử dụng UML để trực quan hóa các ca sử dụng và mối quan hệ giữa chúng.

  ### 2. Danh sách các ca sử dụng cho hệ thống "Payroll System"
- Dựa trên phân tích của hệ thống Payroll System, các ca sử dụng chính bao gồm:

- Maintain Employee Information (Quản lý thông tin nhân viên).

- Maintain Timecard (Quản lý thời gian làm việc).

- Select Payment Method (Lựa chọn phương thức thanh toán).

- Process Payroll (Xử lý tính lương).

- Generate Paycheck (Tạo phiếu lương).

- Track Commissions (Theo dõi hoa hồng).

### 3. Ví dụ mô tả chi tiết một ca sử dụng: Maintain Timecard
- Tên ca sử dụng: Maintain Timecard

- Diễn viên tham gia (Actors): Nhân viên, Quản lý hệ thống.

- Mô tả mục đích: Ca sử dụng này cho phép quản lý thêm, sửa, hoặc xóa thông tin về thời gian làm việc của nhân viên.

- Luồng chính (Main Flow):

- Quản lý đăng nhập vào hệ thống Payroll System.

- Chọn chức năng "Maintain Timecard".

- Hệ thống hiển thị danh sách thời gian làm việc đã nhập trước đó.

- Quản lý chọn một trong các hành động sau:

- Thêm thời gian làm việc mới (Add Timecard).

- Sửa thời gian làm việc hiện có (Edit Timecard).

- Xóa thời gian làm việc (Delete Timecard).

- Hệ thống lưu thay đổi và hiển thị thông báo thành công.

- Luồng phụ (Alternative Flow):

- Trường hợp nhập thông tin sai:

- Hệ thống kiểm tra thông tin nhập vào.

- Nếu có lỗi (ví dụ: ngày không hợp lệ), hệ thống hiển thị thông báo và yêu cầu nhập lại.

 ### 4. Biểu đồ ca sử dụng (Use Case Diagram)

- Dưới đây là biểu đồ UML thể hiện các ca sử dụng chính trong hệ thống Payroll System:

- - ![This is a class diagram](https://www.planttext.com/api/plantuml/png/R98vRiCm44Lxde9GxyAnh295O6I1aKA005a76D3ZM16NW1mNEbkA72bN23UPSP22m7p-H_AJm-_FhvqZi7HHae4WOtdreZwacH4h3eulOZ5RqF26DdgvNgn7q5C_Eq8LtI8NeBEZfhmsryKoxoWexQXGqw-DkhPdxE9GWCCGm2_quvgCl-gJiGfeD3hom_eV-Z0gFsMFYRWhH8_I7ymxcCEnl4Kwcqnj2kNp2NGkODP8cVow-7lKQ84m0EACOah4jX072sBYJqQfqJaVrIMYOUnwaTNg8KJBpvha-bR-SJUtihwL3HlgM9LMyFkOHBkJXtgGOEUA3Tj8vPO499RbBcne4j7smTsZzrB3-3CGL6o7-XX-4Fi1003__mC0)

### 5. Tài liệu giải thích thiết kế
- Lý do đưa ra thiết kế:

- Maintain Employee Information: Cần thiết để đảm bảo thông tin nhân viên luôn chính xác và cập nhật, làm cơ sở cho các ca sử dụng khác.

- Maintain Timecard: Đây là yêu cầu cơ bản để ghi nhận giờ làm việc của nhân viên, hỗ trợ tính toán lương và kiểm tra hiệu suất.

- Select Payment Method: Tính năng linh hoạt cho phép nhân viên chọn cách họ muốn nhận lương, cải thiện trải nghiệm người dùng.

- Process Payroll: Là ca sử dụng cốt lõi của hệ thống, tập trung vào việc tính toán lương dựa trên thời gian làm việc, hoa hồng và các khoản khấu trừ.

- Generate Paycheck: Tự động tạo phiếu lương giúp đơn giản hóa quy trình thanh toán và cung cấp thông tin minh bạch cho nhân viên.

- Track Commissions: Đảm bảo rằng hoa hồng của nhân viên làm theo dự án được theo dõi chính xác.
