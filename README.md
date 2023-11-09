# Gr2_SIOT_Core_Lib_Web_Wifi
**Wi-Fi có hai chế độ hoạt động chính: Station (Client) và Access Point (AP). Dưới đây là mô tả của hai chế độ này:**
Chế độ Station (Client): Chế độ Station cho phép thiết bị kết nối và truy cập vào mạng Wi-Fi. Đây là chế độ phổ biến được sử dụng trên các thiết bị như laptop, điện thoại di động, máy tính bảng và các thiết bị thông minh khác. Trong chế độ này, thiết bị Station hoạt động như một khách hàng, kết nối đến một Access Point (AP) đã tồn tại để truy cập vào mạng Wi-Fi và kết nối với các thiết bị khác trên mạng.
Chế độ Access Point (AP): Chế độ Access Point chuyển thiết bị trở thành một điểm phát Wi-Fi, cho phép các thiết bị khác kết nối và truy cập vào mạng Wi-Fi. Trong chế độ này, thiết bị Access Point hoạt động như một trung tâm phát sóng Wi-Fi, tạo ra một mạng không dây và cho phép các thiết bị khác kết nối vào mạng này để truy cập internet hoặc tương tác với nhau qua mạng nội bộ.

**Cơ chế hoạt động Station (Client) để truy cập internet qua mạng Wi-Fi:**
1.	Xác thực: Thiết bị Station (Client) xác thực với Access Point (AP) bằng mật khẩu hoặc mã xác thực.
2.	Nhận địa chỉ IP: Thiết bị Station (Client) nhận địa chỉ IP từ Access Point (AP) để định danh trên mạng Wi-Fi.
3.	Cấu hình DNS: Thiết bị Station (Client) cấu hình máy chủ DNS để dịch tên miền thành địa chỉ IP.
4.	Truy cập internet: Thiết bị Station (Client) gửi yêu cầu truy cập internet qua Access Point (AP), nhận phản hồi từ internet và hiển thị dữ liệu trên trình duyệt web hoặc ứng dụng tương ứng.

**Cơ chế hoạt động của ESP32**
Ở chế độ Station (Client), ESP32 sẽ quét và tìm kiếm các mạng Wi-Fi có sẵn, sau đó, nó sẽ thực hiện quá trình xác thực và kết nối vào mạng Wi-Fi đó. Khi kết nối thành công, ESP32 có thể truyền và nhận dữ liệu thông qua mạng Wi-Fi.
Ngoài ra, ESP32 cũng có khả năng hoạt động trong chế độ Access Point (AP). Khi được cấu hình thành một Access Point, ESP32 sẽ tạo ra một mạng Wi-Fi riêng, cho phép các thiết bị khác kết nối vào. Các thiết bị khác có thể quét và tìm kiếm mạng Wi-Fi do ESP32 tạo ra, sau đó, kết nối vào mạng này để truyền và nhận dữ liệu.
Với khả năng hỗ trợ cả chế độ Station (Client) và Access Point (AP), ESP32 cho phép tích hợp và mở rộng khả năng kết nối Wi-Fi trong các ứng dụng IoT và các hệ thống nhúng khác.

**Trong trường hợp các thiết bị IoT không biết mạng Wi-Fi và mật khẩu trước đây, nhà phát triển (Dev) thường phải cung cấp thông tin này trong mã nguồn và nạp lại mã nguồn lên ESP32**
Khi lập trình ESP32, Dev cần chỉnh sửa mã nguồn để nhập thông tin mạng Wi-Fi và mật khẩu. Thông thường, mã nguồn sẽ chứa các biến để lưu trữ thông tin này, và Dev phải cung cấp giá trị cho các biến này. Sau đó, mã nguồn sẽ được biên dịch và nạp lên ESP32 để thiết bị có thể kết nối với mạng Wi-Fi.
Việc phải thay đổi mã nguồn và nạp lại mã lên ESP32 mỗi khi cần thay đổi mạng Wi-Fi hoặc mật khẩu có thể gây không tiện và tốn thời gian, đặc biệt khi có nhiều thiết bị IoT cần được cấu hình. Để giải quyết vấn đề này, tôi sẽ cấu hình ESP32 thông qua giao diện web: Bằng cách tạo một trang web nhúng trong ESP32 để người dùng nhập thông tin mạng Wi-Fi và mật khẩu. ESP32 sẽ tạo một Access Point (AP) và khi người dùng kết nối vào AP này, họ có thể truy cập vào trang web và nhập thông tin mạng Wi-Fi và mật khẩu. Sau đó, ESP32 sẽ lưu trữ thông tin này và kết nối vào mạng Wi-Fi được cung cấp.

**Dưới đây là một hướng dẫn ngắn về cách thực hiện:**
1.	Đầu tiên, hãy cài đặt thư viện SIOT Core Lib vào IDE Arduino của bạn (tìm kiếm: nguyen duc tien). Điều này có thể được thực hiện bằng cách truy cập vào "Cài đặt thư viện" trong IDE Arduino và tìm kiếm "SIOT Core Lib" để cài đặt.
2.	Tiếp theo, hãy tạo một tệp tin mới trong IDE Arduino và nhập đoạn code để tạo giao diện web
3.	Sau khi tải code lên ESP32 và chạy, ESP32 sẽ tạo một Access Point (AP) với giao diện web. Người dùng có thể kết nối vào AP này và truy cập vào trang web để nhập mật khẩu Wi-Fi. Khi người dùng nhấp vào nút "Save", thông tin SSID và mật khẩu sẽ được lưu trữ để được sử dụng cho các kết nối Wi-Fi sau này.
 Link ảnh: https://drive.google.com/drive/folders/18LlnjjlOIJkeT8mcedPVGwaNwtebYX_R

