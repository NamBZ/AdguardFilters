# 🛡️ AdGuard Filters - SafeKids

Bộ sưu tập các bộ lọc tên miền (DNS Blocklists) dành cho AdGuard, AdGuard Home và các trình chặn quảng cáo tương thích, giúp tạo ra một môi trường Internet an toàn hơn cho trẻ em (SafeKids).

---

## 📁 Danh sách bộ lọc (Blocklists)

Các bộ lọc được phân loại chi tiết trong thư mục [SafeKids](file:///e:/Project/AdguardFilters/SafeKids):

| Bộ lọc | Mô tả | Liên kết Raw (Import trực tiếp) |
| :--- | :--- | :--- |
| 🌐 **Online Game** | Chặn các trang web trò chơi trực tuyến, cổng game và dịch vụ game trực tuyến. | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/onlinegame.txt` |
| 📱 **Mobile Game** | Chặn các máy chủ kết nối và dịch vụ của game di động. | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/mobilegame.txt` |
| 💻 **PC Game** | Chặn các máy chủ kết nối và dịch vụ của game trên máy tính (PC). | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/pcgame.txt` |
| 🔞 **NSFW** | Chặn nội dung người lớn, khiêu dâm, bạo lực và không lành mạnh cho trẻ em. | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/nsfw.txt` |
| 💬 **Social** | Chặn hoặc hạn chế các mạng xã hội phổ biến (Facebook, TikTok, Instagram, Twitter...). | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/social.txt` |
| 🔑 **VPN/Proxy** | Chặn các dịch vụ VPN, Web Proxy, DNS Bypass nhằm ngăn chặn việc vượt tường lửa. | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/vpn.txt` |
| 🔍 **SafeSearch** | Ép buộc chế độ tìm kiếm an toàn (Safe Search) cho Google, Bing, DuckDuckGo, Yandex, Ecosia. | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/SafeSearch.txt` |
| 🛒 **App Store** | Chặn các cửa hàng ứng dụng và các trang web tải APK/ứng dụng di động không chính thống. | `https://raw.githubusercontent.com/NamBZ/AdguardFilters/main/SafeKids/appstore.txt` |

---

## 🚀 Hướng dẫn cài đặt và sử dụng

### 1. Cài đặt trên AdGuard Home (Khuyên dùng)
Để áp dụng bộ lọc cho các thiết bị trong mạng gia đình:
1. Đăng nhập vào bảng điều khiển (Dashboard) của **AdGuard Home**.
2. Di chuyển tới mục **Filters** (Bộ lọc) -> **DNS blocklists** (Danh sách chặn DNS).
3. Nhấp vào nút **Add blocklist** (Thêm danh sách chặn).
4. Chọn **Add a custom list** (Thêm danh sách tùy chỉnh).
5. Điền thông tin:
   * **Name**: Đặt tên gợi nhớ (ví dụ: `SafeKids - NSFW` hoặc `SafeKids - OnlineGame`).
   * **URL**: Dán liên kết Raw tương ứng ở bảng trên vào.
6. Nhấp vào **Save** (Lưu) để hoàn tất.

#### ⚠️ Lưu ý về việc áp dụng quy tắc theo nhãn Client (ctag)
Các quy tắc trong bộ lọc của dự án này đa số sử dụng cú pháp lọc nâng cao có hậu tố `$ctag=user_child`. Nhờ đó, quy tắc chặn sẽ **chỉ có hiệu lực** đối với các thiết bị được gắn nhãn tương ứng (tránh ảnh hưởng đến thiết bị của người lớn).

Để gán nhãn `user_child` cho thiết bị của trẻ em trong AdGuard Home:
1. Đi tới **Settings** (Cài đặt) -> **Client settings** (Cài đặt máy khách).
2. Tìm thiết bị của con bạn trong danh sách (hoặc nhấn **Add client** để tạo mới bằng địa chỉ IP, MAC hoặc CIDR).
3. Nhấp vào **Edit** (Sửa) cấu hình thiết bị đó.
4. Trong phần **Tags** (Nhãn), nhập hoặc chọn tag: `user_child`.
5. Nhấn **Save** (Lưu). Các thiết bị này bây giờ sẽ bị áp dụng quy tắc chặn của bộ lọc SafeKids.

### 2. Cài đặt trên ứng dụng AdGuard (Windows, macOS, Android, iOS)
Nếu bạn muốn áp dụng bộ lọc trực tiếp trên từng thiết bị:
1. Mở ứng dụng **AdGuard** trên thiết bị của bạn.
2. Đi tới **Settings** (Cài đặt) -> **Filters** (Bộ lọc).
3. Tìm mục **Custom filters** (Bộ lọc tùy chỉnh) hoặc **User rules** (Quy tắc người dùng).
4. Chọn **Add custom filter** và dán liên kết URL Raw tương ứng vào.
5. Kích hoạt bộ lọc.

---

## ⚙️ Cú pháp bộ lọc (Filter Syntax)

Các bộ lọc này được thiết kế theo cú pháp chuẩn của AdGuard DNS:
* Quy tắc chặn tên miền cơ bản: `||example.com^` (Chặn `example.com` và tất cả các phân miền của nó).
* Quy tắc gán nhãn định danh (`$ctag`): Được sử dụng trong các quy tắc nâng cao để phân loại đối tượng áp dụng (ví dụ: `$ctag=user_child` chỉ áp dụng cho hồ sơ trẻ em trên AdGuard Home).
* Quy tắc ngoại lệ (`$denyallow`): Cho phép truy cập một số dịch vụ thiết yếu nằm trong tên miền bị chặn tổng thể.

---

## 🤝 Đóng góp & Báo lỗi (Feedback & Contribution)

Nếu bạn phát hiện thấy trang web nào bị chặn nhầm (False Positive) hoặc có trang web độc hại nào chưa bị chặn (False Negative):
1. Hãy tạo một **Issue** trên repository này.
2. Mô tả rõ tên miền bị lỗi và thuộc bộ lọc nào.
3. Chúng tôi sẽ kiểm tra và cập nhật bộ lọc trong thời gian sớm nhất.
