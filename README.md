📝 Small Note Manager
Ứng dụng quản lý ghi chú đơn giản xây dựng bằng Spring Boot. Đây là dự án đầu tiên của tôi để học Spring Boot, vừa học vừa làm, đúng là một hành trình thú vị! 😄
✨ Tính năng

Xác thực: Đăng ký và đăng nhập người dùng với JWT.
Quản lý ghi chú: Tạo, sửa, xóa, xem ghi chú cá nhân.
Admin: Xem tất cả ghi chú trong hệ thống.
API RESTful bảo mật, dễ dùng.

🚀 Cài đặt
Yêu cầu

Java 17+ ☕
Maven
MySQL
IDE (IntelliJ IDEA, VS Code)

Hướng dẫn

Clone dự án:git clone https://github.com/your-username/small-note-manager.git


Vào thư mục dự án:cd small-note-manager


Cấu hình database:
Tạo database MySQL tên smallnote.
Cập nhật file src/main/resources/application.properties:spring.datasource.url=jdbc:mysql://localhost:3306/smallnote
spring.datasource.username=your-username
spring.datasource.password=your-password
spring.jpa.hibernate.ddl-auto=update
jwt.secret=your-jwt-secret-key



Lưu ý: Thay your-jwt-secret-key bằng khóa bí mật (ví dụ: chuỗi 32 ký tự).

Chạy ứng dụng:mvn spring-boot:run


Truy cập:
Dùng Postman để test API (xem danh sách bên dưới).
Admin: http://localhost:8080/admin/notes/showall (cần quyền admin).



🛠️ Công nghệ

Backend: Spring Boot, Spring Data JPA, Spring Security
Database: MySQL
Xác thực: JWT
Build: Maven

📚 Danh sách API
Xác thực



Phương thức
Endpoint
Mô tả
Request Body
Response



POST
/auth/register
Đăng ký
{ "name": "string", "account": "string", "password": "string" }
String (VD: "Create Account Success.")


POST
/auth/login
Đăng nhập (trả về JWT)
{ "account": "string", "password": "string" }
LoginResponse (message, token)


Quản lý ghi chú (User)



Phương thức
Endpoint
Mô tả
Request Body
Response



POST
/user/notes/create
Tạo ghi chú
{ "title": "string", "content": "string" }
String (VD: "Note created.")


POST
/user/notes/update/{id}
Sửa ghi chú
{ "title": "string", "content": "string" }
String (VD: "Update Note Success.")


POST
/user/notes/delete/{id}
Xóa ghi chú
-
String (VD: "Delete Note Success.")


GET
/user/notes/view
Xem tất cả ghi chú
-
BaseResponse (message, danh sách NoteResponse)


GET
/user/notes/view/details/{id}
Xem chi tiết ghi chú (chỉ chủ sở hữu)
-
BaseResponse (message, NoteResponse)


Admin



Phương thức
Endpoint
Mô tả
Request Body
Response



GET
/admin/notes/showall
Xem tất cả ghi chú
-
List<NoteResponse>


Lưu ý: 

API /user/* và /admin/* cần JWT token trong header Authorization: Bearer <token>.
Lấy token từ /auth/login.
API chạy tại http://localhost:8080.

📸 Hình ảnh
(Sắp có! Thêm ảnh chụp Postman hoặc giao diện nếu có.)
🤝 Đóng góp
Muốn đóng góp? Rất hoan nghênh! 😊  

Fork repo.  
Tạo nhánh mới (git checkout -b feature/your-feature).  
Commit thay đổi (git commit -m 'Thêm tính năng mới').  
Push nhánh (git push origin feature/your-feature).  
Tạo Pull Request.

📜 Giấy phép
MIT License. Xem LICENSE.
🙌 Cảm ơn

Cảm ơn cộng đồng Spring Boot và Spring Security!  
Xây dựng với 💖 để chinh phục Spring Boot.


Tác giả: [Tên của bạn] – email@example.comLink dự án: [Link GitHub của bạn]
