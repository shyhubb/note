📝 Small Note Manager
 
Ứng dụng quản lý ghi chú đơn giản dùng Spring Boot. Đây là dự án đầu tiên để học Spring Boot, vừa học vừa làm, đúng là một trải nghiệm thú vị! 😄
✨ Tính năng

Xác thực: Đăng ký, đăng nhập với JWT.
Ghi chú: Tạo, sửa, xóa, xem ghi chú cá nhân.
Admin: Xem tất cả ghi chú trong hệ thống.
API RESTful bảo mật, dễ sử dụng.

🚀 Cài đặt
Yêu cầu

Java 17+ ☕
Maven
MySQL
IDE (IntelliJ, VS Code)

Hướng dẫn

Clone dự án:git clone https://github.com/your-username/small-note-manager.git


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


Truy cập:
Test API bằng Postman (xem bảng API).
Admin: http://localhost:8080/admin/notes/showall (cần quyền admin).



🛠️ Công nghệ

Backend: Spring Boot, Spring Data JPA, Spring Security
Database: MySQL
Xác thực: JWT
Build: Maven

📚 API Endpoints
Cơ sở URL: http://localhost:8080. API /user/* và /admin/* cần header Authorization: Bearer <token> (lấy từ /auth/login).
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
{ "message": "string", "data": [{ "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" }] }


GET
/user/notes/view/details/{id}
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
/admin/notes/showall
Xem tất cả ghi chú
-
[{ "note_id": number, "user_id": number, "account": "string", "title": "string", "content": "string", "date": "string" }]


Lưu ý: 

API /user/* chỉ cho user sở hữu ghi chú truy cập.
API /admin/* cần quyền admin.
Test bằng Postman hoặc curl.

📸 Hình ảnh
(Sắp có! Thêm ảnh Postman nếu muốn.)
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
Dự án này được xây với 💖 để học Spring Boot.


Tác giả: [Tên của bạn] – email@example.comLink dự án: [Link GitHub của bạn]
