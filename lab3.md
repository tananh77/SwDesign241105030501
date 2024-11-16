### 1. Biểu Đồ Ngữ Cảnh Của Các Hệ Thống Con

- Biểu đồ ngữ cảnh của mỗi hệ thống con mô tả các mối quan hệ giữa hệ thống đó và các hệ thống khác trong Payroll System, cùng các thành phần bên ngoài. Mỗi hệ thống con thực hiện một vai trò nhất định, được kết nối với các hệ thống hoặc thành phần khác để đảm bảo hoạt động tổng thể của Payroll System.

- Hệ Thống Con 1: BankSystem

- Hệ thống con BankSystem chịu trách nhiệm xử lý các giao dịch thanh toán qua ngân hàng cho nhân viên. Dưới đây là một biểu đồ ngữ cảnh của BankSystem và mô tả chi tiết về hệ thống con này.

- Biểu đồ ngữ cảnh của BankSystem

- ![This is a class diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTHQd99ObvwJgg2Ka1YPL5-Jev2S6LnIMgkaa8rbm8GH3ibvcL3X6AvQhcuaFaAkhfs2agk5IMfHNc9EGeW6GM_r9Bo_A9i9GKh1VVCn7o5b8UxkvCp5FBI3o_AKyWul20ldSiXDIy5P3S0003__mC0)

- Mô tả hệ thống con BankSystem

  - Chức năng: BankSystem quản lý các thanh toán qua ngân hàng, bao gồm việc kiểm tra thông tin tài khoản nhân viên và thực hiện giao dịch để chuyển tiền lương vào tài khoản của họ.

  - Interface của BankSystem
  
  - BankTransfer API: Giao diện này cho phép Payroll System gửi yêu cầu chuyển khoản cho ngân hàng.
  
  - AccountValidation API: Dùng để xác thực thông tin tài khoản của nhân viên trước khi thực hiện giao dịch.

  ### Hệ Thống Con 2: PrintService

 - Hệ thống con PrintService chịu trách nhiệm in phiếu lương cho nhân viên. Payroll System sẽ gửi thông tin cần thiết để PrintService tạo các bản in theo yêu cầu.

 - Biểu đồ ngữ cảnh của PrintService

 - ![This is a class diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTHQd99ObvwJgg2Ka1YPL5-Jev2S6LnIMgkaa8rbm8GH3ibvcL3X6AvQhcuaFaAkhfs2agk5IMfHNc9EGeW6GM_r9Bo_A9i9GKh1VVCn7o5b8UxkvCp5FBI3o_AKyWul20ldSiXDIy5P3S0003__mC0)

 - Mô tả hệ thống con PrintService
   
 - Chức năng: PrintService xử lý yêu cầu in phiếu lương từ Payroll System và gửi chúng đến máy in.
   
 - Interface của PrintService:
   
 - PrintRequest API: Giao diện cho phép Payroll System yêu cầu PrintService in phiếu lương.
   
 - PrintStatus API: Cung cấp trạng thái tiến trình in, giúp Payroll System theo dõi quá trình in của từng yêu cầu.

   ### Hệ Thống Con 3: ProjectManagementDatabase
 - ProjectManagementDatabase lưu trữ và quản lý thông tin về các dự án, giúp Payroll System tính toán lương cho những nhân viên làm việc theo dự án.

 - Biểu đồ ngữ cảnh của ProjectManagementDatabase

 - ![This is a class diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTHQd99ObvwJgg2Ka1YPL5-Jev2S6LnIMgkaa8rbm8GH0SKvMS15VacvYMcf-QcvfMu99Oa9YKMfyPorN9nuP5MqDMr0veAaLT0A81ROANWyt3Nqag5b8UxrolaP3xStLuAOczKEBmmZyiXDIy5v40k00000F__0m00)

  ### 4. Biểu đồ ngữ cảnh của Payroll System với tất cả các hệ thống con

 - ![This is a class diagram](https://www.planttext.com/api/plantuml/png/T50nJiD04Epl5IFt-K0A5A4WX0GeKaf4iJWh-yXvZSvh4YkYfk0J18aQQECYXQNymo_W2_XY4Q1WgzNCpkpiVjRRKQ7ajSoSyHmhIU8OqOGgdpk7QLKePn5M1brT7PFCU-Yw1oRUYaxPtzkO3r1-snbTa5326OkEIUc6Yev_CEQt1GQ38qGdIsKlv10ONB8kSZ-FCCIffHopjdwAKqZIl0ZIvbaIytTfRxA7s0VPcU0kjUrcMyBjtdVhNl5Vfc_vdiVFmE7o8SxRpMiLWhp1sRP-B4F_WMOjPiGo2v_x0W00__y30000)

