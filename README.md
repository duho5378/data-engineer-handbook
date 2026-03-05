# 📘 Sổ Tay Kỹ Sư Dữ Liệu (The Pragmatic Data Engineer Handbook)

> _"Công cụ có thể lỗi thời trong vài năm, nhưng tư duy thiết kế hệ thống và kiến trúc dữ liệu nền tảng thì tồn tại mãi mãi."_

Chào mừng bạn đến với **Sổ Tay Kỹ Sư Dữ Liệu**. Đây là một dự án cá nhân được xây dựng với mục tiêu tối thượng: **Hệ thống hóa và đào sâu kiến thức nền tảng về Data Engineering.** Cuốn sổ tay này không phải là một tài liệu hướng dẫn gõ code từng dòng (tutorial). Nó là một bản đồ tư duy dành cho những ai muốn thực sự hiểu **"Tại sao"** hệ thống hoạt động trước khi học cách làm cho nó **"Chạy được"**. Nó cũng là cuốn cẩm nang hoàn hảo để ôn tập lại toàn bộ tư duy hệ thống, sẵn sàng cho các buổi phỏng vấn kỹ thuật chuyên sâu hoặc thiết kế các kiến trúc dữ liệu trên môi trường Production.

---

## 🎯 Mục tiêu ra đời

1. **Tổng hợp kiến thức thực chiến:** Đúc kết lại những kinh nghiệm thiết kế hệ thống, gỡ lỗi và tối ưu hóa từ các dự án thực tế.
2. **Xây dựng một tài liệu cá nhân:** Tập trung vào các kiến thức nền tảng cho các buổi phỏng vấn và làm việc thực tế.

---

## 💡 Điểm khác biệt của Handbook này

- **Gắn kết Lý thuyết và Công cụ:** Mỗi khái niệm trừu tượng đều được minh chứng bằng các công cụ tiêu biểu. Khi nói về Event Streaming, chúng ta mổ xẻ **Apache Kafka**. Khi nói về Real-time CDC, chúng ta dùng **Debezium** kết nối PostgreSQL. Khi bàn về Table Formats, **Apache Hudi** sẽ được đưa ra phân tích.
- **Tư duy Kiến trúc & System Design:** Đi sâu vào việc thiết kế các hệ thống hoàn chỉnh, chẳng hạn như luồng dữ liệu từ Database qua Message Broker, lưu trữ tại Object Storage (**MinIO**) và phục vụ truy vấn siêu tốc (**StarRocks**, **Trino**).
- **Vượt ra ngoài Data Pipeline:** Tích hợp kiến thức về cách luồng dữ liệu giao tiếp với thế giới bên ngoài. Cuốn sách sẽ đề cập đến thiết kế hệ thống Data Dispatching kết hợp với Backend (**Java Spring Boot**) và Frontend (**ReactJS**), cũng như sử dụng API Gateways để quản lý lưu lượng.
- **Bảo mật Hệ thống (Security & Auth):** Dữ liệu vô nghĩa nếu không an toàn. Handbook bao gồm các thiết kế về quản lý định danh và phân quyền (AuthN/AuthZ) sử dụng **Keycloak**, **OpenFGA**, và các chiến lược phòng chống rủi ro bảo mật (như SSRF).
- **Bắt kịp xu hướng:** Tích hợp các kiến thức xử lý dữ liệu hiện đại như Vector Databases (**Qdrant**) phục vụ cho hệ thống tìm kiếm ngữ nghĩa và nhận diện.

---

## 🗺️ Cấu trúc và Lộ trình (How to read)

Nội dung được chia thành các khối kiến thức độc lập nhưng có tính kế thừa. Để giúp người đọc tự đánh giá và định vị bản thân, mỗi phần kiến thức sẽ được gắn nhãn cấp độ:

- 🌱 **[Fresher/Junior]:** Kiến thức nền tảng, bắt buộc phải nắm vững (SQL, Vòng đời dữ liệu, Data Modeling cơ bản).
- ⚙️ **[Mid-level]:** Hiểu sâu về "Under the hood", tối ưu hóa hiệu năng, xử lý luồng thời gian thực và quản lý container/infrastructure (**Docker**, **Kubernetes**).
- 🏛️ **[Senior/Architect]:** Thiết kế hệ thống (System Design), đánh đổi kiến trúc (Trade-offs), bảo mật, phân quyền và DataOps.

Chi tiết các chương có thể xem tại [Mục Lục (SUMMARY)](SUMMARY.md).

---

## 🚀 Đóng góp & Phát triển

Cuốn handbook này là một tài liệu "sống" (living document) và sẽ liên tục được cập nhật. Những công nghệ mới sẽ ra đời, những best practices sẽ thay đổi, nhưng tư duy giải quyết vấn đề sẽ luôn được mài giũa qua từng trang viết.

Trong tài liệu này có nhiều tri thức được tham khảo từ nhiều nguồn khác nhau, tuy nhiên, do tôi không có thời gian để ghi lại nguồn tham khảo, nên chân thành xin lỗi và mong các tác giả thông cảm.

_Happy Engineering!_
