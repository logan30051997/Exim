# Tổng quan về Exim

## 1. Giới thiệu

### a. Khái niệm

Exim là một MTA (Mail Tranfer Agent) chuyển thư mã nguồn mở. Viết bằng ngôn ngữ C, dành cho các máy chủ đang chạy hệ điều hành Unix hoặc Unix giống như vậy. Exim được thiết kế để xử lý một hỗn hợp chung của thư. Nó không cung cấp hàng đợi độc lập cho các tên miền hoặc máy chủ lưu trữ cụ thể.

Exim Sử dụng cơ chế ACL cho thông lượng tốt hơn. Danh sách điều khiển truy cập đảm nhiệm mọi việc liên quan đến việc gửi dữ liệu và chấp nhận dữ liệu cục bộ hoặc từ xa. ACL sẽ có ảnh hưởng cho đến khi từ chối hoặc chấp nhận thư sau khi người dùng đó cũng có thể xác định các bộ lọc.

### b. Sites, websites
 https://exim.org https://wiki.exim.org/ https://bugs.exim.org/

### c. Giới hạn

- Exim được thiết kế để sử dụng như một Internet MTA và do đó chỉ xử lý các địa chỉ ở định dạng miền RFC 2822. Nó không thể xử lý *"bang path"* UUCP, mặc dù các *bang path* hai thành phần đơn giản có thể được chuyển đổi bằng một cấu hình viết lại đơn giản. Hạn chế này không ngăn Exim giao tiếp với UUCP như một cơ chế truyền tải, miễn là địa chỉ miền được sử dụng.
- Exim khẳng định rằng mọi địa chỉ mà nó xử lý đều có một miền được đính kèm. Đối với các thư cục bộ đến, các địa chỉ không có nguồn gốc tự động đủ điều kiện với giá trị miền đã định cấu hình. Các tùy chọn cấu hình chỉ định các địa chỉ không đủ tiêu chuẩn của hệ thống từ xa nào được chấp nhận. Sau đó chúng đủ tiêu chuẩn khi đến nơi.
- Các cơ chế truyền tải bên ngoài duy nhất hiện được triển khai là SMTP và LMTP qua mạng TCP / IP (bao gồm hỗ trợ cho IPv6). Tuy nhiên, có sẵn phương tiện truyền tải đường ống và có các phương tiện để ghi thông điệp vào tệp và đường ống, tùy chọn ở định dạng SMTP theo lô; các phương tiện này có thể được sử dụng để gửi thông điệp đến các cơ chế truyền tải khác như UUCP, miễn là chúng có thể xử lý các địa chỉ kiểu miền. Đầu vào SMTP cũng được cung cấp.
- Exim không được thiết kế để lưu trữ thư cho các máy chủ quay số *(dial-hosts)*. Khi khối lượng thư lớn như vậy, tốt hơn hết bạn nên đưa các thư được “gửi” vào các tệp (nghĩa là nằm ngoài hàng đợi của Exim) và sau đó được chuyển đến các máy chủ quay số bằng các phương tiện khác.
- Mặc dù Exim có các phương tiện cơ bản để quét các tin nhắn đến, nhưng chúng không đủ toàn diện để thực hiện quét toàn bộ vi-rút hoặc thư rác. Các hoạt động này được thực hiện tốt nhất bằng cách sử dụng các gói phần mềm chuyên dụng bổ sung. Nếu bạn biên dịch Exim với phần mở rộng quét nội dung, các giao diện đơn giản cho một số trình quét phổ biến sẽ được cung cấp.

## 2. Exim command line

https://www.exim.org/exim-html-4.93/doc/html/spec_html/ch-the_exim_command_line.html

