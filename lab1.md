### 1. Phân tích kiến trúc
- Đề xuất kiến trúc: Kiến trúc phù hợp cho bài toán là kiến trúc client-server 3 tầng với các thành phần:
- Client Layer: Ứng dụng desktop cho người dùng cuối, bao gồm nhân viên và Payroll Administrator. Mỗi nhân viên có thể nhập bảng chấm công, lựa chọn phương thức thanh toán, xem báo cáo, và Quản trị viên có thể quản lý thông tin nhân viên.

- Business Logic Layer: Chịu trách nhiệm xử lý logic nghiệp vụ, tính toán lương, xử lý giờ làm, hoa hồng, và thanh toán.

- Data Layer: Tầng cơ sở dữ liệu gồm 2 phần chính:

- Cơ sở dữ liệu nội bộ: Lưu trữ thông tin nhân viên, bảng chấm công, phiếu lương.

- Cơ sở dữ liệu Project Management (DB2): Cung cấp thông tin về mã số công việc (charge numbers), được sử dụng để đối chiếu khi tính toán giờ làm việc.
- ###  Giải thích lý do lựa chọn kiến trúc:

- Kiến trúc client-server cho phép tách biệt giữa giao diện người dùng và xử lý nghiệp vụ, giúp dễ dàng bảo trì và nâng cấp.

- Việc tách biệt Business Logic Layer giúp đảm bảo tính bảo mật và khả năng mở rộng của hệ thống.

- Data Layer gồm hai cơ sở dữ liệu giúp hệ thống có thể sử dụng lại cơ sở dữ liệu hiện có mà không cần phải thay đổi cấu trúc cũ.

- ![Diagram](https://www.planttext.com/api/plantuml/png/P59BRW8n3DtFAI9MxOOZL9JI1HAeemeEu7eCfEGpjPDAeugJTT4ZzGfDWCbqX9VlsNxlEVdz_fb900xHcge5FCAUrAHc4d81WlPEhQ0ZdgYlIYaq8AAsGhnqWNW7I6SyLwEbDT1jbtVtL-G0hZ5KkW7pkZDxgaxLe3QFeXsbnIk_rtYhr_CNkjT3C1WD1AgXOszCaGr9wRZHbWfYmIMXPziQtn59mSkA9s-j5kdjvIAtyupKQxz6SnqSUrz0W5l76Nr4p9cANUySOTZupBs13Eu-8d5NitzFzFhirARRB-QbGOBduZwF5uOfiAPFocaHk1cHbzHrP3makHTkYFyb63_YTFemFdCrFdhcXr3LZ5oJFimV0000__y30000)

