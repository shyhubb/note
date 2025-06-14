📝 Small Note Manager
Ứng dụng quản lý ghi chú đơn giản dùng Spring Boot. Đây là dự án đầu tay để học Spring Boot, vừa học vừa làm, đúng là một chuyến phiêu lưu! 😄
✨ Tính năng

Xác thực: Đăng ký, đăng nhập với JWT.
Ghi chú: Tạo, sửa, xóa, xem ghi chú cá nhân.
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


Vào thư mục:cd small-note-manager


Cấu hình database:
Tạo database MySQL: smallnote.
Cập nhật src/main/resources/application.properties:spring.datasource.url=jdbc:mysql://localhost:3306/smallnote
spring.datasource.username=your-username
spring.datasource.password=your-password
spring.jpa.hibernate.ddl-auto=update
jwt.secret=your-jwt-secret-key



Lưu ý: Thay your-jwt-secret-key bằng khóa bí mật (32 ký tự).

Chạy ứng dụng:mvn spring-boot:run


Truy cập:
Test API bằng Postman (xem danh sách API).
Admin: http://localhost:8080/admin/notes/showall (cần quyền admin).



🛠️ Công nghệ

Backend: Spring Boot, Spring Data JPA, Spring Security
Database: MySQL
Xác thực: JWT
Build: Maven

📚 API Endpoints
Tất cả API chạy tại http://localhost:8080. Dùng Bearer <token> trong header Authorization cho API /user/* và /admin/* (lấy token từ /auth/login).
1. Xác thực



Phương thức
Endpoint
Mô tả
Request Body
Response



POST
/auth/register
Đăng ký người dùng
{ "name": "string", "account": "string", "password": "string" }
String (VD: "Create Account Success.")


POST
/auth/login
Đăng nhập, lấy JWT
{ "account": "string", "password": "string" }
{ "message": "string", "token": "string" }


2. Quản lý ghi chú (User)



Phương thức
Endpoint
Mô tả
Request Body
Response



POST
/user/notes/create
Tạo ghi chú mới
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
Xem tất cả ghi chú của user
-
{ "message": "string", "data": [ { "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" } ] }


GET
/user/notes/view/details/{id}
Xem chi tiết ghi chú
-
{ "message": "string", "data": { "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" } }


3. Admin



Phương thức
Endpoint
Mô tả
Request Body
Response



GET
/admin/notes/showall
Xem tất cả ghi chú
-
[ { "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" } ]


Lưu ý: 

API /user/* chỉ cho phép user sở hữu ghi chú truy cập.
API /admin/* cần quyền admin.
Test API bằng Postman hoặc curl.

📸 Hình ảnh
(Sắp có! Thêm ảnh Postman nếu muốn.)
🤝 Đóng góp
Muốn góp ý? Rất hoan nghênh! 😊  

Fork repo.  
Tạo nhánh (git checkout -b feature/your-feature).  
Commit (git commit -m 'Thêm tính năng').  
Push (git push origin feature/your-feature).  
Tạo Pull Request.

📜 Giấy phép
MIT License. Xem LICENSE.
🙌 Cảm ơn

Cảm ơn cộng đồng Spring Boot!  
Dự án này được xây với 💖 để học Spring Boot.


Tác giả: [Tên của bạn] – email@example.comLink dự án: [Link GitHub của bạn]
