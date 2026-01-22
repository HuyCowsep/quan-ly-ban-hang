# smallbiz-sales – Smart Retail Management System

Hệ thống quản lý bán lẻ & phân tích tài chính toàn diện
(Inspired by Sapo POS – but customized & optimized for real-world usage)

📌 Giới thiệu

Smart Retail Management System là một nền tảng web quản lý bán lẻ toàn diện, được xây dựng nhằm hỗ trợ cửa hàng trong việc:
- Bán hàng tại quầy (POS)
- Quản lý sản phẩm, tồn kho theo lô (batch)
- Theo dõi doanh thu – chi phí – lợi nhuận
- Phân tích hiệu quả kinh doanh theo thời gian và theo nhóm hàng
- Hỗ trợ nhiều phương thức thanh toán (Cash, QR Code, PayOS tích hợp check thanh toán tự động)

-> Hệ thống được thiết kế với mục tiêu đơn giản – chính xác – sát nghiệp vụ thực tế, hướng đến các cửa hàng bán lẻ vừa và nhỏ.
-> Dù lấy cảm hứng từ các nền tảng lớn như Sapo, hệ thống này được tùy biến sâu hơn về logic tài chính, tồn kho và báo cáo, phù hợp với thực tế vận hành tại Việt Nam.

📌  Các tính năng chính
1. Bán hàng tại quầy (POS)
Tạo đơn hàng nhanh, realtime
Hỗ trợ:
- Thanh toán tiền mặt
- Thanh toán QR Code (PayOS hoặc QR ngân hàng tĩnh)
- In hóa đơn trực tiếp
- Xác nhận thanh toán thủ công cho QR tĩnh (nghiệp vụ thực tế)

2. Quản lý sản phẩm & tồn kho
Quản lý sản phẩm theo nhóm hàng
- Quản lý kho hàng
- Theo dõi tồn kho, biến thiên tồn kho (Đầu, giữa và cuối kì):
- Tổng tồn theo nhiều kiểu
- Theo sản phẩm riêng, lô hàng (batch FIFO)
- Theo giá vốn thực tế

Cảnh báo:
- Tồn kho thấp, gửi qua email khi đăng ký Account và thông báo trên icon ở Dashboard
- Lô hàng sắp hết / đã hết hạn

3. Quản lý tài chính & chi phí
Tự động tính:
- Doanh thu
- Giá vốn (COGS)
- Lợi nhuận gộp
- Lợi nhuận ròng
- Quản lý chi phí ngoài hệ thống như: Tiền mặt bằng Điện, nước, Marketing, Lương nhân viên,.... (nếu có thì điền vào hệ thống sẽ tính toán giúp)
- Hỗ trợ phân bổ chi phí giữa các kỳ bằng gợi ý chia đều (allocation), có thể đồng ý hoặc không đồng ý thì tự điền thủ công

4. Báo cáo & phân tích
- Báo cáo theo: Ngày - Tháng - Quý - Năm
Biểu đồ:
- Cơ cấu tài chính tổng quan
- So sánh doanh thu – chi phí – lợi nhuận

Phân tích:
- Hiệu quả theo nhóm hàng
- Tỷ lệ quay vòng tồn kho
- Drill-down chi tiết giá vốn theo sản phẩm
- ...........................

5. Thông báo realtime (Socket.IO)

Thông báo khi:
- Thanh toán thành công
- Xác nhận QR tĩnh
- Tồn kho thấp
- Lô hàng sắp hết / hết hạn
- Realtime giữa các màn hình POS & Dashboard

📌  Điểm nổi bật (Khác biệt so với các POS phổ biến)

✔️ Tính giá vốn chính xác theo batch FIFO
✔️ Tách rõ “xác nhận thanh toán” và “in hóa đơn” cho QR tĩnh
✔️ Báo cáo tài chính sát nghiệp vụ kế toán (chưa thật sự đẳng cấp bằng nghề kế toán chuyên biệt nói riêng)
✔️ UI tối ưu cho GenZ và cả người không rành công nghệ (người lớn tuổi, người trung niên)
✔️ Không phụ thuộc hoàn toàn vào cổng thanh toán bên thứ ba

-> Hệ thống không chỉ “bán được hàng” mà còn giúp chủ cửa hàng hiểu rõ tiền của mình đang đi đâu.

📌  Kiến trúc hệ thống
🔹 Backend

Node.js
Express.js
MongoDB + Mongoose
Socket.IO
JWT Authentication
..................

🔹 Frontend
ReactJS
TypeScript
Ant Design
Recharts
Axios
Context API
..................

🔹 Mobile App (dùng expo, tải tại Appstore đối với IOS, android thì đơn giản hơn rồi) - tương tự frontend nhưng dùng React-native - dùng chung backend
ReactJS
TypeScript
Ant Design
Recharts
Axios
Context API
...................

🔹 Database
MongoDB Atlas

📌 Thiết kế schema tối ưu cho:

- Báo cáo tài chính
- Truy vết tồn kho
- Audit & lịch sử giao dịch

📌 Phân quyền & bảo mật

Đăng nhập bằng JWT
- Phân quyền theo:
- Chủ cửa hàng
- Nhân viên bán hàng
- Ghi log hoạt động (audit log)

📌 Định hướng phát triển

- Kết nối máy in bill vật lý
- ... chưa nghĩ ra
- AI gợi ý tồn kho & giá bán

📌 Tác giả và cộng tác
Nguyễn Đức Huy và 2 thành viên (backend, frontend) khác: Lê Chí Mạnh, Lê Quang Trung

📌 Lời kết
Dự án này không chỉ là một bài tập học thuật, mà là một sản phẩm được thiết kế dựa trên nghiệp vụ thực tế, có thể mở rộng và triển khai trong môi trường kinh doanh thật. “Xây một hệ thống mà người dùng không cần hiểu code vẫn dùng được – đó mới là thành công. Lời nói này là chatGPT nói!!! ^_^”. Hệ thống vẫn có nhiều điểm chưa thật sự hoàn hảo, vẫn cần update liên tục

📌 Contact riêng
- huyndhe176876@fpt.edu.vn
- ccoolls147@gmail.com
- 0912 202 885

📌 ENV & Cấu hình hệ thống
Hệ thống sử dụng các file `.env` để cấu hình môi trường và bảo mật thông tin nhạy cảm.

⚠️ Lưu ý:
- Các file `.env` **KHÔNG được push lên GitHub**
- Khi clone project, cần tự tạo file `.env` tương ứng

Hệ thống hiện tại sử dụng **3 file môi trường chính**:
1️⃣ Backend (.env)
- PORT
- MONGO_URI (MongoDB Atlas)
- JWT_SECRET
- PAYOS_CLIENT_ID
- PAYOS_API_KEY
- PAYOS_CHECKSUM_KEY
- SOCKET_SECRET
- CLOUDINARY
- EMAIL_SERVICE_CONFIG (nếu bật email cảnh báo tồn kho)

2️⃣ Frontend (.env)
- VITE_API_URL
- VITE_SOCKET_URL

3️⃣ Mobile App (.env)
- EXPO_PUBLIC_API_URL
- EXPO_PUBLIC_SOCKET_URL

👉 Các biến môi trường này phục vụ cho:
- Kết nối database
- Xác thực người dùng
- Thanh toán QR / PayOS
- Giao tiếp realtime bằng Socket.IO
📩 Nếu cần chạy demo đầy đủ (database + payment test), nhắn mình nhé :>>

📌 Quy ước & nguyên tắc thiết kế

- Ưu tiên nghiệp vụ thực tế hơn là tối ưu lý thuyết
- Logic tài chính (doanh thu, giá vốn, lợi nhuận) được xử lý tại Backend, phải tin tưởng backend thì FE mới nhàn
- Frontend chỉ đảm nhiệm hiển thị và tương tác
- Tránh hard-code, ưu tiên cấu hình qua ENV
- Không phụ thuộc hoàn toàn vào bên thứ ba (Payment Gateway)
- Luôn tách rõ:
  - Tạo đơn
  - Xác nhận thanh toán
  - In hóa đơn
  - ...... 

  📌 Những giới hạn hiện tại
- Hệ thống kế toán chưa đạt mức chuyên sâu như phần mềm kế toán chuyên nghiệp, Mơ ước trở thành KiotViet là 1 mơ ước khá đau đầu đấy nhưng có ước mơ thì cứ ước thật xịn =)))
- Chưa hỗ trợ xuất báo cáo theo chuẩn kế toán Việt Nam (VAS) cho lắm nhưng cũng được hội đồng đánh giá là Ok về tìm hiểu nghiệp vụ
- Mobile App hiện tại giống y hệt web, tức web có gì mobile có đó, tester vẫn đang test vài lần
- Chưa hỗ trợ multi-store nâng cao chuyên sâu (chuỗi lớn), chỉ hỗ trợ quản lý nhiều cửa hàng trong 1 account nhưng cũng được tách biệt riêng về các chức năng và logic theo Id Store
👉 Tuy nhiên, kiến trúc hệ thống cho phép mở rộng các tính năng này trong tương lai...