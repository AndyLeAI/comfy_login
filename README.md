**CoymfUI-Login**
Node tùy chỉnh này sử dụng một mật khẩu đơn giản để bảo vệ ComfyUI.

Đây là một phiên bản tùy chỉnh giao diện với giao diện và hình ảnh cụ thể. Một số tính năng như chế độ khách (guest mode) và chế độ tải ẩn danh (upload incognito) đã bị loại bỏ.

**Điều quan trọng cần biết**
Hãy lưu ý rằng không có hệ thống bảo mật tuyệt đối. Node đăng nhập này chỉ cung cấp mức bảo vệ cơ bản cho ComfyUI. Hãy sử dụng nó với sự cân nhắc của bạn.

**Cài đặt**
Để cài đặt node này, bạn có hai tùy chọn:

Trong thư mục ComfyUI/custom_nodes/, sử dụng lệnh git clone để tải repo này về, sau đó chạy lệnh pip install -r requirements.txt trong thư mục của repo.

Sử dụng ComfyUI-Manager.

**Thiết lập mật khẩu mới**
Khi đăng nhập lần đầu, bạn có thể chọn bất kỳ mật khẩu nào. Mật khẩu này sẽ được mã hóa và lưu trong tệp PASSWORD nằm trong thư mục <thư mục dự án ComfyUI>/login.

**Đặt lại mật khẩu khi quên**
Nếu bạn quên mật khẩu, bạn có thể đặt lại bằng cách xóa tệp PASSWORD nằm trong thư mục <thư mục dự án ComfyUI>/login. Sau đó, bạn có thể đăng nhập lại bằng một mật khẩu mới tùy ý.

**Loại bỏ tính năng đăng nhập**
Để vô hiệu hóa tính năng đăng nhập, bạn có thể:

Thủ công xóa thư mục **ComfyUI-Login** nằm trong thư mục **ComfyUI/custom_nodes/**. Sau đó, khởi động lại ComfyUI để thay đổi có hiệu lực.

Sử dụng ComfyUI-Manager để gỡ cài đặt nó.

**Sử dụng các REST API?**
ComfyUI-Login cũng bảo vệ server khỏi các API call trái phép.

Bạn có thể tìm thấy token của mình trong console (cửa sổ dòng lệnh) nếu bạn đã thiết lập mật khẩu. Token sẽ có định dạng như sau:

text

For direct API calls, use token=$2b...
Bạn có hai cách để xác thực yêu cầu của mình:

Thêm tham số token. Một ví dụ có thể được tìm thấy trong tệp ./script_examples/websockets_api_example.py.

Thêm header Authorization Bearer. Một ví dụ có thể được tìm thấy trong tệp ./script_examples/free_memory.sh.

**Tùy chỉnh trang đăng nhập?**
Bạn có thể tự do chỉnh sửa tệp login.html nếu bạn muốn cá nhân hóa giao diện trang đăng nhập.

**Giải phóng bộ nhớ khi thoát**
Trình duyệt sẽ gửi yêu cầu POST /free đến server khi người dùng thoát ra, đăng xuất, hoặc làm mới trang.

Tính năng này được xử lý hoàn toàn bằng JavaScript. Nếu bạn không muốn sử dụng tính năng này, chỉ cần xóa tệp js/free_memory.js.






