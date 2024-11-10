### 1. Phân tích các ca sử dụng còn lại trong hệ thống Payroll System
Dưới đây là danh sách các ca sử dụng chính của hệ thống Payroll System:
Maintain Employee Information: Cho phép quản lý thêm mới, chỉnh sửa hoặc xóa thông tin nhân viên.
Select Payment Method: Cho phép lựa chọn phương thức thanh toán cho từng nhân viên (tiền mặt, chuyển khoản ngân hàng, hoặc qua ngân hàng).
Process Payroll: Thực hiện quá trình tính toán lương cho tất cả nhân viên dựa trên các thông tin thời gian làm việc và hoa hồng, cùng các khoản khấu trừ nếu có.
Generate Paycheck: Tạo phiếu lương cho nhân viên sau khi tính toán xong.
Maintain Timecard: Quản lý thời gian làm việc của nhân viên bằng cách cho phép thêm, chỉnh sửa và xóa các thẻ thời gian.
Track Commissions: Theo dõi và ghi nhận hoa hồng cho những nhân viên được hưởng hoa hồng từ các dự án.

### 2. Viết mã Java cho ca sử dụng Maintain Timecard
Dưới đây là mã Java mô phỏng ca sử dụng "Maintain Timecard," trong đó bao gồm các phương thức để thêm, sửa, và xóa thời gian làm việc cho nhân viên:
import java.util.ArrayList;
import java.util.List;

class Timecard {
    private String employeeId;
    private String date;
    private int hoursWorked;

    public Timecard(String employeeId, String date, int hoursWorked) {
        this.employeeId = employeeId;
        this.date = date;
        this.hoursWorked = hoursWorked;
    }

    // Getters and setters
    public String getEmployeeId() { return employeeId; }
    public String getDate() { return date; }
    public int getHoursWorked() { return hoursWorked; }

    public void setHoursWorked(int hoursWorked) {
        this.hoursWorked = hoursWorked;
    }

    @Override
    public String toString() {
        return "Timecard [Employee ID=" + employeeId + ", Date=" + date + ", Hours Worked=" + hoursWorked + "]";
    }
}

class TimecardManager {
    private List<Timecard> timecards;

    public TimecardManager() {
        timecards = new ArrayList<>();
    }

    // Add a new timecard
    public void addTimecard(String employeeId, String date, int hoursWorked) {
        Timecard timecard = new Timecard(employeeId, date, hoursWorked);
        timecards.add(timecard);
        System.out.println("Timecard added: " + timecard);
    }

    // Edit an existing timecard
    public void editTimecard(String employeeId, String date, int newHoursWorked) {
        for (Timecard timecard : timecards) {
            if (timecard.getEmployeeId().equals(employeeId) && timecard.getDate().equals(date)) {
                timecard.setHoursWorked(newHoursWorked);
                System.out.println("Timecard updated: " + timecard);
                return;
            }
        }
        System.out.println("Timecard not found for employee ID: " + employeeId + " on date: " + date);
    }

    // Delete a timecard
    public void deleteTimecard(String employeeId, String date) {
        timecards.removeIf(timecard -> timecard.getEmployeeId().equals(employeeId) && timecard.getDate().equals(date));
        System.out.println("Timecard deleted for employee ID: " + employeeId + " on date: " + date);
    }

    // Display all timecards
    public void displayTimecards() {
        System.out.println("All timecards:");
        for (Timecard timecard : timecards) {
            System.out.println(timecard);
        }
    }
}

public class PayrollSystem {
    public static void main(String[] args) {
        TimecardManager timecardManager = new TimecardManager();

        // Add timecards
        timecardManager.addTimecard("E001", "2024-11-01", 8);
        timecardManager.addTimecard("E002", "2024-11-01", 6);

        // Edit a timecard
        timecardManager.editTimecard("E001", "2024-11-01", 9);

        // Delete a timecard
        timecardManager.deleteTimecard("E002", "2024-11-01");

        // Display all timecards
        timecardManager.displayTimecards();
    }
}

