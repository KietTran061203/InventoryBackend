# 🛠 Quản lý đơn hàng - Backend

Đây là module Backend của dự án Quản lý đơn hàng.  
Xây dựng bằng **ASP.NET Core MVC** và **MongoDB**.  

---

## Công nghệ sử dụng
- ASP.NET Core MVC (.NET 8/9)
- MongoDB (Atlas)
- JWT Authentication
- Docker (Render deploy)

---

## 🛠 Cài đặt local

### 1. Clone project
```bash
git clone https://github.com/KietTran061203/InventoryBackend.git
cd Backend
```
### 2. Cấu hình
Tạo file appsettings.json hoặc sử dụng biến môi trường
```bash
{
  "Jwt": {
    "Key": "THIS_IS_MY_SUPER_SECRET_KEY_12345678",
    "Issuer": "inventory-app",
    "Audience": "inventory-app"
  },
  "MongoDB": {
    "ConnectionString": "mongodb+srv://sa:sa@cluster0.un93s.mongodb.net/",
    "Database": "InventoryDb"
  }
}
```
### 3. Chạy ứng dụng
```bash
dotnet restore
dotnet build
dotnet run
```
Mặc định sẽ chạy https://localhost:44350 (IIS Express)

## 🌐 Deploy lên Render
### 1. Push code Backend lên Github
### 2. Tạo Web Service trên Render → chọn repo backend.
### 3. Thêm Environment Variables:
```bash
MONGODB_URI=mongodb+srv://sa:sa@cluster0.un93s.mongodb.net/
JWT_KEY=THIS_IS_MY_SUPER_SECRET_KEY_12345678
ASPNETCORE_ENVIRONMENT=Production
```
### 4. Deploy thành công, Render cấp URL dạng: https://inventorybackend-trantuankiet.onrender.com
##📖 API chính
```bash
POST /api/auth/register → Đăng ký

POST /api/auth/login → Đăng nhập (JWT)

GET /api/products → Lấy danh sách sản phẩm

POST /api/products → Thêm sản phẩm

DELETE /api/products/{id} → Xóa sản phẩm

POST /api/orders → Tạo đơn hàng

PATCH /api/orders/{id}/status → Cập nhật trạng thái đơn hàng
```
---


