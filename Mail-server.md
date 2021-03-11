# Khái niệm Mail Server

## 1. Mail Server là gì

Mail Server là một máy chủ thư điện tử dùng để gửi và nhận thư điện tử (Email).

Các Email Server thực chất là một Server vật lý hoặc là một Server đám mây được cấu hình thành một server gửi và nhận thư điện tử. Nó cũng có đầy đủ các thông số như một Server bình thường

## 2. Phân loại

- Outgoing Email Server là gì?
Outgoing Mail Server hay Mail Server gửi đi sử dụng giao thức SMTP (Simple Mail Transfer Protocol). Đây là giao thức dịch chuyển mail đơn giản được dùng để liên lạc với server từ xa. Đồng thời cho phép gửi nhiều thư cùng một lúc tới các server khác nhau.

- Incoming Email Server là gì?
Giao thức này hay còn được biết đến dưới 2 hình thức:

POP3 (Post Office Protocol): chuyển email tới lưu ở máy tính chứa Mail Client, thường là nội bộ máy tính của người dùng thông qua một ứng dụng email như Outlook, Mac Mail, Windows Mail…

IMAP (Internet Message Access Protocol): là phương thức phức tạp hơn cho phép nhiều client cùng lúc kết nối tới một Mailbox. Email từ Mailbox sẽ được sao chép tới máy client và bản gốc của Email vẫn sẽ được lưu trên Mail Server.

## 3. Hoạt động

**Bước 1**
Sau khi tạo và gửi email, email của bạn sẽ kết nối với Server SMTP mang tên miền của mình. SMTP sẽ đặt tên cho tất cả mọi thứ, ví dụ: smtp.tenmien.com.

**Bước 2**
Email của bạn sẽ "giao tiếp" với SMTP server. Và cung cấp cho SMTP Server mọi thông tin như: địa chỉ mail người gửi, địa chỉ mail người nhận, nội dung email và file đính kèm.

**Bước 3**
Tại đây có 2 trường hợp xảy ra:

Trường hợp 1: Tên miền (domain email) của người gửi và người nhận giống nhau. 

tenemail_1@tenmienA.com tới tenemail_2@tenmienA.com. Mail này sẽ được gửi trực tiếp đến POP3 hoặc IMAP Server có tên miền của bạn. 

Trường hợp 2: Tên miền của người gửi và người nhận khác

tenemail_1@tenmienA.com tới tenemail_2@tenmienB.com. SMTP Server sẽ phải "liên lạc" với một server tên miền khác.

**Bước 4**
Để tìm ra Server của người nhận, SMTP Server của người gửi sẽ phải giao tiếp với DNS (Domain Name Server). 

DNS sẽ lấy thông tin tên miền người nhận và dịch trang địa chỉ IP. 

SMTP Server người gửi không thể thực hiện gửi email chính xác mà chỉ dựa trên tên miền thêm vào đó sẽ là địa chỉ IP. Địa chỉ IP (đơn nhất) sẽ giúp SMTP hoạt động chính xác và hiệu quả hơn.

**Bước 5**
Sau khi có địa chỉ IP của người nhận, tức STMP người gửi đã có thể kết nối STMP Server người nhận.

**Bước 6**
SMTP server người nhận sẽ quét (scan) thư gửi đến. Nếu nhận ra tên miền và tên người gửi, nó sẽ chuyển tiếp (forward) mail thuộc POP3 hoặc IMAP server mang tên miền của bạn. 

Từ đây, email đã được gửi đến mục hộp thư đến của người nhận.

