##📝 Small Note Manager
 
Ứng dụng quản lý ghi chú đơn giản dùng Spring Boot.
✨ Tính năng

Xác thực: Đăng ký, đăng nhập với JWT.
Ghi chú: Tạo, sửa, xóa, xem ghi chú cá nhân.
Admin: Xem tất cả ghi chú.
API RESTful bảo mật, dễ dùng.

🚀 Cài đặt
Yêu cầu

Java 17+ ☕
Maven
MySQL
IDE (IntelliJ, VS Code)

Hướng dẫn

Clone dự án:git clone https://github.com/shyhubb/note


Vào thư mục:cd small-note-manager


Cấu hình database:
Tạo database MySQL: smallnote.
Cập nhật application.properties:spring.datasource.url=jdbc:mysql://localhost:3306/smallnote
spring.datasource.username=your-username
spring.datasource.password=your-password
spring.jpa.hibernate.ddl-auto=update
jwt.secret=your-jwt-secret-key



Lưu ý: Thay your-jwt-secret-key bằng khóa bí mật (32 ký tự).

Chạy ứng dụng:mvn spring-boot:run


Truy cập: Test API bằng Postman (xem bảng API).

🛠️ Công nghệ

Backend: Spring Boot, Spring Data JPA, Spring Security
Database: MySQL
Xác thực: JWT
Build: Maven

📚 API Endpoints
API /user/* và /admin/* cần header Authorization: Bearer <token> (lấy từ /auth/login). Copy endpoint trực tiếp từ code blocks dưới đây.
Xác thực



Phương thức
Endpoint
Mô tả
Request Body
Response



POST
http://localhost:8080/auth/register
Đăng ký
{ "name": "string", "account": "string", "password": "string" }
String (VD: "Create Account Success.")


POST
http://localhost:8080/auth/login
Đăng nhập, lấy JWT
{ "account": "string", "password": "string" }
{ "message": "string", "token": "string" }


Ghi chú (User)



Phương thức
Endpoint
Mô tả
Request Body
Response



POST
http://localhost:8080/user/notes/create
Tạo ghi chú
{ "title": "string", "content": "string" }
String (VD: "Note created.")


POST
http://localhost:8080/user/notes/update/{id}
Sửa ghi chú
{ "title": "string", "content": "string" }
String (VD: "Update Note Success.")


POST
http://localhost:8080/user/notes/delete/{id}
Xóa ghi chú
-
String (VD: "Delete Note Success.")


GET
http://localhost:8080/user/notes/view
Xem tất cả ghi chú
-
{ "message": "string", "data": [{ "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" }] }


GET
http://localhost:8080/user/notes/view/details/{id}
Xem chi tiết ghi chú
-
{ "message": "string", "data": { "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" } }


Admin



Phương thức
Endpoint
Mô tả
Request Body
Response



GET
http://localhost:8080/admin/notes/showall
Xem tất cả ghi chú
-
[{ "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" }]


Lưu ý: 

API /user/* chỉ cho user sở hữu ghi chú truy cập.
API /admin/* cần quyền admin.
Test bằng Postman, copy endpoint từ bảng.

🤝 Đóng góp
Muốn góp ý? Rất hoan nghênh! 😊  

Fork repo.  
Tạo nhánh: git checkout -b feature/your-feature.  
Commit: git commit -m 'Thêm tính năng'.  
Push: git push origin feature/your-feature.  
Tạo Pull Request.

📜 Giấy phép
MIT License. Xem LICENSE.
🙌 Cảm ơn

Cảm ơn cộng đồng Spring Boot!  
Dự án xây với 💖 để học Spring Boot.


Tác giả: [Tên của bạn] – shyhubel@gmail.com Link dự án: [Link GitHub của bạn]
