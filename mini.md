
PHẦN I – PHÂN TÍCH HỆ THỐNG VÀ THU THẬP YÊU CẦU

1. Nhận diện 5 thành phần của Hệ thống Thông tin (HTTT) DentCare
   	Phần cứng (Hardware): Máy tính để bàn/laptop cho Lễ tân, Nha sĩ, Quản lý; máy chủ CSDL (Cloud/On-premise); máy in hóa đơn/phiếu hẹn; thiết bị di động (smartphone/tablet) của bệnh nhân và nha sĩ.
   	Phần mềm (Software): Hệ điều hành (Windows/macOS/iOS/Android); Hệ quản trị CSDL (PostgreSQL/MySQL); Ứng dụng Web/Mobile DentCare; Dịch vụ tích hợp gửi SMS/Email OTP & nhắc lịch.
   	Dữ liệu (Data): Hồ sơ bệnh nhân, Thông tin lịch hẹn, Hồ sơ khám & chẩn đoán điều trị, Danh mục dịch vụ & đơn giá, Hóa đơn & Lịch sử thanh toán, Tài khoản & Quyền truy cập.
   	Quy trình (Process): Quy trình đăng ký & đặt lịch hẹn; Quy trình tiếp đón bệnh nhân; Quy trình khám, chẩn đoán & điều trị; Quy trình lập hóa đơn & thanh toán; Quy trình quản lý danh mục & báo cáo doanh thu.
   	Con người (People): Bệnh nhân, Nhân viên Lễ tân, Nha sĩ (Bác sĩ nha khoa), Quản lý phòng khám, Quản trị viên hệ thống (IT Admin).
   	Phân loại hệ thống: DentCare thuộc loại Hệ thống Xử lý Giao dịch (TPS - Transaction Processing System).
   Lý do: Hệ thống trực tiếp ghi nhận và xử lý các giao dịch nghiệp vụ hàng ngày với tần suất cao (đặt/hủy lịch hẹn, đăng ký khám, tạo hóa đơn, thu tiền), yêu cầu tính nhất quán (ACID), phản hồi thời gian thực và đảm bảo tính chính xác của dữ liệu tài chính cũng như lịch hẹn.
2. Các bước SDLC và Lựa chọn Mô hình Phát triển
   Các bước trong quy trình SDLC cho dự án DentCare:
   	Lập kế hoạch & Khảo sát ban đầu (Planning & Feasibility): Xác định mục tiêu số hóa, ngân sách, nhân lực và tiến độ.
   	Phân tích yêu cầu (Requirement Analysis): Thu thập yêu cầu từ 4 nhóm người dùng, xác định yêu cầu chức năng/phi chức năng, lập tài liệu SRS.
   	Thiết kế hệ thống (System Design): Thiết kế kiến trúc tổng thể, mô hình hóa quy trình (UML: Activity, Use Case, Class, Sequence Diagram), thiết kế CSDL và Giao diện (UI/UX).
   	Phát triển & Cài đặt (Implementation/Coding): Lập trình các phân hệ (Front-end, Back-end, CSDL, Tích hợp SMS API).
   	Kiểm thử hệ thống (Testing/QA): Kiểm thử đơn vị (Unit Test), Kiểm thử tích hợp (Integration Test), Kiểm thử chấp nhận (UAT) với Lễ tân và Nha sĩ.
   	Triển khai & Chuyển giao (Deployment): Cài đặt hệ thống, chuyển đổi dữ liệu từ sổ sách thủ công, đào tạo nhân viên sử dụng.
   	Bảo trì & Nâng cấp (Maintenance): Xử lý lỗi phát sinh, cập nhật tính năng mới theo phản hồi thực tế.
   Lựa chọn mô hình phát triển: Agile / Scrum
   Giải thích lý do:
   	Phòng khám hiện vận hành thủ công, yêu cầu người dùng có thể thay đổi hoặc làm rõ dần trong quá trình chuyển đổi số.
   	Agile cho phép chia nhỏ dự án thành các Sprint (2-3 tuần), bàn giao sớm từng phân hệ cốt lõi (như Đặt lịch -> Khám bệnh -> Thanh toán -> Báo cáo).
   	Lễ tân và Nha sĩ có thể dùng thử và góp ý ngay sau mỗi Sprint, giúp giảm rủi ro thiết kế sai nghiệp vụ thực tế.
3. Đánh giá Stakeholders và Kỹ thuật thu thập yêu cầu
   | Stakeholder | Nguồn yêu cầu                | Kỹ thuật thu thập đề xuất                            | Lý do lựa chọn                                                                                          |
   | ----------- | ------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
   | Bệnh nhân | Nguồn ngoài (End-user)        | Khảo sát trực tuyến (Survey/Form) & Phỏng vấn ngắn  | Thu thập kỳ vọng về trải nghiệm đặt lịch nhanh chóng, tiện lợi trên di động.                |
   | Lễ tân    | Nguồn nội bộ (Vận hành)    | Quan sát trực tiếp (Observation) & Phỏng vấn sâu     | Quan sát thao tác ghi sổ sách thủ công để tối ưu hóa UI/UX đăng ký & thanh toán.            |
   | Nha sĩ     | Nguồn nội bộ (Chuyên môn)  | Phỏng vấn cá nhân (Interview) & Workshop               | Tìm hiểu quy trình chẩn đoán, ghi chép hồ sơ bệnh án chuẩn nha khoa.                           |
   | Quản lý   | Nguồn nội bộ (Chiến lược) | Phỏng vấn trực tiếp & Phân tích tài liệu báo cáo | Xác định nhu cầu thông tin báo cáo doanh thu, hiệu suất làm việc và cấu trúc giá dịch vụ. |
4. Yêu cầu kỹ thuật
   A. Yêu cầu chức năng (Functional Requirements):
   	Phân hệ Đặt lịch: Cho phép Bệnh nhân/Lễ tân tìm khung giờ trống, đặt lịch, đổi lịch, hủy lịch hẹn.
   	Phân hệ Khám bệnh: Cho phép Nha sĩ tra cứu lịch sử khám, ghi chẩn đoán, chỉ định dịch vụ y tế và lưu Hồ sơ điều trị.
   	Phân hệ Thanh toán: Cho phép Lễ tân tự động tạo Hóa đơn từ Hồ sơ điều trị, ghi nhận thanh toán (Tiền mặt/Chuyển khoản).
   	Phân hệ Báo cáo & Danh mục: Cho phép Quản lý thêm/sửa dịch vụ, xem báo cáo doanh thu theo ngày/tháng/lượt khám.
   B. Yêu cầu phi chức năng (Non-Functional Requirements):
   	Hiệu năng (Performance): Thời gian phản hồi hệ thống < 2 giây cho các thao tác tra cứu/đặt lịch.
   	Bảo mật (Security): Mã hóa thông tin cá nhân và hồ sơ bệnh án (tuân thủ quy định bảo mật dữ liệu y tế); Phân quyền RBAC nghiêm ngặt.
   	Khả dụng (Availability): Hệ thống hoạt động liên tục 99.9% trong giờ làm việc của phòng khám.
   	Dễ sử dụng (Usability): Giao diện thân thiện, Lễ tân có thể hoàn thành tạo hóa đơn trong dưới 3 thao tác click.
   C. Viết User Story cho các chức năng chính:
   	US01 (Bệnh nhân): Là Bệnh nhân, tôi muốn đặt lịch hẹn trực tuyến theo khung giờ trống của Nha sĩ, để tôi chủ động thời gian và không phải chờ đợi lâu tại phòng khám.
   	US02 (Lễ tân): Là Lễ tân, tôi muốn đặt lịch hẹn cho bệnh nhân trực tiếp hoặc qua điện thoại, để sắp xếp lịch khám chính xác và không bị trùng lịch.
   	US03 (Nha sĩ): Là Nha sĩ, tôi muốn xem lịch làm việc và ghi nhận hồ sơ điều trị của bệnh nhân sau khi khám, để lưu trữ lịch sử y tế và chuyển thông tin cho Lễ tân thanh toán.
   	US04 (Lễ tân): Là Lễ tân, tôi muốn tạo hóa đơn tự động từ hồ sơ điều trị và ghi nhận thanh toán, để thu tiền chính xác và xuất hóa đơn nhanh chóng.
   	US05 (Quản lý): Là Quản lý, tôi muốn xem báo cáo doanh thu và tổng số lượt khám theo ngày/tháng, để đánh giá hiệu quả kinh doanh của phòng khám.
   PHẦN II – ACTIVITY DIAGRAM & USE CASE
5. Activity Diagram (Sơ đồ hoạt động)
   A. Quy trình Đặt lịch hẹn:

B. Quy trình Khám bệnh và Thanh toán (Sử dụng Swimlanes):

2. Use Case Diagram và Đặc tả Use Case

PHẦN III –CLASS DIAGRAM

PHẦN IV – SEQUENCE DIAGRAM

PHẦN V – RÀNG BUỘC NGHIỆP VỤ VÀ PHÂN QUYỀN

1. Validation Rules (Xác thực dữ liệu đầu vào)
   Số điện thoại bệnh nhân: Phải đúng 10 chữ số, chỉ chứa ký tự số và phải bắt đầu bằng chữ số 0 (Regex: ^0\d{9}$).
   Ngày sinh (DOB): Phải là ngày hợp lệ và DOB <= CurrentDate().
   Ngày hẹn (Appointment Date): Phải >= CurrentDate(). Không cho phép đặt lịch ngược về quá khứ.
   Đơn giá dịch vụ (Unit Price): Phải thuộc kiểu số thực dương và UnitPrice > 0.
   Số lượng dịch vụ (Quantity): Phải thuộc kiểu số nguyên dương và Quantity >= 1.
2. Ma trận Phân quyền (Role-Based Access Control - RBAC)

| Chức năng / Phân hệ                     | Bệnh nhân               | Lễ tân     | Nha sĩ      | Quản lý    |
| ------------------------------------------- | ------------------------- | ------------ | ------------ | ------------ |
| Xem hồ sơ & lịch hẹn cá nhân          | Read                      | Read/Write   | Read         | Read         |
| Đăng ký / Cập nhật hồ sơ bệnh nhân | No Access                 | Full Control | Read         | Read         |
| Đặt / Hủy lịch hẹn                     | Create/Cancel (Cá nhân) | Full Control | Read         | Read         |
| Khám bệnh & Ghi hồ sơ điều trị       | No Access                 | No Access    | Full Control | Read         |
| Tạo hóa đơn & Thu tiền thanh toán     | No Access                 | Full Control | No Access    | Read         |
| Quản lý Danh mục dịch vụ & Giá        | No Access                 | No Access    | No Access    | Full Control |
| Xem báo cáo thống kê doanh thu          | No Access                 | No Access    | No Access    | Full Control |

HIỂN THỊ VÀ BÁO CÁO

1. Báo cáo Tồn kho / Danh mục Dịch vụ Nha khoa
   Mục tiêu: Hiển thị danh sách toàn bộ các dịch vụ nha khoa hiện đang cung cấp tại DentCare kèm theo đơn giá chuẩn để phục vụ niêm yết và chọn khi điều trị.
   Cấu trúc dữ liệu hiển thị: Mã dịch vụ, Tên dịch vụ, Đơn vị tính, Đơn giá (VNĐ), Trạng thái kinh doanh (Đang áp dụng/Ngừng).
2. Báo cáo Doanh thu theo Kỳ
   Mục tiêu: Tổng hợp kết quả hoạt động tài chính của phòng khám theo khoảng thời gian tùy chọn (theo ngày, tuần, tháng, quý, năm).
   Chỉ số tổng hợp:
   Tổng số lượt khám trong kỳ.
   Tổng doanh thu thu được (Tổng tiền mặt + Tổng chuyển khoản).
   Danh sách chi tiết từng Hóa đơn: Mã HD, Ngày tạo, Tên Bệnh nhân, Nha sĩ khám, Số tiền, Phương thức thanh toán.
3. Tra cứu Hồ sơ Bệnh nhân
   Mục tiêu: Cho phép Lễ tân và Nha sĩ tìm kiếm nhanh thông tin bệnh nhân để phục vụ tái khám hoặc xem lịch sử điều trị.
   Tiêu chí tìm kiếm: Tìm kiếm theo Mã bệnh nhân (patientId) hoặc Số điện thoại.
   Thông tin kết quả:
   Thông tin hành chính: Họ tên, Ngày sinh, Giới tính, Số điện thoại, Địa chỉ.
   Lịch sử khám bệnh: Danh sách các lần khám (Ngày khám, Nha sĩ chẩn đoán, Chẩn đoán, Dịch vụ thực hiện).
   Lịch sử hóa đơn: Các hóa đơn tương ứng với trạng thái thanh toán.

## Đặc tả Use Case "Đặt lịch hẹn"

| Tiêu chí          | Nội dung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tên Use Case      | Đặt lịch hẹn khám bệnh                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Actor chính        | Bệnh nhân, Lễ tân                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Mô tả             | Cho phép bệnh nhân được chọn bác sĩ và chọn lịch khám và khung giờ để tạo một lịch hẹn trên hệ thống                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Tiền điều kiện  | Bệnh nhân phải được đăng nhập, có thông tin trên hệ thống, Nha sĩ được chọn đang không có lịch nào trùng                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Hậu điều kiện   | Thông báo cho bệnh nhân đặt lịch thành công, Lịch hẹn được thêm vào dữ liệu của hệ thống, khung giờ của Nha sĩ mà bệnh nhân chọn sẽ chuyển đã có người đặt lịch                                                                                                                                                                                                                                                                                                                                                                                                          |
| Luồng hoạt động | 1. Người dùng chọn Nha sĩ, ngày khám và khung giờ mong muốn<br />2. Hệ thống kiểm tra khung giờ đó còn trống với Nha sĩ đó không<br />3. Hệ thống sẽ ghi nhận thông tin lịch hẹn và tạo một lịch hẹn với trạng thái là "Chờ xác nhận" hoặc "Đã xác nhận"<br />4. Hệ thống thống báo đặt lịch thành công và đã ghi lịch hẹn vào dữ liệu hệ thống                                                                                                                                                                                              |
| Luồng thay thế    | 2.1. Người dùng hủy lịch hẹn thì Hệ thống kiểm tra trạng thái của lịch hẹn<br />2.1.1.  Nếu lịch hẹn ở trạng thái "Chờ xác nhận" hoặc "Đã xác nhận" thì sẽ cập nhật trạng thái thành "Đã hủy"<br />2.1.2. nếu lịch hẹn ở trạng thái "Đã khám" thì hệ thống từ chối yêu cầu hủy lịch vì lịch hẹn đẫ hoàn thành, không thể hủy <br />2.2. Nếu lịch bị trùng thì Hệ thống sẽ thông báo khung giờ này đã có người đặt rồi, Bệnh nhân sẽ xem các khung giờ trống của các Nha sĩ khác và chọn khung giờ mới |
| Luồng mở rộng    | 4.1. Khi thông báo đặt lịch thành công thì có thể thông báo lịch hẹn của bệnh nhân qua tin nhắn SMS                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
