# ☕ Coffee Shop - ASP.NET MVC Razor
📌 *[Xem bản tiếng anh](README.md)*
> Một hệ thống bán hàng trực tuyến cho cửa hàng cà phê được phát triển bằng ASP.NET MVC (Razor Pages). 
Hỗ trợ 3 vai trò người dùng với phân quyền rõ ràng: Người dùng, Khách hàng, và Quản trị viên (Admin).

---

## 🧩 Tính năng chính

### 🧍‍♂️ Người dùng (User - chưa đăng nhập)
- Xem danh sách sản phẩm
- Xem trang giới thiệu cửa hàng
---

### 👤 Khách hàng (Customer - sau khi đăng nhập)
- Đăng ký, đăng nhập, quên mật khẩu
- Quản lý giỏ hàng
- Tạo đơn hàng
- Xem chi tiết đơn hàng
- Thanh toán qua **VNPay**
- Xem lịch sử mua hàng
- **Xuất hóa đơn PDF**

---

### 🛠️ Quản trị viên (Admin)
- Quản lý sản phẩm (CRUD)
- Quản lý mã khuyến mãi
- Quản lý danh mục sản phẩm
- Thống kê sản phẩm đã bán
- Xem lịch sử mua hàng của tất cả khách hàng

---

## ⚙️ Công nghệ sử dụng

- ASP.NET MVC (.NET 9)
- Razor Pages
- Entity Framework Core
- SQL Server
- Identity (phân quyền người dùng)
- VNPay Integration
- SelectPdf (xuất hóa đơn PDF)
- Chart.js (thống kê)

---

## 🚀 Hướng dẫn cài đặt

### 1. Clone dự án
```bash
git clone https://github.com/thanhlongqax/WebsiteCoffeeShop
cd WebsiteCoffeeShop
````

### 2. Cấu hình chuỗi kết nối

Cập nhật chuỗi kết nối trong `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=.;Database=;Trusted_Connection=;"
},
"VNPay": {
  "TmnCode": "",
  "HashSecret": "", // Ví dụ
  "BaseUrl": "https://sandbox.vnpayment.vn/paymentv2/vpcpay.html", // Ví dụ URL của môi trường Sandbox
  "ReturnUrl": "" // Ví dụ thực tế
},
```

### 3. Tạo database

Chạy lệnh migration và update database:

```bash
dotnet ef migrations add Init
dotnet ef database update
```

### 4. Chạy ứng dụng

```bash
dotnet run
```

---

## 🔐 Phân quyền người dùng

| Vai trò     | Mô tả                     | Truy cập                                                  |
| ----------- | ------------------------- | --------------------------------------------------------- |
| **User** | Người dùng chưa đăng nhập | `/`, `/products`, `/about`                                |
| **Customer**    | Khách hàng đã đăng nhập   | Giỏ hàng, đơn hàng, thanh toán, lịch sử mua hàng          |
| **Admin**   | Quản trị viên hệ thống    | Dashboard, thống kê, CRUD sản phẩm, mã giảm giá, danh mục |

Sử dụng `RoleManager` và `UserManager` để phân quyền.

---

## 💳 Tích hợp VNPay

* Đã cấu hình thông tin Merchant, ReturnUrl và NotifyUrl
* Sau khi thanh toán thành công, hệ thống cập nhật trạng thái đơn hàng

---

## 🧾 Xuất hóa đơn PDF

* Sau khi khách hàng hoàn tất thanh toán, có thể tải hóa đơn PDF
* Thư viện sử dụng: `SelectPdf`
---

## 📊 Thống kê và báo cáo

* Trang Dashboard hiển thị:

  * Số lượng sản phẩm đã bán
  * Doanh thu và lợi nhuận theo ngày / tháng
  * Top 5 sản phẩm bán chạy 
  * Đơn hàng theo trạng thái
  * Biểu đồ thống kê bằng **Chart.js**

---

## 📷 UI Screenshots  
📌 
**Giới thiệu**
![alt text](Docs\about.jpg)
**Đăng nhập**
![alt text](Docs\login.jpg)
**Thống kê**
![alt text](Docs\statistics.jpg)
**Quản lý danh mục**
![alt text](Docs\category.jpg)
**Quản lý sản phẩm**
![alt text](Docs\product.jpg)
![alt text](Docs\category.jpg)
**Quản lý mã khuyến mãi**
![alt text](Docs\discountCode.jpg)
**Lịch sử đơn hàng**
![alt text](Docs\order.jpg)
**Thiết lập tài khoản**
![alt text](Docs\setting.jpg)
---   

## 👤 Author  
**Thanh Long**  

🚀 *Made with ❤️ by Long*  

Follow me! 🚀

📧 **Contact**: thanhlongndp@gmail.com  

## 📄 Giấy phép
MIT License © 2025 \[Thành Long]
