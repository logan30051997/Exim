# Khái niệm Mail Server

## 1. Mail Server là gì

Mail Server là một máy chủ thư điện tử dùng để gửi và nhận thư điện tử (Email).

Các Email Server thực chất là một Server vật lý hoặc là một Server đám mây được cấu hình thành một server gửi và nhận thư điện tử. Nó cũng có đầy đủ các thông số như một Server bình thường

Email client (từ kỹ thuật là Mail User Agent (MUA), là một phần mềm máy tính được dùng để truy cập và quản lý email của người dùng


## 2. Phân loại

- Outgoing Email Server là gì? 
Outgoing Mail Server hay Mail Server gửi đi sử dụng giao thức SMTP (Simple Mail Transfer Protocol). Đây là giao thức dịch chuyển mail đơn giản được dùng để liên lạc với server từ xa. Đồng thời cho phép gửi nhiều thư cùng một lúc tới các server khác nhau.
Port 25/465

- Incoming Email Server là gì? 
Giao thức này hay còn được biết đến dưới 2 hình thức: 

POP3 (Post Office Protocol): chuyển email tới lưu ở máy tính chứa Mail Client, thường là nội bộ máy tính của người dùng thông qua một ứng dụng email như Outlook, Mac Mail, Windows Mail… 
Port 110/995

IMAP (Internet Message Access Protocol): là phương thức phức tạp hơn cho phép nhiều client cùng lúc kết nối tới một Mailbox. Email từ Mailbox sẽ được sao chép tới máy client và bản gốc của Email vẫn sẽ được lưu trên Mail Server.
Port 143/993

## 3. Hoạt động

<img src="https://wiki.matbao.net/wp-content/uploads/2019/08/mail-server-la-gi-co-3-giao-thuc-hoat-dong-chinh-cua-mail-server.png">

**Bước 1**:
Sau khi tạo và gửi email, email của bạn sẽ kết nối với Server SMTP mang tên miền của mình. SMTP sẽ đặt tên cho tất cả mọi thứ, ví dụ: smtp.tenmien.com.

**Bước 2**:
Email của bạn sẽ "giao tiếp" với SMTP server. Và cung cấp cho SMTP Server mọi thông tin như: địa chỉ mail người gửi, địa chỉ mail người nhận, nội dung email và file đính kèm.

**Bước 3**:
Tại đây có 2 trường hợp xảy ra:

Trường hợp 1: Tên miền (domain email) của người gửi và người nhận giống nhau. 

tenemail_1@tenmienA.com tới tenemail_2@tenmienA.com. Mail này sẽ được gửi trực tiếp đến POP3 hoặc IMAP Server có tên miền của bạn. 

Trường hợp 2: Tên miền của người gửi và người nhận khác

tenemail_1@tenmienA.com tới tenemail_2@tenmienB.com. SMTP Server sẽ phải "liên lạc" với một server tên miền khác.

**Bước 4**:
Để tìm ra Server của người nhận, SMTP Server của người gửi sẽ phải giao tiếp với DNS (Domain Name Server). 

DNS sẽ lấy thông tin tên miền người nhận và dịch trang địa chỉ IP. 

SMTP Server người gửi không thể thực hiện gửi email chính xác mà chỉ dựa trên tên miền thêm vào đó sẽ là địa chỉ IP. Địa chỉ IP (đơn nhất) sẽ giúp SMTP hoạt động chính xác và hiệu quả hơn.

**Bước 5**:
Sau khi có địa chỉ IP của người nhận, tức STMP người gửi đã có thể kết nối STMP Server người nhận.

**Bước 6**:
SMTP server người nhận sẽ quét (scan) thư gửi đến. Nếu nhận ra tên miền và tên người gửi, nó sẽ chuyển tiếp (forward) mail thuộc POP3 hoặc IMAP server mang tên miền của bạn. 

Từ đây, email đã được gửi đến mục hộp thư đến của người nhận.

## 4. Giải pháp

Thông thường, những cá nhân hay doanh nghiệp yêu cầu một lương lớn dung lượng hơn bình thường sẽ đầu tư riêng Mail Server.

## 5. Thuật ngữ

*TLS Mail Server là gì?*
TLS là bảo mật tầng truyền tải (Transport Layer Security). TLS hoạt động cùng với tầng ổ bảo mật SHL (Secure Sockets Layer). Mục đích chính cung cấp phương thức vận chuyển mã hoá cho đăng nhập được chứng thực của SASL.

*SASL Mail Server là gì?*
SASL là lớp xác thực và bảo mật đơn giản (Simple Authentication and Security Layer). Để xác thực người dùng. SASL thực hiện xác thực, sau đó TLS cung cấp vận chuyển mã hoá dữ liệu xác thực.

*Webmail là gì?*
Webmail là email trên nền website. Một số webmail mà các bạn có thường thấy như hotmail, gmail, yahoo mail. Webmail cho phép người dùng truy cập email bất cứ lúc nào.

*SMTP-IN Queue là gì?*
Trước khi phân tán thư đến các Local queue hoặc Remote Queue, giao thức SMTP sẽ làm một thao tác sao lưu toàn bộ thư điện tử gửi đi từ email server của doanh nghiệp ở SMTP-IN Queue. Nói cách khác, SMTP-IN Queue chính là kho lưu trữ thông tin thư từ trước khi được gửi đi.

*Local Queue là gì?*
Sau khi tiếp nhận thông tin thư từ, hệ thống sẽ tự động điều phối phân loại và xếp thư từ theo thứ tự ngay hàng thẳng lối trước khi chuyến vào hộp thư của người nhận. Việc xếp hàng các bức thư chính là Local Queue.

Để tăng cường khả năng bảo mật và giữ an toàn cho hệ thống email server, trước khi thư được gửi đến người dùng, local queue và remote queue sẽ tiến hành quét virut. Sau đó kiểm tra spam để chắc chắn về chất lượng thư gửi đi. Tránh trường hợp mail server bị các Blacklist liệt vào danh sách IP spam.

*Local Mailboxes là gì?*
Local Mailboxes là hộp thư của các account có đăng kí tài khoản mail server của công ty.

*Email Authentication là gì?*
Email Authentication là tính năng xác nhận danh tính của các user khi truy cập vào hộp thư email. Tính năng này giúp bạn bảo mật thông tin thư từ của chính mình. Nói cách khác Alternate Email là một dạng email dự phòng. Khi quên mật khẩu của mail server, bạn có thể sử dụng email này để giúp bạn lấy lại mật khẩu một cách nhanh chóng.

*Mail Exchanger Record (MX) là gì?*
MX record có nhiệm vụ là chỉ đường cho email đi đến mail server của bạn. MX record thường đi kèm theo một A record sẽ trỏ về địa chỉ IP của mail server. Một thông số pref có giá trị số để chỉ ra mức độ ưu tiên của các mail server. Giá trị pref càng nhỏ thì mức độ ưu tiên càng cao.
