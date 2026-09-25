# Thực hành Xây Dựng và Rà Soát Tổng Hợp Khung SRS Rikkeifood

> 👤 **Học viên:** Đỗ Hoàng Sơn | **Mã SV:** PTIT-HCM-066
> 🏫 **Môn học:** IT105-K25-Phan-tich-thi-t-k-h-th-ng

---

## Nhiệm vụ 1: Phân loại yêu cầu và Xác định vị trí IEEE 830

Dựa trên tập ghi chú nghiệp vụ thô được cung cấp, em đã tiến hành phân tích, bóc tách và phân loại các yêu cầu thành nhóm Chức năng (Functional) và Phi chức năng (Non-functional), đồng thời gắn chính xác vị trí trong khung tài liệu chuẩn IEEE 830.

- Ghi chú 1: Khách gọi món quét mã QR trên bàn để mở thực đơn, không cần đăng nhập -> Loại: Chức năng (Functional) -> Vị trí: 3.2 Functional Requirements
- Ghi chú 2: Hệ thống phải hiển thị thực đơn nhanh chóng sau khi quét mã QR -> Loại: Phi chức năng (Non-functional) -> Vị trí: 3.4 Performance Requirements
- Ghi chú 3: Nhân viên bếp xác nhận đã chế biến xong món trên thiết bị bếp -> Loại: Chức năng (Functional) -> Vị trí: 3.2 Functional Requirements
- Ghi chú 4: Hệ thống chỉ hoạt động tốt trên các trình duyệt di động phổ biến, không hỗ trợ trình duyệt quá cũ -> Loại: Phi chức năng (Non-functional) -> Vị trí: 3.5 Constraints / Software Interfaces
- Ghi chú 5: Dữ liệu đơn hàng của khách phải được mã hóa khi truyền giữa app và server -> Loại: Phi chức năng (Non-functional) -> Vị trí: 3.8 Security and Safety Requirements

| Ghi chú | Loại yêu cầu (Chức năng/Phi chức năng) | Vị trí IEEE 830 đề xuất |
| --- | --- | --- |
| Ghi chú 1 | Chức năng (Functional) | 3.2 Functional Requirements |
| Ghi chú 2 | Phi chức năng (Non-functional) | 3.4 Performance Requirements |
| Ghi chú 3 | Chức năng (Functional) | 3.2 Functional Requirements |
| Ghi chú 4 | Phi chức năng (Non-functional) | 3.5 Constraints / Software Interfaces |
| Ghi chú 5 | Phi chức năng (Non-functional) | 3.8 Security and Safety Requirements |

## Nhiệm vụ 2: Xác định vị trí cho các sơ đồ thiết kế sẵn

Đối với các mô hình trực quan đã được thiết kế (Sơ đồ Use Case tổng thể và Sơ đồ ERD lưu trữ Đơn hàng - Món ăn), việc đặt đúng vị trí trong khung SRS giúp các bên như Dev, QA dễ dàng tra cứu, kiểm chứng phạm vi hệ thống và cấu trúc cơ sở dữ liệu.

| Sơ đồ | Vị trí IEEE 830 đề xuất | Lý do |
| --- | --- | --- |
| Use Case Diagram tổng thể | 2.1 Product Perspective / 3.2 Use Case Descriptions | Mô tả tổng quan các tác nhân (Khách hàng, Nhân viên bếp) tương tác với hệ thống đặt món tại bàn, làm rõ ranh giới hệ thống và các chức năng chính. |
| ERD Đơn hàng - Món ăn | 3.7 Database Requirements / Data Models | Thể hiện cấu trúc lưu trữ dữ liệu quan hệ giữa bảng Đơn hàng (Order) và bảng Món ăn (Dish), phục vụ cho việc thiết kế cơ sở dữ liệu vật lý. |

## Nhiệm vụ 3: Viết lại các ghi chú vi phạm đặc tính vàng

Qua rà soát chất lượng câu chữ, em nhận thấy Ghi chú 2 và Ghi chú 4 đang mắc lỗi diễn đạt cảm tính ('nhanh chóng', 'trình duyệt phổ biến', 'quá cũ'), thiếu các chỉ số đo lường cụ thể (quantitative metrics). Điều này gây khó khăn lớn cho đội QA khi viết kịch bản kiểm thử (Test Cases). Dưới đây là phần chỉnh sửa lại cho đạt chuẩn SRS kỹ thuật:

| Ghi chú | Đặc tính vàng bị vi phạm | Viết lại đạt chuẩn (có chỉ số/điều kiện cụ thể) |
| --- | --- | --- |
| Ghi chú 2 | Tính đo lường được (Testable) và tính tường minh (Unambiguous). Dùng từ 'nhanh chóng' rất cảm tính. | Hệ thống phải hiển thị hoàn tất giao diện thực đơn trên màn hình di động trong thời gian tối đa 2.0 giây tính từ thời điểm quét mã QR thành công dưới điều kiện mạng 4G tiêu chuẩn. |
| Ghi chú 4 | Tính xác định rõ ràng (Specific) và tính kiểm thử được. Các cụm từ 'phổ biến', 'quá cũ' không có ranh giới kỹ thuật rõ ràng. | Ứng dụng web hỗ trợ tối ưu trên các phiên bản trình duyệt di động: Safari từ phiên bản 15.0 trở lên, Google Chrome từ phiên bản 100.0 trở lên trên hệ điều hành iOS và Android. |

---

## 📁 Danh sách tệp tin nộp bài trong Repository
- 📝 `bt2.docx`: Báo cáo tài liệu phân tích nghiệp vụ hoàn chỉnh.
