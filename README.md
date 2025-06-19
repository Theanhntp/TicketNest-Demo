# 🎟️ TicketNest – Hệ Thống Đặt Vé Sự Kiện Thông Minh

**TicketNest** là nền tảng đặt vé sự kiện tiện lợi, cho phép người dùng đăng ký, đặt vé, trở thành nhà tổ chức sự kiện và thanh toán trực tuyến. Hệ thống hỗ trợ đa vai trò: **Guest**, **User**, **Organizer**, và **Admin**, mang đến trải nghiệm mượt mà và hiệu quả.

---

## 🎯 DEMO TẠI
<p align="center">
  https://theanhntp.github.io/TicketNest-Demo/home/
</p>

## 🎯 Mục Tiêu Hệ Thống

- 🚀 **Đặt vé nhanh chóng**: Tạo không gian đặt vé sự kiện dễ dàng, thân thiện với người dùng.
- 💳 **Thanh toán trực tuyến**: Hỗ trợ thanh toán vé qua PayPal.
- 🧑‍💼 **Tổ chức sự kiện**: Cho phép người dùng đủ điều kiện trở thành Organizer và quản lý sự kiện.
- 🛡️ **Quản trị tập trung**: Cung cấp công cụ quản lý mạnh mẽ cho Admin.

---

## 🔧 Chức Năng Chính

### 👤 Guest
- Xem danh sách sự kiện.
- Xem chi tiết sự kiện.
- Đăng ký tài khoản để trở thành User.

### 👥 User (Người dùng đã đăng ký)
- Đăng nhập / Đăng xuất.
- Đặt vé và thanh toán qua **PayPal**.
- Bình luận vào sự kiện.
- Cập nhật hồ sơ cá nhân và avatar.
- Xem lịch sử đặt vé.
- Gửi yêu cầu trở thành Organizer.

### 🧑‍💼 Organizer (Nhà tổ chức sự kiện)
- Tạo sự kiện mới.
- Quản lý sự kiện của mình.
- Xem thông tin người tham dự.

### 🛡️ Admin (Quản trị viên)
- Duyệt yêu cầu trở thành Organizer.
- Duyệt sự kiện do Organizer tạo.
- Quản lý danh sách tài khoản.
- Khóa / Mở khóa tài khoản.

<p align="center">
  <img src="/IMG/usescase.png" alt="Use Case Diagram" width="600" />
  <br><i>Sơ đồ Use Case mô tả các chức năng chính theo vai trò người dùng</i>
</p>

---

## 🧠 Luồng Nghiệp Vụ Tổng Quát

1. **Guest khám phá sự kiện**: Xem danh sách và chi tiết sự kiện → Đăng ký tài khoản → Trở thành User.
2. **User đặt vé**: Đăng nhập → Chọn sự kiện → Thanh toán qua PayPal → Nhận vé.
3. **Trở thành Organizer**: User gửi yêu cầu → Admin duyệt → User trở thành Organizer.
4. **Tạo và quản lý sự kiện**: Organizer tạo sự kiện → Admin duyệt → Sự kiện hiển thị công khai.
5. **Quản trị hệ thống**: Admin giám sát tài khoản và sự kiện.

---

## 🧩 Kiến Trúc Hệ Thống

| **Thành Phần**         | **Công Nghệ**                     |
|-------------------------|-----------------------------------|
| **Frontend**           | React + Redux + Tailwind CSS     |
| **Backend**            | Node.js + Express + MongoDB + JWT |
| **Cơ sở dữ liệu**      | MongoDB                          |
| **Upload ảnh**         | Cloudinary                       |
| **Email Services**     | Gmail SMTP                       |
| **Thanh toán**         | PayPal REST API                  |

---

## 📸 Chụp Màn Hình Giao Diện

Dưới đây là một số hình ảnh chụp màn hình minh họa giao diện của TicketNest:

| **Tính Năng**            | **Hình Ảnh**                                                                 |
|--------------------------|------------------------------------------------------------------------------|
| **Màn hình chính**       | <img src="/IMG/MainHome.png" alt="Main Screen" width="300" />              |
| **Đăng nhập**            | <img src="/IMG/SignUp.png" alt="Login" width="300" />                         |
| **Chọn vé**              | <img src="/IMG/SelectTicket.png" alt="Ticket Selection" width="300" />    |
| **Thanh toán**           | <img src="/IMG/Payment.png" alt="Payment" width="300" />                     |
| **Tạo sự kiện**          | <img src="/IMG/CreateEvent.png" alt="Create Event" width="300" />            |
| **Quản lý sự kiện**      | <img src="/IMG/EventManager.png" alt="Manage Event" width="300" />            |

---

## 📂 Cấu Trúc Dự Án

### Frontend (ticketnestFE)
```
ticketnestFE/
├── src/
│   ├── components/   # Các component giao diện
│   ├── pages/       # Trang: Home, Login, Event Detail, v.v.
│   ├── redux/       # Quản lý trạng thái
│   ├── services/    # Gọi API
│   ├── utils/       # Hàm tiện ích
│   └── App.jsx      # Component chính
├── public/
└── .env
```

### Backend (ticketnestBE)
```
ticketnestBE/
├── src/
│   ├── controllers/  # Xử lý logic nghiệp vụ
│   ├── routes/       # Các route API
│   ├── models/       # Mongoose schema
│   ├── middlewares/  # Xác thực, phân quyền, xử lý lỗi
│   ├── services/     # Email, Cloudinary, PayPal
│   └── app.js        # Khởi tạo ứng dụng
├── .env
```

---

## ⚙️ Biến Môi Trường

### Backend (ticketnestBE/.env)
```env
MONGODB_URI=mongodb://localhost:27017/ticketnest
JWT_SECRET=your_jwt_secret
GOOGLE_EMAIL_PASSWORD=your_google_app_password
GOOGLE_EMAIL_NAME=your_email@gmail.com
URL_SERVER=http://localhost:5000
LIMIT_PRODUCTS=2
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_KEY=your_cloudinary_key
CLOUDINARY_SECRET=your_cloudinary_secret
PAYPAL_CLIENT_ID=your_paypal_client_id
PAYPAL_CLIENT_SECRET=your_paypal_client_secret
```

---

## 🚀 Khởi Động Hệ Thống

### 1. Backend (ticketnestBE)
```bash
cd ticketnestBE
npm i --force
npm run dev
```
- **Mặc định chạy tại**: `http://localhost:5000`
- **Lưu ý**: Đảm bảo cấu hình đúng file `.env` như trên.

### 2. Frontend (ticketnestFE)
```bash
cd ticketnestFE
yarn --ignore-engines
yarn dev
```
- **Mặc định chạy tại**: `http://localhost:3000`

---

## 📝 Ghi Chú
- Sử dụng node v16.20
- Đảm bảo cài đặt đầy đủ các phụ thuộc trước khi chạy dự án.
- Cấu hình chính xác các biến môi trường trong file `.env` cho cả frontend và backend.
- Hình ảnh trong mục **Chụp Màn Hình Giao Diện** hiện là placeholder. Thay thế bằng các hình ảnh thực tế của TicketNest để minh họa tốt hơn.

---

<p align="center">
  <strong>TicketNest</strong> – Đặt vé dễ dàng, trải nghiệm sự kiện tuyệt vời!
</p>
<p align="center">
  theanhntp@gmail.com
</p>
