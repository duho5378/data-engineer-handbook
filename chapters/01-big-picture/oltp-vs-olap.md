# 1.2. Phân biệt OLTP vs OLAP: Ranh giới của Hệ thống

> **Cấp độ:** 🌱 [Fresher]
> **Mục tiêu:** Nắm vững sự khác biệt cốt lõi giữa hệ thống xử lý giao dịch và hệ thống phân tích. Hiểu được lý do tại sao Data Engineering lại tồn tại để làm cầu nối giữa hai thế giới này.

Một trong những sai lầm kinh điển nhất của các kỹ sư mới vào nghề là: _"Tại sao phải xây dựng Data Warehouse phức tạp? Cứ viết câu lệnh SQL đếm tổng doanh thu (GROUP BY, JOIN hàng chục bảng) chạy thẳng trên database của ứng dụng là xong mà!"_.

Hậu quả là truy vấn đó ngốn sạch CPU/RAM, làm khóa bảng (table lock), và khiến toàn bộ người dùng không thể thao tác mua hàng hay đăng nhập được nữa. Đó là lúc chúng ta nhận ra sự khác biệt sống còn giữa **OLTP** và **OLAP**.

---

## 1. OLTP (Online Transaction Processing) - Trái tim vận hành

**OLTP** là hệ thống xử lý giao dịch trực tuyến. Mục tiêu tối thượng của nó là phục vụ các hoạt động diễn ra hàng ngày (day-to-day operations) của hệ thống phần mềm một cách nhanh chóng và chính xác nhất.

- **Đặc điểm cốt lõi:**
  - **Tốc độ là số 1:** Thời gian phản hồi (response time) tính bằng mili-giây.
  - **Giao dịch ngắn & Tần suất cao:** Xử lý hàng ngàn, thậm chí hàng triệu câu lệnh `INSERT`, `UPDATE`, `DELETE` nhỏ lẻ mỗi giây.
  - **Tính toàn vẹn (ACID):** Đảm bảo tuyệt đối không có dữ liệu rác, không mất tiền của khách hàng khi hệ thống xảy ra sự cố giữa chừng.
  - **Thiết kế Dữ liệu:** Thường tuân thủ nghiêm ngặt các nguyên tắc **Chuẩn hóa (Normalization - 3NF)** để tránh dư thừa dữ liệu và đảm bảo tốc độ cập nhật nhanh.
- **Ví dụ thực tế:** \* Hệ thống thanh toán tại quầy siêu thị.
  - Ứng dụng chuyển tiền ngân hàng (ATM).
  - Backend giỏ hàng của ứng dụng thương mại điện tử (ví dụ bạn viết bằng Java Spring Boot lưu xuống Database).
- **Công cụ tiêu biểu:** PostgreSQL, MySQL, Oracle, SQL Server.

---

## 2. OLAP (Online Analytical Processing) - Bộ não chiến lược

**OLAP** là hệ thống xử lý phân tích trực tuyến. Nó không quan tâm đến việc phục vụ một giao dịch mua hàng đơn lẻ, mà tập trung vào việc nhìn nhận bức tranh toàn cảnh để hỗ trợ ra quyết định (Decision Making) và lên kế hoạch.

- **Đặc điểm cốt lõi:**
  - **Truy vấn cực kỳ phức tạp:** Các câu lệnh SQL dài hàng trăm dòng, chứa nhiều phép `JOIN`, `GROUP BY`, `SUM`, `COUNT` trên hàng triệu hoặc hàng tỷ bản ghi.
  - **Thiên về Đọc (Read-heavy):** Rất ít hoặc không có thao tác cập nhật (`UPDATE`) hay xóa (`DELETE`) dữ liệu cục bộ. Dữ liệu chủ yếu được chèn vào theo lô (Batch Insert).
  - **Dữ liệu Lịch sử (Historical Data):** Chứa dữ liệu của nhiều tháng, nhiều năm để tìm ra xu hướng (Trend analysis).
  - **Thiết kế Dữ liệu:** Thường được **Phi chuẩn hóa (Denormalization)**, sử dụng mô hình Star Schema hoặc Snowflake Schema để tối ưu tốc độ truy vấn phân tích.
- **Ví dụ thực tế:**
  - Báo cáo tổng doanh thu bán hàng của tất cả các chi nhánh trong 5 năm qua.
  - Phân tích hành vi người dùng: Nhóm khách hàng nào thường mua sản phẩm A cùng với sản phẩm B vào dịp lễ.
- **Công cụ tiêu biểu:** \* Data Warehouse truyền thống: Amazon Redshift, Google BigQuery, Snowflake.
  - Động cơ truy vấn MPP siêu tốc (như bạn có định tìm hiểu): **StarRocks**, **Trino**.

---

## 3. Bảng so sánh tổng hợp (GeeksforGeeks Comparison)

Dưới đây là bảng tóm tắt các tiêu chí phân biệt rõ ràng nhất giữa hai hệ thống này:

| Tiêu chí                | OLTP (Hệ thống Giao dịch)                             | OLAP (Hệ thống Phân tích)                                    |
| :---------------------- | :---------------------------------------------------- | :----------------------------------------------------------- |
| **Mục đích chính**      | Phục vụ vận hành hàng ngày (Day-to-day operations).   | Hỗ trợ lập kế hoạch và ra quyết định (Decision making).      |
| **Trọng tâm (Focus)**   | Insert, Update, Delete tốc độ cao.                    | Select, Aggregate (Đọc và Tổng hợp dữ liệu lớn).             |
| **Nguồn dữ liệu**       | Giao dịch gốc từ ứng dụng sinh ra.                    | Tổng hợp từ nhiều hệ thống OLTP khác nhau.                   |
| **Loại truy vấn**       | Đơn giản, ngắn gọn (ví dụ: lấy thông tin 1 user).     | Cực kỳ phức tạp (ví dụ: gom nhóm dữ liệu theo năm, khu vực). |
| **Kích thước Dữ liệu**  | Nhỏ đến Trung bình (Megabytes đến Gigabytes).         | Rất lớn (Terabytes đến Petabytes).                           |
| **Số lượng người dùng** | Rất nhiều (Hàng triệu user đang thao tác app).        | Ít (Chủ yếu là Data Analyst, Management Level).              |
| **Thiết kế Schema**     | Chuẩn hóa cao (Highly Normalized).                    | Phi chuẩn hóa (Denormalized - Star/Snowflake Schema).        |
| **Tần suất Backup**     | Liên tục (Full + Incremental/Transaction Log backup). | Định kỳ (Thường là hàng ngày hoặc hàng tuần).                |

---

**Kết luận của Data Engineer:**
Sứ mệnh lớn nhất của chúng ta là xây dựng một "đường ống" an toàn (Data Pipeline/ETL/CDC) để liên tục trích xuất dữ liệu từ các hệ thống **OLTP** đang chạy nhộn nhịp, biến đổi chúng, và đưa một cách gọn gàng vào hệ thống **OLAP** để đội ngũ phân tích có thể tự do "khai phá" mà không làm sập hệ thống bán hàng của công ty.
