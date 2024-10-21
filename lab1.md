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

### 2. Cơ chế phân tích
-Cơ chế cần giải quyết:

-Cơ chế ghi nhận giờ làm việc: Nhân viên phải nhập bảng chấm công cho mỗi ngày làm việc, ghi lại số giờ và mã số công việc (charge number). Hệ thống phải tính lương làm thêm giờ khi số giờ vượt quá 8 giờ.

-Cơ chế tính lương: Hệ thống tính toán lương dựa trên giờ làm hoặc mức lương cố định. Đối với nhân viên có hoa hồng, tính toán dựa trên đơn hàng mua.

-Cơ chế hoa hồng: Tính toán số tiền hoa hồng dựa trên tổng số đơn hàng mua được ghi nhận và tỷ lệ hoa hồng (10%, 15%, 25%, 35%).

-Cơ chế thanh toán: Hệ thống sẽ tự động thực hiện thanh toán vào ngày định kỳ (thứ Sáu hàng tuần cho nhân viên theo giờ và ngày cuối tháng cho nhân viên lương cố định).

-Cơ chế bảo mật và xác thực: Mỗi nhân viên chỉ có quyền truy cập vào thông tin của họ. Quản trị viên có quyền thay đổi thông tin của toàn bộ nhân viên.

-Cơ chế tích hợp với cơ sở dữ liệu Project Management: Hệ thống phải tích hợp để đọc thông tin mã số công việc từ cơ sở dữ liệu DB2 mà không làm thay đổi nó.

![Diagram](https://www.planttext.com/api/plantuml/png/f5BBIWD14BplLpGvHN43NeTb2GOFWa8E_a2pwNtWF9RfpY6eN-R1J_8N72V3iXD5q1oxkhgehkwFj_Sr2thP6rqq6fdXrepQ7OZWkG0eWL9vjrCmM8cOHKCAMFnWkmYCU31avO6aTu6tdPU10C2agP4CN_usT56y5ibFXaTJLHMCa6-neRgEygDt3J4dwXADsrjHq6g7SZMjeARTPl8Rv3xDHV6pn6xGFZrwjDoIFryjpMoF2iwdYsIviOBxWQNAKZg6ugaB7V9_IVtVZgUlMLmleFH3rqjPno9_XcyxHNxvnRqyvSvFirgzr2VjBEmV-ckok_3Mdm000F__0m00)

### 3. Phân tích ca sử dụng: Select Payment
-Lớp phân tích:

-Lớp Employee: Quản lý thông tin nhân viên, bao gồm phương thức thanh toán mà nhân viên chọn.-

-Lớp Payment Method: Xác định các phương thức thanh toán mà nhân viên có thể chọn (nhận qua bưu điện, gửi vào tài khoản ngân hàng, hoặc nhận tại văn phòng).

-Lớp Payment Processor: Xử lý việc thanh toán vào ngày thanh toán định kỳ dựa trên phương thức thanh toán đã được chọn.\

![Diagram](https://www.planttext.com/api/plantuml/png/X95D2i8m48NtESKiAzWBk91kN0h56uHqq42I2SbaqREvw96yWe6qeZNMtVnzxpsOnttg8il0oHeX5LE0a_M6HaJXyrWhxQLZwELeqN4VI66C56hBC_AD1Y4M0MYFNzm18XfK_84q_htRYJLK5mfurP4nR4hz2UDBEIyQQIavtWnGX7-GUy3PxgLHxg6jsvV91MCoN77Dq99_VToX6_BFdW000F__0m00)

### 4. Phân tích ca sử dụng: Maintain Timecard
-Lớp phân tích:

-Lớp Employee: Lưu giữ thông tin bảng chấm công của nhân viên.

-Lớp Timecard: Ghi nhận giờ làm việc và mã số công việc cho từng ngày.

-Lớp Project Management Database: Cung cấp thông tin mã số công việc từ cơ sở dữ liệu DB2 để đối chiếu khi nhân viên ghi thông tin vào bảng chấm công.

![Diagram](https://www.planttext.com/api/plantuml/png/d9DDReCm48Ntd6B4YbG1ALk4K1QDr4hDfie59k0GLyP6zX0rQdkoBdgaNg76_9GGL4NT83FpvfldiVtz-RKsX9hgKdYPG6DWKrP2dHc3DmyW1DRzFkOnS4ak9h5aCHZIN1Os063gVSbfnqkMeSu3wXOnzA65z-5r_3xKyNljc3_NqxcyHxADcs-ha_aaGefGFAXQcnWEGY4vUvZdJTUD97qEyg5Y2SUHSk6a6Ogi5ZQv6qZ1ZFajIYoOdkp1efwueQHNfRSEnvciAgrEx4hN3Q4LQVR2icjMfrdQF1eb-xEPCVvSY_PaayGMC7t0ZAMjpnCAtWpdBwSnx9KI3EKlUOklRam3-H-awLZzbGzX6ARWt_b3oMsgnePtuIcAtjFBz7357K7puaWDPHL5utPhUxtii_W1003__mC0)
![Diagram](https://www.planttext.com/api/plantuml/png/Z58xRWCX4EqvnPHhoRx0IexSM8gBD8ulC859GZGB20PBFbiA7ybN24XBVekYT33lo-VsVjqbmIXvOeLQV8Jz5DXVY5GeOwjjG2TmiXDfZEO17RvGx6BTuJ4pATKyONFtYOo0njJDtacy30Q5rl3gSqmhrJW_-HfPPowyanVa-qeTLbtlkUO8AJzDLjfua7dnbJ0plujhvH7EoBPs-aDRYR3fnSvYwzsHKcPH2baMKzXkGM8c1RyTkcV14A8_BmiTIYNYH5t_Pop8FmCYlP5UNjR1h0k4oRkIuunQtbqnQwymGfCz2afEQbSavNDz0000__y30000)

### 5. Hợp nhất kết quả phân tích

-Sau khi phân tích hai ca sử dụng, kết quả sẽ cho thấy các lớp Employee là lớp chung quan trọng giữa các ca sử dụng. 

-Lớp này chịu trách nhiệm quản lý thông tin về nhân viên, bao gồm cả phương thức thanh toán và bảng chấm công. 

-Kết quả phân tích hai ca sử dụng cần được hợp nhất bằng cách xác định các điểm chung, như việc sử dụng các thuộc tính và lớp dùng chung (ví dụ: Employee, Payment Method và Timecard), và xây dựng một hệ thống hoàn chỉnh quản lý cả quá trình thanh toán và chấm công.

![Diagram](https://www.planttext.com/api/plantuml/png/f5HBRi8m4Dtd51QhW02fsmX5LJzIAnK9LLnWI0P8wzZ8dg2YjYVheaVg5UeuJXe7g6ZPHF7Cc-StusT_VNnUQW95HSw3X8FMx3RVSBb3PAy1OoE6RdcVHYmJP6C2SeoO9fM9bGriO9UZe2dIMXhShBqq0COqSap8YuU_5VMhgcAHPpJFSan0fI6vduZLeNxm7ZZPTSZ9hh5jsOTQiStV09b-oc-54sadGfA0tyb2wOWjkGIoyY1Dorrl1QbTc3OLGxPk8QjE4k19mKrotZ25BV5UxxQ3oSGeHBM41EFOKcoKJ51h1mqXbuKWjycmwIrgpgz5VmrwxUei-LbaLo2Uvmg4Ng8wdytLp2e6gTpnUTumetp8D4syALL3KRWo6LH_TTOPYckZJK702bN7RxNM6XMVQcHhg8tHjSKzd3DitxNyPAxICSpGv45BKL_F0y8V2uv7FBO5dfL6_arfn1PISWJnmpo55slfXlaVJCspqxleiP7ALciQnNRXloR7SEFneDTG1tksikXHYHnq6TktOpn-Ypjfp-y7ybq_U3irWav2bVCBl67Q_RpqfNcTp6Fz3G00__y30000)
